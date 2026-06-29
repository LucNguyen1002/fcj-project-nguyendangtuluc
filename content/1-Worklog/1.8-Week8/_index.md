---
title: "Week 8 Worklog"
date: 2026-06-05
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---

### Week 8 Objectives:

* Learn about the relational database service Amazon RDS.
* Understand the concepts of database engines, DB instances, DB Parameter Groups, and Subnet Groups.
* Create a DB instance (MySQL) and configure connection from an EC2 instance.

### Tasks carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| Mon | - Learn theoretical concepts of Amazon RDS and supported DB engines <br>- Compare self-managed databases on EC2 instances with fully-managed AWS RDS database instances | 06/01/2026 | 06/01/2026 | <https://000013.awsstudygroup.com> |
| Tue | - Set up DB Subnet Groups for RDS (combining private subnets across multiple Availability Zones for High Availability) <br>- Configure Security Group for RDS to authorize incoming connections from the EC2 Web Server | 06/02/2026 | 06/02/2026 | <https://000013.awsstudygroup.com> |
| Wed | - Initialize a MySQL DB Instance using the Free Tier package <br>- Learn about database storage options, automatic backup features, and Multi-AZ deployments | 06/03/2026 | 06/03/2026 | <https://000013.awsstudygroup.com> |
| Thu | - Import sample database schemas and configure remote connection from the EC2 instance in the Public Subnet to the RDS instance in the Private Subnet <br>- Verify secure connection and test queries | 06/04/2026 | 06/04/2026 | <https://000013.awsstudygroup.com> |
| Fri | - Test database backups and restore mechanisms on RDS instances <br>- Measure connectivity performance and compile Week 8 worklog | 06/05/2026 | 06/05/2026 | <https://000013.awsstudygroup.com> |

### Week 8 Achievements:

* Acquired deep understanding of Amazon RDS benefits compared to setting up a database on an EC2 instance.
* Successfully launched a MySQL database running on Amazon RDS inside private subnets with strict Security Groups.
* Successfully connected and performed database queries from an application hosted on an EC2 instance.
* Mastered automatic backups and manual database snapshots on Amazon RDS.

