---
title: "Blog 2"
date: 2026-04-20
weight: 2
chapter: false
pre: " <b> 3.2. </b> "
---

# Nhật Ký Đưa Ứng Dụng Lên Cloud – Từ Bài Học $35 Đến Kiến Trúc Tối Ưu Chi Phí

---

Kính chào các anh/chị admin và các thành viên trong cộng đồng AWS Study Group VN. Bài viết này là những đúc kết từ trải nghiệm thực chiến của nhóm chúng em trong quá trình triển khai dự án "Mini Social Network" trên môi trường AWS.

Trước đây, chúng em từng nhận được một câu hỏi: "Tại sao không thuê một máy chủ ảo (VPS) và triển khai toàn bộ mã nguồn lên đó cho đơn giản, thay vì phải thiết lập các dịch vụ phức tạp trên AWS?". Thực tế, chính nhóm ở những ngày đầu cũng có suy nghĩ tương tự. Tuy nhiên, khi chính thức bắt tay vào việc đưa toàn bộ kiến trúc dự án lên Cloud, chúng em đã rút ra được những bài học thực tế rất đắt giá.

---

## I. Sai lầm trong quá khứ (The "Before")

Ở các dự án cá nhân trước đây, tư duy triển khai của nhóm khá đơn giản: "Gom tất cả vào một máy chủ". Chúng em thường thuê một máy ảo (VPS), tự cài đặt MySQL, chạy trực tiếp Spring Boot Backend và triển khai bản build React Frontend qua Nginx trên cùng hệ thống đó. Những thông tin nhạy cảm như mật khẩu cơ sở dữ liệu hay khóa bảo mật JWT đều được lưu trữ dưới dạng văn bản thô (plaintext) trực tiếp trong tệp `.env`. Chỉ cần trỏ tên miền về Public IP là ứng dụng có thể hoạt động.

Thời điểm đó, nhóm cho rằng hệ thống đã hoàn thiện. Nhưng trên thực tế, kiến trúc này tiềm ẩn rủi ro rất lớn: không có cơ chế cách ly bảo mật, và nếu cơ sở dữ liệu gặp sự cố, toàn bộ ứng dụng sẽ ngừng hoạt động.

---

## II. Bước ngoặt thay đổi tư duy (The Turning Point)

Khi chuyển đổi sang AWS, việc áp dụng máy móc "kiến trúc 3 lớp (3-Tier)" lý thuyết đã bộc lộ nhiều điểm hạn chế:

*   **Chi phí không tối ưu:** Việc đặt ECS Fargate vào Private Subnet buộc hệ thống phải duy trì NAT Gateway để kéo Docker Image. Kết quả là NAT Gateway phát sinh chi phí ~$35/tháng, chiếm hơn 1/3 tổng ngân sách dự án dù lượng truy cập chưa cao.
*   **Lỗi định tuyến SPA:** Khi triển khai Frontend lên S3 Static Website Hosting, nếu người dùng tải lại trang (Refresh) tại các đường dẫn phụ (ví dụ: `/profile`), trình duyệt lập tức trả về lỗi 404.
*   **Nút thắt cổ chai hiệu năng:** Quá trình kiểm thử chịu tải với K6 (giả lập 500 người dùng) cho thấy container Fargate 0.5 vCPU đạt ngưỡng 100% CPU do quá tải trong khâu giải mã chữ ký JWT Token, dù cơ sở dữ liệu chưa bị ảnh hưởng.

Hệ thống cần sự phân tách rõ ràng và tính chuyên môn hóa sâu hơn ở từng bộ phận.

---

## III. Giải pháp và Kiến thức cốt lõi: Tối ưu hóa kiến trúc Cloud Native

Thay vì tiếp tục khắc phục các lỗi nhỏ lẻ, nhóm quyết định tái cấu trúc hệ thống bám sát Sơ Đồ Kiến Trúc Tối Ưu Chi Phí. Dưới đây là cách từng bộ phận giải quyết bài toán chuyên môn:

### 1. Bộ phận Hạ tầng (Cloud/Ops) – Tối ưu chi phí và hiệu năng
*   **Khó khăn:** Việc đặt ECS Fargate vào Private Subnet phát sinh chi phí duy trì NAT Gateway không cần thiết. Đồng thời, CPU của container bị quá tải khi xử lý khối lượng lớn thao tác xác thực JWT.
*   **Giải pháp:** Nhận thấy sự lãng phí tài nguyên, bộ phận Hạ tầng đã cấu hình lại ECS Fargate, chuyển sang Public Subnets (kích hoạt `AssignPublicIp: ENABLED`) và loại bỏ hoàn toàn NAT Gateway. Để đảm bảo nguyên tắc Zero-Trust, Fargate được thiết lập Security Group chỉ tiếp nhận lưu lượng từ Application Load Balancer (ALB). Cơ sở dữ liệu RDS vẫn được cô lập tại Private Subnet. Để quản trị DB an toàn, nhóm thiết lập một máy ảo EC2 t2.micro (Free Tier) làm Bastion Host tại Public Subnet. Kết hợp với việc sử dụng Amazon EventBridge để tự động tắt Database và ép số lượng container ECS về 0 lúc 23:00, bật lại lúc 7:00 sáng, chi phí mạng lưới đã được giảm về $0.

