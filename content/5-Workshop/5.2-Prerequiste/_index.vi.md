---
title : "Chuẩn bị và triển khai dịch vụ"
date : 2024-01-01
weight : 2
chapter : false
pre : " <b> 5.2 </b> "
---

# Chuẩn bị và triển khai dịch vụ

Phần này mô tả các dịch vụ cần chuẩn bị trước khi chạy hệ thống phân tích cổ phiếu. Hệ thống sử dụng Yahoo Finance làm nguồn dữ liệu thị trường, AWS Lambda để thu thập/xử lý dữ liệu, S3 để lưu dữ liệu thô và frontend, SQS để xử lý bất đồng bộ, DynamoDB để lưu báo cáo, Cognito để xác thực người dùng và Bedrock để tạo phân tích AI.

## Tài khoản AWS và quyền truy cập

Trước khi triển khai, cần chuẩn bị:

- Tài khoản AWS có quyền tạo S3, Lambda, SQS, DynamoDB, API Gateway, Cognito, CloudFront, WAF, KMS, Systems Manager Parameter Store và Bedrock.
- Region triển khai thống nhất cho các dịch vụ.
- Quyền truy cập Bedrock model đang sử dụng, ví dụ Claude 3.5 Sonnet.
- API key hoặc cấu hình cần thiết cho Yahoo Finance/API tài chính.

![AWS account information](/images/5-Workshop/5.2-Prerequisite-stock/step-14.png)

## Yahoo Finance API

Yahoo Finance là nguồn dữ liệu thị trường chính của hệ thống. Hệ thống lấy các dữ liệu như giá mở cửa, giá cao nhất, giá thấp nhất, giá đóng cửa, khối lượng giao dịch và lịch sử giá theo từng khung thời gian.

Dữ liệu lấy từ Yahoo Finance sẽ không được đưa trực tiếp cho AI phân tích. Thay vào đó, backend sẽ chuẩn hóa dữ liệu, lưu raw data vào S3 và tính toán chỉ báo kỹ thuật trước khi gửi phần dữ liệu đã xử lý sang Bedrock.

## Triển khai Backend

### 1. Tạo S3 bucket lưu raw data

Tạo S3 bucket dùng để lưu dữ liệu thô, ví dụ:

```text
production-stock-raw-data-finance
```

Amazon S3 giúp lưu lại dữ liệu đầu vào từ Yahoo Finance để có thể kiểm tra lại, debug hoặc tái xử lý khi cần.

![Raw data S3 bucket](/images/5-Workshop/5.2-Prerequisite-stock/step-01.png)

### 2. Tạo SQS Main Queue và DLQ

Tạo hai queue:

```text
stock-processing-queue
stock-processing-dlq
```

Amazon SQS đóng vai trò hàng đợi trung gian giữa Ingestion Lambda và Processing Lambda. Khi dữ liệu mới được ghi vào S3, message được đưa vào SQS để Processing Lambda xử lý sau. DLQ lưu các message lỗi để nhóm có thể điều tra lại.

![SQS queue list](/images/5-Workshop/5.2-Prerequisite-stock/step-08.png)

### 3. Tạo Lambda functions

Tạo hai Lambda function dùng runtime Node.js 22.x:

```text
production-stock-ingestion
production-stock-processing
```

**Ingestion Lambda** nhận yêu cầu phân tích cổ phiếu từ API Gateway, gọi Yahoo Finance để lấy dữ liệu thị trường, chuẩn hóa dữ liệu và lưu raw JSON vào S3. Sau đó Lambda gửi message vào SQS để kích hoạt bước xử lý tiếp theo.

**Processing Lambda** đọc dữ liệu từ S3 thông qua message trong SQS, tính toán các chỉ báo kỹ thuật như RSI, MACD, MA20, MA50 và Volume. Sau khi có chỉ báo kỹ thuật, Lambda gửi dữ liệu đã tính sang Amazon Bedrock để AI tạo phân tích và khuyến nghị.

![Lambda functions](/images/5-Workshop/5.2-Prerequisite-stock/step-12.png)

### 4. Cấu hình IAM Role

Lambda cần IAM Role phù hợp để:

- Đọc/ghi dữ liệu trong S3.
- Gửi và nhận message từ SQS.
- Ghi log vào CloudWatch.
- Gọi Bedrock model.
- Đọc secret/cấu hình từ Systems Manager Parameter Store.
- Ghi kết quả vào DynamoDB.

