---
title: "Worklog Tuần 3"
date: 2026-05-04
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---

### Mục tiêu tuần 3:

* Thực hiện cái bài Lab trong đường link <https://cloudjourney.awsstudygroup.com/>.
* Khởi tạo và cấu hình tường lửa lớp ứng dụng (AWS WAF) trên AWS Console, tiến hành kiểm thử đánh chặn mã độc bằng công cụ Postman.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| **2** | **Học tập AWS:** <br> - Làm Lab Permission Management with IAM Permission Boundaries <br> - Làm Lab Encryption with AWS Key Management Service (KMS) <br> - Làm Lab Credentials Management with AWS Secrets Manager | 04/05/2026 | 04/05/2026 | **- Permission Management with IAM Permission Boundaries** <br> https://000030.awsstudygroup.com/ <br> **- Encryption with AWS Key Management Service (KMS)** <br> https://000033.awsstudygroup.com/ <br> **- Credentials Management with AWS Secrets Manager** <br> https://000096.awsstudygroup.com/ |
| **3** | **Học tập AWS:** <br> - Làm Lab Cross-Domain Authentication with Amazon Cognito <br> - Làm Lab Data Protection with AWS Backup <br> - Làm Lab Network Integration with VPC Peering | 05/05/2026 | 05/05/2026 | **- Cross-Domain Authentication with Amazon Cognito** <br> https://000141.awsstudygroup.com/ <br> **- Data Protection with AWS Backup** <br> https://000013.awsstudygroup.com/ <br> **- Network Integration with VPC Peering** <br> https://000019.awsstudygroup.com/ |
| **4** | **Học tập AWS:** <br> - Làm Lab Messaging Systems with SQS and SNS <br> - Làm Lab Network Monitoring with VPC Flow Logs <br> - Làm Lab Threat Detection with AWS GuardDuty | 06/05/2026 | 06/05/2026 | **- Messaging Systems with SQS and SNS** <br> https://000077.awsstudygroup.com/ <br> **- Network Monitoring with VPC Flow Logs** <br> https://000074.awsstudygroup.com/ <br> **- Threat Detection with AWS GuardDuty** <br> https://000098.awsstudygroup.com/ |
| **5** | **Học tập AWS:** <br> - Làm Lab Cost Visualization and Analytics <br> - Làm Lab Security Compliance with AWS Security Hub <br> - Làm Lab Application Protection with AWS WAF <br> **Thực hiện đồ án nhóm:** <br> - Nhiệm vụ dự án (Pick Task): <br>&emsp; + Lên AWS Console tạo thử Web ACL với các luật cơ bản. <br>&emsp; + Thiết lập luật chống SQL Injection, XSS hoặc chặn IP rác. <br>&emsp; + Dùng Postman đóng vai kẻ tấn công, giả lập gửi request chứa payload mã độc vào hệ thống.  | 07/05/2026 | 07/05/2026 | **- Cost Visualization and Analytics** <br> https://000034.awsstudygroup.com/ <br> **- Security Compliance with AWS Security Hub** <br> https://000018.awsstudygroup.com/ <br> **- Application Protection with AWS WAF** <br> https://000026.awsstudygroup.com/ <br> **- Tài liệu Kiểm thử khởi tạo cấu hình:** <br> https://docs.google.com/document/d/1lOCGsSqTcvzA9FIHvGtMWjFfoimhxlb3ADYyWyX4ov4/edit?usp=sharing |
| **6** | **Học tập AWS:** <br> - Làm Lab Data Protection with Amazon Macie <br> - Làm Lab Single Page Application Authentication <br> - Làm Lab User Authentication with Amazon Cognito | 08/05/2026 | 08/05/2026 | **- Data Protection with Amazon Macie** <br> https://000090.awsstudygroup.com/ <br> **- Single Page Application Authentication** <br> https://000055.awsstudygroup.com/ <br> **- User Authentication with Amazon Cognito** <br> https://000081.awsstudygroup.com/ |

### Kết quả đạt được tuần 3:

* Sử dụng AWS KMS để mã hóa dữ liệu tại chỗ trên S3; đưa API Keys, Passwords vào Secrets Manager để tự động xoay vòng an toàn.

* Khởi tạo khiên bảo vệ: Thiết lập thành công tường lửa ứng dụng web (Web ACL) bảo vệ trực tiếp API Gateway.

* Hoàn thành kiểm chứng thực tế (Red/Blue Team): Sử dụng Postman bắn tải trọng (Payload) chứa mã độc SQL Injection và XSS. Kết quả: WAF đánh chặn lập tức mọi nỗ lực xâm nhập và trả về mã lỗi 403 Forbidden ngay tại biên mạng. Đã lưu trữ hình ảnh minh chứng (PoC) thành công.


### Minh chứng thực hiện tuần 3: 

#### 1. Khởi tạo Web ACL trên AWS WAF

<h4 align="center"><em>Khởi tạo Mock API để kiểm thử</em></h4>

![Khởi tạo Mock API để kiểm thử](/images/1-Worklog/1.3-Week3/mock_api.png)

<h4 align="center"><em>Khởi tạo Web ACL</em></h4>

![Khởi tạo Web ACL](/images/1-Worklog/1.3-Week3/waf.png)

#### 2. Kiểm thử hệ thống với Postman

<h4 align="center"><em>Gửi link truy cập hợp lệ trả về Status: 200 Ok</em></h4>

![Gửi link truy cập hợp lệ trả về Status: 200 Ok](/images/1-Worklog/1.3-Week3/200.png)

<h4 align="center"><em>Kiểm thử tấn công SQL Injection trả về Status: 403 Forbidden</em></h4>

![Kiểm thử tấn công SQL Injection trả về Status: 403 Forbidden](/images/1-Worklog/1.3-Week3/sql_injection.png)

<h4 align="center"><em>Kiểm thử tấn công XSS trả về Status: 403 Forbidden</em></h4>

![Kiểm thử tấn công XSS trả về Status: 403 Forbidden](/images/1-Worklog/1.3-Week3/xss.png)

<h4 align="center"><em>Kiểm thử tấn công Path Traversal trả về Status: 403 Forbidden</em></h4>

![Kiểm thử tấn công Path Traversal trả về Status: 403 Forbidden](/images/1-Worklog/1.3-Week3/path_traversal.png)

