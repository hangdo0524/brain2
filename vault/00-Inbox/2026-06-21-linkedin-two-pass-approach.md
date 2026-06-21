---
title: "Đôi khi làm 2 bước mới nhanh — bài học từ cổng dịch vụ công cho BA/PM"
created: 2026-06-21
type: content-draft
status: draft
platform: LinkedIn
target_audience: Junior BA/PM, Career changers, IT freelancers
source_insight: "[[../01-Atomic/Insights/life-insight-kinh-nghiem-quyet-toan-thue]]"
---

# Draft: Two-Pass Approach — Khi hệ thống có bộ lọc tự động

---

## Hook

Tôi mất 3 tiếng loay hoay với cổng thuế điện tử. Nộp lỗi. Nộp lại lỗi. Cán bộ thuế gọi điện cũng không giải thích được tại sao hệ thống reject.

Rồi một người chỉ tôi "luật ngầm": **nộp tờ khai trắng trước — đừng kèm hồ sơ giảm trừ ngay lần đầu.**

Nghe vô lý. Nhưng nó hoạt động. Và sau đó tôi nhận ra: mình đã làm sai điều này trong cả quản lý dự án — không chỉ ở cổng thuế.

---

## Insight chính

Có một loại hệ thống mà nếu bạn cố "làm trọn một lần" — bạn sẽ bị reject tự động. Không có lý do rõ ràng. Không có hướng dẫn sửa. Chỉ là lỗi.

Lý do: **bộ lọc tự động của hệ thống kiểm tra technical pass trước — và nếu fail ở bước đó, nó không xử lý phần còn lại.**

Giải pháp là **Two-Pass Approach** — chia nhỏ quy trình thành 2 lượt:

> **Lượt 1**: Vượt bộ lọc kỹ thuật — submit phần tối thiểu để hệ thống/người tiếp nhận "chấp nhận" đầu vào.
> **Lượt 2**: Bổ sung chi tiết nghiệp vụ — sau khi đã qua vòng gửi xe.

---

## Ví dụ thực tế

### Trong cuộc sống: Thuế TNCN
Hệ thống thuế điện tử có bộ lọc tự động kiểm tra "nơi cư trú" và "thẩm quyền cơ quan thuế". Nếu nộp luôn hồ sơ giảm trừ ngay lần đầu → hệ thống reject toàn bộ, lý do mơ hồ, làm lại từ đầu.

Cách đúng: nộp tờ khai trắng (không kèm giảm trừ) để pass bộ lọc → sau đó nộp bổ sung hồ sơ giảm trừ.

### Trong BA/PM: Approval chains
Bạn có 1 Change Request phức tạp cần stakeholder duyệt. Nếu bạn gửi ngay bản CR 5 trang với đầy đủ analysis, impact, cost — nhiều khả năng bạn sẽ nhận được: silence (họ chưa có thời gian đọc), hoặc reject phản xạ (quá nhiều thông tin, họ không hiểu phải duyệt cái gì).

Two-Pass: Gửi trước 1 email 3 dòng — *"Em muốn propose thay đổi nhỏ ở flow X, có ảnh hưởng đến team Y. Anh/chị có 10 phút để em brief qua không?"* → sau khi có ý kiến "okay, nghe đi" → mới gửi CR đầy đủ.

### Trong IT freelance: Client proposal
Đừng bao giờ gửi proposal 20 trang cho một client còn đang "tìm hiểu". Họ sẽ không đọc. Two-Pass: gửi 1 trang executive summary trước để confirm họ quan tâm đúng vấn đề — rồi mới gửi proposal chi tiết cho người đã sẵn sàng đọc.

---

## Tại sao điều này không hiển nhiên?

Vì chúng ta được dạy rằng "chuẩn bị kỹ = kết quả tốt hơn". Và đúng — nhưng chỉ khi hệ thống nhận đầu vào của bạn sẵn sàng xử lý nó.

Khi hệ thống có bộ lọc tự động (dù là phần mềm hay là phản xạ tâm lý của con người), thông tin quá đầy đủ ngay từ đầu có thể là lý do bị reject — không phải là lợi thế.

**Chậm lại ở bước 1 là cách đi nhanh nhất đến bước 2.**

---

## Call-to-action

Tuần tới, trước khi bạn nộp một CR, submit một proposal, hoặc gửi một tài liệu phức tạp — thử hỏi: *"Tôi có đang cố làm trọn một lần với một hệ thống chưa sẵn sàng nhận không?"*

Nếu có, hãy thử Two-Pass.

Bạn đã từng bị stuck trong một quy trình "gửi một lần mà không biết sửa ở đâu" chưa? Comment chia sẻ — mình đoán nhiều người cũng đang gặp.

---

## Meta Notes (không đăng)

- **Độ dài ước tính**: ~500 từ — phù hợp LinkedIn long-form post
- **Format khi đăng**: Bỏ headers, dùng line breaks tự nhiên, giữ bold cho key terms
- **Hashtags gợi ý**: #ProjectManagement #BusinessAnalyst #CareerChange #ProductivityTips #ITFreelance
- **Thời điểm đăng**: Thứ 3 hoặc Thứ 4, 8-9h sáng
- **Strength của post này**: Hook từ personal story (dễ relate) → abstraction → 3 ví dụ cụ thể cho đúng 3 audience segments
- **Potential improvement**: Có thể thêm ví dụ từ ConstructHub (submit spec) hoặc Kigg (client onboarding) để tăng thực chiến
- **Next step**: Có thể phát triển thành series "Những bài học outsourcing không ai dạy bạn"
