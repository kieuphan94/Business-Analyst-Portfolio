<div align="center">

# 📊 Enterprise Business Analyst Portfolio
### Kieu Phan

**Senior Business Analyst | Systems Analyst | Product Owner**

*Chuyên sâu về kiến trúc hệ thống nội bộ quy mô lớn, tối ưu hóa quy trình vận hành phức tạp và hợp nhất dữ liệu phân mảnh.*

[![Wix Portfolio](https://shields.io)](https://vibe.wix.com/projects/a255e489-4a79-4bc1-9364-d0209b935e42/v/editor)
[![LinkedIn](https://shields.io)](https://www.linkedin.com/in/phuongkieuphan/)
[![PSPO II Credly Badge](https://shields.io)](https://www.credly.com/earner/earned/badge/bc2c4087-29fe-428c-b690-4d268edeed75)


**Requirements Engineering • Process Modernization • BPMN 2.0 • Data Validation • Agile/Scrum**

</div>

---

## 👋 Professional Overview

Tôi là một **Business Analyst chuyên sâu về hệ thống lớn (Large-scale Internal Systems)** với hơn 5 năm kinh nghiệm thực chiến trong ngành Viễn thông và Công nghệ thông tin. Xuất phát điểm từ nền tảng Kỹ thuật (IT) kết hợp với tư duy UX (User Experience) nhạy bén, tôi tập trung giải quyết các bài toán lõi của doanh nghiệp: quy trình vận hành cồng kềnh, bất đối xứng thông tin và phân mảnh dữ liệu ở mặt trận tiền tuyến.

Các dự án trong Portfolio này chứng minh năng lực cốt lõi bao gồm:
- **Phân tích cấu trúc:** Tách bạch bối cảnh/hành vi người dùng (Big-picture) và tương tác hệ thống chi tiết (Close-up) để tinh giản thao tác thừa.
- **Thiết kế quy trình lõi:** Tái cấu trúc luồng vận hành quy mô lớn, xử lý triệt để các ngoại lệ dữ liệu (data exceptions).
- **Hợp nhất & Đối soát:** Thiết kế các tính năng kiểm thử dữ liệu đa nguồn (multi-source data validation) và giải quyết tranh chấp nghiệp vụ tại hiện trường.
- **Tư duy quản trị:** Tiếp cận bài toán dưới lăng kính của một người định hình tiêu chuẩn, luật lệ hệ thống để đảm bảo tính đồng bộ và mở rộng.

---

## 🚀 Featured Case Studies

| Case Study | Phân Khúc Hệ Thống | Công Cụ & Khả Năng |
|---|---|---|
| [📱 01-mobix-fsm](./01-mobix-fsm) | Field Service Management (FSM) & Revenue Leakage | BPMN 2.0, VSM, Workflow Optimization |
| [📊 02-customer-360](./02-customer-360) | Master Data Management & Data Consolidation | Data Flow Diagram (DFD), Data Modeling |
| [🔁 03-quote-payment](./03-quote-payment) | Transaction Processing & Dispute Resolution | State Machine, Edge-Case Handling, Rules |

---

## 📱 Case Study 1: MobiX FSM — Tối Ưu Vận Hành Hiện Trường

### Bài toán doanh nghiệp
Hệ thống quản lý kỹ thuật viên hiện trường (FSM) gặp tình trạng rò rỉ doanh thu (revenue leakage) nghiêm trọng do dữ liệu giao dịch tại tiền tuyến không được khai thác và đối soát theo thời gian thực, dẫn đến tắc nghẽn quy trình phối hợp.

### Giải pháp & Kết quả giả lập
Thiết kế lại toàn bộ quy trình phối hợp liên phòng ban thông qua sơ đồ BPMN 2.0 và luồng dữ liệu tự động, loại bỏ hoàn toàn các bước nhập liệu thủ công.

| Chỉ số đo lường (KPIs) | Kết quả đạt được |
|---|---:|
| Giảm tỷ lệ rò rỉ doanh thu hiện trường | 45% |
| Tốc độ điều phối kỹ thuật viên | Tăng 60% |
| Thời gian đóng chu trình sự cố (Resolution Time) | Giảm từ 4h → 1.5h |

*Chi tiết deliverable:* [📁 Khám phá thư mục dự án 01-mobix-fsm](./01-mobix-fsm)

---

## 📊 Case Study 2: Customer 360 — Hợp Nhất Dữ Liệu Khách Hàng

### Bài toán doanh nghiệp
Dữ liệu thông tin khách hàng bị phân mảnh ở nhiều phân hệ cũ (Legacy systems: MobiX, Omni Agent, Customer Profile), gây ra hiện tượng trùng lặp, sai lệch thông tin và làm chậm tốc độ tra cứu của điều hành viên.

### Giải pháp & Kết quả giả lập
Xây dựng mô hình dữ liệu tổng thể (To-Be Architecture), thiết kế cơ chế định danh khách hàng duy nhất (Golden Record) và chuẩn hóa luồng tra cứu thời gian thực.

| Chỉ số đo lường (KPIs) | Kết quả đạt được |
|---|---:|
| Tỷ lệ trùng lặp dữ liệu hồ sơ | Giảm từ 32% → < 1% |
| Thời gian phản hồi cuộc gọi tra cứu thông tin | Giảm 70% |
| Độ chính xác của báo cáo định danh hành vi | Đạt 99.4% |

*Chi tiết deliverable:* [📁 Khám phá thư mục dự án 02-customer-360](./02-customer-360)

---

## 🔁 Case Study 3: Quote & Payment — Quy Tắc Đối Soát Giao Dịch

### Bài toán doanh nghiệp
Luồng báo giá và thanh toán phức tạp thường xuyên xảy ra lỗi ngoại lệ dữ liệu. Kỹ thuật viên hiện trường và hệ thống kế toán trung tâm mất rất nhiều thời gian xử lý tranh chấp thủ công do thiếu một bộ quy tắc logic nhất quán.

### Giải pháp & Kết quả giả lập
Thiết kế bộ quy tắc xử lý tranh chấp dữ liệu tự động (Field Dispute Resolution) dựa trên cấu trúc mô hình trạng thái (State Machine), cho phép tự động phát hiện và xử lý các điểm lệch dữ liệu ngay tại front-line.

| Chỉ số đo lường (KPIs) | Kết quả đạt được |
|---|---:|
| Tự động hóa xử lý tranh chấp dữ liệu thanh toán | Đạt 85% |
| Thời gian phê duyệt và tạo báo giá | Giảm 50% |
| Tỷ lệ khiếu nại sai lệch từ hiện trường | Giảm từ 18% xuống 3% |

*Chi tiết deliverable:* [📁 Khám phá thư mục dự án 03-quote-payment](./03-quote-payment)

---

## 🔄 Business Analysis Framework

Tôi tiếp cận việc phân tích và thiết kế hệ thống theo một khung tư duy chặt chẽ nhằm đảm bảo tính toàn vẹn của giải pháp:

```text
XÁC ĐỊNH BÀI TOÁN KINH DOANH
            │
            ▼
KHẢO SÁT HIỆN TRẠNG (AS-IS) & ĐỊNH VỊ ĐIỂM NGHẼN
            │
            ▼
MÔ HÌNH HÓA QUY TRÌNH MỚI (TO-BE & BPMN)
            │
            ▼
THIẾT KẾ QUY TẮC LOGIC HỆ THỐNG & ĐỐI SOÁT DỮ LIỆU
            │
            ▼
PHỐI HỢP TRIỂN KHAI & ĐO LƯỜNG CHỈ SỐ GIÁ TRỊ (KPI)
```

---

## 🧠 Technical Skills & Competencies

| Lĩnh vực | Công nghệ & Kỹ năng |
|---|---|
| **Business Analysis** | Requirements Elicitation, User Stories, Data Exceptional Handling, UAT |
| **Process & Modeling** | BPMN 2.0, Value Stream Mapping (VSM), As-Is/To-Be Mapping, State Machine |
| **Systems & Architecture**| Data Flow Diagram (DFD), Enterprise Systems, Migration & Modernization |
| **Frameworks** | Agile, Scrum (Professional Scrum Product Owner - PSPO II) |
| **UX Mindset** | Persona Context, User Flow Optimization, Screen Layout Logic |

---

## 🤝 Contact & Connection

Tôi luôn cởi mở đón nhận các cơ hội hợp tác và thử thách mới trong vai trò Senior Business Analyst hoặc Product Owner cho các hệ thống phức tạp. 

- **GitHub:** https://github.com
- **LinkedIn:** [Kết nối với tôi trên LinkedIn](#)

---
*Hệ thống tài liệu được xây dựng và duy trì bởi Kieu Phan.*
