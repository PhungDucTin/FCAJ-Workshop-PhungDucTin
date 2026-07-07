---
title: "Worklog Week 7"
date: 2026-06-01
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---

### Objectives for Week 7:

* Establish an application-layer security checkpoint (AWS WAF) to directly protect the Application Load Balancer (ALB).
* Completely eliminate the hardcoding of sensitive information, deploying centralized security key management using AWS Systems Manager Parameter Store for Containers on ECS.
* Conduct Dynamic Application Security Testing (DAST) using the OWASP ZAP tool to verify the strength of the firewall.
* Synthesize data and report project progress to the team.

### Tasks to be implemented this week:

| Day | Tasks | Start Date | End Date | Resources |
| --- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| **Mon** | **Group Project Execution:** <br> - Research & Initialize Parameter Store: <br>&emsp; + Research AWS Systems Manager Parameter Store configuration documentation for ECS Fargate. <br>&emsp; + Initialize the project's 4 sensitive keys (SPRING_DATASOURCE_PASSWORD, JWT_SECRET, SPRING_MAIL_PASSWORD, GRAFANA_OTLP_TOKEN) as `SecureString`. | 01/06/2026 | 01/06/2026 | **- Parameter Store Documentation:** <br> https://docs.aws.amazon.com/systems-manager/ <br> **- Parameter Store Implementation Document:** <br> https://docs.google.com/document/d/1ig-ue9NNFZUFrOD_MsCNOFAXimNGalQ8MG9WObW-VBk/edit?usp=sharing |
| **Tue** | **Group Project Execution:** <br> - Setup & Configure AWS WAF: <br>&emsp; + Initialize a Web ACL on the AWS Console interface. <br>&emsp; + Integrate built-in rule sets: `Core rule set`, `SQL database`, and configure `Rate Limiting` (limit of 100 requests/5 minutes). <br>&emsp; + Directly associate the Web ACL with the project's Application Load Balancer (ALB). | 02/06/2026 | 02/06/2026 | **- AWS WAF Documentation:** <br> https://docs.aws.amazon.com/waf/ <br> **- AWS WAF Implementation Document:** <br> https://docs.google.com/document/d/181yLB9Dp5UefwajYwUxg7DctGfgi6Ms5qm8LtJjwIk0/edit?usp=sharing |
| **Wed** | **Group Project Execution:** <br> - Update ECS & Troubleshooting: <br>&emsp; + Update Task Definitions on AWS ECS so the application automatically fetches keys from the Parameter Store upon startup (Force new deployment). <br>&emsp; + Read system logs, analyze "Stopped reason", and troubleshoot Task failure due to missing IAM permissions for the execution role (`ssm:GetParameters`, `kms:Decrypt`). | 03/06/2026 | 03/06/2026 | **- AWS ECS & IAM Documentation:** <br> https://docs.aws.amazon.com/ecs/ |
| **Thu** | **Group Project Execution:** <br> - Dynamic Application Security Testing (DAST) & Reporting <br>&emsp; + Use the OWASP ZAP tool to conduct a comprehensive security scan of the ALB infrastructure. <br>&emsp; + Run 2 comparison scenarios: WAF On and WAF Off to verify defense capabilities. <br>&emsp; + Extract logs, aggregate vulnerabilities, and draft the "Security Action Report". | 04/06/2026 | 04/06/2026 | **- OWASP ZAP Documentation:** <br> https://www.zaproxy.org/docs/ <br> **- OWASP ZAP Security Scanning Document:** <br> https://docs.google.com/document/d/1lGwMO8Kvm7h4iTFyOHO4aXp1FeDljdSxksYxDNayHu4/edit?usp=sharing |
| **Fri** | **Group Meeting:** <br> - Review & Report to the team: <br>&emsp; + Be physically present at the Bootcamp office to report project progress. <br>&emsp; + Present and defend the security architecture (WAF, Parameter Store) to gain task acceptance from the team leader. | 05/06/2026 | 05/06/2026 | |

### Achieved Results for Week 7:

* Initialized and securely stored 4 core keys on AWS Systems Manager Parameter Store, encrypted using KMS (SecureString).

* Successfully configured foundational protection rule sets: `Core Rule Set`, `SQL database`, and established `Rate Limiting` (100 requests / 5 minutes) to prevent DDoS/API Spam.

* Conducted a comprehensive infrastructure security scan with 2 empirical scenarios.

* Proved that WAF operates effectively (blocking 100% of scanning requests). When WAF was turned off, ZAP only detected Low/Medium level alerts regarding Cookie configurations, affirming that the Backend source code is secure against Injection vulnerabilities.

* Submitted a complete "Security Action Report", pinpointing the Top vulnerabilities along with exploitation locations and remediation guidelines for the Dev team.

### Evidence of Implementation for Week 7:

#### 1. Initializing and storing core keys on AWS

<h4 align="center"><em>Managing 4 core configuration keys on AWS Systems Manager (Parameter Store)</em></h4>

![Managing 4 core configuration keys on AWS Systems Manager (Parameter Store)](/ssm.png)

#### 2. Configuring foundational rule sets for the system

<h4 align="center"><em>Deploying and configuring WAF Rule-sets on ALB</em></h4>

![Deploying and configuring WAF Rule-sets on ALB](/waf.png)

#### 3. Conducting a scan with OWASP ZAP

<h4 align="center"><em>System security scanning with OWASP ZAP</em></h4>

![System security scanning with OWASP ZAP](/zap.png)

#### 4. Group meeting to exchange implementation information

<h4 align="center"><em>Going to the office for studying and teamwork</em></h4>

![Going to the office for studying and teamwork](/0406_meeting_w7.JPG)