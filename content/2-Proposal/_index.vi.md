---
title: "Đề xuất Dự án"
date: 2026-07-01
weight: 2
chapter: false
pre: "  2.  "
---

# Mạng Xã Hội Thu Nhỏ (Mini Social Network)

## Triển khai Hạ tầng Cloud-Native AWS với Kênh CI/CD Tự động và Tính năng Gamification

### Tổng quan dự án
- Một nền tảng mạng xã hội full-stack được xây dựng như một minh chứng thực tế cho kỹ năng Cloud Engineering hiện đại.
- Được thiết kế để phục vụ từ 20 đến 100 người dùng đồng thời, đồng thời vẫn giữ được khả năng mở rộng và tiết kiệm chi phí.
- Kết hợp AWS, container, tự động hóa CI/CD, bảo mật và giám sát vào một blueprint triển khai chuẩn production.
- Tập trung vào độ tin cậy vận hành, khả năng quan sát hệ thống và triển khai DevOps thực tế.

Để giúp người đọc hình dung rõ hơn về toàn bộ ý tưởng, sơ đồ kiến trúc dưới đây minh họa luồng hoạt động từ đầu vào người dùng đến các dịch vụ AWS phía sau.

![MiniSocial Architecture](/Minisocial-Architect_final.png)

### 1. Tóm tắt dự án (Executive Summary)
Mini Social Network (MiniSocial) là một nền tảng mạng xã hội thu nhỏ tích hợp các tính năng gamification (trò chơi hóa), được xây dựng dưới dạng một dự án học thuật thực chiến nhằm chứng minh năng lực chuyên sâu về DevOps và Cloud Engineering. Hệ thống được thiết kế để vận hành ổn định phục vụ từ 20 đến 100 người dùng đồng thời, có khả năng mở rộng linh hoạt nhờ kiến trúc Cloud-native. Được triển khai hoàn toàn trên hạ tầng điện toán đám mây AWS thông qua mã nguồn hạ tầng (IaC) CloudFormation và quản lý tự động bởi hệ thống Jenkins CI/CD đặt bên ngoài, dự án áp dụng các best practices tiêu chuẩn doanh nghiệp về bảo mật, kiểm thử tự động, giám sát thời gian thực và tối ưu hóa chi phí một cách chủ động.

### 2. Định nghĩa bài toán (Problem Statement)

### Vấn đề là gì?
Việc xây dựng và triển khai một ứng dụng mạng xã hội fullstack hiện đại đòi hỏi phải giải quyết những thách thức lớn về mặt hạ tầng kỹ thuật. Các môi trường triển khai truyền thống thường thiếu các kênh phân phối tự động (CI/CD pipeline), gây ra sự chậm trễ và sai sót giữa giai đoạn phát triển và vận hành. Thêm vào đó, việc duy trì các tính năng thời gian thực (như chat và thông báo) cùng hệ thống cơ sở dữ liệu trên Cloud rất dễ dẫn đến chi phí vận hành tăng cao, lỗ hổng bảo mật và thiếu cơ chế giám sát chi tiết, gây khó khăn cho việc chứng minh tính sẵn sàng của sản phẩm khi đưa ra môi trường Production.

### Giải pháp
Nền tảng MiniSocial giải quyết triệt để các vấn đề trên bằng cách áp dụng kiến trúc Serverless và Container hóa tiên tiến của AWS. Frontend của hệ thống sử dụng React 19, TypeScript 5.9 và Vite, được lưu trữ an toàn trên Amazon S3 và phân phối toàn cầu qua Amazon CloudFront với cơ chế kiểm soát truy cập nguồn gốc OAC. Backend được phát triển bằng Spring Boot 3.2.6 (Java 17), chạy trong các container Docker được quản lý bởi Amazon ECS Fargate trên nhiều Availability Zone (AZ) khác nhau. Dữ liệu được lưu trữ và bảo mật nghiêm ngặt bên trong hệ quản trị cơ sở dữ liệu Amazon RDS cho SQL Server đặt tại các subnet riêng biệt (Private Subnet). Toàn bộ quy trình Tích hợp và Triển khai liên tục (CI/CD) được tự động hóa hoàn toàn qua hệ thống Jenkins local với hai pipeline độc lập để tự động kiểm thử, đóng gói và phát hành mã nguồn. Chi phí vận hành được tối ưu hóa tối đa thông qua công cụ AWS EventBridge Scheduler (bật/tắt hạ tầng tự động) và cấu hình ECS Fargate Spot.

