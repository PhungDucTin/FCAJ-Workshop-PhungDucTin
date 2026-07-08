---
title: "Worklog Week 8"
date: 2026-06-08
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---

### Objectives for Week 8:

* Advance the dynamic application security testing (DAST) process to a deeper level by performing authenticated scanning and logic vulnerability assessment.
* Focus on reviewing and testing for broken access control (BAC) vulnerabilities and SQL injection attempts that may bypass the WAF.

### Tasks to be implemented this week:

| Day | Tasks | Start Date | End Date | Resources |
| :---: | :--- | :---: | :---: | :--- |
| **Mon** | **Group Project Execution:** <br> - Research and configure advanced OWASP ZAP features: <br>&emsp; + Review the Replacer feature in OWASP ZAP. <br>&emsp; + Configure ZAP to inject a valid JWT token directly into the `Authorization` header (`Bearer <JWT>`), preparing for an authenticated scan. | 08/06/2026 | 08/06/2026 | **- OWASP ZAP Documentation (Replacer):** <br> https://www.zaproxy.org/docs/ |
| **Tue** | **Group Project Execution:** <br> - Test for privilege escalation (BAC and IDOR): <br>&emsp; + Use ZAP's Manual Request Editor. <br>&emsp; + Act as a valid user and intentionally send a `DELETE` request targeting post IDs that belong to other users' accounts to verify the resource authorization logic. | 09/06/2026 | 09/06/2026 | **- OWASP Documentation (BAC):** <br> https://owasp.org/www-community/Broken_Access_Control <br> **- Security Testing Implementation Document:** <br> https://docs.google.com/document/d/1GEyjB94n11W4QRiCeyGlwQj5SbOsCIgL_go_GqllWzA/edit?usp=sharing |
| **Wed** | **Group Project Execution:** <br> - Perform automated scanning through the authentication layer (Active Scan): <br>&emsp; + Trigger an Active Scan directly against the `/api/post/` endpoint for data fuzzing. <br>&emsp; + Simulate insider-attack behavior by sending payloads containing malicious SQL injection, SSRF, and RCE patterns through the input layer to test the WAF and backend. | 10/06/2026 | 10/06/2026 | **- OWASP ZAP Documentation (Active Scan):** <br> https://www.zaproxy.org/docs/ |
| **Thu** | **Group Project Execution:** <br> - Analyze logs, diagnose the system, and prepare the report: <br>&emsp; + Interpret HTTP status codes (400, 403, 500) generated during testing to evaluate the exception handling mechanism. <br>&emsp; + Resolve header conflicts and compile the results into the Phase 2 DAST report. | 11/06/2026 | 11/06/2026 | |
| **Fri** | **Group Meeting:** <br> - Report the results at the FCAJ Bootcamp office: <br>&emsp; + Package the exported ZAP log files (CSV) as proof-of-concept (PoC) evidence. <br>&emsp; + Prepare a visual live demo of two ZAP scenarios: BAC and SQL injection issues for the development team at the FCAJ Bootcamp office. | 12/06/2026 | 12/06/2026 | |


### Achieved Results for Week 8:

* Successfully configured ZAP to act as a valid user interacting through the authentication layer.
* Result: The backend system (Spring Boot) correctly detected the mismatch between the token owner and the resource owner, blocking unauthorized deletion attempts and returning a 403 Forbidden response, which demonstrated that the access control logic was working effectively.
* Successfully set up the Replacer feature to automatically attach the Authorization header for authenticated testing.
* SSRF/RCE prevention: attempts to access cloud metadata or inject execution commands were blocked remotely by AWS WAF and ALB, returning 403 Forbidden responses.
* SQL injection prevention: requests that bypassed the WAF were neutralized by the backend's parameterized query mechanism and rejected with a 400 Bad Request response, effectively preventing malicious payloads from being executed.

### Evidence of Implementation for Week 8:

#### 1. Team meeting at FCAJ Bootcamp

<h4 align="center"><em>Working together at the office for study and team collaboration</em></h4>

![Going to the office for studying and teamwork](/1206_meeting_w9.JPG)

#### 2. Configuring ZAP to execute BAC

<h4 align="center"><em>Checking information to execute BAC</em></h4>

![Checking information to execute BAC](/preview.png)

#### 3. Configuring ZAP to implement Header Authorization

<h4 align="center"><em>Configuring ZAP to attach Header Authorization</em></h4>

![Configuring ZAP to attach Header Authorization](/delete.png)