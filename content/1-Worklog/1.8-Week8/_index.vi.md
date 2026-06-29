---
title: "Worklog Tuần 8"
date: 2026-06-05
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---

### Mục tiêu tuần 8:

* Tìm hiểu dịch vụ cơ sở dữ liệu quan hệ Amazon RDS.
* Nắm được các khái niệm về database engine, DB instances, DB Parameter Groups, Subnet Groups.
* Tạo lập DB instance (MySQL) và cấu hình kết nối từ máy chủ EC2.

### Các công việc đã triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - Tìm hiểu lý thuyết về Amazon RDS và các loại DB engine được hỗ trợ <br>- Phân biệt giữa quản trị CSDL truyền thống trên EC2 và CSDL được quản lý hoàn toàn (Managed) bởi AWS RDS | 01/06/2026 | 01/06/2026 | <https://000013.awsstudygroup.com> |
| 3 | - Thiết lập Subnet Group cho RDS (kết hợp các private subnets trên nhiều Availability Zones để đảm bảo tính High Availability) <br>- Tạo Security Group cho RDS cho phép truy cập từ Security Group của EC2 Web Server | 02/06/2026 | 02/06/2026 | <https://000013.awsstudygroup.com> |
| 4 | - Khởi tạo một DB Instance MySQL (sử dụng gói Free Tier) <br>- Tìm hiểu về cấu hình lưu trữ, backup tự động, và các tùy chọn Multi-AZ | 03/06/2026 | 03/06/2026 | <https://000013.awsstudygroup.com> |
| 5 | - Cài đặt cơ sở dữ liệu mẫu và cấu hình kết nối từ máy chủ EC2 nằm trong Public Subnet sang RDS instance nằm trong Private Subnet <br>- Thực hành kiểm tra kết nối qua giao thức bảo mật | 04/06/2026 | 04/06/2026 | <https://000013.awsstudygroup.com> |
| 6 | - Kiểm thử sao lưu (backup) và khôi phục (restore) cơ sở dữ liệu trên RDS <br>- Đo lường hiệu năng kết nối và tổng kết tuần 8 | 05/06/2026 | 05/06/2026 | <https://000013.awsstudygroup.com> |

### Kết quả đạt được tuần 8:

* Hiểu sâu sắc lợi ích của việc sử dụng dịch vụ Amazon RDS so với việc tự triển khai cơ sở dữ liệu trên máy chủ EC2 thông thường.
* Thiết lập thành công một CSDL MySQL chạy trên Amazon RDS nằm trong private subnets với cấu hình bảo mật Security Groups nghiêm ngặt.
* Đã thực hiện kết nối thành công và truy vấn cơ sở dữ liệu từ xa từ ứng dụng chạy trên máy chủ EC2.
* Nắm vững cơ chế sao lưu tự động (Automatic Backup) và tạo bản chụp snapshot thủ công trên RDS.

