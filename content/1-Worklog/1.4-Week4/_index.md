---
title: "Worklog Week 4"
date: 2026-05-11
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---
### Week 4 Objectives:

* Complete the advanced Labs provided at <https://cloudjourney.awsstudygroup.com/>.
* Configure centralized security governance mechanisms and ensure high availability for data.
* Practice deploying AWS WAF to protect the application layer (ALB) and conduct security testing using Black-box techniques.

### Tasks to be implemented this week:

| Day | Task | Start Date | Completion Date | Resources |
| --- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| **Mon** | **AWS Learning:** <br> - Complete Lab: Networking Essentials with Amazon Virtual Private Cloud (VPC) <br> - Complete Lab: Networking on AWS Workshop <br> - Complete Lab: Centralized Network Management with AWS Transit Gateway | 11/05/2026 | 11/05/2026 | **- Networking Essentials with Amazon Virtual Private Cloud (VPC)** <br> https://000003.awsstudygroup.com/ <br> **- Networking on AWS Workshop** <br> https://000092.awsstudygroup.com/ <br> **- Centralized Network Management with AWS Transit Gateway** <br> https://000020.awsstudygroup.com/ |
| **Tue** | **AWS Learning:** <br> - Complete Lab: Hybrid DNS Management with Amazon Route 53 <br> - Complete Lab: Security Governance with AWS Firewall Manager <br> - Complete Lab: Anomaly Detection for EBS Backups | 12/05/2026 | 12/05/2026 | **- Hybrid DNS Management with Amazon Route 53** <br> https://000010.awsstudygroup.com/ <br> **- Security Governance with AWS Firewall Manager** <br> https://000097.awsstudygroup.com/ <br> **- Anomaly Detection for EBS Backups** <br> https://000089.awsstudygroup.com/ |
| **Wed** | **AWS Learning:** <br> - Complete Lab: Systems Patching with EC2 Image Builder <br> - Complete Lab: Shared Storage with Amazon EBS Multi-Attach <br> - Complete Lab: Database High Availability with EBS Multi-Attach and Systems Manager | 13/05/2026 | 13/05/2026 | **- Systems Patching with EC2 Image Builder** <br> https://000099.awsstudygroup.com/ <br> **- Shared Storage with Amazon EBS Multi-Attach** <br> https://100000.awsstudygroup.com/ <br> **- Database High Availability with EBS Multi-Attach and Systems Manager** <br> https://100001.awsstudygroup.com/ |
| **Thu** | **AWS Learning:** <br> - Complete Lab: Monolith to Microservices Migration <br> - Complete Lab: Container Orchestration with Amazon ECS <br> - Complete Lab: Cloud Development Kit (AWS CDK) Essentials <br> **Group Project Execution:** <br> Project Assignment (Task Pick): <br>&emsp; + Create a Web ACL with built-in rules against SQLi/XSS and associate it directly with the Application Load Balancer (ALB). <br>&emsp; + Use Postman to simulate sending malicious payloads into the system. <br>&emsp; + Conduct Black-box testing on the frontend hosted on Amazon S3. | 14/05/2026 | 14/05/2026 | **- Monolith to Microservices Migration** <br> https://000050.awsstudygroup.com/ <br> **- Container Orchestration with Amazon ECS** <br> https://000016.awsstudygroup.com/ <br> **- Cloud Development Kit (AWS CDK) Essentials** <br> https://000038.awsstudygroup.com/ |
| **Fri** | **AWS Learning:** <br> - Complete Lab: AWS CDK Advanced <br> - Complete Lab: Infrastructure as Code for ECS with CDK <br> - Complete Lab: Automated Deployments with AWS CodePipeline <br> **Team Meeting:** <br> - Offline team meeting to present implementation progress | 15/05/2026 | 15/05/2026 | **- AWS CDK Advanced** <br> https://000076.awsstudygroup.com/ <br> **- Infrastructure as Code for ECS with CDK** <br> https://000118.awsstudygroup.com/ <br> **- Automated Deployments with AWS CodePipeline** <br> https://000023.awsstudygroup.com/ |



### Week 4 Achievements:

* Managed risks at scale using **AWS Firewall Manager**, successfully setting and enforcing consistent firewall policies across all organizational accounts.

* Successfully established a secure network perimeter: Deployed AWS WAF to directly protect the Application Load Balancer (ALB). Effectively utilized Managed Rule groups to block SQLi and XSS vulnerabilities.

* Completed interception testing (Red Team): Acted as an attacker using Postman to simulate sending requests containing malicious payloads into the system. AWS WAF successfully detected and defended against the attacks.

### Week 4 Implementation Evidence: 

#### 1. Offline team meeting

<h4 align="center"><em>Team meeting discussing completed tasks</em></h4>

![Team meeting discussing completed tasks](/1505_meeting_w4.JPG)

#### 2. System Testing with Postman

<h4 align="center"><em>SQL Injection attack test returns Status: 403 Forbidden</em></h4>

![SQL Injection attack test returns Status: 403 Forbidden](/sql_injection_alb.png)

<h4 align="center"><em>XSS attack test returns Status: 403 Forbidden</em></h4>

![XSS attack test returns Status: 403 Forbidden](/xss_alb.png)