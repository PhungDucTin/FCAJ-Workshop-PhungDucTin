---
title: "Worklog Tuần 6"
date: 2026-05-25
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
---


### Mục tiêu tuần 6:

* Thực hiện các bài Lab chuyên sâu trong đường link <https://cloudjourney.awsstudygroup.com/>.

* Ứng dụng DevSecOps: Tích hợp công cụ quét bảo mật (SAST/SCA) vào luồng CI/CD và thiết lập kho lưu trữ khóa bảo mật tập trung trên AWS.


### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| **2** | **Học tập AWS:** <br> - Làm Lab Building Microservices <br> - Làm Lab Data and Workflow Restructuring <br> - Làm Lab Event-Driven Architecture | 25/05/2026 | 25/05/2026 | **- Building Microservices** <br> https://000052.awsstudygroup.com/ <br> **- Data and Workflow Restructuring** <br> https://000053.awsstudygroup.com/ <br> **- Event-Driven Architecture** <br> https://000054.awsstudygroup.com/ |
| **3** | **Học tập AWS:** <br> - Làm Lab Serverless Backend with Lambda, S3, and DynamoDB <br> - Làm Lab Frontend Development for Serverless APIs <br> - Làm Lab Building Serverless CRUD with Lambda and DynamoDB | 26/05/2026 | 26/05/2026 | **- Serverless Backend with Lambda, S3, and DynamoDB** <br> https://000078.awsstudygroup.com/ <br> **- Frontend Development for Serverless APIs** <br> https://000079.awsstudygroup.com/ <br> **- Building Serverless CRUD with Lambda and DynamoDB** <br> https://000133.awsstudygroup.com/ |
| **4** | **Học tập AWS:** <br> - Làm Lab CI/CD for Application Release <br> - Làm Lab Deployment Automation with AWS SAM <br> - Làm Lab CI/CD for Serverless Applications <br> **Thực hiện đồ án nhóm:** <br> - Nhiệm vụ dự án (Pick Task): <br>&emsp; + Chuyển đổi việc lưu biến môi trường từ file `.env` sang hệ thống quản lý của AWS. Viết tài liệu hướng dẫn Backend lấy cấu hình từ AWS lúc chạy. <br>&emsp; + Sử dụng SonarCloud để quét Repository. | 27/05/2026 | 27/05/2026 | **- CI/CD for Application Release** <br> https://000051.awsstudygroup.com/ <br> **- Deployment Automation with AWS SAM** <br> https://000080.awsstudygroup.com/ <br> **- CI/CD for Serverless Applications** <br> https://000084.awsstudygroup.com/ <br> **- Tài liệu Chuyển đổi biến lên AWS Systems Manager:** <br> https://docs.google.com/document/d/1-JWPB3X-2IkXRvHF5f19nVo686wB473vR3SE6oUKoi4/edit?usp=sharing <br> **- Tài liệu Báo cáo lỗ hổng trên SonarCloud:** https://docs.google.com/document/d/1UeXtlMtoneGW1W65jewPU1Jn9RD6yXfjzYlGXwqMkqw/edit?usp=sharing |
| **5** | **Học tập AWS:** <br> - Làm Lab Event Processing with SQS and SNS <br> - Làm Lab Building GraphQL APIs with AWS AppSync <br> - Làm Lab AWS AI Services Integration | 28/05/2026 | 28/05/2026 | **- Event Processing with SQS and SNS** <br> https://000083.awsstudygroup.com/ <br> **- Building GraphQL APIs with AWS AppSync** <br> https://000086.awsstudygroup.com/ <br> **- AWS AI Services Integration** <br> https://000056.awsstudygroup.com/ |
| **6** | **Học tập AWS:** <br> - Làm Lab Serverless Storage and Auth with AWS Amplify <br> - Làm Lab Custom Domains and SSL for Serverless Applications <br> - Làm Lab Monitoring Serverless Applications <br> **Họp nhóm:** <br> - Báo cáo kết quả thực hiện <br> - Trao đổi thông tin giữa các thành viên | 29/05/2026 | 29/05/2026 | **- Serverless Storage and Auth with AWS Amplify** <br> https://000134.awsstudygroup.com/ <br> **- Custom Domains and SSL for Serverless Applications** <br> https://000082.awsstudygroup.com/ <br> **- Monitoring Serverless Applications** <br> https://000085.awsstudygroup.com/ |

### Kết quả đạt được tuần 6:

* Hoàn thành việc chuyển đổi quản lý biến môi trường từ file `.env` sang hệ thống quản lý cấu hình trên AWS, giúp dữ liệu cấu hình được lưu trữ và truy xuất an toàn hơn trong môi trường triển khai.

* Viết tài liệu hướng dẫn Backend lấy cấu hình từ AWS trong quá trình chạy ứng dụng, nhằm giảm phụ thuộc vào thông tin nhạy cảm được lưu cục bộ.

### Minh chứng thực hiện tuần 6: 

#### 1. Họp nhóm offline báo cáo kết quả

<h4 align="center"><em>Họp nhóm trao đổi nhiệm vụ đã thực hiện</em></h4>

![Họp nhóm trao đổi nhiệm vụ đã thực hiện](/images/1-Worklog/1.6-Week6/2905_meeting_w6.JPG)

#### 2. Chuyển đổi biến từ file .env lên AWS 

<h4 align="center"><em>Chuyển đổi quản lý biến môi trường</em></h4>

![Chuyển đổi quản lý biến môi trường](/images/1-Worklog/1.6-Week6/ssm.png)

#### 3. Tích hợp SonarCloud để quét lỗ hổng

<h4 align="center"><em>Tích hợp SonarCloud vào dự án</em></h4>

![Tích hợp SonarCloud vào dự án](/images/1-Worklog/1.6-Week6/SonarCloud.png)
