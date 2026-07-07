---
title: "Worklog Week 4"
date: 2026-05-11
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---

### Objectives for Week 4:

* Complete the advanced Labs via the link <https://cloudjourney.awsstudygroup.com/>.
* Configure centralized security governance mechanisms and ensure high availability for data.
* Practice deploying AWS WAF to protect the application layer (ALB) and conduct security testing using Black-box techniques.

### Tasks to be implemented this week:

| Day | Tasks | Start Date | End Date | Resources |
| --- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| **Mon** | **AWS Learning:** <br> - Complete Lab: Networking Essentials with Amazon Virtual Private Cloud (VPC) <br> - Complete Lab: Networking on AWS Workshop <br> - Complete Lab: Centralized Network Management with AWS Transit Gateway | 11/05/2026 | 11/05/2026 | **- Networking Essentials with Amazon Virtual Private Cloud (VPC)** <br> https://000003.awsstudygroup.com/ <br> **- Networking on AWS Workshop** <br> https://000092.awsstudygroup.com/ <br> **- Centralized Network Management with AWS Transit Gateway** <br> https://000020.awsstudygroup.com/ |
| **Tue** | **AWS Learning:** <br> - Complete Lab: Hybrid DNS Management with Amazon Route 53 <br> - Complete Lab: Security Governance with AWS Firewall Manager <br> - Complete Lab: Anomaly Detection for EBS Backups | 12/05/2026 | 12/05/2026 | **- Hybrid DNS Management with Amazon Route 53** <br> https://000010.awsstudygroup.com/ <br> **- Security Governance with AWS Firewall Manager** <br> https://000097.awsstudygroup.com/ <br> **- Anomaly Detection for EBS Backups** <br> https://000089.awsstudygroup.com/ |
| **Wed** | **AWS Learning:** <br> - Complete Lab: Systems Patching with EC2 Image Builder <br> - Complete Lab: Shared Storage with Amazon EBS Multi-Attach <br> - Complete Lab: Database High Availability with EBS Multi-Attach and Systems Manager | 13/05/2026 | 13/05/2026 | **- Systems Patching with EC2 Image Builder** <br> https://000099.awsstudygroup.com/ <br> **- Shared Storage with Amazon EBS Multi-Attach** <br> https://100000.awsstudygroup.com/ <br> **- Database High Availability with EBS Multi-Attach and Systems Manager** <br> https://100001.awsstudygroup.com/ |
| **Thu** | **AWS Learning:** <br> - Complete Lab: Monolith to Microservices Migration <br> - Complete Lab: Container Orchestration with Amazon ECS <br> - Complete Lab: Cloud Development Kit (AWS CDK) Essentials <br> **Group Project Execution:** <br> - Project Task (Pick Task): <br>&emsp; + Create a Web ACL with built-in rules against SQLi/XSS and associate it directly with the Application Load Balancer (ALB). <br>&emsp; + Use Postman to simulate live attacks (malicious payloads) on the system. <br>&emsp; + Conduct Black-box testing on the S3 interface. | 14/05/2026 | 14/05/2026 | **- Monolith to Microservices Migration** <br> https://000050.awsstudygroup.com/ <br> **- Container Orchestration with Amazon ECS** <br> https://000016.awsstudygroup.com/ <br> **- Cloud Development Kit (AWS CDK) Essentials** <br> https://000038.awsstudygroup.com/ |
| **Fri** | **AWS Learning:** <br> - Complete Lab: AWS CDK Advanced <br> - Complete Lab: Infrastructure as Code for ECS with CDK <br> - Complete Lab: Automated Deployments with AWS CodePipeline <br> **Group Meeting:** <br> - Offline group meeting to present implemented information | 15/05/2026 | 15/05/2026 | **- AWS CDK Advanced** <br> https://000076.awsstudygroup.com/ <br> **- Infrastructure as Code for ECS with CDK** <br> https://000118.awsstudygroup.com/ <br> **- Automated Deployments with AWS CodePipeline** <br> https://000023.awsstudygroup.com/ |

### Achieved Results for Week 4:

* Managed risk at scale using **AWS Firewall Manager**, establishing and enforcing consistent firewall policies across all organizational accounts.

* Established a secure network perimeter: Successfully deployed AWS WAF to directly protect the Application Load Balancer (ALB). Effectively used Managed Rules sets to block SQLi and XSS vulnerabilities.

* Interception testing (Red Team): Acted as an attacker, using Postman to simulate requests containing malicious payloads targeting the system. WAF successfully detected and defended against the attacks.

### Evidence of Implementation for Week 4: 

#### 1. Offline group meeting

<h4 align="center"><em>Group meeting to exchange completed tasks</em></h4>

![Group meeting to exchange completed tasks](/1505_meeting_w4.JPG)

#### 2. System testing with Postman

<h4 align="center"><em>Testing SQL Injection attack returns Status: 403 Forbidden</em></h4>

![Testing SQL Injection attack returns Status: 403 Forbidden](/sql_injection_alb.png)

<h4 align="center"><em>Testing XSS attack returns Status: 403 Forbidden</em></h4>

![Testing XSS attack returns Status: 403 Forbidden](/xss_alb.png)