---
title : "Project overview"
date : 2024-01-01
weight : 1
chapter : false
pre : " <b> 5.1 </b> "
---

# System overview

The system is designed to support stock analysis using AWS Serverless architecture. Stock price data is collected from Yahoo Finance, then stored, processed, and analyzed through AWS services such as Lambda, S3, SQS, Amazon Bedrock, and DynamoDB.

The system automatically collects market data, calculates technical indicators such as **RSI**, **MACD**, **MA**, and **Volume**, then sends the calculated indicators to Amazon Bedrock to generate analysis and investment recommendations. The result is displayed on a Dashboard so that a Trader can review, approve, or reject it before sending an email notification to customers.

![Stock Alerts System Architecture](/images/2-Proposal/stock-alerts-architecture.png)

## Who are the customers?

The customers of this system are people interested in monitoring and investing in stocks, including:

- Individual investors who want stock analysis suggestions.
- Beginners who need support understanding technical signals.
- Traders or financial advisors who need a Dashboard to review recommendations before sending them to customers.

In this system, end customers do not receive AI recommendations directly. The analysis result is reviewed by a Trader first to improve safety and reduce risk before investment information is shared.

## What problem does the system solve?

The system addresses the problem of time-consuming manual stock analysis and the risk of missing technical signals. As the number of tracked tickers grows, it becomes difficult for a Trader to continuously monitor price data, trading volume, and technical indicators.

The system automates the main steps:

1. Collect stock data from Yahoo Finance.
2. Store raw data for verification and reprocessing.
3. Calculate technical indicators in the backend.
4. Use AI to support analysis based on calculated indicators.
5. Store analysis results in DynamoDB.
6. Allow the Trader to approve results before sending emails to customers.

As a result, the system reduces analysis time, improves the ability to monitor multiple tickers at the same time, and ensures that the final recommendation remains under human control.

