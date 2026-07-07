---
title: "Worklog Week 10"
date: 2026-06-22
weight: 10
chapter: false
pre: " <b> 1.10. </b> "
---

### Objectives for Week 10:

* Run SonarCloud to scan the source code repository.
* Perform Dynamic Application Security Testing (DAST) using the OWASP ZAP tool.
* Aggregate and classify risk alerts from the scanning process.
* Initialize the WAF firewall system and attach it to the ALB and CloudFront.
* Initialize the secret key store and attach it to ECS for 4 core environment variables.

### Tasks to be implemented this week:

| Day | Tasks | Start Date | End Date | Resources |
| :---: | :--- | :---: | :---: | :--- |
| **Mon** | **Group Project Execution:** <br> - Use the provided AWS account on GitHub to execute the task. <br>- Run SonarCloud to scan the Repo as soon as the source code completion notification is received. | 22/06/2026 | 22/06/2026 | |
| **Tue** | **Group Project Execution:** <br> - Initialize the key store and attach it to ECS. <br>- Set up 4 secure keys: `SPRING_DATASOURCE_PASSWORD` (DB Password), `JWT_SECRET` (Token Signing Key), `SPRING_MAIL_PASSWORD` (Mail Sending Password), and `GRAFANA_OTLP_TOKEN` (University Monitoring Token). | 23/06/2026 | 23/06/2026 |  |
| **Wed** | **Group Project Execution:** <br> - Wait until sufficient information about the ALB and CloudFront links is available to avoid delaying the project schedule. <br>- Initialize WAF and proceed to attach WAF to the ALB and CloudFront. | 24/06/2026 | 24/06/2026 | |
| **Thu** | **Group Project Execution:** <br> - Perform Dynamic Application Security Testing (DAST) using OWASP ZAP. <br>- Conduct detailed OWASP ZAP scans on both Public APIs and token-required APIs. | 25/06/2026 | 25/06/2026 |  |
| **Fri** | **Group Project Execution:** <br> - Create the Vulnerability Report from SonarCloud and OWASP ZAP in Word/PDF format. <br>- Extract the Top most dangerous vulnerabilities. <br>- Present in the mandatory format: Vulnerability Name, Specific Location, Proof of Concept (PoC) via ZAP tool screenshots, and a brief mitigation guide for Devs. | 26/06/2026 | 26/06/2026 | **- SonarCloud Security Reporting Implementation Document:** <br> https://docs.google.com/document/d/1P7uWuUfEtSceGTTazdJHuX-n5w7m9G571ZvFVf6DjBw/edit?usp=sharing <br> **- Vulnerability Scanning Implementation Document:** <br> https://docs.google.com/document/d/1hfYRIkfMq1UDflqW6_HULIm1Ju9E4nrgUyUhC9OMybU/edit?usp=sharing|

### Achieved Results for Week 10:

* Successfully scanned the source code repository using SonarCloud.

* Completed dynamic security testing using OWASP ZAP for both the Public API and token-required API partitions.

* Successfully initialized the WAF firewall and attached it directly to the ALB and CloudFront endpoints.

* Initialized the key store for ECS, ensuring security for 4 important variables: DB password, Token signing key, mail password, and Grafana monitoring token.

### Evidence of Implementation for Week 10: 

#### 1. Initializing WAF firewall attached to ALB

<h4 align="center"><em>AWS WAF is designed to be attached directly to the ALB at the Regional level</em></h4>

![AWS WAF is designed to be attached directly to the ALB at the Regional level](/wafalb.png)

#### 2. Initializing WAF firewall attached to CloudFront

<h4 align="center"><em>AWS WAF is designed to be attached directly to CloudFront at the Global level</em></h4>

![AWS WAF is designed to be attached directly to CloudFront at the Global level](/waf.png)

#### 3. Initializing variables in the Singapore Region

<h4 align="center"><em>Initializing secure variables on Parameter Store in the Singapore Region</em></h4>

![Initializing secure variables on Parameter Store in the Singapore Region](/pssg.png)

#### 4. Initializing variables in the N.Virginia Region

<h4 align="center"><em>Initializing secure variables on Parameter Store in the N.Virginia Region</em></h4>

![Initializing secure variables on Parameter Store in the N.Virginia Region](/psus.png)

#### 5. System scanning results with OWASP ZAP

<h4 align="center"><em>Performing system scan with OWASP ZAP</em></h4>

![Performing system scan with OWASP ZAP](/zap.png)