### Lợi ích và Hiệu quả đầu tư (ROI)
Là một dự án học thuật và xây dựng portfolio cá nhân, giá trị đầu tư cốt lõi của dự án không nằm ở nguồn thu tài chính trực tiếp, mà ở việc chứng minh năng lực triển khai một hệ thống tiêu chuẩn Production hoàn chỉnh trên AWS. Về mặt kinh tế, chi phí vận hành được kiểm soát vô cùng chặt chẽ, chỉ dao động từ $45–$60 USD/tháng nhờ áp dụng các giải pháp tối ưu: tự động đưa hạ tầng vào trạng thái "ngủ" từ 22:00 đến 07:00 hàng ngày (tiết kiệm ~37.5% thời gian chạy), sử dụng Fargate Spot cho các task dự phòng (giảm ~70% chi phí compute), và thiết lập S3 VPC Gateway Endpoint để truyền tải dữ liệu trực tiếp không qua NAT Gateway, giúp loại bỏ hoàn toàn phí chuyển đổi dữ liệu. Dự án mang lại một bộ khuôn mẫu (blueprint) có tính tái sử dụng cao bao gồm 4 stack CloudFormation và các file cấu hình Jenkinsfile mẫu, dễ dàng áp dụng cho các dự án quy mô doanh nghiệp sau này.

### 3. Kiến trúc giải pháp (Solution Architecture)
Nền tảng này không chỉ là một ứng dụng web hoạt động bình thường mà còn là một blueprint triển khai hạ tầng Cloud hoàn chỉnh, chú trọng cả tính năng lẫn hiệu quả vận hành. Kiến trúc được xây dựng quanh ba nguyên tắc cốt lõi:
- Đưa lưu lượng truy cập vào hệ thống một cách an toàn thông qua Route 53 và AWS WAF.
- Chạy logic nghiệp vụ trên ECS Fargate ở nhiều Availability Zone để đảm bảo độ sẵn sàng.
- Phân phối tài nguyên tĩnh nhanh chóng và ổn định thông qua S3 và CloudFront.

Lưu lượng từ người dùng được định tuyến qua Amazon Route 53, đi qua bộ lọc AWS WAF để ngăn chặn các cuộc tấn công DDoS và Injection trước khi chuyển đến bộ cân bằng tải Application Load Balancer (ALB) qua giao thức bảo mật HTTPS. Các tác vụ xử lý logic backend được thực hiện bởi các task ECS Fargate phân bổ trong các Private Subnet, đảm bảo tính sẵn sàng cao và khả năng chịu lỗi tốt.

### Các dịch vụ AWS được sử dụng

- **VPC & Networking**: Thiết lập hệ thống subnet phân tách (Public Subnet cho ALB, Private Subnet cho Compute và Data), NAT Gateway, và S3 VPC Gateway Endpoint.
- **Amazon ECS Fargate**: Khởi chạy container serverless cho các node ứng dụng backend mà không cần quản lý server EC2.
- **Amazon ECR**: Kho lưu trữ bảo mật cho các bản đóng gói Docker image production.
- **Amazon RDS cho SQL Server**: Dịch vụ cơ sở dữ liệu được quản lý (db.t3.small) đặt trong subnet dữ liệu riêng biệt, mã hóa dữ liệu lưu trữ.
- **Amazon S3 & CloudFront**: Lưu trữ mã nguồn frontend tĩnh và tài nguyên media, phân phối qua CDN với chứng chỉ bảo mật OAC.
- **AWS WAF & ACM**: Tường lửa ứng dụng web bảo vệ hệ thống và dịch vụ cấp phát, tự động gia hạn chứng chỉ SSL/TLS miễn phí.
- **Amazon Route 53**: Hệ thống quản lý tên miền và định tuyến DNS độ trễ thấp.
- **AWS SSM Parameter Store**: Lưu trữ tập trung và mã hóa các thông tin cấu hình nhạy cảm, mật khẩu hệ thống (Secrets).
- **Amazon CloudWatch & EventBridge**: Thu thập log, giám sát chỉ số hạ tầng và lập lịch tự động hóa tác vụ tắt/bật.

