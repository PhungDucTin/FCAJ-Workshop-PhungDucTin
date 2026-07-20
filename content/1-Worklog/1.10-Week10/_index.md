---
title: "Worklog Week 10"
date: 2026-06-22
weight: 10
chapter: false
pre: " <b> 1.10. </b> "
---

### Objectives for Week 10:

* Run SonarCloud to scan the source code repository.
* Perform dynamic application security testing (DAST) using the OWASP ZAP tool.
* Consolidate and classify the risk alerts identified during the scanning process.
* Initialize the WAF firewall system and attach it to the ALB and CloudFront.
* Initialize the secrets store and connect it to ECS for four core environment variables.

### Tasks to be implemented this week:

| Day | Tasks | Start Date | End Date | Resources |
| :---: | :--- | :---: | :---: | :--- |
| **Mon** | **Group Project Execution:** <br> - Use the provided AWS account from GitHub to carry out the task. <br> - Run SonarCloud to scan the repository as soon as the source code completion notification is received. | 22/06/2026 | 22/06/2026 | |
| **Tue** | **Group Project Execution:** <br> - Initialize the secrets store and connect it to ECS. <br> - Set up four secure keys: `SPRING_DATASOURCE_PASSWORD` (DB password), `JWT_SECRET` (token signing key), `SPRING_MAIL_PASSWORD` (mail sending password), and `GRAFANA_OTLP_TOKEN` (university monitoring token). | 23/06/2026 | 23/06/2026 | |
| **Wed** | **Group Project Execution:** <br> - Wait until the ALB and CloudFront links are available to avoid delaying the project schedule. <br> - Initialize WAF and attach it to the ALB and CloudFront. | 24/06/2026 | 24/06/2026 | |
| **Thu** | **Group Project Execution:** <br> - Perform dynamic application security testing (DAST) using OWASP ZAP. <br> - Conduct detailed OWASP ZAP scans for both public APIs and token-protected APIs. | 25/06/2026 | 25/06/2026 | |
| **Fri** | **Group Project Execution:** <br> - Create the vulnerability report from SonarCloud and OWASP ZAP in Word/PDF format. <br> - Extract the most critical vulnerabilities. <br> - Present them in the required format: vulnerability name, specific location, PoC evidence through ZAP screenshots, and brief mitigation guidance for developers. | 26/06/2026 | 26/06/2026 | **- SonarCloud Security Reporting Implementation Document:** <br> https://docs.google.com/document/d/1P7uWuUfEtSceGTTazdJHuX-n5w7m9G571ZvFVf6DjBw/edit?usp=sharing <br> **- Vulnerability Scanning Implementation Document:** <br> https://docs.google.com/document/d/1hfYRIkfMq1UDflqW6_HULIm1Ju9E4nrgUyUhC9OMybU/edit?usp=sharing |

### Achieved Results for Week 10:

* Successfully scanned the source code repository with SonarCloud.

* Completed dynamic security testing with OWASP ZAP for both the public API and token-protected API endpoints.

* Successfully initialized the WAF firewall and attached it directly to the ALB and CloudFront endpoints.

* Initialized the secrets store for ECS, securing four important variables: the database password, token signing key, mail password, and Grafana monitoring token.

### Evidence of Implementation for Week 10: 

#### 1. Initializing WAF firewall attached to ALB

<h4 align="center"><em>AWS WAF is designed to be attached directly to the ALB at the Regional level</em></h4>

![AWS WAF is designed to be attached directly to the ALB at the Regional level](/images/1-Worklog/1.10-Week10/wafalb.png)

#### 2. Initializing WAF firewall attached to CloudFront

<h4 align="center"><em>AWS WAF is designed to be attached directly to CloudFront at the Global level</em></h4>

![AWS WAF is designed to be attached directly to CloudFront at the Global level](/images/1-Worklog/1.10-Week10/waf.png)

#### 3. Initializing variables in the Singapore Region

<h4 align="center"><em>Initializing secure variables on Parameter Store in the Singapore Region</em></h4>

![Initializing secure variables on Parameter Store in the Singapore Region](/images/1-Worklog/1.10-Week10/pssg.png)

#### 4. Initializing variables in the N.Virginia Region

<h4 align="center"><em>Initializing secure variables on Parameter Store in the N.Virginia Region</em></h4>

![Initializing secure variables on Parameter Store in the N.Virginia Region](/images/1-Worklog/1.10-Week10/psus.png)

#### 5. System scanning results with OWASP ZAP

<h4 align="center"><em>Performing system scan with OWASP ZAP</em></h4>

![Performing system scan with OWASP ZAP](/images/1-Worklog/1.10-Week10/zap.png)