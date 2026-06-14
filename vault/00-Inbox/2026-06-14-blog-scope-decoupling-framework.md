---
title: "Scope Decoupling: Framework 3 bước để ký hợp đồng outsourcing mà không bị ép làm việc không công"
created: 2026-06-14
type: content-draft
status: draft
platform: Blog / LinkedIn Long-form
target_audience: Junior BA/PM, Career changers, IT freelancers
source_insight: "[[../01-Atomic/Insights/pm-insight-negotiation-scope-decoupling]]"
related_draft: "[[2026-05-31-linkedin-scope-decoupling]]"
---

# Scope Decoupling: Framework 3 bước để ký hợp đồng outsourcing mà không bị ép làm việc không công

---

Tôi đã học được bài này theo cách đắt nhất: sau nhiều dự án bị "vỡ" vì scope mờ.

Đây là tình huống cổ điển trong IT outsourcing:

> Khách hàng cần ký hợp đồng **ngay tuần này**. Deadline Go-live đang cận. Nhưng một phần scope vẫn còn mù mờ — chưa có tài liệu, chưa có design, thậm chí chưa có estimate.

Bạn đứng trước 2 lựa chọn đều tệ:

- **Ký gấp** → scope mờ → 3 tháng sau team ôm thêm việc không công, không có ngân sách, không có cơ sở từ chối
- **Đợi scope rõ hoàn toàn** → mất thêm 2-4 tuần → deadline bị trễ ngay từ đầu → team mất uy tín

**Scope Decoupling** là lối thoát thứ 3. Và đây là framework tôi dùng sau 15 năm làm IT outsourcing.

---

## Scope Decoupling là gì?

Đơn giản là: **ký phần đã rõ — tách phần chưa rõ**.

Thay vì chờ 100% scope sáng tỏ mới ký, hoặc ký gộp tất cả dù chưa rõ, bạn tách hợp đồng thành:

- **Base Contract**: Chỉ bao gồm scope đã có tài liệu đầy đủ, đã estimate được, đã cả hai bên hiểu rõ
- **Exclusions list**: Liệt kê tường minh những gì KHÔNG nằm trong hợp đồng này
- **Phụ lục / CR (Change Request)**: Dành cho scope chưa rõ — sẽ được bổ sung sau khi có đủ thông tin

---

## Framework 3 bước

### Bước 1: Phân loại scope thành 3 nhóm

Trước mọi cuộc đàm phán hợp đồng, hãy ngồi với team và phân loại:

| Nhóm | Điều kiện | Xử lý |
|------|-----------|-------|
| **Clear** | Có tài liệu, đã estimate, cả hai bên đồng thuận | Đưa vào Base Contract |
| **Fuzzy** | Khái niệm rõ nhưng chưa có spec/design cụ thể | Đưa vào Phụ lục, ký bổ sung sau |
| **Unknown** | Chưa được define, chưa có tài liệu, chưa estimate | Ghi vào Exclusions, không ký |

Bước này thường mất 30-60 phút nhưng tiết kiệm hàng tuần tranh cãi về sau.

### Bước 2: Viết Exclusions list tường minh

Đây là bước hầu hết Junior BA/PM bỏ qua — và đây cũng là bước quan trọng nhất.

Một Exclusions list tốt không chỉ nói "Chưa bao gồm Admin Portal" mà cần nói:

> *"Admin Portal module chưa được đưa vào hợp đồng này do chưa có tài liệu đặc tả cụ thể. Phạm vi và nguồn lực sẽ được đàm phán và ký bổ sung sau khi có đầy đủ tài liệu từ phía Client."*

Tại sao? Vì "chưa bao gồm" mà không giải thích rõ lý do sẽ dễ bị diễn giải thành "có thể thêm vào sau mà không cần ký bổ sung". Câu chữ cụ thể = ranh giới rõ ràng.

### Bước 3: Dùng deadline của khách hàng làm đòn bẩy ngược

Đây là phần phản trực giác nhất.

Khi khách hàng thúc ép *"Ký gấp vào, deadline Go-live tháng 8 gần rồi!"*, hầu hết Junior PM sẽ bị áp lực và nhượng bộ. Nhưng bạn có thể dùng chính deadline đó để bảo vệ scope:

> *"Đúng vì deadline Go-live tháng 8 rất gấp, nên chúng tôi không muốn mạo hiểm bằng cách nhận thêm phần Admin khi chưa có estimate chính xác. Nếu scope bị hiểu sai và cần làm thêm 10+ man-months, phần cốt lõi của dự án sẽ bị ảnh hưởng — điều đó ảnh hưởng trực tiếp đến timeline Go-live của anh/chị."*