### Thiết kế thành phần (Component Design)

- **Giao diện người dùng (Frontend)**: Phát triển trên React 19, TypeScript và thư viện MUI 7.x, giao tiếp qua HTTP Client Axios và xử lý các sự kiện thời gian thực bằng STOMP.js chạy trên nền WebSocket.
- **Xử lý nghiệp vụ (Backend)**: Kiến trúc Spring Boot chia thành 28 package nghiệp vụ chuyên sâu, tích hợp Spring Security + JWT để xác thực phi trạng thái, Spring Data JPA để tương tác cơ sở dữ liệu và Spring WebSocket điều phối luồng chat STOMP.
- **Cơ sở dữ liệu (Database)**: Sử dụng Microsoft SQL Server 2022 Express chạy trên Docker ở môi trường local phục vụ phát triển, đồng bộ cấu hình để chuyển đổi mượt mà lên Amazon RDS khi lên Production.
- **Hệ thống giám sát (Monitoring)**: Sử dụng thư viện Micrometer OTLP tích hợp trong backend để thu thập và đẩy trực tiếp các chỉ số hệ thống về dashboard quản trị tập trung trên Grafana Cloud kết hợp cùng CloudWatch Logs.

### 4. Triển khai kỹ thuật (Technical Implementation)
**Các giai đoạn triển khai**
Quy trình xây dựng và triển khai dự án MiniSocial được chia nhỏ thành 5 giai đoạn cuốn chiếu tuần tự:

- Giai đoạn 1 — Nền tảng cơ bản (Foundation): Thiết kế cấu trúc Database Schema (MSSQL), hoàn thiện các REST API cốt lõi (Auth JWT, CRUD bài đăng), xây dựng bộ khung React SPA và đóng gói môi trường phát triển local bằng Docker Compose.
- Giai đoạn 2 — Tính năng xã hội (Social Features): Hiện thực hóa các tính năng tương tác thời gian thực bao gồm kết bạn (Friend Requests), nhắn tin trực tuyến qua WebSocket STOMP, quản lý hội thoại, gửi thông báo hệ thống và thả cảm xúc bài đăng (Post Reactions).
- Giai đoạn 3 — Gamification & Cosmetics: Tích hợp cơ chế trò chơi hóa nâng cao trải nghiệm người dùng bao gồm hệ thống điểm thưởng VPTL, cửa hàng vật phẩm trang trí, vòng quay may mắn Gacha/Lootbox, các hiệu ứng hình ảnh (Avatar Frame, Name Color) và mini-games (Rắn săn mồi, Tích-tắc-tô).
- Giai đoạn 4 — Cloud Deployment & DevOps: Thiết kế hoàn chỉnh 4 stack mã nguồn hạ tầng AWS CloudFormation, cấu hình mạng Multi-AZ an toàn, khởi tạo cluster ECS Fargate, quản lý tập trung secrets trên SSM và cấu hình hệ thống tự động hóa Jenkins CI/CD.
- Giai đoạn 5 — Giám sát & Kiểm thử tải (Monitoring & Load Testing): Kết nối Grafana Cloud qua Micrometer OTLP, viết kịch bản kiểm thử hiệu năng bằng K6 (giả lập người dùng bình thường, giả lập tấn công DDoS, stress test bảng tin), nâng tỷ lệ bao phủ code (Code Coverage) của JaCoCo đạt ≥70% và chạy kiểm thử Selenium E2E.

**Yêu cầu kỹ thuật**

- Tên miền ứng dụng: Vận hành live môi trường Production tại địa chỉ `https://minisocial-network.id.vn` và hệ thống API tại `api.minisocial-network.id.vn`.
- Hạ tầng CI/CD: Sử dụng máy chủ Jenkins đặt ngoài đám mây (chạy local trên Windows), lắng nghe các thay đổi mã nguồn từ GitHub thông qua cơ chế tự động quét (Poll SCM) để kích hoạt pipeline.
- Tiêu chuẩn kiểm thử: Ràng buộc quy trình build CI/CD nghiêm ngặt, đảm bảo các bài kiểm thử tự động của JUnit 5 phải vượt qua và đạt tỷ lệ bao phủ mã nguồn theo chuẩn JaCoCo đề ra.

