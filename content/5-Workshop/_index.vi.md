---
title: "Workshop"
date: 2024-01-01
weight: 5
chapter: false
pre: " <b> 5. </b> "
---

# Xây dựng hệ thống phân tích và cảnh báo giá cổ phiếu trên AWS

Workshop này hướng dẫn triển khai một hệ thống phân tích cổ phiếu theo kiến trúc AWS Serverless. Hệ thống lấy dữ liệu thị trường từ Yahoo Finance, lưu dữ liệu thô vào Amazon S3, xử lý bất đồng bộ qua Amazon SQS và AWS Lambda, gọi Amazon Bedrock để tạo phân tích, sau đó lưu báo cáo vào Amazon DynamoDB để hiển thị trên Dashboard.

Mục tiêu chính của workshop là giúp người học hiểu cách kết hợp các dịch vụ AWS managed/serverless để xây dựng một pipeline xử lý dữ liệu tài chính có khả năng mở rộng, kiểm soát chi phí tốt và vẫn giữ cơ chế kiểm duyệt của Trader trước khi gửi khuyến nghị cho khách hàng.

#### Nội dung

1. [Tổng quan dự án](5.1-Workshop-overview/)
2. [Chuẩn bị và triển khai dịch vụ](5.2-Prerequiste/)
3. [Lý do lựa chọn kiến trúc](5.3-Why-Choose-Structure/)
4. [Kiểm thử hệ thống](5.4-Test/)