Khi dùng deadline của họ làm lý do, bạn không còn là người "khó tính" hay "trì hoãn". Bạn đang bảo vệ dự án của họ.

---

## Case study thực tế: KBC Community (2026)

Tháng 5/2026, chúng tôi đang triển khai **KBC Community** — nền tảng cộng đồng nhà đầu tư nhúng vào app giao dịch chứng khoán của KBC, đối tác phía Hàn là Quantit. Team 15 người, deadline Go-live tháng 9.

Tình huống xảy ra: Quantit muốn ký hợp đồng ngay để kịp deadline, nhưng phần **Admin Portal** chưa có tài liệu — design còn viết bằng tiếng Hàn, chưa có spec tiếng Anh hay tiếng Việt.

Lập luận của họ: *"Admin scope nhỏ hơn trong RFP, team hiện tại làm được, không cần thêm người."*

Estimate thực tế của chúng tôi: **10.5 Man-Months**.

Không phải con số nhỏ. Và nếu ký gộp mà không định nghĩa rõ, 10.5 MM đó sẽ rơi vào vùng xám — team phải làm nhưng không có ngân sách, không có quyền từ chối nếu scope bị "phình" thêm.

**Cách chúng tôi xử lý:**
1. Đồng ý ký Base Contract cho tất cả phần đã có spec đầy đủ
2. Thêm Exclusions list: *"Admin Portal module chưa được đưa vào do chưa có tài liệu đặc tả từ Quantit/KBC"*
3. Admin Portal → Phụ lục, sẽ ký bổ sung trong tháng 6 khi đủ tài liệu

Kết quả: Dự án khởi động đúng hạn. Team có căn cứ rõ ràng nếu Admin scope bị mở rộng về sau. Quantit cũng hiểu rằng họ cần cung cấp tài liệu trước — đây là trách nhiệm của họ, không phải của chúng tôi.

---

## 3 công cụ cần chuẩn bị ngay hôm nay

Nếu bạn đang làm BA/PM trong outsourcing, đây là 3 thứ cần có sẵn:

**1. Template Exclusions chuẩn**
Mẫu câu: *"The following items are explicitly excluded from this contract's scope: [list]. These will be addressed via separate addendum or Change Request upon receipt of complete specifications."*

**2. Câu "sẵn sàng dùng" khi bị thúc ký**
*"Phần [X] cần thêm [N] ngày để estimate chính xác — chúng ta ký phần còn lại trước, đảm bảo dự án không bị delay, rồi bổ sung phần này trong tuần tới?"*

**3. Estimate thô với khoảng dao động**
Dù chưa có spec rõ, bạn vẫn cần một con số — dù là khoảng. Ví dụ: *"Ước tính thô: 8-15 MM, cần spec cụ thể để narrow down."* Con số thô còn tốt hơn không có số, vì nó thay đổi cuộc đàm phán từ "chắc nhỏ thôi" thành "à, phức tạp hơn tôi nghĩ."

---

## Kết

Scope Decoupling không phải là kỹ thuật "khó" — nó là một tư duy: **tách biệt cái đã rõ khỏi cái chưa rõ, và xử lý từng phần đúng lúc.**

Sau 15 năm, tôi thấy Junior BA/PM thường thua không phải vì thiếu kỹ năng kỹ thuật mà vì thiếu ngôn ngữ và framework để nói "không" (hoặc "chưa") một cách chuyên nghiệp.

Đây là một trong những framework đó.

---

Bạn đã từng gặp tình huống khách hàng ép ký gấp chưa? Mình muốn nghe cách bạn xử lý — comment bên dưới.

---

## Meta Notes (không đăng)

- **Độ dài**: ~900 từ — phù hợp blog post hoặc LinkedIn newsletter
- **Format khi đăng LinkedIn**: Bỏ headers H2/H3, dùng bold + line breaks tự nhiên. Table có thể giữ hoặc chuyển thành bullet list.
- **Hashtags gợi ý**: #ProjectManagement #BusinessAnalyst #ITOutsourcing #ScopeManagement #CareerTips #PMTips
- **SEO title option**: "Cách ký hợp đồng outsourcing khi scope chưa rõ — Framework thực tế từ dự án Hàn-Việt"
- **Thời điểm đăng**: Thứ 3 hoặc Thứ 4, 8-9h sáng
- **Cross-post**: LinkedIn (long-form) → rút gọn thành short post → link blog
- **LinkedIn short version**: Đã có ở `2026-05-31-linkedin-scope-decoupling.md` — nên đăng ngắn trước, blog sau
