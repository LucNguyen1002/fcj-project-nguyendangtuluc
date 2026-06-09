---
title: "Week 7 Worklog"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.7. </b> "
---

### Week 7 Objectives:

* Learn about Amazon DynamoDB – NoSQL database on AWS.
* Learn about Amazon CloudFront – CDN service for global content delivery.
* Practice combining serverless services learned so far.

### Tasks to be carried out this week:
| Day | Task                                                                                                                                                                                                                                             | Start Date  | Completion Date | Reference Material                        |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------- | --------------- | ----------------------------------------- |
| Mon | - Learn about Amazon DynamoDB: <br>&emsp; + NoSQL vs SQL, when to use DynamoDB <br>&emsp; + Table, Item, Attribute <br>&emsp; + Partition Key and Sort Key <br>&emsp; + Read/Write Capacity (On-Demand vs Provisioned)                              | 06/02/2026  | 06/02/2026      | <https://000060.awsstudygroup.com>         |
| Tue | - Learn more about DynamoDB: <br>&emsp; + Secondary Indexes (GSI, LSI) <br>&emsp; + DynamoDB Streams <br>&emsp; + TTL (Time to Live) <br> - **Practice:** <br>&emsp; + Create a DynamoDB table <br>&emsp; + CRUD operations via Console and CLI      | 06/03/2026  | 06/03/2026      | <https://000060.awsstudygroup.com>         |
| Wed | - Learn about Amazon CloudFront: <br>&emsp; + What is CDN and how it works <br>&emsp; + Edge Locations and Points of Presence <br>&emsp; + Origin types (S3, ALB, Custom) <br>&emsp; + Cache behaviors and TTL                                      | 06/04/2026  | 06/04/2026      | <https://000094.awsstudygroup.com>         |
| Thu | - Learn more about CloudFront: <br>&emsp; + Origin Access Control (OAC) for S3 <br>&emsp; + SSL/TLS with AWS Certificate Manager <br>&emsp; + Invalidation for cache clearing <br>&emsp; + Geo Restriction                                          | 06/05/2026  | 06/05/2026      | <https://000094.awsstudygroup.com>         |
| Fri | - **Comprehensive practice:** <br>&emsp; + Create S3 static website + CloudFront distribution <br>&emsp; + Configure OAC to allow access only via CloudFront <br>&emsp; + Build serverless API: API Gateway + Lambda + DynamoDB                       | 06/06/2026  | 06/06/2026      | <https://000094.awsstudygroup.com>         |


### Week 7 Achievements:

* Understood Amazon DynamoDB and NoSQL databases:
  * Differentiated NoSQL and SQL, knowing when to use DynamoDB
  * Table design: Partition Key, Sort Key
  * Capacity modes: On-Demand (flexible) vs Provisioned (cost-effective)
  * Secondary Indexes: GSI for flexible queries, LSI for alternative sort keys

* Successfully practiced DynamoDB:
  * Created tables with Partition Key and Sort Key
  * Performed CRUD (Create, Read, Update, Delete) via Console and CLI
  * Used Query and Scan for data retrieval

* Understood Amazon CloudFront and CDN:
  * How CDN works: Edge Locations cache content close to users
  * Supported origin types
  * Cache behaviors: path pattern, TTL, viewer protocol policy
  * Origin Access Control (OAC) to protect S3 origins

* Mastered CloudFront security features:
  * OAC replacing OAI for S3 access control
  * Free SSL/TLS via ACM
  * Geo Restriction to limit access by country
  * Cache Invalidation to clear cache when content updates

* Successfully completed comprehensive practice:
  * Created S3 static website + CloudFront distribution with OAC
  * Website only accessible via CloudFront, not directly from S3
  * Built a complete serverless API: API Gateway → Lambda → DynamoDB

