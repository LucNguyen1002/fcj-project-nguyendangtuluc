---
title: "Các bài blogs đã dịch"
date: 2024-01-01
weight: 3
chapter: false
pre: " <b> 3. </b> "
---

Tại đây sẽ là phần liệt kê và giới thiệu các blog đã dịch/chuyển ngữ trong quá trình thực tập.

### [Blog 1 - Deploy Backend lên AWS EC2 và lỗi chỉ vì chữ hoa](3.1-Blog1/)

Blog này chia sẻ một lỗi thực tế khi deploy backend Node.js từ Windows local lên AWS EC2 Ubuntu/Linux: giá trị Boolean trong file `.env` bị xử lý sai do khác biệt chữ hoa và chữ thường. Bài viết giải thích nguyên nhân, cách khắc phục nhanh bằng việc chuẩn hóa giá trị cấu hình, đồng thời đề xuất hướng quản lý biến môi trường và secret an toàn hơn với AWS Systems Manager Parameter Store hoặc AWS Secrets Manager.

### [Blog 2 - AWS Cost & AI: Khi chạy cloud không còn chỉ là vấn đề kỹ thuật](3.2-Blog2/)

Blog này chia sẻ trải nghiệm khi hệ thống AWS bắt đầu phát sinh bài toán chi phí sau giai đoạn deploy backend thành công. Nội dung tập trung vào hiểu đúng AWS Free Tier, kiểm soát EC2/EBS, thiết lập AWS Budgets, Billing Alarm, Cost Explorer, và cách thử nghiệm các dịch vụ AI như Bedrock, SageMaker, Comprehend trong môi trường sandbox để tránh vượt ngân sách.

### [Blog 3 - Triển khai ứng dụng Serverless với AWS Lambda và Amazon API Gateway](3.3-Blog3/)

Blog này trình bày trải nghiệm tìm hiểu kiến trúc Serverless trên AWS sau khi đã triển khai backend bằng EC2. Nội dung tập trung vào cách API Gateway, Lambda, DynamoDB, IAM Role và CloudWatch phối hợp để xây dựng REST API không cần tự quản lý server, đồng thời phân tích ưu điểm, hạn chế, cold start và góc nhìn chi phí khi so sánh với mô hình EC2 truyền thống.
