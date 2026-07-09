---
title : "Lý do lựa chọn kiến trúc"
date : 2024-01-01
weight : 3
chapter : false
pre : " <b> 5.3 </b> "
---

# Vì sao chọn kiến trúc này?

Mô hình kiến trúc được lựa chọn dựa trên bốn tiêu chí chính: **chi phí thấp**, **đơn giản khi triển khai**, **sử dụng Managed Service/Serverless** và **có khả năng mở rộng tốt**.

## 1. Chi phí thấp

Các dịch vụ như Lambda, S3, SQS, DynamoDB, API Gateway và CloudFront đều phù hợp với mô hình trả tiền theo mức sử dụng. Hệ thống không cần thuê máy chủ chạy liên tục, nên chi phí ban đầu thấp và phù hợp với đồ án sinh viên.

Ví dụ:

- Lambda chỉ phát sinh chi phí khi có request hoặc event.
- SQS tính theo số lượng message.
- DynamoDB tính theo dung lượng và lượt đọc/ghi.
- S3 tính theo dung lượng lưu trữ.
- CloudFront giúp giảm tải cho S3 và cải thiện tốc độ truy cập frontend.

So với việc triển khai một EC2 chạy 24/7, mô hình serverless giúp giảm chi phí khi hệ thống chưa có nhiều người dùng hoặc workload chưa ổn định.

## 2. Đơn giản và Serverless

Project sử dụng kiến trúc Serverless để giảm khối lượng vận hành. Thay vì tự cấu hình server, cài đặt runtime, quản lý scaling, cập nhật hệ điều hành và giám sát tài nguyên, nhóm sử dụng các dịch vụ serverless:

- **AWS Lambda** để chạy backend logic.
- **API Gateway** để cung cấp API.
- **S3** để lưu dữ liệu và frontend tĩnh.
- **SQS** để xử lý hàng đợi.
- **DynamoDB** để lưu báo cáo phân tích.

Nhờ đó, nhóm có thể tập trung vào nghiệp vụ chính: lấy dữ liệu cổ phiếu, tính toán chỉ báo kỹ thuật, gọi Amazon Bedrock và xây dựng luồng phê duyệt của Trader.

## 3. Managed Service

Các dịch vụ trong mô hình phần lớn là Managed Service, nghĩa là AWS chịu trách nhiệm vận hành hạ tầng nền bên dưới. Điều này giúp hệ thống ổn định hơn và giảm rủi ro lỗi vận hành.

Một số ví dụ:

- **Amazon Bedrock** giúp tích hợp AI mà không cần tự triển khai mô hình machine learning.
- **DynamoDB** cung cấp database NoSQL hiệu năng cao mà không cần tự quản trị database server.
- **Amazon SQS** tách rời các bước xử lý mà không cần tự xây dựng message queue.
- **AWS KMS** quản lý khóa mã hóa dữ liệu mà không cần tự xây dựng cơ chế mã hóa riêng.
- **Amazon Cognito** hỗ trợ xác thực người dùng cho Dashboard.

## 4. Khả năng mở rộng

Mô hình có khả năng mở rộng tốt vì các thành phần được tách rời theo từng nhiệm vụ. Khi số lượng mã cổ phiếu hoặc số lượng người dùng tăng lên, hệ thống có thể mở rộng từng phần mà không ảnh hưởng toàn bộ kiến trúc.

Ví dụ:

- Nếu nhiều người gửi yêu cầu phân tích cùng lúc, API Gateway và Lambda có thể xử lý nhiều request song song.
- Nếu lượng dữ liệu tăng nhanh, SQS giúp xếp hàng message để Processing Lambda xử lý dần, tránh quá tải.
- Nếu cần lưu nhiều báo cáo hơn, DynamoDB và S3 có thể mở rộng theo dung lượng và lưu lượng truy cập.
- Nếu nhiều người truy cập Dashboard, CloudFront giúp phân phối frontend nhanh hơn và giảm tải cho S3.
- Nếu cần tăng khả năng bảo vệ ứng dụng, AWS WAF có thể bổ sung rule để chặn request độc hại.

## Các hướng cải tiến trong tương lai

### 1. Mở rộng nguồn dữ liệu

Hiện tại hệ thống sử dụng Yahoo Finance. Trong tương lai có thể bổ sung thêm các nguồn dữ liệu khác để đối chiếu giá, tăng độ tin cậy và hỗ trợ dữ liệu gần thời gian thực hơn.

### 2. Cải thiện mô hình phân tích AI

Amazon Bedrock hiện phân tích dựa trên chỉ báo kỹ thuật. Sau này có thể mở rộng thêm nhiều chỉ báo hơn như Bollinger Bands, Stochastic, ADX hoặc ATR để AI có thêm dữ liệu đầu vào và đưa ra phân tích chính xác hơn.

### 3. Bổ sung cảnh báo thời gian thực

Hệ thống có thể thêm chức năng cảnh báo khi giá cổ phiếu vượt ngưỡng, RSI quá mua/quá bán hoặc MACD đảo chiều. Khi có tín hiệu quan trọng, hệ thống có thể gửi thông báo cho Trader hoặc khách hàng.

### 4. Hoàn thiện quản trị người dùng

Có thể phân quyền rõ hơn giữa Admin, Trader và Customer. Ví dụ Admin quản lý người dùng, Trader phê duyệt khuyến nghị, Customer chỉ nhận báo cáo hoặc xem lịch sử khuyến nghị.

### 5. Tăng cường bảo mật

Hệ thống có thể bổ sung CloudWatch Alarm, AWS WAF Rules nâng cao, giới hạn request theo IP, audit log bằng CloudTrail và mã hóa dữ liệu nhạy cảm bằng KMS.

### 6. Tối ưu chi phí và hiệu năng

Có thể theo dõi chi phí qua AWS Cost Explorer, tối ưu số lần gọi Bedrock, giảm token đầu vào, cache dữ liệu cổ phiếu và điều chỉnh timeout/memory của Lambda để giảm chi phí vận hành.

### 7. Cải thiện Dashboard

Dashboard có thể được nâng cấp thêm biểu đồ trực quan hơn, bộ lọc theo mã cổ phiếu, trạng thái phê duyệt, độ tin cậy, khung thời gian và lịch sử các lần phân tích trước đó.

### 8. Bổ sung CI/CD

Trong tương lai có thể triển khai CI/CD bằng GitHub Actions hoặc AWS CodePipeline để tự động build, test và deploy frontend/backend, giúp quá trình cập nhật hệ thống an toàn và chuyên nghiệp hơn.

### 9. Mở rộng khả năng scale

Khi số lượng mã cổ phiếu và người dùng tăng lên, hệ thống có thể tối ưu batch processing, tăng concurrency cho Lambda, cấu hình DLQ cho SQS và thiết lập retry policy rõ ràng.

### 10. Thêm cơ chế đánh giá độ chính xác

Sau khi hệ thống đưa ra khuyến nghị, có thể lưu lại kết quả thực tế của cổ phiếu sau một khoảng thời gian để đánh giá khuyến nghị đúng hay sai. Từ đó cải thiện logic tính điểm và chất lượng phân tích.

