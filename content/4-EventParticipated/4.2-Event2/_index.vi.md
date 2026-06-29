---
title: "Event 2"
date: 2024-01-01
weight: 2
chapter: false
pre: " <b> 4.2. </b> "
---

# Bài thu hoạch "FCAJ Community Day - June 2026"

### Mục Đích Của Sự Kiện

- Là sự kiện định kỳ hàng tháng nhằm tạo không gian để các chuyên gia từ nhiều doanh nghiệp chia sẻ kiến thức, trải nghiệm và góc nhìn thực tế nhất trong môi trường làm việc.
- Cập nhật các xu hướng công nghệ mới nhất về **Cloud** và **AI (Trí tuệ nhân tạo)**, cách AI đang tái định hình hạ tầng đám mây (Cloud Infrastructure) và thị trường nhân sự.
- Tạo cơ hội kết nối, giao lưu trực tiếp (tại tầng 26 và 36) và trực tuyến (livestream YouTube) giữa các developer, engineer, sinh viên và cộng đồng yêu công nghệ.

### Danh Sách Diễn Giả

| # | Diễn giả | Chức vụ / Đơn vị | Chủ đề |
|---|----------|-------------------|--------|
| 1 | **Steve Trần** | Founder @ Cloud Thinker | Sự nghiệp Cloud/AI, kiến trúc Multi-Agent & Single-Agent trong vận hành Cloud |
| 2 | **Hiếu Nghị, Kiệt, Trung Đ.** | Renova Cloud, AWS Study Builder, CEO @ R AI | Ứng dụng Voice AI và kiến trúc Voice Agent cho Tiếng Việt |
| 3 | **Bảo & Nguyên** | Cloud Engineer @ Cloud Kinetics | Giải pháp AWS DevOps Agent: Tự động hóa điều tra và xử lý sự cố |
| 4 | **Trường (Wayne) & Minh Anh** | AI Solution @ Noventis | Ứng dụng AI/Amazon Q trong chiến lược nhân sự (HR) và tuyển dụng |
| 5 | **Toàn Nguyễn & Hiếu Nghị** | AWS Security Builder / Renova Cloud | Thiết lập bảo mật mạng riêng (Private Security) cho Amazon Q và MCP Server qua VPC |

### Nội Dung Nổi Bật – Các Chủ Đề Chuyên Sâu

Do sự kiện có nhiều chủ đề chuyên sâu, dưới đây là tổng hợp các nội dung nổi bật nhất:

#### 1. Tự động hóa vận hành với AWS DevOps Agent (Bảo & Nguyên)

**Vấn đề:** Khi hệ thống gặp sự cố, các kỹ sư mất nhiều thời gian để điều tra do log/trace nằm rải rác (fragmented telemetry), dẫn đến thiếu hụt ngữ cảnh (context loss) và thời gian phục hồi (**MTTR**) cao.

**AWS DevOps Agent là gì?** Là một trợ lý AI giúp chủ động tự động hóa việc nghiên cứu, trích xuất log và tìm ra **nguyên nhân gốc rễ (root cause)** khi có incident.

**Cơ chế hoạt động (4 bước):**
1. **Phân loại thông tin (Triage)** – Thu thập và phân loại alert/incident
2. **Điều tra nguyên nhân (Investigate)** – Trích xuất log, trace, metric để tìm root cause
3. **Đề xuất phương án giảm thiểu (Mitigate)** – Gợi ý cách khắc phục tạm thời
4. **Đề xuất cải thiện hệ thống (Improve)** – Đề xuất giải pháp dài hạn

> **Lưu ý:** AI chỉ đóng vai trò phân tích và đề xuất (recommend), quyền quyết định thực thi (execute) vẫn thuộc về con người để đảm bảo an toàn.

#### 2. Tiềm năng của Voice AI tại Việt Nam (Hiếu Nghị, Kiệt, Trung)

**Kiến trúc cốt lõi:** Thay vì dùng Model Speech-to-Speech truyền thống (thường không hỗ trợ tốt tiếng Việt), giải pháp tối ưu hiện tại là:

> **Nhận âm thanh → Chuyển thành Text (STT) → Đưa vào LLM xử lý ra Text → Chuyển Text thành Giọng nói (TTS)**

**Giải quyết bài toán thực tế:** Cần đào tạo model hiểu được:
- Ngữ cảnh **ngắt lời** của người dùng
- Phân biệt **giới tính** (cách xưng hô anh/chị trong tiếng Việt)
- Nhận diện **giọng vùng miền** (như giọng miền Trung) để AI giao tiếp tự nhiên nhất

#### 3. Amazon Q giúp cách mạng hóa ngành Nhân sự – HR (Trường & Minh Anh)

**Vấn đề của HR:** Đọc CV thủ công tốn thời gian, dễ bỏ sót nhân tài, mang tính cảm tính và có nguy cơ lộ dữ liệu nếu dùng AI public.

