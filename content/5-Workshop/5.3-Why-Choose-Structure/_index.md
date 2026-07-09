---
title : "Why this architecture was chosen"
date : 2024-01-01
weight : 3
chapter : false
pre : " <b> 5.3 </b> "
---

# Why choose this architecture?

The architecture was selected based on four main criteria: **low cost**, **deployment simplicity**, **Managed Service/Serverless usage**, and **good scalability**.

## 1. Low cost

Services such as Lambda, S3, SQS, DynamoDB, API Gateway, and CloudFront follow a pay-as-you-go model. The system does not require a continuously running server, so the initial cost is low and suitable for a student project.

Examples:

- Lambda incurs cost only when there are requests or events.
- SQS is charged based on the number of messages.
- DynamoDB is charged based on storage and read/write usage.
- S3 is charged based on storage capacity.
- CloudFront reduces load on S3 and improves frontend access speed.

Compared with running an EC2 instance 24/7, the serverless model helps reduce cost when the system does not yet have many users or stable workload.

## 2. Simplicity and Serverless

The project uses Serverless architecture to reduce operational workload. Instead of configuring servers, installing runtimes, managing scaling, updating operating systems, and monitoring resources manually, the team uses serverless services:

- **AWS Lambda** for backend logic.
- **API Gateway** for APIs.
- **S3** for data storage and static frontend hosting.
- **SQS** for queue-based processing.
- **DynamoDB** for analysis reports.

As a result, the team can focus on the main business flow: collecting stock data, calculating technical indicators, calling Amazon Bedrock, and building the Trader approval workflow.

## 3. Managed Service

Most services in the model are Managed Services, meaning AWS operates the underlying infrastructure. This improves stability and reduces operational risk.

Examples:

- **Amazon Bedrock** provides AI integration without self-hosting machine learning models.
- **DynamoDB** provides high-performance NoSQL storage without database server management.
- **Amazon SQS** decouples processing steps without building a custom message queue.
- **AWS KMS** manages encryption keys without building a custom encryption system.
- **Amazon Cognito** supports user authentication for the Dashboard.

## 4. Scalability

The model scales well because components are separated by responsibility. When the number of tickers or users increases, each part can scale independently without affecting the whole architecture.

Examples:

- If many users send analysis requests at the same time, API Gateway and Lambda can process requests in parallel.
- If data volume grows quickly, SQS queues messages so Processing Lambda can handle them gradually and avoid overload.
- If more reports need to be stored, DynamoDB and S3 can scale with storage and traffic.
- If many users access the Dashboard, CloudFront distributes the frontend faster and reduces load on S3.
- If stronger protection is needed, AWS WAF rules can be added to block malicious requests.

## Future improvements

### 1. Expand data sources

The current system uses Yahoo Finance. In the future, additional data sources can be added to cross-check prices, improve reliability, and support near-real-time data.

### 2. Improve AI analysis

Amazon Bedrock currently analyzes technical indicators. More indicators such as Bollinger Bands, Stochastic, ADX, or ATR can be added to provide richer input for AI.

### 3. Add real-time alerts

The system can alert when stock price crosses a threshold, RSI reaches overbought/oversold zones, or MACD reverses. Important signals can be sent to Traders or customers.

### 4. Improve user management

Roles can be separated more clearly among Admin, Trader, and Customer. For example, Admin manages users, Trader approves recommendations, and Customer receives reports or views recommendation history.

### 5. Strengthen security

The system can add CloudWatch Alarm, advanced AWS WAF rules, request limits by IP, CloudTrail audit logs, and KMS encryption for sensitive data.

### 6. Optimize cost and performance

The team can monitor cost through AWS Cost Explorer, optimize Bedrock calls, reduce input tokens, cache stock data, and tune Lambda timeout/memory to reduce operating cost.

### 7. Improve the Dashboard

The Dashboard can be enhanced with better charts, filters by ticker, approval status, confidence score, timeframe, and previous analysis history.

### 8. Add CI/CD

Future versions can use GitHub Actions or AWS CodePipeline to automatically build, test, and deploy frontend/backend changes.

### 9. Expand scaling capability

As ticker count and users grow, the system can optimize batch processing, increase Lambda concurrency, configure SQS DLQ, and define retry policies clearly.

### 10. Add recommendation accuracy tracking

After the system generates a recommendation, actual stock movement can be recorded after a period of time to evaluate whether the recommendation was correct. This helps improve scoring logic and analysis quality.

