---
title: "Week 5 Worklog"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.5. </b> "
---

### Week 5 Objectives:

* Learn about Amazon Route 53 for DNS management and traffic routing.
* Learn about AWS CLI for managing AWS resources via command line.
* Combine knowledge from previous weeks to build a complete web architecture.

### Tasks to be carried out this week:
| Day | Task                                                                                                                                                                                                                                             | Start Date  | Completion Date | Reference Material                        |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------- | --------------- | ----------------------------------------- |
| Mon | - Learn about Amazon Route 53: <br>&emsp; + What is DNS and how it works <br>&emsp; + Hosted Zone (Public / Private) <br>&emsp; + Record types: A, AAAA, CNAME, Alias, MX, TXT                                                                    | 05/19/2026  | 05/19/2026      | <https://000010.awsstudygroup.com>         |
| Tue | - Learn about Route 53 Routing Policies: <br>&emsp; + Simple routing <br>&emsp; + Weighted routing <br>&emsp; + Latency-based routing <br>&emsp; + Failover routing <br>&emsp; + Health Checks with Route 53                                       | 05/20/2026  | 05/20/2026      | <https://000010.awsstudygroup.com>         |
| Wed | - Learn about AWS CLI: <br>&emsp; + Install and configure AWS CLI v2 <br>&emsp; + Configure profiles (access key, secret key, region) <br>&emsp; + Basic commands: aws s3, aws ec2, aws iam <br> - Learn about AWS CloudShell                       | 05/21/2026  | 05/21/2026      | <https://000011.awsstudygroup.com>         |
| Thu | - **Practice AWS CLI:** <br>&emsp; + Create and manage S3 buckets via CLI <br>&emsp; + Manage EC2 instances via CLI (describe, start, stop) <br>&emsp; + Manage IAM users via CLI <br>&emsp; + Use AWS CloudShell on the console                     | 05/22/2026  | 05/22/2026      | <https://000011.awsstudygroup.com>         |
| Fri | - **Comprehensive practice:** <br>&emsp; + Register a domain or use existing one <br>&emsp; + Create a Hosted Zone on Route 53 <br>&emsp; + Create records pointing domain to ALB/EC2 <br>&emsp; + Configure Health Check for endpoints              | 05/23/2026  | 05/23/2026      | <https://000010.awsstudygroup.com>         |


### Week 5 Achievements:

* Understood Amazon Route 53 and DNS concepts:
  * Hosted Zone (Public and Private)
  * DNS record types: A, AAAA, CNAME, Alias, MX, TXT
  * AWS Alias record and how it differs from CNAME

* Mastered Routing Policies:
  * Simple: basic routing, one record pointing to one or more IPs
  * Weighted: distributes traffic by percentage
  * Latency-based: routes to the lowest latency endpoint
  * Failover: automatically redirects when primary endpoint fails
  * Health Checks for monitoring endpoint status

* Proficient in AWS CLI v2:
  * Installation, profile configuration with named profiles
  * S3 management: `aws s3 ls`, `aws s3 cp`, `aws s3 sync`, `aws s3 mb`
  * EC2 management: `aws ec2 describe-instances`, `aws ec2 start-instances`, `aws ec2 stop-instances`
  * IAM management: `aws iam list-users`, `aws iam create-user`
  * Using `--output` (json, table, text) and `--query` to filter results

* Learned to use AWS CloudShell for running CLI commands directly on the console without local installation.

* Completed comprehensive practice:
  * Created Hosted Zone and DNS records pointing to ALB
  * Configured Health Checks for endpoints
  * Combined Route 53 + ALB + Auto Scaling + EC2 for a complete web architecture

