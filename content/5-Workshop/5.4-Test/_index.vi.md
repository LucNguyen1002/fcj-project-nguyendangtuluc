---
title : "Kiểm thử hệ thống"
date : 2024-01-01
weight : 4
chapter : false
pre : " <b> 5.4 </b> "
---

# Gửi request, xem log và kiểm thử lỗi

Phần này mô tả quy trình kiểm thử hệ thống sau khi đã triển khai các dịch vụ chính. Mục tiêu là xác nhận toàn bộ flow hoạt động đúng: Dashboard gửi request, Ingestion Lambda lấy dữ liệu từ Yahoo Finance, S3 lưu raw data, SQS kích hoạt Processing Lambda, DynamoDB lưu báo cáo và CloudWatch ghi log.

## 1. Đăng nhập Dashboard bằng Cognito

Do hệ thống đã có user nội bộ trong Cognito, người dùng có thể đăng nhập vào Dashboard bằng tài khoản được cấp.

![Cognito users](/images/5-Workshop/5.4-Test-stock/step-01.png)

![Dashboard login](/images/5-Workshop/5.4-Test-stock/step-14.png)

Sau khi đăng nhập, Dashboard hiển thị giao diện tổng quan và danh sách mã cổ phiếu.

![Dashboard overview](/images/5-Workshop/5.4-Test-stock/step-03.png)

## 2. Gửi yêu cầu phân tích

Trên Dashboard, chọn tab **Phân tích**, chọn mã cổ phiếu cần kiểm thử, ví dụ **VNM**, sau đó bấm **Phân tích**.

![Select stock for analysis](/images/5-Workshop/5.4-Test-stock/step-08.png)

Sau khi gửi request thành công, Dashboard hiển thị thông báo đã kích hoạt phân tích.

![Analysis request success](/images/5-Workshop/5.4-Test-stock/step-15.png)

## 3. Kiểm tra dữ liệu raw trong S3

Sau khi request được gửi, Ingestion Lambda gọi Yahoo Finance API để lấy dữ liệu thị trường và lưu raw JSON vào S3.

![Raw JSON in S3](/images/5-Workshop/5.4-Test-stock/step-04.png)

Việc lưu raw data giúp nhóm có thể kiểm tra dữ liệu đầu vào và xử lý lại nếu cần.

## 4. Kiểm tra SQS

Sau khi S3 nhận object mới, message được đẩy vào SQS để kích hoạt Processing Lambda. Trong quá trình kiểm thử, số message trong queue có thể nhanh chóng trở về 0 vì Processing Lambda đã xử lý xong message.

![SQS queue state](/images/5-Workshop/5.4-Test-stock/step-03.png)

## 5. Kiểm tra DynamoDB

Sau khi Processing Lambda xử lý xong, kết quả phân tích được lưu vào DynamoDB. Bảng báo cáo lưu các thông tin như mã cổ phiếu, khung thời gian, chỉ báo kỹ thuật, khuyến nghị, confidence score và trạng thái phê duyệt.

![DynamoDB reports](/images/5-Workshop/5.4-Test-stock/step-05.png)

Dashboard cũng hiển thị kết quả phân tích với các thông số như MA20, MACD, RSI và Volume.

![Analysis dashboard](/images/5-Workshop/5.4-Test-stock/step-09.png)

![Analysis detail](/images/5-Workshop/5.4-Test-stock/step-10.png)

## 6. Xem log Processing Lambda

Vào CloudWatch Log Group của Processing Lambda để kiểm tra flow đã chạy đúng chưa.

![Processing Lambda log group](/images/5-Workshop/5.4-Test-stock/step-02.png)

Log cho thấy Lambda đã nhận message, đọc dữ liệu, xử lý chỉ báo và ghi kết quả theo đúng logic thiết kế.

![Processing Lambda log detail](/images/5-Workshop/5.4-Test-stock/step-11.png)

## 7. Kiểm thử lỗi Bedrock quota

Trong quá trình kiểm thử, hệ thống gặp lỗi Bedrock:

```text
Too many tokens per day, please try again.
```

Nguyên nhân là quota token theo ngày của model đang sử dụng không đủ cho số lần phân tích. Khi Bedrock lỗi, hệ thống fallback về dữ liệu mock với confidence score khoảng 68, thấp hơn ngưỡng 75. Vì vậy các mã cổ phiếu chỉ được đánh dấu **THEO DÕI** thay vì tạo báo cáo đủ điều kiện gửi email.

![Bedrock quota error](/images/5-Workshop/5.4-Test-stock/step-06.png)

![Low confidence result](/images/5-Workshop/5.4-Test-stock/step-07.png)

Cách khắc phục là gửi request tăng quota cho model đang dùng, ví dụ Claude 3.5 v2, để Bedrock có đủ token xử lý chỉ số và trả về báo cáo phân tích cho Dashboard.

## 8. Kiểm duyệt cuối bởi Trader

Trader là người kiểm duyệt báo cáo cuối cùng. Nếu hệ thống có tín hiệu **MUA MẠNH** hoặc **BÁN MẠNH**, Trader cần xem lại chỉ báo kỹ thuật, lập luận AI và trạng thái phê duyệt trước khi gửi báo cáo qua email cho khách hàng.

![Trader review empty state](/images/5-Workshop/5.4-Test-stock/step-13.png)

## Kết luận kiểm thử

Flow kiểm thử đã xác nhận các bước chính hoạt động đúng theo kiến trúc:

1. Dashboard gửi request phân tích.
2. Ingestion Lambda lấy dữ liệu từ Yahoo Finance.
3. Raw data được lưu vào S3.
4. Message được đưa qua SQS.
5. Processing Lambda xử lý dữ liệu.
6. DynamoDB lưu báo cáo.
7. CloudWatch ghi log.
8. Bedrock cần quota đủ để tạo phân tích AI hoàn chỉnh.

Kết quả này cho thấy hệ thống đã vận hành đúng logic đã thiết kế, đồng thời giúp nhóm phát hiện điểm cần cải thiện là request quota cho Amazon Bedrock.

