---
title: "Worklog Tuần 9"
date: 2026-06-12
weight: 9
chapter: false
pre: " <b> 1.9. </b> "
---

### Mục tiêu tuần 9:

* Tích hợp thành công ba dịch vụ cốt lõi Amazon EC2, Amazon S3 và Amazon RDS thành một hệ thống web 3-tier hoàn chỉnh.
* Thiết lập phân quyền bảo mật IAM Roles và IAM Instance Profile cho phép EC2 truy cập S3 một cách bảo mật không cần dùng Access Keys.
* Triển khai mã nguồn ứng dụng web kết nối cơ sở dữ liệu động và lưu trữ media file.

### Các công việc đã triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - Thiết lập kiến trúc mạng và phân bổ Security Groups: Cấu hình Web Security Group chỉ nhận HTTP/HTTPS từ ngoài và RDS Security Group chỉ nhận kết nối MySQL từ Web Security Group | 08/06/2026 | 08/06/2026 | Sơ đồ kiến trúc mạng |
| 3 | - Tạo IAM Role với chính sách AmazonS3FullAccess (hoặc cụ thể hóa quyền trên bucket) <br>- Gắn IAM Role này vào EC2 Web Server (IAM Instance Profile) | 09/06/2026 | 09/06/2026 | [AWS IAM Roles for EC2](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/iam-roles-for-null.html) |
| 4 | - Deploy mã nguồn ứng dụng web lên máy chủ EC2 <br>- Cấu hình chuỗi kết nối (Connection String) đến database RDS trong file config của ứng dụng | 10/06/2026 | 10/06/2026 | Tài liệu triển khai code |
| 5 | - Cấu hình mã nguồn ứng dụng để khi người dùng tải tệp ảnh/tài liệu lên, ứng dụng sẽ gọi AWS SDK gửi thẳng tệp đó lên S3 Bucket thay vì lưu local trên EC2 | 11/06/2026 | 11/06/2026 | [AWS SDK for Python/Node.js](https://aws.amazon.com/developer/tools/) |
| 6 | - Kiểm thử hệ thống end-to-end: Thực hiện tạo tài khoản, đăng tin kèm ảnh, kiểm tra dữ liệu đã ghi vào RDS và ảnh đã hiển thị từ S3 <br>- Tổng kết tuần 9 | 12/06/2026 | 12/06/2026 | Nhật ký thực tập |

### Kết quả đạt được tuần 9:

* Xây dựng thành công hệ thống tích hợp 3 dịch vụ cơ bản EC2, S3 và RDS hoạt động trơn tru.
* Áp dụng nguyên tắc bảo mật tối thiểu bằng cách sử dụng IAM Roles thay vì lưu trực tiếp AWS Access Key/Secret Key trong code trên máy chủ EC2.
* Tách biệt tầng dữ liệu tĩnh (S3) và dữ liệu động (RDS) giúp tối ưu hóa hiệu năng hệ thống và giảm tải ổ đĩa cho máy chủ EC2.
* Giải quyết thành công các vấn đề xung đột mạng/cổng kết nối giữa EC2 và RDS thông qua Security Groups.

