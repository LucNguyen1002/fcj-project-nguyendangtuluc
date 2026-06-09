---
title: "Week 2 Worklog"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.2. </b> "
---

### Week 2 Objectives:

* Learn about Amazon VPC (Virtual Private Cloud) and basic networking components.
* Learn about Amazon EC2 (Elastic Compute Cloud) and practice creating EC2 instances.
* Understand how to SSH into EC2 and manage Security Groups.

### Tasks to be carried out this week:
| Day | Task                                                                                                                                                                                                                                                | Start Date  | Completion Date | Reference Material                        |
| --- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------- | --------------- | ----------------------------------------- |
| Mon | - Learn about Amazon VPC: <br>&emsp; + What is VPC and why it's needed <br>&emsp; + Subnet (Public / Private) <br>&emsp; + Internet Gateway <br>&emsp; + Route Table <br> - Learn about CIDR block and IP addressing                                  | 04/28/2026  | 04/28/2026      | <https://000003.awsstudygroup.com>         |
| Tue | - Learn more about VPC: <br>&emsp; + NAT Gateway <br>&emsp; + Security Group vs Network ACL <br>&emsp; + Elastic IP <br> - **Practice:** <br>&emsp; + Create VPC with public and private subnets <br>&emsp; + Configure Internet Gateway and Route Table | 04/29/2026  | 04/29/2026      | <https://000003.awsstudygroup.com>         |
| Wed | - Learn basic Amazon EC2: <br>&emsp; + Instance types (t2.micro, t3.micro...) <br>&emsp; + AMI (Amazon Machine Image) <br>&emsp; + Instance lifecycle (Start, Stop, Terminate) <br>&emsp; + Key Pair for SSH                                          | 04/30/2026  | 04/30/2026      | <https://000004.awsstudygroup.com>         |
| Thu | - Learn about EBS (Elastic Block Store): <br>&emsp; + EBS volume types (gp2, gp3, io1...) <br>&emsp; + Snapshot <br> - Learn about Security Groups: <br>&emsp; + Inbound / Outbound rules <br>&emsp; + Allow SSH (port 22), HTTP (port 80)              | 05/01/2026  | 05/01/2026      | <https://000004.awsstudygroup.com>         |
| Fri | - **Practice:** <br>&emsp; + Launch EC2 instance (Amazon Linux 2, t2.micro) <br>&emsp; + Configure Security Group for SSH and HTTP <br>&emsp; + Connect via SSH to EC2 <br>&emsp; + Attach an additional EBS volume <br>&emsp; + Assign Elastic IP to EC2 | 05/02/2026  | 05/02/2026      | <https://000004.awsstudygroup.com>         |


### Week 2 Achievements:

* Understood Amazon VPC and basic networking components:
  * VPC, Subnet (Public/Private)
  * Internet Gateway, NAT Gateway
  * Route Table
  * CIDR block and IP addressing

* Differentiated between Security Group and Network ACL:
  * Security Group: stateful, applied at instance level
  * Network ACL: stateless, applied at subnet level

* Successfully practiced creating a complete VPC with public and private subnets, configured Internet Gateway and Route Table.

* Understood fundamental Amazon EC2 concepts:
  * Instance types and how to choose the right one
  * AMI and its usage
  * Instance lifecycle
  * Key Pair for SSH access

* Learned about EBS (Elastic Block Store):
  * Volume types and use cases
  * Creating and managing Snapshots

* Successfully completed hands-on practice:
  * Launched an EC2 instance (Amazon Linux 2, t2.micro) in VPC
  * Configured Security Group for SSH and HTTP
  * Connected via SSH to EC2 from local machine
  * Attached an additional EBS volume to the instance
  * Assigned Elastic IP to the EC2 instance

