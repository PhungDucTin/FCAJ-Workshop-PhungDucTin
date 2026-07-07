---
title: "Worklog Week 1"
date: 2026-04-20
weight: 1
chapter: false
pre: " <b> 1.1. </b> "
---

### Objectives for Week 1:

* Learn about, connect, and get acquainted with the members of the First Cloud AI Journey program.
* Understand basic AWS services, how to use the Management Console and CLI, combining theoretical study with hands-on practice.
* Perform a security review (System Audit) for the internal project and propose defense solutions.

### Tasks to be implemented this week:

| Day | Tasks | Start Date | End Date | Resources |
| :---: | :--- | :---: | :---: | :--- |
| **Mon** | **AWS Learning:** <br> - Module 01-01 - Introduction to AWS <br> - Module 01-02 - Management Console <br> - Module 01-03 - Gen AI on AWS - Kiro <br> - Module 01-04 - Cost Optimization on AWS | 20/04/2026 | 20/04/2026 | **- Module 01-01:** <br> https://www.youtube.com/watch?v=qVCF7UjYC5s <br> **- Module 01-02:** <br> https://www.youtube.com/watch?v=95quNuhvMT0 <br> **- Module 01-03:** <br> https://www.youtube.com/watch?v=uAQCm4sm_1c <br> **- Module 01-04:** <br> https://www.youtube.com/watch?v=UIw8UxGZCHA |
| **Tue** | **AWS Learning:** <br> - Understand the 6 Pillars of the AWS Well-Architected Framework: Security, Operational Excellence, Reliability, Performance Efficiency, Cost Optimization, and Sustainability. <br> - Get familiar with the AWS Well-Architected Tool to assess project risks. <br> **Group Project Execution:** <br> - Project Task (Pick Task):<br>&emsp; + Receive the Ngrok link, use tools (Nmap, Nikto, ZAP) to scan the target. <br>&emsp; + Log the attack diary (time, tools used). <br>&emsp; + Create a Risk Report: Top 3 vulnerabilities and propose blocking methods using AWS WAF/Security Group. | 21/04/2026 | 21/04/2026 | **- Attack Diary Document:** <br> https://docs.google.com/document/d/1gIt2LZPLds8ZAZtRbFF6XhKoFawWnP8_fzAp2Bv54CM/edit?usp=sharing <br> **- Risk Report Document:** <br> https://docs.google.com/document/d/1qHgT8dhm1h4-MQoz0GSuyaJ9g12W7GO9haqEEOwCfic/edit?usp=sharing |
| **Wed** | **AWS Learning:** <br> - Complete Lab000001: Creating Your First AWS Account <br> - Complete Lab000009: Getting Help with AWS Support | 22/04/2026 | 22/04/2026 | **- Lab000001:** <br> https://000001.awsstudygroup.com/ <br> **- Lab000009:** <br> https://000009.awsstudygroup.com/ |
| **Thu** | **AWS Learning:** <br> - Complete Lab000007: Managing Costs with AWS Budgets <br> - Complete Lab000180: Kiro Spec Driven Development | 23/04/2026 | 23/04/2026 | **- Lab000007:** <br> https://000007.awsstudygroup.com/ |
| **Fri** | **Group Meeting:** <br> - Exchange information on completed tasks <br> - Report achieved results to the team | 24/04/2026 | 24/04/2026 | |

<br>

### Achieved Results for Week 1:

* Set up a secure account with MFA; strictly applied the Least Privilege principle for the Admins group and IAM Users. Successfully executed the process of opening a Support Case.

* Successfully configured AWS Budgets as an early warning system: set a cost ceiling, enabled instant alerts from $0.01, and monitored EC2 uptime to prevent unauthorized server execution.

* Grasped the 6 pillars of the AWS Well-Architected Framework and the 4 Support tiers.

* Performed manual testing on the application published via Ngrok. Successfully simulated attacks, detected, and logged critical vulnerabilities including SQL Injection, Path Traversal, and XSS attacks into the `security_audit.log` file.
 
### Evidence of Implementation for Week 1: 

#### 1. Scanning Ngrok with Nmap and Nikto 

<h4 align="center"><em>Results after execution</em></h4>

![Results after execution](/nmap_nikto.png)

#### 2. Scanning Ngrok with OWASP ZAP 

<h4 align="center"><em>Results after execution</em></h4>

![Results after execution](/owaspzap.png)

#### 3. Logging vulnerabilities in the `security_audit.log` file

<h4 align="center"><em>Logging vulnerabilities in the file</em></h4>

```json
{"time":"2026-04-20T21:58:02", "level":"WARN", "type":"SECURITY", "msg":"type=SQL_INJECTION ip=42.119.86.124 method=GET uri=/ query=search=%27%20OR%202%3D2%20-- ua=curl/8.18.0"}
{"time":"2026-04-20T21:58:21", "level":"WARN", "type":"SECURITY", "msg":"type=PATH_TRAVERSAL ip=42.119.86.124 method=GET uri=/ query=file=../../../../etc/passwd ua=curl/8.18.0"}
{"time":"2026-04-20T21:58:14", "level":"WARN", "type":"SECURITY", "msg":"type=XSS_ATTACK ip=42.119.86.124 method=GET uri=/ query=username=%3Cscript%3Ealert(1)%3C/script%3E ua=curl/8.18.0"}

#### 4. Meeting Group Online 

<h4 align="center"><em>Group meeting to exchange completed tasks</em></h4>

![Group meeting to exchange completed tasks](/2604_meetingOnl_w1.png)