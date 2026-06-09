---
title: "Worklog Tuần 7"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.7. </b> "
---

### Mục tiêu tuần 7:

* Tìm hiểu Amazon DynamoDB – cơ sở dữ liệu NoSQL trên AWS.
* Tìm hiểu Amazon CloudFront – dịch vụ CDN phân phối nội dung toàn cầu.
* Thực hành kết hợp các dịch vụ serverless đã học.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc                                                                                                                                                                                                                                         | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                            |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2   | - Tìm hiểu Amazon DynamoDB: <br>&emsp; + NoSQL vs SQL, khi nào dùng DynamoDB <br>&emsp; + Table, Item, Attribute <br>&emsp; + Partition Key và Sort Key <br>&emsp; + Read/Write Capacity (On-Demand vs Provisioned)                                 | 02/06/2026   | 02/06/2026      | <https://000060.awsstudygroup.com>         |
| 3   | - Tìm hiểu thêm DynamoDB: <br>&emsp; + Secondary Indexes (GSI, LSI) <br>&emsp; + DynamoDB Streams <br>&emsp; + TTL (Time to Live) <br> - **Thực hành:** <br>&emsp; + Tạo DynamoDB table <br>&emsp; + CRUD operations qua Console và CLI              | 03/06/2026   | 03/06/2026      | <https://000060.awsstudygroup.com>         |
| 4   | - Tìm hiểu Amazon CloudFront: <br>&emsp; + CDN là gì và cách hoạt động <br>&emsp; + Edge Locations và Points of Presence <br>&emsp; + Origin types (S3, ALB, Custom) <br>&emsp; + Cache behaviors và TTL                                            | 04/06/2026   | 04/06/2026      | <https://000094.awsstudygroup.com>         |
| 5   | - Tìm hiểu thêm CloudFront: <br>&emsp; + Origin Access Control (OAC) cho S3 <br>&emsp; + SSL/TLS với AWS Certificate Manager <br>&emsp; + Invalidation để xóa cache <br>&emsp; + Geo Restriction                                                    | 05/06/2026   | 05/06/2026      | <https://000094.awsstudygroup.com>         |
| 6   | - **Thực hành tổng hợp:** <br>&emsp; + Tạo S3 static website + CloudFront distribution <br>&emsp; + Cấu hình OAC để chỉ cho phép truy cập qua CloudFront <br>&emsp; + Tạo serverless API: API Gateway + Lambda + DynamoDB                           | 06/06/2026   | 06/06/2026      | <https://000094.awsstudygroup.com>         |


### Kết quả đạt được tuần 7:

* Hiểu được Amazon DynamoDB và cơ sở dữ liệu NoSQL:
  * Phân biệt NoSQL và SQL, biết khi nào nên dùng DynamoDB
  * Table design: Partition Key, Sort Key
  * Capacity modes: On-Demand (linh hoạt) vs Provisioned (tiết kiệm)
  * Secondary Indexes: GSI cho query linh hoạt, LSI cho sort key thay thế

* Đã thực hành DynamoDB thành công:
  * Tạo table với Partition Key và Sort Key
  * Thực hiện CRUD (Create, Read, Update, Delete) qua Console và CLI
  * Sử dụng Query và Scan để truy vấn dữ liệu

* Hiểu được Amazon CloudFront và CDN:
  * Cách CDN hoạt động: Edge Locations cache nội dung gần người dùng
  * Các loại origin được hỗ trợ
  * Cache behaviors: path pattern, TTL, viewer protocol policy
  * Origin Access Control (OAC) để bảo vệ S3 origin

* Nắm được các tính năng bảo mật CloudFront:
  * OAC thay thế OAI để kiểm soát truy cập S3
  * SSL/TLS miễn phí qua ACM
  * Geo Restriction để giới hạn truy cập theo quốc gia
  * Cache Invalidation để xóa cache khi cập nhật nội dung

* Đã thực hành tổng hợp thành công:
  * Tạo S3 static website + CloudFront distribution với OAC
  * Website chỉ truy cập được qua CloudFront, không trực tiếp qua S3
  * Xây dựng serverless API hoàn chỉnh: API Gateway → Lambda → DynamoDB

