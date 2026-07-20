---
title: "Worklog Week 7"
date: 2026-06-01
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---

### Objectives for Week 7:

* Establish an application-layer security control (AWS WAF) to directly protect the Application Load Balancer (ALB).
* Eliminate hardcoded sensitive information by implementing centralized secret management with AWS Systems Manager Parameter Store for containers on ECS.
* Conduct dynamic application security testing (DAST) with OWASP ZAP to validate the effectiveness of the firewall.
* Consolidate project data and report progress to the team.

### Tasks to be implemented this week:

| Day | Tasks | Start Date | End Date | Resources |
| --- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| **Mon** | **Group Project Execution:** <br> - Research and initialize Parameter Store: <br>&emsp; + Review AWS Systems Manager Parameter Store configuration documentation for ECS Fargate. <br>&emsp; + Create four sensitive project keys (SPRING_DATASOURCE_PASSWORD, JWT_SECRET, SPRING_MAIL_PASSWORD, GRAFANA_OTLP_TOKEN) as `SecureString` values. | 01/06/2026 | 01/06/2026 | **- Parameter Store Documentation:** <br> https://docs.aws.amazon.com/systems-manager/ <br> **- Parameter Store Implementation Document:** <br> https://docs.google.com/document/d/1ig-ue9NNFZUFrOD_MsCNOFAXimNGalQ8MG9WObW-VBk/edit?usp=sharing |
| **Tue** | **Group Project Execution:** <br> - Set up and configure AWS WAF: <br>&emsp; + Create a Web ACL in the AWS Console. <br>&emsp; + Integrate built-in rule sets: `Core Rule Set`, `SQL database`, and configure `Rate Limiting` (100 requests / 5 minutes). <br>&emsp; + Associate the Web ACL directly with the project's Application Load Balancer (ALB). | 02/06/2026 | 02/06/2026 | **- AWS WAF Documentation:** <br> https://docs.aws.amazon.com/waf/ <br> **- AWS WAF Implementation Document:** <br> https://docs.google.com/document/d/181yLB9Dp5UefwajYwUxg7DctGfgi6Ms5qm8LtJjwIk0/edit?usp=sharing |
| **Wed** | **Group Project Execution:** <br> - Update ECS and troubleshoot issues: <br>&emsp; + Update the task definitions in AWS ECS so the application automatically retrieves keys from Parameter Store at startup (force a new deployment). <br>&emsp; + Review system logs, analyze the "Stopped reason", and resolve task failures caused by missing IAM permissions in the execution role (`ssm:GetParameters`, `kms:Decrypt`). | 03/06/2026 | 03/06/2026 | **- AWS ECS & IAM Documentation:** <br> https://docs.aws.amazon.com/ecs/ |
| **Thu** | **Group Project Execution:** <br> - Conduct dynamic application security testing (DAST) and prepare the report <br>&emsp; + Use OWASP ZAP to perform a comprehensive security scan of the ALB infrastructure. <br>&emsp; + Run two comparison scenarios: WAF enabled and WAF disabled, to verify the defense capability. <br>&emsp; + Extract logs, consolidate findings, and draft the "Security Action Report". | 04/06/2026 | 04/06/2026 | **- OWASP ZAP Documentation:** <br> https://www.zaproxy.org/docs/ <br> **- OWASP ZAP Security Scanning Document:** <br> https://docs.google.com/document/d/1lGwMO8Kvm7h4iTFyOHO4aXp1FeDljdSxksYxDNayHu4/edit?usp=sharing |
| **Fri** | **Team Meeting:** <br> - Review and report progress to the team: <br>&emsp; + Attend the Bootcamp office in person to report project progress. <br>&emsp; + Present and defend the security architecture (WAF and Parameter Store) to obtain approval from the team leader. | 05/06/2026 | 05/06/2026 | |

### Achieved Results for Week 7:

* Initialized and securely stored four core keys in AWS Systems Manager Parameter Store, encrypted with KMS using `SecureString`.

* Successfully configured the foundational protection rule sets: `Core Rule Set`, `SQL database`, and `Rate Limiting` (100 requests / 5 minutes) to mitigate DDoS and API spam.

* Conducted a comprehensive infrastructure security scan using two validation scenarios.

* Verified that WAF operated effectively, blocking 100% of scanning requests. When WAF was disabled, ZAP only reported low- to medium-severity cookie configuration alerts, confirming that the backend source code was resilient against injection vulnerabilities.

* Submitted a complete "Security Action Report" identifying the most critical vulnerabilities, their exploitation points, and remediation guidance for the development team.

### Evidence of Implementation for Week 7:

#### 1. Initializing and storing core keys on AWS

<h4 align="center"><em>Managing 4 core configuration keys on AWS Systems Manager (Parameter Store)</em></h4>

![Managing 4 core configuration keys on AWS Systems Manager (Parameter Store)](/images/1-Worklog/1.7-Week7/ssm.png)

#### 2. Configuring foundational rule sets for the system

<h4 align="center"><em>Deploying and configuring WAF Rule-sets on ALB</em></h4>

![Deploying and configuring WAF Rule-sets on ALB](/images/1-Worklog/1.7-Week7/waf.png)

#### 3. Conducting a scan with OWASP ZAP

<h4 align="center"><em>System security scanning with OWASP ZAP</em></h4>

![System security scanning with OWASP ZAP](/images/1-Worklog/1.7-Week7/zap.png)

#### 4. Team meeting to exchange implementation information

<h4 align="center"><em>Working together at the office for study and project collaboration</em></h4>

![Going to the office for studying and teamwork](/images/1-Worklog/1.7-Week7/0406_meeting_w7.JPG)