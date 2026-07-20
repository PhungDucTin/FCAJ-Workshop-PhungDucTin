---
title: "Worklog Week 5"
date: 2026-05-18
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---

### Objectives for Week 5:

* Complete the advanced labs through the link <https://cloudjourney.awsstudygroup.com/>.
* Apply a defense-in-depth approach to design the security architecture for the project and conduct dynamic application security testing (DAST) at the application layer.

### Tasks to be implemented this week:

| Day | Tasks | Start Date | End Date | Resources |
| --- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| **Mon** | **AWS Learning:** <br> - Complete Lab: Windows Server Failover Clustering on AWS <br> - Complete Lab: SQL Server High Availability on AWS (2019) <br> - Complete Lab: SQL Server High Availability on AWS (2022) | 18/05/2026 | 18/05/2026 | **- Windows Server Failover Clustering on AWS** <br> https://100002.awsstudygroup.com/ <br> **- SQL Server High Availability on AWS (2019)** <br> https://100003.awsstudygroup.com/ <br> **- SQL Server High Availability on AWS (2022)** <br> https://100004.awsstudygroup.com/ |
| **Tue** | **AWS Learning:** <br> - Complete Lab: Containerization with Docker <br> - Complete Lab: CI/CD Pipeline with AWS CodePipeline <br> - Complete Lab: DevOps with AWS CodePipeline <br> **Group Project Execution:** <br> - Project task (selected task): <br>&emsp; + Draft the data flow (sequence diagram) for the "Forgot Password" feature. <br>&emsp; + Conduct dynamic application security testing (DAST) using OWASP ZAP, extract the top 10 most critical vulnerabilities, and create a security action report. | 19/05/2026 | 19/05/2026 | **- Containerization with Docker** <br> https://100000.awsstudygroup.com/ <br> **- CI/CD Pipeline with AWS CodePipeline** <br> https://000017.awsstudygroup.com/ <br> **- DevOps with AWS CodePipeline** <br> https://000152.awsstudygroup.com/  <br> **- "Forgot Password" Sequence Diagram Document:** https://docs.google.com/document/d/1UeXtlMtoneGW1W65jewPU1Jn9RD6yXfjzYlGXwqMkqw/edit?usp=sharing |
| **Wed** | **AWS Learning:** <br> - Complete Lab: Hybrid Storage with AWS Storage Gateway <br> - Complete Lab: Windows File Storage with Amazon FSx <br> - Complete Lab: Storage Performance Workshop | 20/05/2026 | 20/05/2026 | **- Hybrid Storage with AWS Storage Gateway** <br> https://000024.awsstudygroup.com/ <br> **- Windows File Storage with Amazon FSx** <br> https://000025.awsstudygroup.com/ <br> **- Storage Performance Workshop** <br> https://000068.awsstudygroup.com/ |
| **Thu** | **AWS Learning:** <br> - Complete Lab: Building Advanced Applications with Amazon DynamoDB <br> - Complete Lab: Workflow Orchestration with AWS Step Functions <br> - Complete Lab: Cost Savings with Savings Plans and Reserved Instances | 21/05/2026 | 21/05/2026 | **- Building Advanced Applications with Amazon DynamoDB** <br> https://000039.awsstudygroup.com/ <br> **- Workflow Orchestration with AWS Step Functions** <br> https://000047.awsstudygroup.com/ <br> **- Cost Savings with Savings Plans and Reserved Instances** <br> https://000042.awsstudygroup.com/ |
| **Fri** | **AWS Learning:** <br> - Complete Lab: Advanced Monitoring with CloudWatch and Grafana <br> - Complete Lab: CloudWatch Advanced Workshop <br> - Complete Lab: Infrastructure as Code Workshop Series | 22/05/2026 | 22/05/2026 | **- Advanced Monitoring with CloudWatch and Grafana** <br> https://000029.awsstudygroup.com/ <br> **- CloudWatch Advanced Workshop** <br> https://000036.awsstudygroup.com/ <br> **- Infrastructure as Code Workshop Series** <br> https://000102.awsstudygroup.com/ |

### Achieved Results for Week 5:

* Designed the "Forgot Password" flow: completed a draft of the data flow (sequence diagram) incorporating robust security checkpoints, including protection against user enumeration, rate limiting, and hashed authentication tokens.

* Dynamic Application Security Testing (DAST): ran OWASP ZAP to scan the application, analyzed the logs, and isolated variables to thoroughly eliminate false positives.

* Reporting and handover: created a security action report, extracted the top 10 most critical vulnerabilities, and provided concise, targeted remediation guidance for the development team.

### Evidence of Implementation for Week 5:

#### 1. "Forgot Password" Sequence Diagram

<h4 align="center"><em>"Forgot Password" Sequence Diagram</em></h4>

!["Forgot Password" sequence diagram](/images/1-Worklog/1.5-Week5/SoDoLuongQuenMatKhau.png)