---
title: "Worklog Tuần 8"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.8. </b> "
---

### Mục tiêu tuần 8:

* Tìm hiểu các dịch vụ bảo mật cơ bản trên AWS.
* Nắm được cách bảo vệ ứng dụng web với AWS WAF.
* Tìm hiểu quản lý mã hóa với KMS và quản lý credentials với Secrets Manager.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc                                                                                                                                                                                                                                         | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                            |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2   | - Tìm hiểu AWS WAF (Web Application Firewall): <br>&emsp; + WAF là gì và tại sao cần WAF <br>&emsp; + Web ACL, Rules, Rule Groups <br>&emsp; + Managed Rules của AWS <br>&emsp; + Tích hợp WAF với CloudFront và ALB                               | 09/06/2026   | 09/06/2026      | <https://000026.awsstudygroup.com>         |
| 3   | - **Thực hành WAF:** <br>&emsp; + Tạo Web ACL <br>&emsp; + Thêm AWS Managed Rules (SQL injection, XSS) <br>&emsp; + Gắn WAF vào CloudFront distribution <br>&emsp; + Kiểm tra chặn request độc hại                                                 | 10/06/2026   | 10/06/2026      | <https://000026.awsstudygroup.com>         |
| 4   | - Tìm hiểu AWS KMS (Key Management Service): <br>&emsp; + Mã hóa đối xứng và bất đối xứng <br>&emsp; + Customer Managed Key (CMK) <br>&emsp; + Mã hóa S3, EBS, RDS với KMS <br>&emsp; + Key rotation tự động                                       | 11/06/2026   | 11/06/2026      | <https://000033.awsstudygroup.com>         |
| 5   | - Tìm hiểu AWS Secrets Manager: <br>&emsp; + Lưu trữ database credentials, API keys an toàn <br>&emsp; + Automatic rotation <br>&emsp; + Truy xuất secret từ Lambda/EC2 <br> - Tìm hiểu AWS Systems Manager Parameter Store                         | 12/06/2026   | 12/06/2026      | <https://000096.awsstudygroup.com>         |
| 6   | - **Thực hành tổng hợp bảo mật:** <br>&emsp; + Mã hóa S3 bucket với KMS key <br>&emsp; + Lưu RDS credentials vào Secrets Manager <br>&emsp; + Tạo Lambda function đọc secret từ Secrets Manager <br>&emsp; + Ôn tập AWS Security Best Practices      | 13/06/2026   | 13/06/2026      | <https://000069.awsstudygroup.com>         |


### Kết quả đạt được tuần 8:

* Hiểu được AWS WAF và cách bảo vệ ứng dụng web:
  * Web ACL với các rules chặn tấn công phổ biến
  * AWS Managed Rules giúp triển khai nhanh không cần viết rule thủ công
  * Kết hợp WAF với CloudFront/ALB tạo lớp bảo vệ phía trước

* Nắm được AWS KMS và mã hóa dữ liệu:
  * Phân biệt mã hóa đối xứng và bất đối xứng
  * Tạo và quản lý Customer Managed Key
  * Mã hóa data at rest cho S3, EBS, RDS
  * Key rotation tự động để tăng cường bảo mật

* Hiểu được AWS Secrets Manager:
  * Lưu trữ credentials an toàn thay vì hardcode trong code
  * Automatic rotation cho database passwords
  * Truy xuất secret qua SDK trong Lambda/EC2

* Đã thực hành bảo mật tổng hợp:
  * Mã hóa S3 bucket bằng KMS key
  * Lưu và truy xuất RDS credentials từ Secrets Manager
  * Lambda function kết nối RDS qua Secrets Manager
  * Nắm được AWS Security Best Practices

