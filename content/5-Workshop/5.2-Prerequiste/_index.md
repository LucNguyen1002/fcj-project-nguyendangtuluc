---
title : "Prerequisites and service deployment"
date : 2024-01-01
weight : 2
chapter : false
pre : " <b> 5.2 </b> "
---

# Prerequisites and service deployment

This section describes the services required before running the stock analysis system. The system uses Yahoo Finance as the market data source, AWS Lambda for ingestion/processing, S3 for raw data and frontend hosting, SQS for asynchronous processing, DynamoDB for reports, Cognito for authentication, and Bedrock for AI analysis.

## AWS account and permissions

Before deployment, prepare:

- An AWS account with permission to create S3, Lambda, SQS, DynamoDB, API Gateway, Cognito, CloudFront, WAF, KMS, Systems Manager Parameter Store, and Bedrock resources.
- A consistent deployment Region for all services.
- Access to the Bedrock model used by the system, such as Claude 3.5 Sonnet.
- API keys or configuration required for Yahoo Finance/finance APIs.

![AWS account information](/images/5-Workshop/5.2-Prerequisite-stock/step-14.png)

## Yahoo Finance API

Yahoo Finance is the main market data source. The system uses it to retrieve open, high, low, close, volume, and historical price data for selected timeframes.

Data from Yahoo Finance is not sent directly to AI. The backend first normalizes the data, stores raw data in S3, and calculates technical indicators before sending processed inputs to Bedrock.

## Backend deployment

### 1. Create the raw data S3 bucket

Create an S3 bucket for raw data, for example:

```text
production-stock-raw-data-finance
```

Amazon S3 stores the original input from Yahoo Finance so the team can inspect, debug, or reprocess data when needed.

![Raw data S3 bucket](/images/5-Workshop/5.2-Prerequisite-stock/step-01.png)

### 2. Create SQS Main Queue and DLQ

Create two queues:

```text
stock-processing-queue
stock-processing-dlq
```

Amazon SQS works as a middle layer between Ingestion Lambda and Processing Lambda. When new data is written to S3, a message is placed in SQS so Processing Lambda can process it later. DLQ stores failed messages for investigation.

![SQS queue list](/images/5-Workshop/5.2-Prerequisite-stock/step-08.png)

### 3. Create Lambda functions

Create two Lambda functions using Node.js 22.x:

```text
production-stock-ingestion
production-stock-processing
```

**Ingestion Lambda** receives stock analysis requests from API Gateway, calls Yahoo Finance to fetch market data, normalizes the data, and stores raw JSON in S3. It then sends a message to SQS to trigger the next processing step.

**Processing Lambda** reads data from S3 using the SQS message, calculates technical indicators such as RSI, MACD, MA20, MA50, and Volume, then sends the calculated indicators to Amazon Bedrock for AI analysis and recommendation generation.

![Lambda functions](/images/5-Workshop/5.2-Prerequisite-stock/step-12.png)

### 4. Configure IAM Role

Lambda needs an IAM Role that can:

- Read/write data in S3.
- Send and receive SQS messages.
- Write logs to CloudWatch.
- Invoke Bedrock models.
- Read secrets/configuration from Systems Manager Parameter Store.
- Write results to DynamoDB.

![IAM role policy](/images/5-Workshop/5.2-Prerequisite-stock/step-06.png)

## Database deployment

### 1. Create AWS KMS key

AWS KMS is used to encrypt data stored in DynamoDB. Analysis data and related information are protected at rest through encryption.

![KMS encryption key](/images/5-Workshop/5.2-Prerequisite-stock/step-07.png)

### 2. Create DynamoDB table

Create the DynamoDB table:

```text
Stock_reports_1
```

Key design:

```text
PK (String)
SK (String)
```

DynamoDB stores final analysis results, including ticker, timeframe, technical indicators, AI recommendation, confidence score, reasoning, and Trader approval status.

![DynamoDB table](/images/5-Workshop/5.2-Prerequisite-stock/step-09.png)

## Frontend deployment

### 1. Create an S3 bucket for static website hosting

Create an S3 bucket for the frontend, for example:

```text
stock-frontend-finance
```

HTML, CSS, JavaScript, and static assets are stored in S3. This approach reduces operating cost because no separate web server is required.

![Frontend S3 origin](/images/5-Workshop/5.2-Prerequisite-stock/step-10.png)

### 2. Create CloudFront distribution and attach WAF

CloudFront distributes the frontend to users with lower latency through Edge Locations. It also supports HTTPS and can integrate with AWS WAF to protect the web application.

AWS WAF is deployed in front of CloudFront to filter malicious requests such as SQL Injection, Cross-Site Scripting, bots, or abnormal request rates.

![CloudFront distribution](/images/5-Workshop/5.2-Prerequisite-stock/step-18.png)

![AWS WAF association](/images/5-Workshop/5.2-Prerequisite-stock/step-05.png)

## Create Cognito User Pool

Amazon Cognito is used to authenticate users who sign in to the Dashboard. Only valid users such as Trader or Admin can view analysis reports and approve/reject recommendations.

![Cognito user pool overview](/images/5-Workshop/5.2-Prerequisite-stock/step-21.png)

![Cognito user list](/images/5-Workshop/5.2-Prerequisite-stock/step-16.png)

## Create API Gateway

API Gateway is the communication layer between the Frontend and Backend. When a user interacts with the Dashboard, the request is sent to API Gateway and then forwarded to the corresponding Lambda function.

Example API:

```text
Ingestion-lambda_API
```

API Gateway needs resources, methods, and Lambda integration configured.

![API Gateway API](/images/5-Workshop/5.2-Prerequisite-stock/step-13.png)

![API Gateway resource](/images/5-Workshop/5.2-Prerequisite-stock/step-15.png)

## Connect Bedrock and request quota

Amazon Bedrock is used to analyze technical data calculated by the backend. Bedrock does not directly fetch market data and does not use news. It only receives indicators such as RSI, MACD, MA, and stock price to generate recommendations such as **STRONG BUY**, **STRONG SELL**, or **WATCH**, together with confidence score and reasoning.

Make sure the account has model access and enough request quota for testing.

![Bedrock model access](/images/5-Workshop/5.2-Prerequisite-stock/step-03.png)

![Bedrock quota](/images/5-Workshop/5.2-Prerequisite-stock/step-04.png)

## Overall deployment view

After completing the steps above, the system has the main components needed to run the pipeline from Dashboard to Backend, AI Analysis, and Database.

![Deployment architecture](/images/5-Workshop/5.2-Prerequisite-stock/step-11.png)
