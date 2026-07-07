---
title: "Worklog Week 11"
date: 2026-06-29
weight: 11
chapter: false
pre: " <b> 1.11. </b> "
---

### Objectives for Week 11:

* Handle false positives on the AWS WAF Console.
* Fine-tune the Scope-Down Statement for the Rate Limiting function.
* Test flow 1 with Rule Action = "Count" for regular users.
* Test flow 2 with Rule Action = "Block" for simulated DDoS/API traffic using K6.
* Conduct cross-checking and finalize the Hugo Server along with the internship report.

### Tasks to be implemented this week:

| Day | Tasks | Start Date | End Date | Resources |
| --- | --------- | ------------ | --------------- | -------------- |
| **Mon** | **Group Project Execution:** <br> - Review false positives on the AWS WAF Console. <br> - Differentiate valid traffic from suspicious requests. <br> - Adjust rule logic and prepare initial optimization plans. | 29/06/2026 | 29/06/2026 | |
| **Tue** | **Group Project Execution:** <br> - Fine-tune the Scope-Down Statement for Rate Limiting. <br> - Add conditions to reduce the false blocking of normal user traffic. <br> - Document optimized logic and expected behaviors. | 30/06/2026 | 30/06/2026 | |
| **Wed** | **Group Project Execution:** <br> - Switch Rule Action to "Count". <br> - Run tests using K6 for flow 1 (regular users). <br> - Observe request behavior, WAF logs, and alerts without blocking traffic. | 01/07/2026 | 01/07/2026 | |
| **Thu** | **Group Project Execution:** <br> - Switch Rule Action to "Block". <br> - Run tests using K6 for flow 2 (simulated DDoS/API attack). <br> - Verify that malicious traffic is effectively blocked and protection logic functions properly. | 02/07/2026 | 02/07/2026 | |
| **Fri** | **Group Meeting:** <br> - Perform cross-checking with team members. <br> - Finalize content on the Hugo Server and ensure report consistency. <br> - Complete the internship report and related documentation. | 03/07/2026 | 03/07/2026 | |


### Achieved Results for Week 11:

* Fine-tuned the Scope-Down Statement for Rate Limiting to reduce the likelihood of falsely blocking valid user traffic.

* Conducted tests in "Count" mode for flow 1 and confirmed that the monitoring logic operates correctly for regular user traffic.

* Conducted tests in "Block" mode for flow 2 using K6 and confirmed that DDoS/API traffic is effectively blocked.

### Evidence of Implementation for Week 11:

#### 1. Fine-tuning the Block-DDoS-Login Rule to reduce false blocking

<h4 align="center"><em>Implementing Web ACL setup with 4 Rules on ALB for the system</em></h4>

![Implementing Web ACL setup with 4 Rule Groups on ALB for the system](/ruleset.png)

<h4 align="center"><em>Configuring Rate-Limit parameters to prevent DDoS</em></h4>

![Configuring Rate-Limit parameters to prevent DDoS](/config1.png)

![Configuring Rate-Limit parameters to prevent DDoS](/config2.png)

#### 2. Flow 1 test results using K6

<h4 align="center"><em>Dashboard showing WAF allowing valid traffic into the system</em></h4>

![Dashboard showing WAF allowing valid traffic into the system](/k6_flow1.png)

![Dashboard showing WAF allowing valid traffic into the system](/k6_flow1_1.png)

#### 3. Flow 2 test results using K6

<h4 align="center"><em>Dashboard showing WAF blocking DDoS attacks on the system</em></h4>

![Dashboard showing WAF blocking DDoS attacks on the system](/k6_flow2.png)

![Dashboard showing WAF blocking DDoS attacks on the system](/k6_flow2_1.png)

#### 4. Group meeting to exchange information 

<h4 align="center"><em>Group meeting to exchange completed tasks</em></h4>

![Group meeting to exchange completed tasks](/307_meeting_w11.JPG)