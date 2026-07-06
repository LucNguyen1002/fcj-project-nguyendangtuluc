---
title: "Translated Blogs"
date: 2024-01-01
weight: 3
chapter: false
pre: " <b> 3. </b> "
---

This section lists and introduces the blog posts translated or rewritten during the internship.

### [Blog 1 - Deploying a Backend to AWS EC2 and the Bug Caused by Capital Letters](3.1-Blog1/)

This blog shares a practical issue when deploying a Node.js backend from a Windows local environment to an AWS EC2 Ubuntu/Linux instance: Boolean values in the `.env` file were interpreted incorrectly because of uppercase and lowercase differences. It explains the root cause, the quick fix by normalizing configuration values, and a more secure direction using AWS Systems Manager Parameter Store or AWS Secrets Manager.

### [Blog 2 - AWS Cost & AI: When Running Cloud Becomes a Cost Management Problem](3.2-Blog2/)

This blog shares the team's experience when AWS cost became an important concern after the backend deployment worked successfully. It focuses on understanding AWS Free Tier correctly, controlling EC2/EBS usage, setting up AWS Budgets, Billing Alarm, Cost Explorer, and testing AI services such as Bedrock, SageMaker, and Comprehend in a sandbox environment to avoid unexpected spending.

### [Blog 3 - Deploying a Serverless Application with AWS Lambda and Amazon API Gateway](3.3-Blog3/)

This blog shares the team's experience learning about serverless architecture on AWS after deploying a backend with EC2. It focuses on how API Gateway, Lambda, DynamoDB, IAM Role, and CloudWatch work together to build REST APIs without direct server management, while also discussing benefits, limitations, cold starts, and cost considerations compared with the traditional EC2 model.
