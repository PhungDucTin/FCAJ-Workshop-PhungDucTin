---
title: "Worklog Tuần 10"
date: 2026-06-22
weight: 10
chapter: false
pre: " <b> 1.10. </b> "
---

### Mục tiêu tuần 10:

* Chạy SonarCloud để quét repo mã nguồn.
* Thực hiện đánh giá bảo mật động (DAST) bằng công cụ OWASP ZAP.
* Tổng hợp và phân loại các cảnh báo rủi ro từ quá trình quét.
* Khởi tạo hệ thống tường lửa WAF và gắn vào ALB, CloudFront.
* Khởi tạo kho khóa bí mật và gắn vào ECS cho 4 biến môi trường cốt lõi.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| :---: | :--- | :---: | :---: | :--- |
| **2** | **Thực hiện đồ án nhóm:** <br> - Sử dụng tài khoản AWS được cấp trên github để thực hiện task. <br>- Chạy SonarCloud quét Repo ngay khi nhận được thông báo hoàn thiện source code. | 22/06/2026 | 22/06/2026 | |
| **3** | **Thực hiện đồ án nhóm:** <br> - Khởi tạo kho khóa và gắn vào ECS. <br>- Thiết lập 4 khóa an toàn: `SPRING_DATASOURCE_PASSWORD` (Mật khẩu DB), `JWT_SECRET` (Khóa ký Token), `SPRING_MAIL_PASSWORD` (Mật khẩu gửi mail), và `GRAFANA_OTLP_TOKEN` (Token giám sát của Trường). | 23/06/2026 | 23/06/2026 |  |
| **4** | **Thực hiện đồ án nhóm:** <br> - Đợi có đủ thông tin link ALB, CloudFront để tránh làm chậm tiến độ dự án. <br>- Khởi tạo WAF và tiến hành gắn WAF vào ALB, CloudFront. | 24/06/2026 | 24/06/2026 | |
| **5** | **Thực hiện đồ án nhóm:** <br> - Thực hiện đánh giá bảo mật động (DAST) bằng OWASP ZAP. <br>- Quét OWASP ZAP chi tiết ở cả API Public và API cần token. | 25/06/2026 | 25/06/2026 |  |
| **6** | **Thực hiện đồ án nhóm:** <br> - Lập Báo cáo lỗ hổng từ SonarCloud và OWASP ZAP dưới dạng Word/PDF. <br>- Trích lọc ra Top lỗ hổng nguy hiểm nhất. <br>- Trình bày theo format bắt buộc: Tên lỗ hổng, Vị trí cụ thể, Bằng chứng (PoC) qua ảnh chụp màn hình tool ZAP, và Cách khắc phục ngắn gọn cho Dev. | 26/06/2026 | 26/06/2026 | **- Tài liệu thực hiện Báo cáo bảo mật trên SonarCloud:** <br> https://docs.google.com/document/d/1P7uWuUfEtSceGTTazdJHuX-n5w7m9G571ZvFVf6DjBw/edit?usp=sharing <br> **- Tài liệu thực hiện Quét lỗ hổng:** <br> https://docs.google.com/document/d/1hfYRIkfMq1UDflqW6_HULIm1Ju9E4nrgUyUhC9OMybU/edit?usp=sharing|

### Kết quả đạt được tuần 10:

* Quét repo mã nguồn thành công bằng SonarCloud.

* Hoàn thiện đánh giá bảo mật động bằng OWASP ZAP hoàn tất cho cả phân vùng API Public và API cần token.

* Khởi tạo thành công tường lửa WAF và gắn trực tiếp vào các điểm endpoint ALB, CloudFront.

* Khởi tạo kho khóa cho ECS, đảm bảo bảo mật cho 4 biến quan trọng: mật khẩu DB, khóa ký Token, mật khẩu mail và token giám sát Grafana.

### Minh chứng thực hiện tuần 10: 

#### 1. Khởi tạo tường lửa WAF gắn vào ALB

<h4 align="center"><em>AWS WAF được thiết kế để tích hợp (attach) trực tiếp vào ALB ở cấp độ khu vực (Regional)</em></h4>

![AWS WAF được thiết kế để tích hợp (attach) trực tiếp vào ALB ở cấp độ khu vực (Regional)](/images/1-Worklog/1.10-Week10/wafalb.png)

#### 2. Khởi tạo tường lửa WAF gắn vào CloudFront

<h4 align="center"><em>AWS WAF được thiết kế để tích hợp (attach) trực tiếp vào CloudFront ở cấp độ toàn cầu (Global)</em></h4>

![AWS WAF được thiết kế để tích hợp (attach) trực tiếp vào CloudFront ở cấp độ toàn cầu (Global)](/images/1-Worklog/1.10-Week10/waf.png)

#### 3. Khởi tạo biến ở Region Singapore

<h4 align="center"><em>Khởi tạo các biến an toàn trên Parameter Store ở Region Singapore</em></h4>

![Khởi tạo các biến an toàn trên Parameter Store ở Region Singapore](/images/1-Worklog/1.10-Week10/pssg.png)

#### 4. Khởi tạo biến ở Region N.Virginia

<h4 align="center"><em>Khởi tạo các biến an toàn trên Parameter Store ở Region N.Virginia</em></h4>

![Khởi tạo các biến an toàn trên Parameter Store ở N.Virginia](/images/1-Worklog/1.10-Week10/psus.png)

#### 5. Kết quả quét hệ thống với OWASP ZAP

<h4 align="center"><em>Thực hiện quét hệ thống với OWASP ZAP</em></h4>

![Thực hiện quét hệ thống với OWASP ZAP](/images/1-Worklog/1.10-Week10/zap.png)