### 5. Lịch trình & Các cột mốc dự kiến (Timeline & Milestones)
**Lịch trình dự án**
Tổng thời gian triển khai từ khi phác thảo kiến trúc đến khi hệ thống vận hành thực tế trên Production kéo dài từ 14 đến 21 tuần:

- Tuần 1–3 (Giai đoạn 1): Đạt cột mốc MVP — Hoàn thành hệ thống xác thực, API cơ bản và môi trường Docker local chạy ổn định.
- Tuần 4–6 (Giai đoạn 2): Đạt cột mốc Social Ready — Kênh chat WebSocket, thông báo trực tuyến và logic kết bạn đi vào hoạt động.
- Tuần 7–8 (Giai đoạn 3): Đạt cột mốc Gamification Live — Mở cửa hàng vật phẩm, thuật toán quay Gacha và các mini-game hoàn thiện.
- Tuần 9–10 (Giai đoạn 4): Đạt cột mốc AWS Production Live — Toàn bộ hạ tầng đám mây được khởi tạo tự động, kích hoạt tường lửa WAF và thông suốt các đường ống Jenkins CI/CD.
- Tuần 11–12 (Giai đoạn 5): Đạt cột mốc Hoàn thiện sản phẩm — Hệ thống Grafana giám sát đầy đủ chỉ số, hoàn thành các báo cáo kiểm thử tải K6 và JaCoCo đạt mục tiêu đề ra.

### 6. Ước tính ngân sách (Budget Estimation)
Bảng tính toán chi phí hạ tầng Cloud được thiết kế tối ưu tối đa nhờ các cơ chế lập lịch tự động nhằm loại bỏ lãng phí tài nguyên khi không có nhu cầu sử dụng.

### Chi phí hạ tầng
Chi phí vận hành hạ tầng AWS ước tính hàng tháng chi tiết như sau:

- Amazon ECS Fargate (Chạy 2 task chính, cấu hình 0.5 vCPU / 1GB RAM, hoạt động 15 giờ/ngày): ~$15.00 – $20.00/tháng
- ECS Fargate Spot (Khởi chạy 1 task phụ bổ sung, giúp tiết kiệm đến 70% chi phí compute): ~$3.00 – $5.00/tháng
- Amazon RDS cho SQL Server (Gói db.t3.small, dung lượng 20GB gp2, hoạt động 15 giờ/ngày): ~$10.00 – $15.00/tháng
- AWS NAT Gateway (1 NAT Instance + tối ưu hóa lưu lượng qua S3 Endpoint): ~$5.00 – $8.00/tháng
- Application Load Balancer (Bộ cân bằng tải định tuyến traffic): ~$5.00/tháng
- AWS WAF (Bảo vệ an toàn ứng dụng web): ~$5.00/tháng
- Amazon S3 & CloudFront (Lưu trữ frontend và dữ liệu media hình ảnh): ~$1.00 – $2.00/tháng
- Amazon CloudWatch & ECR (Lưu trữ log hệ thống và Docker images): ~$1.00 – $2.00/tháng
- Amazon Route 53, ACM, SSM, EventBridge Scheduler: ~$0.50/tháng (Áp dụng các gói Free Tier có sẵn)
Tổng chi phí hạ tầng ước tính: ~$45.00 – $60.00 / tháng

Các chi phí ngoại vi khác bao gồm: Chi phí duy trì tên miền (`.id.vn`) khoảng ~$5.00 – $10.00/năm; Máy chủ Jenkins, tài khoản Grafana Cloud và GitHub sử dụng hoàn toàn các gói miễn phí ($0 Free Tier).

### 7. Đánh giá rủi ro (Risk Assessment)

#### Ma trận rủi ro (Risk Matrix)