**Giải pháp với Amazon Q:**
- Cho phép tạo các **Agent chuyên biệt (Skill)** để tự động đọc, quét CV từ nhiều nguồn (SharePoint, Google Drive, Outlook).
- Amazon Q có thể **trích xuất kỹ năng**, so sánh ứng viên với **Job Description (JD)** và tự động tạo **báo cáo đánh giá (Report)** mà không lo rò rỉ dữ liệu.

#### 4. Thiết lập kết nối bảo mật cho Amazon Q (Toàn Nguyễn)

**Bảo mật:** Không để Amazon Q kết nối với **MCP (Model Context Protocol) Server** qua Public Internet để tránh bị tấn công **DDoS** hoặc **Man-in-the-Middle**.

**Giải pháp:** Đưa Amazon Q kết nối thông qua giao diện mạng riêng (**VPC Connection**), dùng **DNS nội bộ** và **ALB (Application Load Balancer)** để đảm bảo dữ liệu truy vấn hoàn toàn nằm trong nội bộ AWS Cloud.

### Những Gì Học Được

#### Kiến thức kỹ thuật

- Hiểu được các **kiến trúc AI hiện đại**: Khác biệt giữa **Single-Agent** và **Multi-Agent**, luồng hoạt động của Voice AI (**STT → LLM → TTS**).
- Nắm bắt công cụ AWS mới: Cách sử dụng **Amazon Q** để thiết lập các tác vụ tự động (Agentic workflows) và **AWS DevOps Agent** để phân tích topology của hệ thống mạng.
- Biết cách thiết kế hạ tầng bảo mật trên AWS bằng việc sử dụng **VPC**, **Resolver** và **ALB** để giấu kín (private) các endpoint AI khỏi public internet.

#### Tư duy thiết kế hệ thống

- **Tư duy tự động hóa (Automation):** Chuyển dịch từ việc xử lý thủ công (như sửa lỗi server, lọc CV) sang sử dụng các AI Agent làm trợ lý phân tích dữ liệu.
- Hệ thống AI không thay thế con người mà để **"khuếch đại" năng lực** của kỹ sư. Điều kiện tiên quyết để AI hoạt động tốt là hệ thống phải có tính minh bạch (**Observability** tốt) và thu thập đầy đủ log/metric.

#### Ứng dụng thực tế

- Có thể áp dụng kiến trúc **Voice AI** để xây dựng bot CSKH tự động cho doanh nghiệp Việt Nam.
- Áp dụng **Amazon Q** vào doanh nghiệp để làm **Business Intelligence**, tự động hóa luồng tuyển dụng (HR tracking) hoặc viết báo cáo nội bộ mà không bị lệ thuộc vào một hệ sinh thái duy nhất.

### Trải nghiệm trong event

Tham gia **FCAJ Community Day - June 2026** là một trải nghiệm rất bổ ích và đáng nhớ. Một số trải nghiệm nổi bật:

#### Học hỏi từ diễn giả chuyên môn cao
- Được lắng nghe chia sẻ từ các **founder** và **chuyên gia giàu kinh nghiệm** đến từ AWS, Cloud Thinker, Renova Cloud, Noventis...
- Các diễn giả không chỉ nói lý thuyết mà còn **demo trực tiếp** các sản phẩm ứng dụng AWS.

#### Mở rộng kiến thức
- Nhận thức rõ ràng về sự thay đổi của thị trường việc làm IT. Các vị trí như Developer hay Cloud Engineer đang dịch chuyển yêu cầu, công ty ưu tiên tuyển người biết **ứng dụng AI** (Senior làm việc với AI) thay vì chỉ tuyển số lượng lớn.

#### Kết nối cộng đồng
- Được trực tiếp tham gia tương tác, **đặt câu hỏi (Q&A)** với các diễn giả về các vấn đề hóc búa thực tế (như tối ưu chi phí, xử lý giọng vùng miền, thiết lập logic cho AI).
- Cảm nhận được sự phát triển mạnh mẽ của cộng đồng công nghệ AWS tại Việt Nam.

#### Bài học rút ra
- Sự trỗi dậy của AI không đồng nghĩa với việc mất hoàn toàn công việc, nhưng nó đòi hỏi con người phải **nâng cấp bản thân** để trở thành những người "sử dụng AI giỏi".
- Việc áp dụng công nghệ mới phải luôn đi đôi với giải quyết **"nỗi đau" (pain points)** thực tế của doanh nghiệp (như tối ưu chi phí, giảm thời gian chết - downtime, bảo mật dữ liệu).
- Trải nghiệm sớm ở môi trường doanh nghiệp và liên tục cập nhật các giải pháp Cloud/AI mới (như **Amazon Q**, **AWS DevOps Agent**) là chìa khóa để tiến xa hơn trong sự nghiệp.

#### Một số hình ảnh khi tham gia sự kiện
![FCAJ Community Day June 2026](/images/event2.jpg)

> Tổng thể, sự kiện FCAJ Community Day không chỉ cung cấp kiến thức kỹ thuật chuyên sâu về AI và Cloud mà còn giúp em mở rộng tầm nhìn về cách AI đang tái định hình ngành công nghệ, từ vận hành hệ thống, nhân sự đến bảo mật – và quan trọng nhất là cách tự trang bị năng lực để thích nghi với sự thay đổi đó.
