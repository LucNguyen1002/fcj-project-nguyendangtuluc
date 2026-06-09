---
title: "Week 3 Worklog"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.3. </b> "
---

### Week 3 Objectives:

* Learn about Amazon S3 (Simple Storage Service) and basic storage features.
* Practice hosting a static website on S3.
* Learn about Amazon RDS (Relational Database Service) and practice creating a database.

### Tasks to be carried out this week:
| Day | Task                                                                                                                                                                                                                                              | Start Date  | Completion Date | Reference Material                        |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------- | --------------- | ----------------------------------------- |
| Mon | - Learn about Amazon S3: <br>&emsp; + What is S3, common use cases <br>&emsp; + Bucket and Object <br>&emsp; + Storage classes (Standard, IA, Glacier...) <br>&emsp; + Versioning                                                                  | 05/05/2026  | 05/05/2026      | <https://000057.awsstudygroup.com>         |
| Tue | - Learn more about S3: <br>&emsp; + Bucket Policy and ACL <br>&emsp; + Static Website Hosting <br>&emsp; + Lifecycle rules <br> - **Practice:** <br>&emsp; + Create an S3 bucket <br>&emsp; + Upload files and manage objects <br>&emsp; + Enable Versioning | 05/06/2026  | 05/06/2026      | <https://000057.awsstudygroup.com>         |
| Wed | - **Practice hosting a static website on S3:** <br>&emsp; + Create a bucket for static website <br>&emsp; + Configure Bucket Policy for public access <br>&emsp; + Upload HTML/CSS files <br>&emsp; + Access the website via S3 endpoint             | 05/07/2026  | 05/07/2026      | <https://000057.awsstudygroup.com>         |
| Thu | - Learn about Amazon RDS: <br>&emsp; + What is RDS and supported database engines (MySQL, PostgreSQL, Aurora...) <br>&emsp; + Multi-AZ deployment <br>&emsp; + Read Replica <br>&emsp; + Automated Backup and Snapshot                               | 05/08/2026  | 05/08/2026      | <https://000005.awsstudygroup.com>         |
| Fri | - **Practice:** <br>&emsp; + Create an RDS instance (MySQL, db.t3.micro) <br>&emsp; + Configure Security Group for RDS <br>&emsp; + Connect from EC2 to RDS <br>&emsp; + Create a database and run basic queries                                     | 05/09/2026  | 05/09/2026      | <https://000005.awsstudygroup.com>         |


### Week 3 Achievements:

* Understood Amazon S3 and storage concepts:
  * Bucket, Object and data organization
  * Storage classes and when to use each
  * Versioning for file version management
  * Lifecycle rules for automatic storage class transitions

* Learned S3 access management:
  * Bucket Policy (JSON-based)
  * ACL (Access Control List)
  * Block Public Access settings

* Successfully practiced hosting a static website on S3:
  * Created a bucket, configured static website hosting
  * Wrote a Bucket Policy for public read access
  * Uploaded HTML/CSS and accessed the website via S3 endpoint

* Understood Amazon RDS and its features:
  * Supported database engines
  * Multi-AZ for high availability
  * Read Replica for read scaling
  * Automated Backup and manual Snapshot

* Successfully completed hands-on practice:
  * Created an RDS instance MySQL (db.t3.micro) in VPC
  * Configured Security Group to allow connections from EC2
  * Connected from EC2 instance to RDS and ran basic queries

