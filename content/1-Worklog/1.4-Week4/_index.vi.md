---
title: "Worklog Tuần 4"
date: 2026-05-11
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---
### Mục tiêu tuần 4:

* Thực hiện các bài Lab chuyên sâu trong đường link <https://cloudjourney.awsstudygroup.com/>.
* Cấu hình các cơ chế quản trị bảo mật tập trung và đảm bảo tính sẵn sàng cao cho dữ liệu.
* Thực hành triển khai AWS WAF để bảo vệ lớp ứng dụng (ALB) và tiến hành kiểm thử bảo mật bằng kỹ thuật Black-box.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| **2** | **Học tập AWS:** <br> - Làm Lab Networking Essentials with Amazon Virtual Private Cloud (VPC) <br> - Làm Lab Networking on AWS Workshop <br> - Làm Lab Centralized Network Management with AWS Transit Gateway | 11/05/2026 | 11/05/2026 | **- Networking Essentials with Amazon Virtual Private Cloud (VPC)** <br> https://000003.awsstudygroup.com/ <br> **- Networking on AWS Workshop** <br> https://000092.awsstudygroup.com/ <br> **- Centralized Network Management with AWS Transit Gateway** <br> https://000020.awsstudygroup.com/ |
| **3** | **Học tập AWS:** <br> - Làm Lab Hybrid DNS Management with Amazon Route 53 <br> - Làm Lab Security Governance with AWS Firewall Manager <br> - Làm Lab Anomaly Detection for EBS Backups | 12/05/2026 | 12/05/2026 | **- Hybrid DNS Management with Amazon Route 53** <br> https://000010.awsstudygroup.com/ <br> **- Security Governance with AWS Firewall Manager** <br> https://000097.awsstudygroup.com/ <br> **- Anomaly Detection for EBS Backups** <br> https://000089.awsstudygroup.com/ |
| **4** | **Học tập AWS:** <br> - Làm Lab Systems Patching with EC2 Image Builder <br> - Làm Lab Shared Storage with Amazon EBS Multi-Attach <br> - Làm Lab Database High Availability with EBS Multi-Attach and Systems Manager | 13/05/2026 | 13/05/2026 | **- Systems Patching with EC2 Image Builder** <br> https://000099.awsstudygroup.com/ <br> **- Shared Storage with Amazon EBS Multi-Attach** <br> https://100000.awsstudygroup.com/ <br> **- Database High Availability with EBS Multi-Attach and Systems Manager** <br> https://100001.awsstudygroup.com/ |
| **5** | **Học tập AWS:** <br> - Làm Lab Monolith to Microservices Migration <br> - Làm Lab Container Orchestration with Amazon ECS <br> - Làm Lab Cloud Development Kit (AWS CDK) Essentials <br> **Thực hiện đồ án nhóm:** <br> Nhiệm vụ dự án (Pick Task): <br>&emsp; + Tạo Web ACL có sẵn các rule chống SQL/XSS và gắn trực tiếp (Associate) vào Application Load Balancer (ALB). <br>&emsp; + Sử dụng Postman để bắn thử đạn thật (Payload mã độc) vào hệ thống. <br>&emsp; + Tiến hành kiểm thử hộp đen (Black-box testing) đối với giao diện trên S3.  | 14/05/2026 | 14/05/2026 | **- Monolith to Microservices Migration** <br> https://000050.awsstudygroup.com/ <br> **- Container Orchestration with Amazon ECS** <br> https://000016.awsstudygroup.com/ <br> **- Cloud Development Kit (AWS CDK) Essentials** <br> https://000038.awsstudygroup.com/ |
| **6** | **Học tập AWS:** <br> - Làm Lab AWS CDK Advanced <br> - Làm Lab Infrastructure as Code for ECS with CDK <br> - Làm Lab Automated Deployments with AWS CodePipeline <br> **Họp nhóm:** <br> - Họp nhóm offline trình bày thông tin thực hiện | 15/05/2026 | 15/05/2026 | **- AWS CDK Advanced** <br> https://000076.awsstudygroup.com/ <br> **- Infrastructure as Code for ECS with CDK** <br> https://000118.awsstudygroup.com/ <br> **- Automated Deployments with AWS CodePipeline** <br> https://000023.awsstudygroup.com/ |



### Kết quả đạt được tuần 4:

* Quản trị rủi ro trên quy mô lớn bằng **AWS Firewall Manager**, thiết lập và ép buộc các chính sách tường lửa đồng nhất trên toàn bộ các tài khoản của tổ chức.

* Hoàn thành thiết lập biên mạng an toàn: Triển khai AWS WAF bảo vệ trực tiếp Application Load Balancer (ALB) thành công. Sử dụng hiệu quả các bộ Managed Rules để chặn đứng lỗi SQLi và XSS.

* Hoàn thành kiểm thử đánh chặn (Red Team): Đóng vai kẻ tấn công, sử dụng Postman giả lập bắn request chứa payload mã độc vào hệ thống. WAF đã nhận diện và phòng thủ thành công.

### Minh chứng thực hiện tuần 4: 

#### 1. Họp nhóm offline

<h4 align="center"><em>Họp nhóm trao đổi nhiệm vụ đã thực hiện</em></h4>

![Họp nhóm trao đổi nhiệm vụ đã thực hiện](/images/1-Worklog/1.4-Week4/1505_meeting_w4.JPG)

#### 2. Kiểm thử hệ thống với Postman

<h4 align="center"><em>Kiểm thử tấn công SQL Injection trả về Status: 403 Forbidden</em></h4>

![Kiểm thử tấn công SQL Injection trả về Status: 403 Forbidden](/images/1-Worklog/1.4-Week4/sql_injection_alb.png)

<h4 align="center"><em>Kiểm thử tấn công XSS trả về Status: 403 Forbidden</em></h4>

![Kiểm thử tấn công XSS trả về Status: 403 Forbidden](/images/1-Worklog/1.4-Week4/xss_alb.png)