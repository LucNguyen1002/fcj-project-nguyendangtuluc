---
title : "System testing"
date : 2024-01-01
weight : 4
chapter : false
pre : " <b> 5.4 </b> "
---

# Sending requests, viewing logs, and testing errors

This section describes the testing process after the main services have been deployed. The goal is to confirm that the full flow works correctly: the Dashboard sends a request, Ingestion Lambda retrieves data from Yahoo Finance, S3 stores raw data, SQS triggers Processing Lambda, DynamoDB stores reports, and CloudWatch records logs.

## 1. Sign in to the Dashboard with Cognito

Because the system already has internal users in Cognito, users can sign in to the Dashboard using the assigned account.

![Cognito users](/images/5-Workshop/5.4-Test-stock/step-01.png)

![Dashboard login](/images/5-Workshop/5.4-Test-stock/step-14.png)

After signing in, the Dashboard displays the overview screen and stock list.

![Dashboard overview](/images/5-Workshop/5.4-Test-stock/step-03.png)

## 2. Send an analysis request

On the Dashboard, open the **Analysis** tab, select a stock ticker for testing, for example **VNM**, then click **Analyze**.

![Select stock for analysis](/images/5-Workshop/5.4-Test-stock/step-08.png)

After the request is sent successfully, the Dashboard shows that analysis has been triggered.

![Analysis request success](/images/5-Workshop/5.4-Test-stock/step-15.png)

## 3. Check raw data in S3

After the request is sent, Ingestion Lambda calls Yahoo Finance API to fetch market data and stores raw JSON in S3.

![Raw JSON in S3](/images/5-Workshop/5.4-Test-stock/step-04.png)

Storing raw data allows the team to inspect input data and reprocess it when needed.

## 4. Check SQS

After S3 receives a new object, a message is sent to SQS to trigger Processing Lambda. During testing, the number of messages in the queue may quickly return to 0 because Processing Lambda has already consumed the message.

![SQS queue state](/images/5-Workshop/5.4-Test-stock/step-03.png)

## 5. Check DynamoDB

After Processing Lambda finishes, the analysis result is stored in DynamoDB. The report table stores information such as ticker, timeframe, technical indicators, recommendation, confidence score, and approval status.

![DynamoDB reports](/images/5-Workshop/5.4-Test-stock/step-05.png)

The Dashboard also displays analysis results with indicators such as MA20, MACD, RSI, and Volume.

![Analysis dashboard](/images/5-Workshop/5.4-Test-stock/step-09.png)

![Analysis detail](/images/5-Workshop/5.4-Test-stock/step-10.png)

## 6. View Processing Lambda logs

Open the CloudWatch Log Group of Processing Lambda to check whether the flow ran correctly.

![Processing Lambda log group](/images/5-Workshop/5.4-Test-stock/step-02.png)

Logs show that Lambda received the message, read the data, processed indicators, and wrote results according to the designed logic.

![Processing Lambda log detail](/images/5-Workshop/5.4-Test-stock/step-11.png)

## 7. Test Bedrock quota error

During testing, the system encountered a Bedrock error:

```text
Too many tokens per day, please try again.
```

The cause is that the daily token quota of the selected model is not enough for the analysis workload. When Bedrock fails, the system falls back to mock data with a confidence score around 68, which is below the threshold of 75. Therefore, the stocks are marked as **WATCH** instead of generating a report eligible for email delivery.

![Bedrock quota error](/images/5-Workshop/5.4-Test-stock/step-06.png)

![Low confidence result](/images/5-Workshop/5.4-Test-stock/step-07.png)

The fix is to request a quota increase for the model being used, such as Claude 3.5 v2, so Bedrock has enough tokens to process indicators and return analysis reports to the Dashboard.

## 8. Final Trader review

The Trader is responsible for the final report review. If the system produces **STRONG BUY** or **STRONG SELL** signals, the Trader must review technical indicators, AI reasoning, and approval status before sending the report by email to customers.

![Trader review empty state](/images/5-Workshop/5.4-Test-stock/step-13.png)

## Test conclusion

The test flow confirmed that the main steps work according to the architecture:

1. The Dashboard sends an analysis request.
2. Ingestion Lambda retrieves data from Yahoo Finance.
3. Raw data is stored in S3.
4. The message is sent through SQS.
5. Processing Lambda processes the data.
6. DynamoDB stores the report.
7. CloudWatch records logs.
8. Bedrock needs sufficient quota to generate complete AI analysis.

This result shows that the system follows the designed logic and also reveals an improvement point: requesting enough Amazon Bedrock quota for the selected model.