### 2. Bộ phận Frontend (UI/UX) – Xử lý lỗi định tuyến và Tích hợp CloudFront
*   **Khó khăn:** Việc lưu trữ Single Page Application (SPA) trên Amazon S3 gây ra lỗi 404 khi người dùng tải lại trang phụ. Thêm vào đó, cấu hình S3 thuần không hỗ trợ chứng chỉ HTTPS và có độ trễ tải trang cao đối với người dùng ở xa khu vực lưu trữ.
*   **Giải pháp:** Để khắc phục lỗi 404, bộ phận Frontend đã cấu hình Error document trỏ về `index.html`, trao lại quyền điều hướng cho React Router. Để tối ưu tốc độ phân phối và đảm bảo tiêu chuẩn bảo mật đường truyền, hệ thống được tích hợp mạng phân phối nội dung (CDN) Amazon CloudFront ở tuyến đầu. Quá trình triển khai sau đó được tự động hóa hoàn toàn bằng máy chủ Jenkins CI/CD (chạy trên EC2), tự động kéo mã nguồn từ GitHub, đóng gói và đẩy lên S3/ECR, giảm thiểu tối đa thao tác thủ công.

### 3. Bộ phận Giám sát (Observability) – Giám sát chủ động và Quản lý cảnh báo
*   **Khó khăn:** Quá trình theo dõi hệ thống đòi hỏi một cơ chế tự động hóa thay vì giám sát thủ công. Dù đã tích hợp AWS CloudWatch, Grafana và cấy OpenTelemetry (OTLP) vào Spring Boot, bài toán lớn nhất là làm sao phát hiện tấn công mạng mà không gây tình trạng nhiễu loạn cảnh báo (Email Storm).
*   **Giải pháp:** Nhóm đã thiết lập Metric Filters trên CloudWatch để rà soát log ứng dụng theo cú pháp `{$.type = "SECURITY"}`. Hệ thống chỉ kích hoạt CloudWatch Alarm khi phát hiện các hành vi rà quét lỗ hổng SQL Injection hay XSS vượt ngưỡng 1 hành vi/phút. Đồng thời, tính năng "Gom nhóm cảnh báo" (Alert grouping) trên Grafana được cấu hình để tổng hợp thông tin trước khi gửi qua Amazon SNS, giúp nhóm phản ứng nhanh chóng mà vẫn bảo toàn hạn mức 1.000 email miễn phí của AWS.

### 4. Bộ phận An toàn thông tin (DevSecOps) – Tích hợp bảo mật từ giai đoạn thiết kế
*   **Khó khăn:** Ở khâu đánh giá an toàn thông tin, công cụ OWASP ZAP ban đầu trả về rất nhiều cảnh báo giả (False Positives). Mã nguồn Backend vẫn tồn tại rủi ro do lưu mật khẩu DB và JWT Secret trong tệp cấu hình. Tuy nhiên, việc chuyển đổi sang biến môi trường Cloud khiến container Fargate gặp lỗi khởi tạo.
*   **Giải pháp:** Nhóm áp dụng phương pháp "Shift-left Security" – đưa yếu tố bảo mật vào ngay từ khâu thiết kế. Toàn bộ thông tin nhạy cảm được loại bỏ khỏi mã nguồn và quản lý tập trung tại AWS Systems Manager Parameter Store. Để khắc phục lỗi sập Task, quyền `ssm:GetParameters` đã được bổ sung vào IAM Role thực thi. Tại biên mạng, tường lửa AWS WAF được triển khai ở hai phân lớp: bảo vệ giao diện trên CloudFront và bảo vệ luồng API trên ALB. Phối hợp với công cụ quét mã tĩnh SonarCloud, các rủi ro được phân tích thành hướng dẫn cụ thể (như việc áp dụng `encodeURIComponent`) để nhóm phát triển khắc phục kịp thời.

---

## IV. Tổng kết và Hành trình phía trước

Quá trình đưa "Mini Social Network" lên môi trường Cloud đã giúp nhóm giải quyết được bài toán cân bằng giữa mức độ tối ưu chi phí, khả năng tự động hóa và trải nghiệm người dùng cuối.

Tuy nhiên, kiến trúc trong sơ đồ hiện tại vẫn chưa phải là phiên bản cuối cùng. Để đảm bảo hệ thống đạt mức độ bảo mật cao nhất, dự án đang bước vào giai đoạn đánh giá nghiêm ngặt: Code Freeze & Security Audit. Toàn bộ kiến trúc sẽ trải qua đợt rà soát bảo mật tổng thể trước khi chính thức chốt hạ bản "Final Architecture".

## V. Sơ đồ kiến trúc về dự án "Mini Social Network" trước và sau 
<h4 align="center"><em>Sơ đồ kiến trúc ban đầu thực hiện</em></h4>

![Sơ đồ kiến trúc ban đầu thực hiện](anh1.png)
<h4 align="center"><em>Sơ đồ kiến trúc sau khi lắng nghe ý kiến đánh giá và tối ưu chi phí</em></h4>

![Sơ đồ kiến trúc sau khi lắng nghe ý kiến đánh giá và tối ưu chi phí](anh2.png)

> Bài viết trên AWS Study Group: Đường link bài Blog https://www.facebook.com/groups/awsstudygroupfcj/permalink/2198727654225528
<br>
> Rất mong nhận được sự góp ý, đánh giá và chia sẻ kinh nghiệm từ các anh/chị chuyên gia cùng các bạn trong AWS Study Group VN!
