---
title: "Worklog Week 3"
date: 2026-05-04
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---

### Objectives for Week 3:

* Complete the Hands-on Labs via the link <https://cloudjourney.awsstudygroup.com/>.
* Initialize and configure the application-layer firewall (AWS WAF) on the AWS Console, and conduct malicious code blocking tests using Postman.

### Tasks to be implemented this week:

| Day | Tasks | Start Date | End Date | Resources |
| :---: | :--- | :---: | :---: | :--- |
| **Mon** | **AWS Learning:** <br> - Complete Lab: Permission Management with IAM Permission Boundaries <br> - Complete Lab: Encryption with AWS Key Management Service (KMS) <br> - Complete Lab: Credentials Management with AWS Secrets Manager | 04/05/2026 | 04/05/2026 | **- Permission Management with IAM Permission Boundaries** <br> https://000030.awsstudygroup.com/ <br> **- Encryption with AWS Key Management Service (KMS)** <br> https://000033.awsstudygroup.com/ <br> **- Credentials Management with AWS Secrets Manager** <br> https://000096.awsstudygroup.com/ |
| **Tue** | **AWS Learning:** <br> - Complete Lab: Cross-Domain Authentication with Amazon Cognito <br> - Complete Lab: Data Protection with AWS Backup <br> - Complete Lab: Network Integration with VPC Peering | 05/05/2026 | 05/05/2026 | **- Cross-Domain Authentication with Amazon Cognito** <br> https://000141.awsstudygroup.com/ <br> **- Data Protection with AWS Backup** <br> https://000013.awsstudygroup.com/ <br> **- Network Integration with VPC Peering** <br> https://000019.awsstudygroup.com/ |
| **Wed** | **AWS Learning:** <br> - Complete Lab: Messaging Systems with SQS and SNS <br> - Complete Lab: Network Monitoring with VPC Flow Logs <br> - Complete Lab: Threat Detection with AWS GuardDuty | 06/05/2026 | 06/05/2026 | **- Messaging Systems with SQS and SNS** <br> https://000077.awsstudygroup.com/ <br> **- Network Monitoring with VPC Flow Logs** <br> https://000074.awsstudygroup.com/ <br> **- Threat Detection with AWS GuardDuty** <br> https://000098.awsstudygroup.com/ |
| **Thu** | **AWS Learning:** <br> - Complete Lab: Cost Visualization and Analytics <br> - Complete Lab: Security Compliance with AWS Security Hub <br> - Complete Lab: Application Protection with AWS WAF <br> **Group Project Execution:** <br> - Project Task (Pick Task): <br>&emsp; + Access the AWS Console to create a test Web ACL with basic rules. <br>&emsp; + Configure rules to prevent SQL Injection, XSS, or block spam IPs. <br>&emsp; + Use Postman to act as an attacker, simulating requests with malicious payloads to the system. | 07/05/2026 | 07/05/2026 | **- Cost Visualization and Analytics** <br> https://000034.awsstudygroup.com/ <br> **- Security Compliance with AWS Security Hub** <br> https://000018.awsstudygroup.com/ <br> **- Application Protection with AWS WAF** <br> https://000026.awsstudygroup.com/ <br> **- Configuration Initialization Testing Document:** <br> https://docs.google.com/document/d/1lOCGsSqTcvzA9FIHvGtMWjFfoimhxlb3ADYyWyX4ov4/edit?usp=sharing |
| **Fri** | **AWS Learning:** <br> - Complete Lab: Data Protection with Amazon Macie <br> - Complete Lab: Single Page Application Authentication <br> - Complete Lab: User Authentication with Amazon Cognito | 08/05/2026 | 08/05/2026 | **- Data Protection with Amazon Macie** <br> https://000090.awsstudygroup.com/ <br> **- Single Page Application Authentication** <br> https://000055.awsstudygroup.com/ <br> **- User Authentication with Amazon Cognito** <br> https://000081.awsstudygroup.com/ |

### Achieved Results for Week 3:

* Used AWS KMS for at-rest data encryption on S3; securely stored API Keys and Passwords in Secrets Manager for automatic and safe rotation.

* Initialized defense shield: Successfully set up a Web Application Firewall (Web ACL) to directly protect the API Gateway.

* Practical verification (Red/Blue Team): Used Postman to fire payloads containing malicious SQL Injection and XSS code. Result: WAF immediately intercepted all intrusion attempts and returned a 403 Forbidden error right at the network edge. Successfully documented and saved Proof of Concept (PoC) images.

### Evidence of Implementation for Week 3: 

#### 1. Initializing Web ACL on AWS WAF

<h4 align="center"><em>Initializing Mock API for testing</em></h4>

![Initializing Mock API for testing](/mock_api.png)

<h4 align="center"><em>Initializing Web ACL</em></h4>

![Initializing Web ACL](/waf.png)

#### 2. System testing with Postman

<h4 align="center"><em>Sending a valid access link returns Status: 200 OK</em></h4>

![Sending a valid access link returns Status: 200 OK](/200.png)

<h4 align="center"><em>Testing SQL Injection attack returns Status: 403 Forbidden</em></h4>

![Testing SQL Injection attack returns Status: 403 Forbidden](/sql_injection.png)

<h4 align="center"><em>Testing XSS attack returns Status: 403 Forbidden</em></h4>

![Testing XSS attack returns Status: 403 Forbidden](/xss.png)

<h4 align="center"><em>Testing Path Traversal attack returns Status: 403 Forbidden</em></h4>

![Testing Path Traversal attack returns Status: 403 Forbidden](/path_traversal.png)