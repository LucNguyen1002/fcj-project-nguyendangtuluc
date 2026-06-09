---
title: "Worklog Tuần 5"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.5. </b> "
---

### Mục tiêu tuần 5:

* Tìm hiểu Amazon Route 53 để quản lý DNS và định tuyến traffic.
* Tìm hiểu AWS CLI để quản lý tài nguyên AWS qua dòng lệnh.
* Kết hợp kiến thức các tuần trước để xây dựng kiến trúc web hoàn chỉnh.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc                                                                                                                                                                                                                                         | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                            |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2   | - Tìm hiểu Amazon Route 53: <br>&emsp; + DNS là gì và cách hoạt động <br>&emsp; + Hosted Zone (Public / Private) <br>&emsp; + Các loại record: A, AAAA, CNAME, Alias, MX, TXT                                                                     | 19/05/2026   | 19/05/2026      | <https://000010.awsstudygroup.com>         |
| 3   | - Tìm hiểu Route 53 Routing Policies: <br>&emsp; + Simple routing <br>&emsp; + Weighted routing <br>&emsp; + Latency-based routing <br>&emsp; + Failover routing <br>&emsp; + Health Check với Route 53                                             | 20/05/2026   | 20/05/2026      | <https://000010.awsstudygroup.com>         |
| 4   | - Tìm hiểu AWS CLI: <br>&emsp; + Cài đặt và cấu hình AWS CLI v2 <br>&emsp; + Cấu hình profile (access key, secret key, region) <br>&emsp; + Các lệnh cơ bản: aws s3, aws ec2, aws iam <br> - Tìm hiểu AWS CloudShell                              | 21/05/2026   | 21/05/2026      | <https://000011.awsstudygroup.com>         |
| 5   | - **Thực hành AWS CLI:** <br>&emsp; + Tạo và quản lý S3 bucket qua CLI <br>&emsp; + Quản lý EC2 instance qua CLI (describe, start, stop) <br>&emsp; + Quản lý IAM user qua CLI <br>&emsp; + Sử dụng AWS CloudShell trên console                     | 22/05/2026   | 22/05/2026      | <https://000011.awsstudygroup.com>         |
| 6   | - **Thực hành tổng hợp:** <br>&emsp; + Đăng ký domain hoặc sử dụng domain có sẵn <br>&emsp; + Tạo Hosted Zone trên Route 53 <br>&emsp; + Tạo record trỏ domain về ALB/EC2 <br>&emsp; + Cấu hình Health Check cho endpoint                          | 23/05/2026   | 23/05/2026      | <https://000010.awsstudygroup.com>         |


### Kết quả đạt được tuần 5:

* Hiểu được Amazon Route 53 và các khái niệm DNS:
  * Hosted Zone (Public và Private)
  * Các loại DNS record: A, AAAA, CNAME, Alias, MX, TXT
  * Alias record của AWS và sự khác biệt với CNAME

* Nắm được các Routing Policies:
  * Simple: định tuyến đơn giản, một record trỏ một hoặc nhiều IP
  * Weighted: phân phối traffic theo tỷ lệ phần trăm
  * Latency-based: định tuyến theo độ trễ thấp nhất
  * Failover: tự động chuyển hướng khi primary endpoint bị lỗi
  * Health Check để kiểm tra trạng thái endpoint

* Thành thạo AWS CLI v2:
  * Cài đặt, cấu hình profile với named profiles
  * Quản lý S3: `aws s3 ls`, `aws s3 cp`, `aws s3 sync`, `aws s3 mb`
  * Quản lý EC2: `aws ec2 describe-instances`, `aws ec2 start-instances`, `aws ec2 stop-instances`
  * Quản lý IAM: `aws iam list-users`, `aws iam create-user`
  * Sử dụng `--output` (json, table, text) và `--query` để lọc kết quả

* Biết sử dụng AWS CloudShell để chạy lệnh CLI trực tiếp trên console mà không cần cài đặt.

* Đã thực hành tổng hợp:
  * Tạo Hosted Zone và DNS record trỏ về ALB
  * Cấu hình Health Check cho endpoint
  * Kết hợp Route 53 + ALB + Auto Scaling + EC2 tạo kiến trúc web hoàn chỉnh

