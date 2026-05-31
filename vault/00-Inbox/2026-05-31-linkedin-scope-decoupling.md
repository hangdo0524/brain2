---
title: "Khi khách hàng muốn ký hợp đồng gấp mà scope còn mờ — đây là cách tôi xử lý"
created: 2026-05-31
type: content-draft
status: draft
platform: LinkedIn
target_audience: Junior BA/PM, Career changers, IT freelancers
source_insight: "[[../01-Atomic/Insights/pm-insight-negotiation-scope-decoupling]]"
---

# Draft: Scope Decoupling — Khi ký hợp đồng gấp mà scope chưa rõ

---

## Hook

Khách hàng gọi điện: *"Chị ơi ký hợp đồng tuần này được không, deadline Go-live tháng 8 gấp lắm rồi!"*

Nhưng một phần scope vẫn còn mù mờ, chưa có tài liệu. Ký hay không ký?

---

## Insight chính

Sau 15 năm làm IT outsourcing, tôi học được một chiến thuật gọi là **Scope Decoupling** — tách phạm vi:

> **Đồng ý ký ngay phần đã rõ. Tách phần chưa rõ thành Phụ lục / Change Request.**

Nghe đơn giản. Nhưng hầu hết Junior BA/PM đều không làm được vì họ đang chọn giữa 2 lựa chọn sai:
- **Ký gấp tất cả** → scope mờ → team ôm thêm việc không công
- **Đợi cho đủ rõ** → mất momentum → deadline bị trễ từ đầu

Scope Decoupling là lối thoát thứ 3.

---

## Ví dụ thực tế — Dự án KBC (Hàn Quốc, 2026)

Chúng tôi đang làm **KBC Community** — nền tảng cộng đồng nhà đầu tư nhúng vào app giao dịch chứng khoán, team 15 người, đối tác phía Hàn là Quantit.

Tình huống:
- Phần **Admin Portal** chưa có tài liệu cụ thể (bản design còn viết tiếng Hàn)
- Quantit muốn ký hợp đồng gấp để kịp Go-live tháng 9
- Lập luận của họ: *"Admin scope nhỏ hơn RFP, dùng team hiện tại làm được, không cần thêm người"*

Estimate thực tế của chúng tôi: **10.5 Man-Months** — không phải con số nhỏ.

Nếu ký "gộp" mà không định nghĩa rõ, 10.5 MM đó sẽ rơi vào vùng xám: team phải làm nhưng không có ngân sách rõ ràng, không có cơ sở từ chối nếu scope bị "phình".

**Cách xử lý:**
1. Đồng ý ký hợp đồng cho phần Base Scope đã có tài liệu đầy đủ
2. Ghi rõ **Exclusions** — phần Admin Portal chưa được đưa vào
3. Admin Portal → trở thành Phụ lục, sẽ ký bổ sung khi có spec rõ ràng

Kết quả: Dự án vẫn khởi động đúng hạn. Team có căn cứ để negotiate nếu Admin scope bị mở rộng về sau.

---

## Tại sao chiến thuật này hoạt động?

Có một đòn bẩy ngược rất hiệu quả:

> *"Nếu chúng tôi nhận thêm Admin mà không có thêm nguồn lực, rủi ro hỏng deadline Go-live phần cốt lõi là rất cao — điều đó ảnh hưởng trực tiếp đến timeline của anh/chị."*

Khi bạn dùng **deadline của khách hàng** làm lý do để bảo vệ scope của mình, cuộc đàm phán hoàn toàn thay đổi. Bạn không còn là người "khó tính" — bạn là người đang bảo vệ dự án của họ.

---

## Call-to-action

Nếu bạn đang là Junior BA/PM và cảm thấy khó xử mỗi khi khách hàng "ép" ký gấp — đây là 3 thứ cần chuẩn bị từ bây giờ:

1. **Template Exclusions**: Luôn có sẵn mục "Không bao gồm" trong mọi proposal/báo giá
2. **Câu nói sẵn sàng**: *"Phần này cần thêm X ngày để estimate chính xác — chúng ta ký phần còn lại trước được không?"*
3. **Estimate thực tế**: Đừng để scope mờ mà không có con số — dù thô, dù có khoảng dao động, cũng cần có

Bạn đã từng gặp tình huống tương tự chưa? Comment cho tôi biết — mình có thể chia sẻ thêm cách xử lý cụ thể.

---

## Meta Notes (không đăng)

- **Độ dài ước tính**: ~450 từ — phù hợp LinkedIn long-form post
- **Format khi đăng**: Bỏ headers, dùng line breaks tự nhiên, emoji nhẹ ở hook nếu muốn
- **Hashtags gợi ý**: #ProjectManagement #BusinessAnalyst #ITOutsourcing #CareerChange #ScopeManagement
- **Thời điểm đăng**: Thứ 3 hoặc Thứ 4, 8-9h sáng
- **Variant**: Có thể reformat thành blog post dài hơn với phần "Framework Scope Decoupling 3 bước"
