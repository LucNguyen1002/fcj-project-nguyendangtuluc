---
title: "Worklog Tuần 6"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.6. </b> "
---

### Mục tiêu tuần 6:

* Tìm hiểu AWS Lambda và mô hình Serverless.
* Tìm hiểu AWS CloudFormation để triển khai hạ tầng bằng code (Infrastructure as Code).
* Tìm hiểu Amazon API Gateway để xây dựng REST API.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc                                                                                                                                                                                                                                         | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                            |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2   | - Tìm hiểu AWS Lambda: <br>&emsp; + Serverless là gì và lợi ích <br>&emsp; + Lambda function: runtime, handler, event <br>&emsp; + Trigger: API Gateway, S3, CloudWatch Events <br>&emsp; + Pricing model (pay per request + duration)              | 26/05/2026   | 26/05/2026      | <https://000022.awsstudygroup.com>         |
| 3   | - **Thực hành Lambda:** <br>&emsp; + Tạo Lambda function (Python/Node.js) <br>&emsp; + Cấu hình trigger từ S3 (xử lý khi upload file) <br>&emsp; + Xem logs trên CloudWatch Logs <br>&emsp; + Cấu hình Environment Variables và Timeout            | 27/05/2026   | 27/05/2026      | <https://000022.awsstudygroup.com>         |
| 4   | - Tìm hiểu Amazon API Gateway: <br>&emsp; + REST API vs HTTP API <br>&emsp; + Tạo API endpoint, resource, method <br>&emsp; + Tích hợp API Gateway với Lambda <br> - **Thực hành:** Tạo REST API đơn giản gọi Lambda function                       | 28/05/2026   | 28/05/2026      | <https://000066.awsstudygroup.com>         |
| 5   | - Tìm hiểu AWS CloudFormation: <br>&emsp; + Infrastructure as Code (IaC) là gì <br>&emsp; + Template structure (YAML/JSON) <br>&emsp; + Stack, Resources, Parameters, Outputs <br>&emsp; + Change Sets và Stack Updates                              | 29/05/2026   | 29/05/2026      | <https://000037.awsstudygroup.com>         |
| 6   | - **Thực hành CloudFormation:** <br>&emsp; + Viết template tạo VPC + EC2 <br>&emsp; + Deploy stack từ template <br>&emsp; + Update stack với Change Set <br>&emsp; + Delete stack và kiểm tra resource cleanup                                        | 30/05/2026   | 30/05/2026      | <https://000037.awsstudygroup.com>         |


### Kết quả đạt được tuần 6:

* Hiểu được mô hình Serverless và AWS Lambda:
  * Không cần quản lý server, auto-scaling tự động
  * Lambda function với các runtime hỗ trợ (Python, Node.js, Java...)
  * Event-driven: Lambda được kích hoạt bởi các sự kiện từ nhiều nguồn
  * Pricing: chỉ trả tiền khi function thực thi

* Đã thực hành Lambda thành công:
  * Tạo function xử lý event khi upload file lên S3
  * Theo dõi logs và debug qua CloudWatch Logs
  * Cấu hình environment variables và timeout phù hợp

* Nắm được Amazon API Gateway:
  * Phân biệt REST API và HTTP API
  * Tạo endpoint, resource, method (GET, POST...)
  * Kết hợp API Gateway + Lambda tạo serverless API

* Hiểu được AWS CloudFormation và Infrastructure as Code:
  * Tại sao cần IaC: version control, repeatable, consistent
  * Cấu trúc template: AWSTemplateFormatVersion, Description, Parameters, Resources, Outputs
  * Stack lifecycle: Create → Update (Change Set) → Delete
  * Automatic resource cleanup khi delete stack

* Đã thực hành CloudFormation thành công:
  * Viết template YAML tạo VPC + Subnet + EC2
  * Deploy và quản lý stack qua Console
  * Sử dụng Change Set để preview thay đổi trước khi update
  * Delete stack và xác nhận toàn bộ resource được dọn dẹp

