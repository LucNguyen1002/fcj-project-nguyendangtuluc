---
title: "Worklog Tuần 4"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.4. </b> "
---

### Mục tiêu tuần 4:

* Tìm hiểu EC2 Auto Scaling để tự động mở rộng/thu hẹp tài nguyên.
* Tìm hiểu Amazon CloudWatch để giám sát và theo dõi hệ thống.
* Tìm hiểu Elastic Load Balancing (ELB) để phân phối traffic.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc                                                                                                                                                                                                                                         | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                            |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2   | - Tìm hiểu Elastic Load Balancing (ELB): <br>&emsp; + Application Load Balancer (ALB) <br>&emsp; + Network Load Balancer (NLB) <br>&emsp; + Target Group và Health Check <br>&emsp; + Listener rules                                               | 12/05/2026   | 12/05/2026      | <https://000006.awsstudygroup.com>         |
| 3   | - Tìm hiểu EC2 Auto Scaling: <br>&emsp; + Launch Template <br>&emsp; + Auto Scaling Group (ASG) <br>&emsp; + Scaling policies (Target tracking, Step, Simple) <br>&emsp; + Desired, Minimum, Maximum capacity                                       | 13/05/2026   | 13/05/2026      | <https://000006.awsstudygroup.com>         |
| 4   | - **Thực hành:** <br>&emsp; + Tạo Launch Template <br>&emsp; + Tạo Application Load Balancer với Target Group <br>&emsp; + Tạo Auto Scaling Group gắn với ALB <br>&emsp; + Cấu hình scaling policy (Target tracking CPU 70%)                        | 14/05/2026   | 14/05/2026      | <https://000006.awsstudygroup.com>         |
| 5   | - Tìm hiểu Amazon CloudWatch: <br>&emsp; + Metrics (CPU, Network, Disk...) <br>&emsp; + Alarms và thresholds <br>&emsp; + Dashboards <br>&emsp; + Logs (CloudWatch Logs) <br> - Tìm hiểu SNS để gửi thông báo                                      | 15/05/2026   | 15/05/2026      | <https://000008.awsstudygroup.com>         |
| 6   | - **Thực hành:** <br>&emsp; + Tạo CloudWatch Dashboard theo dõi EC2 <br>&emsp; + Tạo Alarm khi CPU > 80% <br>&emsp; + Cấu hình SNS gửi email cảnh báo <br>&emsp; + Kết hợp CloudWatch Alarm với Auto Scaling                                       | 16/05/2026   | 16/05/2026      | <https://000008.awsstudygroup.com>         |


### Kết quả đạt được tuần 4:

* Hiểu được Elastic Load Balancing và các loại Load Balancer:
  * ALB (Layer 7) cho HTTP/HTTPS traffic
  * NLB (Layer 4) cho TCP/UDP traffic
  * Target Group và Health Check để kiểm tra sức khỏe instance

* Nắm được EC2 Auto Scaling:
  * Launch Template để định nghĩa cấu hình instance
  * Auto Scaling Group với desired, min, max capacity
  * Các loại scaling policy và khi nào nên sử dụng
  * Kết hợp ASG với ALB để tự động đăng ký/hủy instance

* Đã thực hành thành công:
  * Tạo hệ thống Auto Scaling hoàn chỉnh: ALB + Target Group + ASG
  * Cấu hình Target tracking policy (CPU 70%)
  * Kiểm tra auto scaling khi tải tăng/giảm

* Hiểu được Amazon CloudWatch:
  * Metrics mặc định và custom metrics
  * Tạo Alarm với các ngưỡng cảnh báo
  * Dashboard để trực quan hóa dữ liệu giám sát
  * CloudWatch Logs để thu thập log từ EC2

* Đã thực hành giám sát và cảnh báo:
  * Tạo Dashboard theo dõi CPU, Network, Disk của EC2
  * Tạo Alarm gửi email qua SNS khi CPU vượt ngưỡng
  * Kết hợp CloudWatch Alarm với Auto Scaling để tự động scale

