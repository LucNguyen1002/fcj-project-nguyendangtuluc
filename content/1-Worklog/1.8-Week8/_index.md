---
title: "Week 8 Worklog"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.8. </b> "
---

### Week 8 Objectives:

* Learn about basic security services on AWS.
* Understand how to protect web applications with AWS WAF.
* Learn about encryption management with KMS and credential management with Secrets Manager.

### Tasks to be carried out this week:
| Day | Task                                                                                                                                                                                                                                             | Start Date  | Completion Date | Reference Material                        |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------- | --------------- | ----------------------------------------- |
| Mon | - Learn about AWS WAF (Web Application Firewall): <br>&emsp; + What is WAF and why it's needed <br>&emsp; + Web ACL, Rules, Rule Groups <br>&emsp; + AWS Managed Rules <br>&emsp; + Integrating WAF with CloudFront and ALB                        | 06/09/2026  | 06/09/2026      | <https://000026.awsstudygroup.com>         |
| Tue | - **Practice WAF:** <br>&emsp; + Create a Web ACL <br>&emsp; + Add AWS Managed Rules (SQL injection, XSS) <br>&emsp; + Attach WAF to CloudFront distribution <br>&emsp; + Test blocking malicious requests                                         | 06/10/2026  | 06/10/2026      | <https://000026.awsstudygroup.com>         |
| Wed | - Learn about AWS KMS (Key Management Service): <br>&emsp; + Symmetric and asymmetric encryption <br>&emsp; + Customer Managed Key (CMK) <br>&emsp; + Encrypting S3, EBS, RDS with KMS <br>&emsp; + Automatic key rotation                          | 06/11/2026  | 06/11/2026      | <https://000033.awsstudygroup.com>         |
| Thu | - Learn about AWS Secrets Manager: <br>&emsp; + Storing database credentials and API keys securely <br>&emsp; + Automatic rotation <br>&emsp; + Retrieving secrets from Lambda/EC2 <br> - Learn about AWS Systems Manager Parameter Store             | 06/12/2026  | 06/12/2026      | <https://000096.awsstudygroup.com>         |
| Fri | - **Comprehensive security practice:** <br>&emsp; + Encrypt S3 bucket with KMS key <br>&emsp; + Store RDS credentials in Secrets Manager <br>&emsp; + Create Lambda function to read secrets from Secrets Manager <br>&emsp; + Review AWS Security Best Practices | 06/13/2026  | 06/13/2026      | <https://000069.awsstudygroup.com>         |


### Week 8 Achievements:

* Understood AWS WAF and web application protection:
  * Web ACL with rules blocking common attacks
  * AWS Managed Rules for quick deployment without manual rule writing
  * Combining WAF with CloudFront/ALB for front-line protection

* Mastered AWS KMS and data encryption:
  * Differentiated symmetric and asymmetric encryption
  * Created and managed Customer Managed Keys
  * Encrypted data at rest for S3, EBS, RDS
  * Automatic key rotation for enhanced security

* Understood AWS Secrets Manager:
  * Secure credential storage instead of hardcoding in source code
  * Automatic rotation for database passwords
  * Retrieving secrets via SDK in Lambda/EC2

* Completed comprehensive security practice:
  * Encrypted S3 bucket using KMS key
  * Stored and retrieved RDS credentials from Secrets Manager
  * Lambda function connecting to RDS via Secrets Manager
  * Grasped AWS Security Best Practices

