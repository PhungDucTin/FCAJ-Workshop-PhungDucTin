---
title: "Worklog Tuần 7"
date: 2026-06-01
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---

### Mục tiêu tuần 7:

* Thiết lập chốt chặn bảo mật tầng ứng dụng (AWS WAF) bảo vệ trực tiếp Application Load Balancer (ALB).
* Loại bỏ hoàn toàn việc Hardcode thông tin nhạy cảm, triển khai quản lý khóa bảo mật tập trung bằng AWS Systems Manager Parameter Store cho các Container trên ECS.
* Thực hiện rà quét bảo mật động (DAST) bằng công cụ OWASP ZAP để kiểm chứng sức mạnh của tường lửa.
* Tổng hợp dữ liệu và báo cáo tiến độ dự án với nhóm.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| **2** | **Thực hiện đồ án nhóm:** <br> - Nghiên cứu & Khởi tạo Parameter Store: <br>&emsp; + Nghiên cứu tài liệu cấu hình AWS Systems Manager Parameter Store cho ECS Fargate. <br>&emsp; + Khởi tạo 4 khóa nhạy cảm của dự án (SPRING_DATASOURCE_PASSWORD, JWT_SECRET, SPRING_MAIL_PASSWORD, GRAFANA_OTLP_TOKEN) dưới dạng `SecureString`. | 01/06/2026 | 01/06/2026 | **- Tài liệu Parameter Store:** <br> https://docs.aws.amazon.com/systems-manager/ <br> **- Tài liệu thực hiện Parameter Store:** <br> https://docs.google.com/document/d/1ig-ue9NNFZUFrOD_MsCNOFAXimNGalQ8MG9WObW-VBk/edit?usp=sharing |
| **3** | **Thực hiện đồ án nhóm:** <br> - Thiết lập & Cấu hình AWS WAF: <br>&emsp; + Khởi tạo Web ACL trên giao diện AWS Console. <br>&emsp; + Tích hợp các bộ luật có sẵn: `Core rule set`, `SQL database` và cấu hình `Rate Limiting` (giới hạn 100 requests/5 phút). <br>&emsp; + Gắn trực tiếp (Associate) Web ACL vào Application Load Balancer (ALB) của dự án. | 02/06/2026 | 02/06/2026 | **- Tài liệu AWS WAF:** <br> https://docs.aws.amazon.com/waf/ <br> **- Tài liệu thực hiện AWS WAF:** <br> https://docs.google.com/document/d/181yLB9Dp5UefwajYwUxg7DctGfgi6Ms5qm8LtJjwIk0/edit?usp=sharing |
| **4** | **Thực hiện đồ án nhóm:** <br> - Cập nhật ECS & Xử lý sự cố (Troubleshooting): <br>&emsp; + Cập nhật Task Definitions trên AWS ECS để ứng dụng tự động lấy khóa từ Parameter Store lúc khởi động (Force new deployment). <br>&emsp; + Đọc log hệ thống, phân tích "Stopped reason" và xử lý sự cố sập Task do Role thực thi bị thiếu quyền IAM (`ssm:GetParameters`, `kms:Decrypt`). | 03/06/2026 | 03/06/2026 | **- Tài liệu AWS ECS & IAM:** <br> https://docs.aws.amazon.com/ecs/ |
| **5** | **Thực hiện đồ án nhóm:** <br> - Đánh giá Bảo mật Động (DAST) & Lập Báo cáo <br>&emsp; + Sử dụng công cụ OWASP ZAP tiến hành rà quét bảo mật tổng thể hạ tầng ALB. <br>&emsp; + Chạy 2 kịch bản đối chiếu: Bật WAF và Tắt WAF để kiểm chứng khả năng phòng thủ. <br>&emsp; + Trích xuất log, tổng hợp lỗi và soạn thảo "Báo cáo Hành động Bảo mật". | 04/06/2026 | 04/06/2026 | **- Tài liệu OWASP ZAP:** <br> https://www.zaproxy.org/docs/ <br> **- Tài liệu thực hiện quét bảo mật với OWASP ZAP:** <br> https://docs.google.com/document/d/1lGwMO8Kvm7h4iTFyOHO4aXp1FeDljdSxksYxDNayHu4/edit?usp=sharing |
| **6** | **Họp nhóm:** <br> - Báo cáo với nhóm (Review & Report): <br>&emsp; + Trực tiếp có mặt tại văn phòng Bootcamp để báo cáo tiến độ dự án. <br>&emsp; + Thuyết trình và bảo vệ kiến trúc bảo mật (WAF, Parameter Store) để nghiệm thu Task với nhóm trưởng. | 05/06/2026 | 05/06/2026 | |

### Kết quả đạt được tuần 7:

* Khởi tạo và lưu trữ an toàn 4 khóa cốt lõi trên AWS Systems Manager Parameter Store, được mã hóa bằng KMS (SecureString).

* Cấu hình thành công các bộ luật bảo vệ nền tảng: `Core Rule Set`, `SQL database`, và thiết lập giới hạn `Rate Limiting` (100 requests / 5 phút) để chống DDoS/Spam API. 

* Rà quét bảo mật tổng thể hạ tầng với 2 kịch bản thực chứng.

* Chứng minh WAF hoạt động hiệu quả (chặn 100% request rà quét). Khi tắt WAF, ZAP chỉ phát hiện các cảnh báo mức độ Low/Medium về cấu hình Cookie, khẳng định mã nguồn Backend an toàn trước các lỗi Injection.

* Nộp "Báo cáo Hành động Bảo mật" hoàn chỉnh, chỉ rõ Top các lỗ hổng kèm vị trí khai thác và hướng dẫn khắc phục cho team Dev.

### Minh chứng thực hiện tuần 7:

#### 1. Khởi tạo và lưu trữ khoá cốt lõi lên AWS

<h4 align="center"><em>Quản lý 4 khóa cấu hình cốt lõi trên AWS Systems Manager (Parameter Store)</em></h4>

![Quản lý 4 khóa cấu hình cốt lõi trên AWS Systems Manager (Parameter Store)](/images/1-Worklog/1.7-Week7/ssm.png)

#### 2. Cấu hình các bộ luật nền tảng cho hệ thống

<h4 align="center"><em>Triển khai và cấu hình các Rule-set WAF trên ALB</em></h4>

![Triển khai và cấu hình các Rule-set WAF trên ALB](/images/1-Worklog/1.7-Week7/waf.png)

#### 3. Thực hiện rà quét với OWASP ZAP

<h4 align="center"><em>Rà quét bảo mật hệ thống bằng OWASP ZAP</em></h4>

![Rà quét bảo mật hệ thống bằng OWASP ZAP](/images/1-Worklog/1.7-Week7/zap.png)

#### 4. Họp nhóm trao đổi thông tin thực hiện

<h4 align="center"><em>Lên văn phòng học tập và làm việc nhóm</em></h4>

![Lên văn phòng học tập và làm việc nhóm](/images/1-Worklog/1.7-Week7/0406_meeting_w7.JPG)

