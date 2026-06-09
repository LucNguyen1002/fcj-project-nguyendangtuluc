---
title: "Event 1"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 4.1. </b> "
---

# Bài thu hoạch "AWS Vietnam Community Day 2026"

### Mục Đích Của Sự Kiện

- Quy tụ cộng đồng AWS tại Việt Nam để chia sẻ kiến thức và kinh nghiệm thực tế.
- Giới thiệu các công nghệ và dịch vụ AWS mới nhất qua các bài trình bày từ các chuyên gia trong ngành.
- Tạo cơ hội kết nối, giao lưu giữa các developer, engineer và cộng đồng AWS.

### Danh Sách Diễn Giả

| # | Diễn giả | Chức vụ | Chủ đề |
|---|----------|---------|--------|
| 1 | **Tinh Truong** | Platform Engineer @ GoTymeX | Context Is Everything – Making AI Actually Work for You |
| 2 | **Pham Ng Hai Anh** | AWS Community Builder @ G-AsiaPacific Vietnam | Friendly AI Assistant w/ Amazon Quick |
| 3 | **Nguyen Tuan Thinh** | AWS Champion Instructor, 12x AWS Certified | From Edge To Origin: CloudFront as Your Foundation |
| 4 | **Team VIB** | AWS Track Winner (LotusHacks 2026) | 36 hrs with LotusHacks – Building UTMorpho |
| 5 | **Duc Dao** | Solution Architect @ Cloud Kinetics | Non-Determinism of "Deterministic" LLM Settings |
| 6 | **Vy Lam** | Sr. Business Systems Analyst @ VPBank | Enterprise-Grade Multi-Agent System |

### Nội Dung Nổi Bật – Bài "From Edge To Origin: CloudFront as Your Foundation"

Trong các bài trình bày, em ấn tượng nhất với bài của anh **Nguyen Tuan Thinh** về **Amazon CloudFront** vì nội dung rất dễ hiểu và liên quan trực tiếp đến kiến thức AWS cơ bản mà em đang học.

#### Amazon CloudFront là gì?

- **CDN (Content Delivery Network)** của AWS, giúp phân phối nội dung đến người dùng với tốc độ cao và độ trễ thấp.
- AWS sở hữu **600+ Points of Presence (PoPs)** trải rộng hơn 100 thành phố tại 50+ quốc gia, kết nối bằng đường truyền cáp quang riêng của Amazon.
- Tại **Việt Nam** có 2 trạm Edge đặt tại **Hà Nội** và **TP.HCM**, kết nối trực tiếp (peering) với các nhà mạng lớn: Viettel, VNPT, FPT, CMC.

#### Tại sao cần CloudFront?

- **Không có CDN**: Người dùng Việt Nam truy cập server ở Mỹ → dữ liệu đi qua nhiều chặng trên internet công cộng → độ trễ **200ms+**.
- **Có CloudFront**: Nội dung tĩnh được cache ngay tại Edge gần nhất → độ trễ giảm xuống **dưới 10ms**.

#### Tăng tốc nội dung động (Dynamic Content Acceleration)

- CloudFront không chỉ cache nội dung tĩnh mà còn **tối ưu hóa đường truyền cho request động** (không thể cache).
- Sử dụng **connection pooling**, **tái sử dụng TCP handshake** và **mạng riêng AWS backbone** để giảm độ trễ.

#### Origin linh hoạt

CloudFront hỗ trợ nhiều loại origin:
- AWS: S3, EC2, ALB, API Gateway, Lambda Function URL
- Ngoài AWS: Server on-premise hoặc cloud khác

#### Bảo mật với CloudFront

- **AWS Shield Standard**: Chống DDoS mặc định, miễn phí.
- **AWS WAF**: Chặn SQL injection, XSS, bot, rate limiting ngay tại Edge.
- **SSL/TLS miễn phí**: Tích hợp AWS Certificate Manager (ACM), tự động gia hạn.
- **Mutual TLS (mTLS)**: Xác thực 2 chiều cho các use case tài chính, bảo mật cao.
- **Origin cloaking**: Ẩn origin khỏi internet công cộng qua VPC Origin, OAC, hoặc custom header.
- **Geo Restriction**: Cho phép/chặn truy cập theo quốc gia.
- **Signed URL**: Bảo vệ nội dung trả phí bằng URL có chữ ký mã hóa, giới hạn thời gian và IP.

#### Tính sẵn sàng cao (High Availability)

