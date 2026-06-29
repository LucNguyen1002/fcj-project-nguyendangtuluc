---
title: "Worklog Tuần 11"
date: 2026-06-26
weight: 11
chapter: false
pre: " <b> 1.11. </b> "
---

### Mục tiêu tuần 11:

* Deploy hoàn chỉnh trang web Workshop lên môi trường Production sử dụng GitHub Pages thông qua Git.
* Cấu hình quy trình tự động hóa CI/CD với GitHub Actions.
* Kiểm thử hệ thống, liên kết và hiển thị trên môi trường thực tế.
* Sửa lỗi giao diện và đảm bảo tính tương thích đa nền tảng.

### Các công việc đã triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - Đóng gói mã nguồn và thực hiện lệnh Git push lên nhánh `main` của repository GitHub <br>- Cấu hình tệp tin workflow GitHub Actions (`hugo.yml`) để tự động kích hoạt tiến trình build website tĩnh khi có commit mới | 22/06/2026 | 22/06/2026 | [GitHub Pages Docs](https://docs.github.com/pages) |
| 3 | - Cấu hình tên miền tùy chỉnh (Custom Domain) trỏ về GitHub Pages bằng cách thiết lập các bản ghi DNS (CNAME, A Records) <br>- Kích hoạt tính năng bảo mật HTTPS của GitHub Pages qua chứng chỉ SSL/TLS được tự động cấp phát | 23/06/2026 | 23/06/2026 | Quản lý DNS tên miền |
| 4 | - Kiểm thử thủ công (Manual Testing) toàn bộ trang web: Check liên kết gãy, hình ảnh tải chậm, kiểm tra chuyển đổi ngôn ngữ Anh - Việt | 24/06/2026 | 24/06/2026 | Test case tự xây dựng |
| 5 | - Kiểm thử khả năng hiển thị giao diện Responsive trên các thiết bị di động (iPhone/iPad/Android) và các trình duyệt Chrome, Safari, Firefox | 25/06/2026 | 25/06/2026 | DevTools Browser |
| 6 | - Tối ưu hóa dung lượng hình ảnh tĩnh để đẩy nhanh tốc độ load trang <br>- Tiếp nhận feedback từ người dùng thử để tinh chỉnh nội dung và bố cục báo cáo <br>- Viết báo cáo tuần 11 | 26/06/2026 | 26/06/2026 | Nhật ký dự án |

### Kết quả đạt được tuần 11:

* Deploy thành công trang web báo cáo thực tập & Workshop lên GitHub Pages, hoạt động công khai trên internet.
* Cấu hình thành công pipeline CI/CD bằng GitHub Actions tự động build và deploy mỗi khi push code bằng Git.
* Tên miền tùy chỉnh và HTTPS bảo mật hoạt động ổn định trên GitHub Pages.
* Hệ thống liên kết, hình ảnh hiển thị mượt mà không xảy ra lỗi 404 hay lỗi giao diện.
* Website hiển thị tốt trên cả máy tính lẫn thiết bị di động, tối ưu hóa trải nghiệm đọc báo cáo.
