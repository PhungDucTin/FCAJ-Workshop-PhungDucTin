---
title: "Worklog Tuần 1"
date: 2026-04-20
weight: 1
chapter: false
pre: " <b> 1.1. </b> "
---

### Mục tiêu tuần 1:

* Tìm hiểu, kết nối, làm quen với các thành viên trong First Cloud AI Journey.
* Hiểu các dịch vụ AWS cơ bản, cách dùng console và CLI, kết hợp học tập lý thuyết và thực hành.
* Thực hiện rà soát bảo mật (System Audit) cho dự án nội bộ và đề xuất giải pháp phòng thủ.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| :---: | :--- | :---: | :---: | :--- |
| **2** | **Học tập AWS:** <br> - Module 01-01 - Introduction to AWS <br> - Module 01-02 - Management Console <br> - Module 01-03 - Gen AI on AWS - Kiro <br> - Module 01-04 - Cost Optimization on AWS | 20/04/2026 | 20/04/2026 | **- Module 01-01:** <br> https://www.youtube.com/watch?v=qVCF7UjYC5s <br> **- Module 01-02:** <br> https://www.youtube.com/watch?v=95quNuhvMT0 <br> **- Module 01-03:** <br> https://www.youtube.com/watch?v=uAQCm4sm_1c <br> **- Module 01-04:** <br> https://www.youtube.com/watch?v=UIw8UxGZCHA |
| **3** | **Học tập AWS:** <br> - Hiểu rõ 6 Trụ cột kiến trúc: Bảo mật, Vận hành xuất sắc, Độ tin cậy, Hiệu suất, Tối ưu chi phí và Bền vững. <br> - Làm quen với AWS Well-Architected Tool để đánh giá rủi ro dự án. <br> **Thực hiện đồ án nhóm:** <br> - Nhiệm vụ dự án (Pick Task):<br>&emsp; + Nhận link Ngrok, dùng tool (Nmap, Nikto, ZAP) rà quét mục tiêu. <br>&emsp; + Ghi chú lại nhật ký tấn công (thời gian, công cụ). <br>&emsp; + Lập Báo cáo rủi ro: Top 3 lỗ hổng và đề xuất chặn bằng AWS WAF/Security Group. | 21/04/2026 | 21/04/2026 | **- Tài liệu thực hiện Nhật kí tấn công:** <br> https://docs.google.com/document/d/1gIt2LZPLds8ZAZtRbFF6XhKoFawWnP8_fzAp2Bv54CM/edit?usp=sharing <br> **- Tài liệu Báo cáo rủi ro:** <br> https://docs.google.com/document/d/1qHgT8dhm1h4-MQoz0GSuyaJ9g12W7GO9haqEEOwCfic/edit?usp=sharing |
| **4** | **Học tập AWS:** <br> - Làm Lab000001: Creating Your First AWS Account <br> - Làm Lab000009: Getting Help with AWS Support | 22/04/2026 | 22/04/2026 | **- Lab000001:** <br> https://000001.awsstudygroup.com/ <br> **- Lab000009:** <br> https://000009.awsstudygroup.com/ |
| **5** | **Học tập AWS:** <br> - Làm Lab000007: Managing Costs with AWS Budgets <br> - Làm Lab000180: Kiro Spec Driven Development | 23/04/2026 | 23/04/2026 | **- Lab000007:** <br> https://000007.awsstudygroup.com/ |
| **6** | **Họp nhóm:** <br> - Trao đổi thông tin đã thực hiện <br> - Báo cáo kết quả đạt được với nhóm | 24/04/2026 | 24/04/2026 | |

<br>

### Kết quả đạt được tuần 1:

* Thành công thiết lập tài khoản an toàn với MFA; áp dụng triệt để nguyên tắc đặc quyền tối thiểu (Least Privilege) cho nhóm Admins và IAM User. Thực hiện thành công quy trình mở Support Case.

* Cấu hình thành công AWS Budgets làm hệ thống cảnh báo sớm: đặt trần chi phí, bật cảnh báo tức thời từ mức $0.01 và theo dõi thời gian hoạt động của EC2 để phòng ngừa việc chạy máy chủ trái phép.

* Nắm được 6 trụ cột của AWS Well-Architected Framework và 4 cấp độ Support.

* Hoàn thành kiểm thử thủ công trên ứng dụng được public qua Ngrok. Đã mô phỏng tấn công, phát hiện và ghi log thành công các lỗ hổng nghiêm trọng bao gồm SQL Injection, Path Traversal và XSS attack vào file `security_audit.log`.
 ### Minh chứng thực hiện tuần 1: 

 #### 1. Thực hiện quét Ngrok với Nmap và Nikto 

 <h4 align="center"><em>Kết quả sau khi thực hiện</em></h4>

![Kết quả sau khi thực hiện](/images/1-Worklog/1.1-Week1/nmap_nikto.png)

#### 2. Thực hiện quét Ngrok với OWASP ZAP 

 <h4 align="center"><em>Kết quả sau khi thực hiện</em></h4>

![Kết quả sau khi thực hiện](/images/1-Worklog/1.1-Week1/owaspzap.png)

#### 3. Ghi nhận lỗ hổng trong file `security_audit.log`

 <h4 align="center"><em>Ghi nhận lỗ hổng trong file</em></h4>

```json
{"time":"2026-04-20T21:58:02", "level":"WARN", "type":"SECURITY", "msg":"type=SQL_INJECTION ip=42.119.86.124 method=GET uri=/ query=search=%27%20OR%202%3D2%20-- ua=curl/8.18.0"}
{"time":"2026-04-20T21:58:21", "level":"WARN", "type":"SECURITY", "msg":"type=PATH_TRAVERSAL ip=42.119.86.124 method=GET uri=/ query=file=../../../../etc/passwd ua=curl/8.18.0"}
{"time":"2026-04-20T21:58:14", "level":"WARN", "type":"SECURITY", "msg":"type=XSS_ATTACK ip=42.119.86.124 method=GET uri=/ query=username=%3Cscript%3Ealert(1)%3C/script%3E ua=curl/8.18.0"}
```

#### 4. Họp nhóm online 

<h4 align="center"><em>Họp nhóm online trao đổi thông tin</em></h4>

![Họp nhóm online trao đổi thông tin](/images/1-Worklog/1.1-Week1/2604_meetingOnl_w1.png)