- R1: Tác vụ Fargate Spot bị AWS thu hồi đột ngột (Xác suất: Trung bình | Tác động: Thấp) — Gây gián đoạn dịch vụ tạm thời đối với task phụ do đặc thù chi phí rẻ của Spot Instance.
- R2: Chi phí AWS vượt kiểm soát / Bill Shock (Xác suất: Thấp | Tác động: Cao) — Phát sinh chi phí ngoài ý muốn do mã nguồn lặp vô hạn hoặc bị tấn công làm tăng lưu lượng truyền tải.
- R3: Sự cố lỗi Cơ sở dữ liệu vùng đơn Single-AZ (Xác suất: Thấp | Tác động: Cao) — Phiên bản SQL Server Express trên RDS không hỗ trợ Multi-AZ, dễ dẫn đến downtime nếu zone đó gặp sự cố.
- R4: Máy chủ Jenkins local bị hỏng hóc phần cứng (Xác suất: Trung bình | Tác động: Trung bình) — Làm gián đoạn quy trình tự động hóa triển khai code lên AWS.
- R5: Rò rỉ thông tin bảo mật / Lộ API Keys (Xác suất: Thấp | Tác động: Cao) — Kẻ xấu có thể chiếm quyền điều khiển hạ tầng hoặc thao túng dữ liệu người dùng.

#### Chiến lược giảm thiểu rủi ro (Mitigation Strategies)

- R1 (Xử lý Spot): Luôn thiết lập cấu hình chạy tối thiểu một task On-demand cố định (Base=1) không bao giờ bị thu hồi. ALB sẽ tự động chuyển hướng toàn bộ traffic sang task On-demand này nếu task Spot bị AWS thu hồi.
- R2 (Kiểm soát chi phí): Sử dụng EventBridge Scheduler tự động tắt toàn bộ cụm ECS và RDS SQL Server từ 22:00 tối đến 07:00 sáng hôm sau, giúp cắt giảm trực tiếp 37.5% chi phí lãng phí.
- R3 (Bảo vệ Database): Cấu hình chiến lược sao lưu tự động (Auto-backup) cuốn chiếu 7 ngày, bật tính năng mã hóa lưu trữ StorageEncrypted và áp dụng chính sách DeletionPolicy: Snapshot để giữ lại dữ liệu an toàn ngay cả khi stack bị xóa nhầm.
- R5 (Bảo mật Secrets): Loại bỏ hoàn toàn mật khẩu dạng chữ thuần (Plaintext) khỏi mã nguồn, lưu trữ tập trung vào AWS SSM Parameter Store và cô lập ứng dụng trong Private Subnet.

#### Kế hoạch dự phòng (Contingency Plans)

- Khi các task Fargate Spot bị thu hồi, hệ thống cảnh báo tự động kích hoạt giúp dịch vụ On-demand tự động gánh tải mà không làm gián đoạn trải nghiệm người dùng.
- Trong trường hợp máy chủ Jenkins local gặp sự cố phần cứng nghiêm trọng, các tệp cấu hình Jenkinsfile lưu trên Git có thể nhanh chóng được import và chuyển đổi sang chạy trên dịch vụ GitHub Actions chỉ trong thời gian ngắn.

### 8. Kết quả kỳ vọng (Expected Outcomes)

#### Cải tiến kỹ thuật
Việc chuyển dịch từ mô hình phát triển cục bộ lên hạ tầng đám mây chuẩn Enterprise mang lại những bước tiến kỹ thuật vượt bậc:

- Loại bỏ hoàn toàn thao tác cấu hình thủ công bằng tay (FTP/SSH), thay thế bằng các đường ống dẫn mã nguồn tự động hóa 100% từ khi push code đến khi lên production.
- Thay thế việc đọc log mò mẫm truyền thống bằng hệ thống Dashboard giám sát trực quan, sinh động thời gian thực trên Grafana Cloud.
- Thiết lập một nền tảng bảo mật vững chắc (WAF, SSL mã hóa, cô lập subnet) giúp ngăn chặn hiệu quả các cuộc tấn công mạng cơ bản.

#### Giá trị lâu dài
Tài sản lớn nhất dự án để lại chính là bộ Blueprint (khuôn mẫu) DevOps có tính thực tiễn cao. Bộ 4 stack CloudFormation IaC có thể nhanh chóng được tái sử dụng, nhân bản cho các dự án khác chỉ bằng cách thay đổi tham số đầu vào. Đồng thời, cấu trúc cấu hình phân tách luồng của hai file Jenkinsfile (Frontend và Backend) đóng vai trò như một cẩm nang kiến trúc triển khai tiêu chuẩn cho mọi kỹ sư Cloud/DevOps trong tương lai.