---
title: "Đàm phán tách biệt phạm vi (Scope Decoupling) để bảo đảm tiến độ và nguồn lực"
created: 2026-05-08
updated: 2026-05-08
type: insight
status: atomic
source: "Trải nghiệm thực tế dự án KBC/Quantit"
discovered_from: "Negotiation with Sukju Hwang regarding Admin scope"
confidence: high
related: []
used_count: 1
used_in:
  - "[[../../00-Inbox/2026-05-31-linkedin-scope-decoupling]]"
tags: ["negotiation", "project-management", "outsourcing", "scope-creep"]
maturity: seed
review_interval: 14
next_review: 2026-05-22
reuse_count: 0
evolution_log:
  - date: 2026-05-08
    change: "Tạo lần đầu từ tình huống thực tế dự án KBC"
---

# Đàm phán tách biệt phạm vi (Scope Decoupling) để bảo đảm tiến độ và nguồn lực

## The Insight

Khi đối tác muốn ký hợp đồng gấp nhưng một phần phạm vi (scope) chưa rõ ràng, chiến thuật tốt nhất là **Đồng ý ký hợp đồng cho phần đã rõ ràng (Base Scope)** và **Tách biệt phần chưa rõ ràng vào Phụ lục/CR (Decoupling)**. Điều này giúp dự án bắt đầu ngay mà vẫn bảo vệ được nguồn lực của team trước nguy cơ bị ép làm thêm việc không công do áp lực deadline.

## Evidence

### Observation 1
- Trong dự án KBC/Quantit (tháng 5/2026), đối tác muốn ký hợp đồng ngay để kịp deadline Go-live tháng 8 nhưng phần Admin Portal chưa có tài liệu cụ thể.
- Đối tác đưa ra lập luận: *"Phạm vi Admin nhỏ hơn RFP, có thể làm với nhân sự hiện tại mà không cần thêm người"* nhằm mục đích khóa ngân sách sớm.

### Observation 2
- Ước tính của team cho phần Admin là 10.5 MM (Man-Months), một con số đáng kể. Nếu chấp nhận ký "gộp" mà không có định nghĩa rõ ràng, rủi ro vỡ tiến độ hoặc thiếu hụt nguồn lực là cực lớn.

## Implications

- Nếu điều này đúng thì việc trì hoãn ký hợp đồng toàn bộ chỉ làm tình hình tệ hơn (mất thêm thời gian chuẩn bị).
- Việc tách bạch giúp thiết lập một "Line in the Sand" (Ranh giới rõ ràng): Những gì không nằm trong Base Contract thì mặc nhiên là Change Request.

## Applications

- **Áp dụng vào Outsourcing:** Luôn liệt kê rõ những phần "Exclusions" (Không bao gồm) trong báo giá và hợp đồng chính.
- **Áp dụng vào Quản lý kỳ vọng:** Sử dụng deadline Go-live của khách hàng làm đòn bẩy ngược: *"Nếu làm thêm việc này mà không có thêm người, rủi ro hỏng deadline Go-live của phần cốt lõi là rất cao"*.

## Counter-arguments

- Tuy nhiên, khách hàng có thể cảm thấy phiền phức vì phải làm nhiều thủ tục giấy tờ (ký nhiều lần).
- Ngoại lệ khi mối quan hệ đối tác đã cực kỳ bền chặt và có cơ chế "back-log" bù trừ linh hoạt ở các giai đoạn sau.

## Related

- [[pm-framework-change-request-management]]
- [[pm-concept-man-month-estimation]]
