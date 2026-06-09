---
title: "Worklog Tuần 3"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.3. </b> "
---

### Mục tiêu tuần 3:

* Tìm hiểu Amazon S3 (Simple Storage Service) và các tính năng lưu trữ cơ bản.
* Thực hành hosting static website trên S3.
* Tìm hiểu Amazon RDS (Relational Database Service) và thực hành tạo database.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc                                                                                                                                                                                                                                          | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                            |
| --- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2   | - Tìm hiểu Amazon S3: <br>&emsp; + S3 là gì, các use case phổ biến <br>&emsp; + Bucket và Object <br>&emsp; + Storage classes (Standard, IA, Glacier...) <br>&emsp; + Versioning                                                                   | 05/05/2026   | 05/05/2026      | <https://000057.awsstudygroup.com>         |
| 3   | - Tìm hiểu thêm về S3: <br>&emsp; + Bucket Policy và ACL <br>&emsp; + Static Website Hosting <br>&emsp; + Lifecycle rules <br> - **Thực hành:** <br>&emsp; + Tạo S3 bucket <br>&emsp; + Upload file và quản lý object <br>&emsp; + Bật Versioning   | 06/05/2026   | 06/05/2026      | <https://000057.awsstudygroup.com>         |
| 4   | - **Thực hành hosting static website trên S3:** <br>&emsp; + Tạo bucket cho static website <br>&emsp; + Cấu hình Bucket Policy để public access <br>&emsp; + Upload file HTML/CSS <br>&emsp; + Truy cập website qua S3 endpoint                      | 07/05/2026   | 07/05/2026      | <https://000057.awsstudygroup.com>         |
| 5   | - Tìm hiểu Amazon RDS: <br>&emsp; + RDS là gì và các database engine hỗ trợ (MySQL, PostgreSQL, Aurora...) <br>&emsp; + Multi-AZ deployment <br>&emsp; + Read Replica <br>&emsp; + Automated Backup và Snapshot                                      | 08/05/2026   | 08/05/2026      | <https://000005.awsstudygroup.com>         |
| 6   | - **Thực hành:** <br>&emsp; + Tạo RDS instance (MySQL, db.t3.micro) <br>&emsp; + Cấu hình Security Group cho RDS <br>&emsp; + Kết nối từ EC2 đến RDS <br>&emsp; + Tạo database và thực hiện query cơ bản                                            | 09/05/2026   | 09/05/2026      | <https://000005.awsstudygroup.com>         |


### Kết quả đạt được tuần 3:

* Hiểu được Amazon S3 và các khái niệm lưu trữ:
  * Bucket, Object và cách tổ chức dữ liệu
  * Các Storage classes và khi nào nên sử dụng
  * Versioning để quản lý phiên bản file
  * Lifecycle rules để tự động chuyển storage class

* Nắm được cách quản lý quyền truy cập S3:
  * Bucket Policy (JSON-based)
  * ACL (Access Control List)
  * Block Public Access settings

* Đã thực hành hosting static website trên S3 thành công:
  * Tạo bucket, cấu hình static website hosting
  * Viết Bucket Policy cho public read access
  * Upload HTML/CSS và truy cập website qua S3 endpoint

* Hiểu được Amazon RDS và các tính năng:
  * Các database engine được hỗ trợ
  * Multi-AZ cho high availability
  * Read Replica cho read scaling
  * Automated Backup và manual Snapshot

* Đã thực hành thành công:
  * Tạo RDS instance MySQL (db.t3.micro) trong VPC
  * Cấu hình Security Group cho phép kết nối từ EC2
  * Kết nối từ EC2 instance đến RDS và thực hiện query cơ bản