- **Caching**: Không chỉ tăng tốc mà còn giúp hệ thống vẫn hoạt động khi origin sập (trả về stale content).
- **Origin Failover**: Tự động chuyển hướng sang origin thứ 2 khi origin chính bị lỗi.
- **Custom Error Page**: Hiển thị trang lỗi thân thiện thay vì lỗi mặc định.

#### Tối ưu hiệu năng

- **Multi-layer caching**: PoPs → Regional Edge Caches → Origin Shield → Origin. Request collapsing giúp giảm tải origin (10,000 req → gom thành 1).
- **HTTP/3 (QUIC/UDP)**: Tải song song hàng chục tài nguyên cùng lúc (thay vì 4-6 như HTTP/1.1).
- **HTTP Compression**: Giảm 81% thời gian tải trang.
- **Persistent Connections**: Duy trì kết nối mở về origin, bỏ qua TCP handshake cho các request sau.

#### Edge Computing

- **CloudFront Functions**: Siêu nhanh (<1ms), JavaScript nhẹ, dùng cho URL rewrite, header modification, redirect.
- **Lambda@Edge**: Full Node.js/Python, dùng cho logic phức tạp, AB testing, geo redirect.

### Những Gì Học Được

#### Kiến thức kỹ thuật

- Hiểu cách CDN hoạt động và tại sao nó quan trọng cho performance và bảo mật.
- Biết cách CloudFront tối ưu cả nội dung tĩnh lẫn động.
- Hiểu kiến trúc caching đa tầng và request collapsing.
- Nắm được các tính năng bảo mật từ cơ bản (Shield, WAF) đến nâng cao (mTLS, Signed URL, Origin cloaking).

#### Tư duy thiết kế hệ thống

- CloudFront không chỉ là "cache hình ảnh" mà là một **lớp bảo vệ toàn diện** cho hệ thống.
- Origin cloaking giúp ẩn hoàn toàn server khỏi internet công cộng.
- Edge computing cho phép xử lý logic ngay tại Edge mà không cần về origin.

#### Ứng dụng thực tế

- Có thể áp dụng CloudFront cho project workshop (IoT Weather Platform) để phân phối dashboard nhanh hơn.
- Kết hợp CloudFront + S3 để hosting static website với performance và bảo mật tốt hơn.
- Sử dụng Signed URL cho các nội dung cần kiểm soát quyền truy cập.

### Trải nghiệm trong event

Tham gia **AWS Vietnam Community Day 2026** là một trải nghiệm rất bổ ích và đáng nhớ. Một số trải nghiệm nổi bật:

#### Học hỏi từ diễn giả chuyên môn cao
- Anh Nguyen Tuan Thinh với **12 chứng chỉ AWS** đã trình bày rất dễ hiểu, từ cơ bản đến nâng cao.
- Cách anh dùng ví dụ thực tế (người dùng Việt Nam truy cập server Mỹ) giúp hình dung rõ ràng vấn đề mà CDN giải quyết.
- Speaker notes chi tiết cho thấy sự chuẩn bị kỹ lưỡng của diễn giả.

#### Mở rộng kiến thức
- Ngoài bài CloudFront, các bài về AI/LLM, Multi-Agent System cũng cho thấy xu hướng công nghệ mới nhất trên AWS.
- Team VIB chia sẻ trải nghiệm hackathon giúp em thấy cách áp dụng AWS vào sản phẩm thực tế trong thời gian ngắn.

#### Kết nối cộng đồng
- Được giao lưu với các developer, engineer từ nhiều công ty khác nhau.
- Cảm nhận được sự phát triển mạnh mẽ của cộng đồng AWS tại Việt Nam.

#### Bài học rút ra
- CloudFront là một dịch vụ toàn diện hơn nhiều so với những gì em hình dung ban đầu (không chỉ cache mà còn bảo mật, edge computing, high availability).
- Việc đặt CloudFront phía trước hệ thống giúp bảo vệ origin, tăng performance và giảm chi phí vận hành.
- Edge computing là xu hướng quan trọng, cho phép xử lý logic gần người dùng nhất.

#### Một số hình ảnh khi tham gia sự kiện
![AWS Community Day 2026](/images/event1.jpg)

> Tổng thể, sự kiện không chỉ cung cấp kiến thức kỹ thuật sâu về CloudFront mà còn giúp em mở rộng tầm nhìn về cách thiết kế hệ thống hiệu quả, bảo mật và hiệu năng cao trên AWS.

