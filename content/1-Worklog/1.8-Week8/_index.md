---
title: "Worklog Week 8"
date: 2026-06-08
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---

### Objectives for Week 8:

* Elevate the Dynamic Application Security Testing (DAST) process to an advanced level: Authenticated Scan and Logic Vulnerability Assessment.
* Focus on reviewing and testing for Broken Access Control (BAC) vulnerabilities or SQLi attempts that bypass the WAF.

### Tasks to be implemented this week:

| Day | Tasks | Start Date | End Date | Resources |
| :---: | :--- | :---: | :---: | :--- |
| **Mon** | **Group Project Execution:** <br> - Research & Configure Advanced OWASP ZAP: <br>&emsp; + Research the Replacer feature on OWASP ZAP. <br>&emsp; + Configure ZAP to inject a valid JWT Token directly into the Header (`Authorization: Bearer <JWT>`), preparing for the authenticated scan. | 08/06/2026 | 08/06/2026 | **- OWASP ZAP Documentation (Replacer):** <br> https://www.zaproxy.org/docs/ |
| **Tue** | **Group Project Execution:** <br> - Privilege Escalation Testing (BAC & IDOR): <br>&emsp; + Utilize ZAP's Manual Request Editor feature. <br>&emsp; + Act as a valid user, intentionally issuing a `DELETE` command targeting post IDs belonging to other users' accounts to test the resource authorization logic. | 09/06/2026 | 09/06/2026 | **- OWASP Documentation (BAC):** <br> https://owasp.org/Top10/A01/ <br> **- Security Testing Implementation Document:** <br> https://docs.google.com/document/d/1GEyjB94n11W4QRiCeyGlwQj5SbOsCIgL_go_GqllWzA/edit?usp=sharing|
| **Wed** | **Group Project Execution:** <br> - Automated Scanning through the Auth Layer (Active Scan): <br>&emsp; + Trigger an Active Scan aimed directly at the `/api/post/` endpoint for data fuzzing. <br>&emsp; + Simulate an insider attack behavior, carpet-bombing payloads containing malicious SQLi, SSRF/RCE code through the input authentication layer to test the WAF and Backend. | 10/06/2026 | 10/06/2026 | **- OWASP ZAP Documentation (Active Scan):** <br> https://www.zaproxy.org/docs/ |
| **Thu** | **Group Project Execution:** <br> - Log Analysis, System Diagnostics & Reporting: <br>&emsp; + Interpret HTTP status codes (400, 403, 500) generated during testing to evaluate the Exception Handling mechanism. <br>&emsp; + Resolve Header conflicts and compile data into the Phase 2 DAST Report. | 11/06/2026 | 11/06/2026 | |
| **Fri** | **Group Meeting:** <br> - Report results at the FCAJ Bootcamp office: <br>&emsp; + Package the exported log files from ZAP (CSV) as Proof of Concept (PoC) evidence. <br>&emsp; + Build a visual presentation flow (Live Demo) for 2 ZAP scenarios: BAC and SQLi errors in front of the development team at the FCAJ Bootcamp office. | 12/06/2026 | 12/06/2026 | |


### Achieved Results for Week 8:

* Successfully configured ZAP to act as a valid user penetrating the Authentication layer.
* Result: The Backend system (Spring Boot) accurately identified the mismatch between the Token owner and the resource owner, blocking unauthorized data deletion attempts (returning a 403 Forbidden code), proving that the security logic operates perfectly.
* Successfully set up the Replacer feature to automatically attach the Authorization Header to fire payloads through the authentication layer.
* SSRF/RCE Prevention: Attempts to access cloud metadata or inject execution commands were blocked remotely by AWS WAF and ALB (403 Forbidden).
* SQL Injection Prevention: Requests that bypassed the WAF were neutralized by the Backend's Parameterized Queries mechanism, refusing to process them (returning a 400 Bad Request), completely eliminating the risk of malicious payload leakage.

### Evidence of Implementation for Week 8:

#### 1. Group meeting at FCAJ Bootcamp

<h4 align="center"><em>Going to the office for studying and teamwork</em></h4>

![Going to the office for studying and teamwork](/1206_meeting_w9.JPG)

#### 2. Configuring ZAP to execute BAC

<h4 align="center"><em>Checking information to execute BAC</em></h4>

![Checking information to execute BAC](/preview.png)

#### 3. Configuring ZAP to implement Header Authorization

<h4 align="center"><em>Configuring ZAP to attach Header Authorization</em></h4>

![Configuring ZAP to attach Header Authorization](/delete.png)