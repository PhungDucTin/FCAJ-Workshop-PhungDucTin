---
title: "Worklog Tuần 5"
date: 2026-05-18
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---
### Mục tiêu tuần 5:

* Thực hiện các bài Lab chuyên sâu trong đường link <https://cloudjourney.awsstudygroup.com/>.
* Ứng dụng tư duy "Phòng thủ chiều sâu" để thiết kế kiến trúc bảo mật cho dự án và tiến hành đánh giá bảo mật động (DAST) tầng ứng dụng.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| **2** | **Học tập AWS:** <br> - Làm Lab Windows Server Failover Clustering on AWS <br> - Làm Lab SQL Server High Availability on AWS (2019) <br> - Làm Lab SQL Server High Availability on AWS (2022) | 18/05/2026 | 18/05/2026 | **- Windows Server Failover Clustering on AWS** <br> https://100002.awsstudygroup.com/ <br> **- SQL Server High Availability on AWS (2019)** <br> https://100003.awsstudygroup.com/ <br> **- SQL Server High Availability on AWS (2022)** <br> https://100004.awsstudygroup.com/ |
| **3** | **Học tập AWS:** <br> - Làm Lab Containerization with Docker <br> - Làm Lab CI/CD Pipeline with AWS CodePipeline <br> - Làm Lab DevOps with AWS CodePipeline <br> **Thực hiện đồ án nhóm:** <br> - Nhiệm vụ dự án (Pick Task): <br>&emsp; + Phác thảo luồng dữ liệu (Sequence Diagram) cho tính năng "Quên mật khẩu". <br>&emsp; + Đánh giá bảo mật động (DAST) bằng OWASP ZAP, trích lọc Top 10 lỗ hổng nguy hiểm nhất và lập Báo cáo hành động bảo mật.| 19/05/2026 | 19/05/2026 | **- Containerization with Docker** <br> https://100000.awsstudygroup.com/ <br> **- CI/CD Pipeline with AWS CodePipeline** <br> https://000017.awsstudygroup.com/ <br> **- DevOps with AWS CodePipeline** <br> https://000152.awsstudygroup.com/  <br> **- Tài liệu Sơ đồ luồng "Quên mật khẩu":** https://docs.google.com/document/d/1UeXtlMtoneGW1W65jewPU1Jn9RD6yXfjzYlGXwqMkqw/edit?usp=sharing |
| **4** | **Học tập AWS:** <br> - Làm Lab Hybrid Storage with AWS Storage Gateway <br> - Làm Lab Windows File Storage with Amazon FSx <br> - Làm Lab Storage Performance Workshop | 20/05/2026 | 20/05/2026 | **- Hybrid Storage with AWS Storage Gateway** <br> https://000024.awsstudygroup.com/ <br> **- Windows File Storage with Amazon FSx** <br> https://000025.awsstudygroup.com/ <br> **- Storage Performance Workshop** <br> https://000068.awsstudygroup.com/ |
| **5** | **Học tập AWS:** <br> - Làm Lab Building Advanced Applications with Amazon DynamoDB <br> - Làm Lab Workflow Orchestration with AWS Step Functions <br> - Làm Lab Cost Savings with Savings Plans and Reserved Instances | 21/05/2026 | 21/05/2026 | **- Building Advanced Applications with Amazon DynamoDB** <br> https://000039.awsstudygroup.com/ <br> **- Workflow Orchestration with AWS Step Functions** <br> https://000047.awsstudygroup.com/ <br> **- Cost Savings with Savings Plans and Reserved Instances** <br> https://000042.awsstudygroup.com/ |
| **6** | **Học tập AWS:** <br> - Làm Lab Advanced Monitoring with CloudWatch and Grafana <br> - Làm Lab CloudWatch Advanced Workshop <br> - Làm Lab Infrastructure as Code Workshop Series | 22/05/2026 | 22/05/2026 | **- Advanced Monitoring with CloudWatch and Grafana** <br> https://000029.awsstudygroup.com/ <br> **- CloudWatch Advanced Workshop** <br> https://000036.awsstudygroup.com/ <br> **- Infrastructure as Code Workshop Series** <br> https://000102.awsstudygroup.com/ |

### Kết quả đạt được tuần 5:

* Thiết kế luồng "Quên mật khẩu": Hoàn thành bản phác thảo luồng dữ liệu (Sequence Diagram) áp dụng các chốt chặn an toàn mạnh mẽ bao gồm: chống dò quét người dùng (User Enumeration), giới hạn tốc độ (Rate-Limiting) và băm mã xác thực (Hash Token).

* Đánh giá bảo mật động (DAST): Chạy công cụ OWASP ZAP để rà quét ứng dụng, tiến hành phân tích log và cô lập biến số nhằm loại bỏ triệt để các cảnh báo giả (False Positives).

* Báo cáo & Chuyển giao: Lập Báo cáo hành động bảo mật, trích lọc Top 10 lỗ hổng nguy hiểm nhất và chuyển giao hướng dẫn vá lỗi (Patching) ngắn gọn, trúng đích cho team Dev xử lý.

### Minh chứng thực hiện tuần 5:

#### 1. Sơ đồ luồng "Quên mật khẩu"

<h4 align="center"><em>Sơ đồ luồng "Quên mật khẩu"</em></h4>

![Sơ đồ luồng quên mật khẩu](/images/1-Worklog/1.5-Week5/SoDoLuongQuenMatKhau.png)


