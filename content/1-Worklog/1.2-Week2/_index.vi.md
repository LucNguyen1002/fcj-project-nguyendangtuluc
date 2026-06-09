---
title: "Worklog Tuần 2"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.2. </b> "
---

### Mục tiêu tuần 2:

* Tìm hiểu Amazon VPC (Virtual Private Cloud) và các thành phần mạng cơ bản.
* Tìm hiểu Amazon EC2 (Elastic Compute Cloud) và thực hành tạo EC2 instance.
* Nắm được cách kết nối SSH vào EC2 và quản lý Security Group.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc                                                                                                                                                                                                                                             | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                            |
| --- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2   | - Tìm hiểu Amazon VPC: <br>&emsp; + VPC là gì và tại sao cần VPC <br>&emsp; + Subnet (Public / Private) <br>&emsp; + Internet Gateway <br>&emsp; + Route Table <br> - Tìm hiểu CIDR block và cách phân chia IP                                        | 28/04/2026   | 28/04/2026      | <https://000003.awsstudygroup.com>         |
| 3   | - Tìm hiểu thêm về VPC: <br>&emsp; + NAT Gateway <br>&emsp; + Security Group vs Network ACL <br>&emsp; + Elastic IP <br> - **Thực hành:** <br>&emsp; + Tạo VPC với public và private subnet <br>&emsp; + Cấu hình Internet Gateway và Route Table      | 29/04/2026   | 29/04/2026      | <https://000003.awsstudygroup.com>         |
| 4   | - Tìm hiểu Amazon EC2 cơ bản: <br>&emsp; + Instance types (t2.micro, t3.micro...) <br>&emsp; + AMI (Amazon Machine Image) <br>&emsp; + Instance lifecycle (Start, Stop, Terminate) <br>&emsp; + Key Pair để SSH                                        | 30/04/2026   | 30/04/2026      | <https://000004.awsstudygroup.com>         |
| 5   | - Tìm hiểu EBS (Elastic Block Store): <br>&emsp; + Các loại EBS volume (gp2, gp3, io1...) <br>&emsp; + Snapshot <br> - Tìm hiểu Security Group: <br>&emsp; + Inbound / Outbound rules <br>&emsp; + Cho phép SSH (port 22), HTTP (port 80)               | 01/05/2026   | 01/05/2026      | <https://000004.awsstudygroup.com>         |
| 6   | - **Thực hành:** <br>&emsp; + Tạo EC2 instance (Amazon Linux 2, t2.micro) <br>&emsp; + Cấu hình Security Group cho SSH và HTTP <br>&emsp; + Kết nối SSH vào EC2 <br>&emsp; + Gắn thêm EBS volume <br>&emsp; + Gán Elastic IP cho EC2                    | 02/05/2026   | 02/05/2026      | <https://000004.awsstudygroup.com>         |


### Kết quả đạt được tuần 2:

* Hiểu được Amazon VPC và các thành phần mạng cơ bản:
  * VPC, Subnet (Public/Private)
  * Internet Gateway, NAT Gateway
  * Route Table
  * CIDR block và phân chia IP

* Phân biệt được Security Group và Network ACL:
  * Security Group: stateful, áp dụng ở mức instance
  * Network ACL: stateless, áp dụng ở mức subnet

* Đã thực hành tạo VPC hoàn chỉnh với public và private subnet, cấu hình Internet Gateway và Route Table.

* Nắm được các khái niệm cơ bản về Amazon EC2:
  * Instance types và cách chọn loại phù hợp
  * AMI và cách sử dụng
  * Instance lifecycle
  * Key Pair cho SSH

* Hiểu về EBS (Elastic Block Store):
  * Các loại volume và use case
  * Tạo và quản lý Snapshot

* Đã thực hành thành công:
  * Tạo EC2 instance (Amazon Linux 2, t2.micro) trong VPC
  * Cấu hình Security Group cho SSH và HTTP
  * Kết nối SSH vào EC2 từ máy local
  * Gắn thêm EBS volume vào instance
  * Gán Elastic IP cho EC2 instance

