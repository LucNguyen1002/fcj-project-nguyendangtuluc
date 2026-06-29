---
title: "Week 9 Worklog"
date: 2026-06-12
weight: 9
chapter: false
pre: " <b> 1.9. </b> "
---

### Week 9 Objectives:

* Successfully integrate three core services: Amazon EC2, Amazon S3, and Amazon RDS into a complete 3-tier web architecture.
* Establish secure IAM Roles and IAM Instance Profiles for EC2 to access S3 securely without exposing hardcoded access keys.
* Deploy web application source code to EC2 and connect it to RDS and S3.

### Tasks carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| Mon | - Configure network routing and Security Groups: Align Web Security Group to accept public traffic and RDS Security Group to only allow MySQL connections from the Web Security Group | 06/08/2026 | 06/08/2026 | Network Architecture Diagram |
| Tue | - Create an IAM Role with AmazonS3FullAccess policies (or bucket-specific permissions) <br>- Attach this IAM Role to the EC2 Web Server instance as an IAM Instance Profile | 06/09/2026 | 06/09/2026 | [AWS IAM Roles for EC2](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/iam-roles-for-null.html) |
| Wed | - Deploy web application source code on the EC2 server <br>- Configure DB connection strings pointing to the RDS endpoint in the configuration files | 06/10/2026 | 06/10/2026 | Deployment Manual |
| Thu | - Configure application code to utilize AWS SDK to upload uploaded media files directly to the S3 Bucket instead of local disk storage | 06/11/2026 | 06/11/2026 | [AWS SDK for Python/Node.js](https://aws.amazon.com/developer/tools/) |
| Fri | - Perform end-to-end integration testing: Create accounts, upload images, verify database records in RDS and image hosting in S3 <br>- Compile Week 9 worklog | 06/12/2026 | 06/12/2026 | Internship Log |

### Week 9 Achievements:

* Successfully built and deployed a fully integrated 3-tier system consisting of EC2, S3, and RDS.
* Applied security best practices by utilizing IAM Roles instead of storing static AWS credentials inside the application source code.
* Segregated static data (S3) and dynamic data (RDS) to optimize system performance and reduce EC2 disk usage.
* Successfully resolved port connection issues between the web tier and DB tier through Security Group rule refinement.

