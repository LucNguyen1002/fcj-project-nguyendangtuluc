---
title: "Week 4 Worklog"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.4. </b> "
---

### Week 4 Objectives:

* Learn about EC2 Auto Scaling for automatic resource scaling.
* Learn about Amazon CloudWatch for system monitoring.
* Learn about Elastic Load Balancing (ELB) for traffic distribution.

### Tasks to be carried out this week:
| Day | Task                                                                                                                                                                                                                                             | Start Date  | Completion Date | Reference Material                        |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------- | --------------- | ----------------------------------------- |
| Mon | - Learn about Elastic Load Balancing (ELB): <br>&emsp; + Application Load Balancer (ALB) <br>&emsp; + Network Load Balancer (NLB) <br>&emsp; + Target Group and Health Check <br>&emsp; + Listener rules                                          | 05/12/2026  | 05/12/2026      | <https://000006.awsstudygroup.com>         |
| Tue | - Learn about EC2 Auto Scaling: <br>&emsp; + Launch Template <br>&emsp; + Auto Scaling Group (ASG) <br>&emsp; + Scaling policies (Target tracking, Step, Simple) <br>&emsp; + Desired, Minimum, Maximum capacity                                    | 05/13/2026  | 05/13/2026      | <https://000006.awsstudygroup.com>         |
| Wed | - **Practice:** <br>&emsp; + Create a Launch Template <br>&emsp; + Create an Application Load Balancer with Target Group <br>&emsp; + Create an Auto Scaling Group attached to ALB <br>&emsp; + Configure scaling policy (Target tracking CPU 70%)    | 05/14/2026  | 05/14/2026      | <https://000006.awsstudygroup.com>         |
| Thu | - Learn about Amazon CloudWatch: <br>&emsp; + Metrics (CPU, Network, Disk...) <br>&emsp; + Alarms and thresholds <br>&emsp; + Dashboards <br>&emsp; + Logs (CloudWatch Logs) <br> - Learn about SNS for notifications                                | 05/15/2026  | 05/15/2026      | <https://000008.awsstudygroup.com>         |
| Fri | - **Practice:** <br>&emsp; + Create CloudWatch Dashboard for EC2 monitoring <br>&emsp; + Create an Alarm when CPU > 80% <br>&emsp; + Configure SNS email alerts <br>&emsp; + Integrate CloudWatch Alarm with Auto Scaling                            | 05/16/2026  | 05/16/2026      | <https://000008.awsstudygroup.com>         |


### Week 4 Achievements:

* Understood Elastic Load Balancing and Load Balancer types:
  * ALB (Layer 7) for HTTP/HTTPS traffic
  * NLB (Layer 4) for TCP/UDP traffic
  * Target Group and Health Check for instance health monitoring

* Mastered EC2 Auto Scaling:
  * Launch Template for instance configuration
  * Auto Scaling Group with desired, min, max capacity
  * Scaling policy types and when to use each
  * Integrating ASG with ALB for automatic instance registration/deregistration

* Successfully completed hands-on practice:
  * Built a complete Auto Scaling system: ALB + Target Group + ASG
  * Configured Target tracking policy (CPU 70%)
  * Verified auto scaling during load increase/decrease

* Understood Amazon CloudWatch:
  * Default metrics and custom metrics
  * Creating Alarms with alert thresholds
  * Dashboards for monitoring data visualization
  * CloudWatch Logs for collecting logs from EC2

* Practiced monitoring and alerting:
  * Created a Dashboard tracking CPU, Network, Disk of EC2
  * Set up Alarms sending email via SNS when CPU exceeds threshold
  * Integrated CloudWatch Alarm with Auto Scaling for automatic scaling

