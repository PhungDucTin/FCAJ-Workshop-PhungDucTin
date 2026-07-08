---
title: "Worklog Week 3"
date: 2026-05-04
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---

### Week 3 Objectives:

* Complete the Labs provided at <https://cloudjourney.awsstudygroup.com/>.
* Initialize and configure a web application firewall (AWS WAF) on the AWS Console, and conduct malicious payload interception testing using Postman.

### Tasks to be implemented this week:

| Day | Task | Start Date | Completion Date | Resources |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| **Mon** | **AWS Learning:** <br> - Complete Lab: Permission Management with IAM Permission Boundaries <br> - Complete Lab: Encryption with AWS Key Management Service (KMS) <br> - Complete Lab: Credentials Management with AWS Secrets Manager | 04/05/2026 | 04/05/2026 | **- Permission Management with IAM Permission Boundaries** <br> https://000030.awsstudygroup.com/ <br> **- Encryption with AWS Key Management Service (KMS)** <br> https://000033.awsstudygroup.com/ <br> **- Credentials Management with AWS Secrets Manager** <br> https://000096.awsstudygroup.com/ |
| **Tue** | **AWS Learning:** <br> - Complete Lab: Cross-Domain Authentication with Amazon Cognito <br> - Complete Lab: Data Protection with AWS Backup <br> - Complete Lab: Network Integration with VPC Peering | 05/05/2026 | 05/05/2026 | **- Cross-Domain Authentication with Amazon Cognito** <br> https://000141.awsstudygroup.com/ <br> **- Data Protection with AWS Backup** <br> https://000013.awsstudygroup.com/ <br> **- Network Integration with VPC Peering** <br> https://000019.awsstudygroup.com/ |
| **Wed** | **AWS Learning:** <br> - Complete Lab: Messaging Systems with SQS and SNS <br> - Complete Lab: Network Monitoring with VPC Flow Logs <br> - Complete Lab: Threat Detection with AWS GuardDuty | 06/05/2026 | 06/05/2026 | **- Messaging Systems with SQS and SNS** <br> https://000077.awsstudygroup.com/ <br> **- Network Monitoring with VPC Flow Logs** <br> https://000074.awsstudygroup.com/ <br> **- Threat Detection with AWS GuardDuty** <br> https://000098.awsstudygroup.com/ |
| **Thu** | **AWS Learning:** <br> - Complete Lab: Cost Visualization and Analytics <br> - Complete Lab: Security Compliance with AWS Security Hub <br> - Complete Lab: Application Protection with AWS WAF <br> **Group Project Execution:** <br> - Project Assignment (Task Pick): <br>&emsp; + Access the AWS Console to create a test Web ACL with basic rules. <br>&emsp; + Configure rules to prevent SQL Injection, XSS, or block malicious IPs. <br>&emsp; + Act as an attacker using Postman to simulate sending malicious payloads in requests to the system. | 07/05/2026 | 07/05/2026 | **- Cost Visualization and Analytics** <br> https://000034.awsstudygroup.com/ <br> **- Security Compliance with AWS Security Hub** <br> https://000018.awsstudygroup.com/ <br> **- Application Protection with AWS WAF** <br> https://000026.awsstudygroup.com/ <br> **- Configuration Testing Document:** <br> https://docs.google.com/document/d/1lOCGsSqTcvzA9FIHvGtMWjFfoimhxlb3ADYyWyX4ov4/edit?usp=sharing |
| **Fri** | **AWS Learning:** <br> - Complete Lab: Data Protection with Amazon Macie <br> - Complete Lab: Single Page Application Authentication <br> - Complete Lab: User Authentication with Amazon Cognito | 08/05/2026 | 08/05/2026 | **- Data Protection with Amazon Macie** <br> https://000090.awsstudygroup.com/ <br> **- Single Page Application Authentication** <br> https://000055.awsstudygroup.com/ <br> **- User Authentication with Amazon Cognito** <br> https://000081.awsstudygroup.com/ |

### Week 3 Achievements:

* Utilized AWS KMS for data-at-rest encryption on Amazon S3; integrated API Keys and Passwords into AWS Secrets Manager for secure, automated rotation.

* Deployed security shield: Successfully configured a Web Application Firewall (Web ACL) to directly protect the API Gateway.

* Completed practical verification (Red/Blue Team): Used Postman to inject payloads containing malicious SQL Injection and XSS code. Result: AWS WAF instantly intercepted all intrusion attempts and returned a 403 Forbidden error right at the network edge. Successfully documented Proof of Concept (PoC) images.


### Week 3 Implementation Evidence: 

#### 1. Initializing Web ACL on AWS WAF

<h4 align="center"><em>Mock API initialization for testing</em></h4>

![Mock API initialization for testing](/mock_api.png)

<h4 align="center"><em>Web ACL initialization</em></h4>

![Web ACL initialization](/waf.png)

#### 2. System Testing with Postman

<h4 align="center"><em>Sending a valid request returns Status: 200 OK</em></h4>

![Sending a valid request returns Status: 200 OK](/200.png)

<h4 align="center"><em>SQL Injection attack test returns Status: 403 Forbidden</em></h4>

![SQL Injection attack test returns Status: 403 Forbidden](/sql_injection.png)

<h4 align="center"><em>XSS attack test returns Status: 403 Forbidden</em></h4>

![XSS attack test returns Status: 403 Forbidden](/xss.png)

<h4 align="center"><em>Path Traversal attack test returns Status: 403 Forbidden</em></h4>

![Path Traversal attack test returns Status: 403 Forbidden](/path_traversal.png)