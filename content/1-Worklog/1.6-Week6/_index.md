---
title: "Week 6 Worklog"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.6. </b> "
---

### Week 6 Objectives:

* Learn about AWS Lambda and the Serverless model.
* Learn about AWS CloudFormation for Infrastructure as Code (IaC) deployment.
* Learn about Amazon API Gateway to build REST APIs.

### Tasks to be carried out this week:
| Day | Task                                                                                                                                                                                                                                             | Start Date  | Completion Date | Reference Material                        |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------- | --------------- | ----------------------------------------- |
| Mon | - Learn about AWS Lambda: <br>&emsp; + What is Serverless and its benefits <br>&emsp; + Lambda function: runtime, handler, event <br>&emsp; + Triggers: API Gateway, S3, CloudWatch Events <br>&emsp; + Pricing model (pay per request + duration)   | 05/26/2026  | 05/26/2026      | <https://000022.awsstudygroup.com>         |
| Tue | - **Practice Lambda:** <br>&emsp; + Create a Lambda function (Python/Node.js) <br>&emsp; + Configure S3 trigger (process on file upload) <br>&emsp; + View logs on CloudWatch Logs <br>&emsp; + Configure Environment Variables and Timeout         | 05/27/2026  | 05/27/2026      | <https://000022.awsstudygroup.com>         |
| Wed | - Learn about Amazon API Gateway: <br>&emsp; + REST API vs HTTP API <br>&emsp; + Create API endpoint, resource, method <br>&emsp; + Integrate API Gateway with Lambda <br> - **Practice:** Create a simple REST API calling Lambda function          | 05/28/2026  | 05/28/2026      | <https://000066.awsstudygroup.com>         |
| Thu | - Learn about AWS CloudFormation: <br>&emsp; + What is Infrastructure as Code (IaC) <br>&emsp; + Template structure (YAML/JSON) <br>&emsp; + Stack, Resources, Parameters, Outputs <br>&emsp; + Change Sets and Stack Updates                        | 05/29/2026  | 05/29/2026      | <https://000037.awsstudygroup.com>         |
| Fri | - **Practice CloudFormation:** <br>&emsp; + Write a template to create VPC + EC2 <br>&emsp; + Deploy stack from template <br>&emsp; + Update stack with Change Set <br>&emsp; + Delete stack and verify resource cleanup                              | 05/30/2026  | 05/30/2026      | <https://000037.awsstudygroup.com>         |


### Week 6 Achievements:

* Understood the Serverless model and AWS Lambda:
  * No server management, automatic auto-scaling
  * Lambda function with supported runtimes (Python, Node.js, Java...)
  * Event-driven: Lambda triggered by events from multiple sources
  * Pricing: pay only when the function executes

* Successfully practiced Lambda:
  * Created a function to process events when files are uploaded to S3
  * Monitored logs and debugged via CloudWatch Logs
  * Configured environment variables and appropriate timeout

* Mastered Amazon API Gateway:
  * Differentiated REST API and HTTP API
  * Created endpoints, resources, methods (GET, POST...)
  * Combined API Gateway + Lambda to create serverless APIs

* Understood AWS CloudFormation and Infrastructure as Code:
  * Why IaC matters: version control, repeatable, consistent
  * Template structure: AWSTemplateFormatVersion, Description, Parameters, Resources, Outputs
  * Stack lifecycle: Create → Update (Change Set) → Delete
  * Automatic resource cleanup when deleting a stack

* Successfully practiced CloudFormation:
  * Wrote YAML templates to create VPC + Subnet + EC2
  * Deployed and managed stacks via Console
  * Used Change Sets to preview changes before updating
  * Deleted stacks and confirmed all resources were cleaned up