![IAM role policy](/images/5-Workshop/5.2-Prerequisite-stock/step-06.png)

## Triển khai Database

### 1. Tạo AWS KMS key

AWS KMS được dùng để mã hóa dữ liệu trong DynamoDB. Dữ liệu phân tích và thông tin liên quan được bảo vệ ở trạng thái lưu trữ bằng cơ chế encryption at rest.

![KMS encryption key](/images/5-Workshop/5.2-Prerequisite-stock/step-07.png)

### 2. Tạo DynamoDB table

Tạo DynamoDB table:

```text
Stock_reports_1
```

Thiết kế khóa:

```text
PK (String)
SK (String)
```

DynamoDB lưu kết quả phân tích cuối cùng, bao gồm mã cổ phiếu, khung thời gian, chỉ báo kỹ thuật, khuyến nghị AI, điểm tin cậy, lý do phân tích và trạng thái phê duyệt của Trader.

![DynamoDB table](/images/5-Workshop/5.2-Prerequisite-stock/step-09.png)

## Triển khai Frontend

### 1. Tạo S3 bucket cho static website

Tạo S3 bucket để lưu frontend, ví dụ:

```text
stock-frontend-finance
```

Các file HTML, CSS, JavaScript và tài nguyên tĩnh được lưu trong S3. Cách triển khai này giúp giảm chi phí vận hành vì không cần quản lý web server riêng.

![Frontend S3 origin](/images/5-Workshop/5.2-Prerequisite-stock/step-10.png)

### 2. Tạo CloudFront distribution và gắn WAF

CloudFront phân phối frontend đến người dùng với độ trễ thấp hơn thông qua các Edge Location. CloudFront cũng hỗ trợ HTTPS và có thể tích hợp AWS WAF để bảo vệ ứng dụng web.

AWS WAF được triển khai trước CloudFront để lọc các request độc hại như SQL Injection, Cross-Site Scripting, bot hoặc request có tần suất bất thường.

![CloudFront distribution](/images/5-Workshop/5.2-Prerequisite-stock/step-18.png)

![AWS WAF association](/images/5-Workshop/5.2-Prerequisite-stock/step-05.png)

## Tạo Cognito User Pool

Amazon Cognito được dùng để xác thực người dùng đăng nhập vào Dashboard. Chỉ những người dùng hợp lệ như Trader hoặc Admin mới có thể xem báo cáo phân tích và thực hiện thao tác phê duyệt/từ chối khuyến nghị.

![Cognito user pool overview](/images/5-Workshop/5.2-Prerequisite-stock/step-21.png)

![Cognito user list](/images/5-Workshop/5.2-Prerequisite-stock/step-16.png)

## Tạo API Gateway

API Gateway đóng vai trò cổng giao tiếp giữa Frontend và Backend. Khi người dùng thao tác trên Dashboard, request sẽ được gửi đến API Gateway, sau đó API Gateway chuyển tiếp request đến Lambda tương ứng.

Ví dụ API:

```text
Ingestion-lambda_API
```

API Gateway cần cấu hình resource, method và integration với Ingestion Lambda.

![API Gateway API](/images/5-Workshop/5.2-Prerequisite-stock/step-13.png)

![API Gateway resource](/images/5-Workshop/5.2-Prerequisite-stock/step-15.png)

## Kết nối Bedrock và request quota

Amazon Bedrock được dùng để phân tích dữ liệu kỹ thuật đã được backend tính toán. Bedrock không trực tiếp lấy dữ liệu thị trường và không dùng tin tức. Nó chỉ nhận các chỉ số như RSI, MACD, MA và giá cổ phiếu để tạo ra khuyến nghị như **MUA MẠNH**, **BÁN MẠNH** hoặc **THEO DÕI**, kèm điểm tin cậy và lý do phân tích.

Cần đảm bảo account đã được cấp quyền truy cập model và request quota đủ cho quá trình kiểm thử.

![Bedrock model access](/images/5-Workshop/5.2-Prerequisite-stock/step-03.png)

![Bedrock quota](/images/5-Workshop/5.2-Prerequisite-stock/step-04.png)

## Sơ đồ tổng thể sau khi chuẩn bị

Sau khi hoàn tất các bước trên, hệ thống có đủ các thành phần chính để chạy pipeline từ Dashboard đến Backend, AI Analysis và Database.

![Deployment architecture](/images/5-Workshop/5.2-Prerequisite-stock/step-11.png)
