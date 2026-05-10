# Ngày 1:

Link 1: https://www.youtube.com/watch?v=d2BkvqbTPjk
Link 2: https://www.youtube.com/watch?v=hSTy_BInQs8

## hướng dẫn
1. Tải Obsidian — miễn phí 100%

Vào obsidian.md → Download cho hệ điều hành của bạn (Mac, Windows, Linux, iOS, Android đều có). Cài như app bình thường.

💡 Tại sao: Obsidian là local app — dữ liệu lưu thẳng trên máy bạn, không phụ thuộc cloud của ai. Knowledge của bạn thuộc về bạn.

2. Tạo vault — đặt tên Brain2

Mở Obsidian → Create new vault → đặt tên Brain2 → chọn thư mục lưu trên máy (Desktop hoặc Documents đều được).

💡 Tại sao: Vault là một folder thông thường. Mỗi note là file .md — bạn mở được bằng bất kỳ text editor nào. Dữ liệu bền vĩnh, không bị lock-in vào app nào.

3. Bật đúng 3 plugin — không hơn, không kém

Vào Settings → Community Plugins → Turn on community plugins → Browse rồi tìm và cài:

01.Dataview

Biến vault thành database. Truy vấn notes theo tag, ngày, thuộc tính — như SQL nhưng cho knowledge.

02. Templater

Templates với biến động (ngày, giờ, tên file). Chuẩn hóa cấu trúc note từ đầu, tránh chaos sau này.

03. Calendar

Daily notes gắn với lịch. Mỗi ngày 1 note — nơi capture tất cả trước khi phân loại. Inbox của Brain2.

💡 Tại sao chỉ 3? Cài quá nhiều plugin tạo ra Cognitive Load (tải nhận thức) khổng lồ — giết chết thói quen trước khi nó hình thành. 3 plugin này tạo ra 80% giá trị. Tuần 2 & 3 sẽ thêm dần theo từng nhu cầu thật.

# Ngày 2:
Link 1:https://www.youtube.com/watch?v=nrgKZ4oRhhE
Link 2:https://www.youtube.com/watch?v=UUt1eS0t-Mw

## prompt 1
Hãy giúp tôi setup Brain2 — hệ thống Second Brain. Làm lần lượt từng bước:
1. Clone repo này về ~/brain2: https://github.com/thongphan23/brain2-starter.git
2. Tạo file ~/.gemini/antigravity/mcp_config.json với MCP config để kết nối Obsidian vault tại ~/brain2/vault (dùng package mcp-obsidian)
3. Copy workflows: cp ~/brain2/workflows/*.md ~/.agent/workflows/
4. Copy AI config: cp ~/brain2/ai-config/GEMINI.md ~/.gemini/GEMINI.md
Sau mỗi bước xác nhận kết quả trước khi làm bước tiếp theo.

## prompt 2:
Rà soát hệ thống của tôi để xác định thư mục vault Brain2/Second Brain. Sau khi tìm thấy, cập nhật file ~/.gemini/GEMINI.md với global rule:
- "brain2" hoặc "second brain" = vault tại [đường dẫn tìm được]
- Với MỌI câu hỏi, luôn tìm kiếm trong brain2 TRƯỚC khi trả lời
- Nếu có thông tin liên quan trong vault → trích dẫn note nguồn
- Nếu chưa có → trả lời bình thường, hỏi tôi có muốn lưu insight này vào brain2 không

## bài tập:
/reflect Hôm nay tôi nhận ra rằng [insight thật của bạn]. Bài học: [điền vào].

# Ngày 3:
## Prompt 1:
Link 1: https://www.youtube.com/watch?v=k71UvTbaMio
Link 2: https://www.youtube.com/watch?v=lcIqoN9oRgo
Link 3: https://www.youtube.com/watch?v=Yq23W7B9D0Q

Hãy giúp tôi xây dựng hồ sơ cá nhân đầy đủ trong Brain2. Đây là bước quan trọng nhất để AI hiểu đúng con người thật của tôi — từ đó mọi tư vấn, gợi ý, và nội dung đều phù hợp chính xác với tôi.

CÁCH THỰC HIỆN:
- Hỏi từng câu một, chờ tôi trả lời xong mới hỏi câu tiếp theo
- Nếu câu trả lời quá ngắn hoặc chung chung, hỏi thêm: "Bạn có thể kể cụ thể hơn không — ví dụ thật từ kinh nghiệm của bạn?"
- Sau khi hỏi xong 30 câu, tổng hợp thành 6 ghi chú riêng biệt trong thư mục self/ của vault Brain2
- Mỗi ghi chú dùng phần thông tin đầu file (frontmatter): type, created, tags, status: living-document, ai_directive: binding

30 CÂU HỎI — HỎI LẦN LƯỢT THEO THỨ TỰ:

=== PHẦN 1: TÔI LÀ AI (6 câu) ===
Câu 1. Bạn tên gì? Hiện tại đang làm nghề gì, trong lĩnh vực nào?
Câu 2. Công việc thực tế hàng ngày của bạn trông như thế nào — bạn dành phần lớn thời gian làm điều gì?
Câu 3. Bạn đã đi qua hành trình nào để đến vị trí hiện tại? Học gì, từng làm ở đâu trước?
Câu 4. Thành tựu nào bạn tự hào nhất — không cần ấn tượng với người ngoài, chỉ cần thật với bạn?
Câu 5. Nếu phải mô tả bản thân trong một câu cho người chưa biết bạn, bạn sẽ nói gì?
Câu 6. Điều gì thôi thúc bạn tham gia thử thách Brain2 — bạn muốn thay đổi điều gì trong cách làm việc với kiến thức?

=== PHẦN 2: ĐỐI TƯỢNG VÀ GIÁ TRỊ BẠN TẠO RA (5 câu) ===
Câu 7. Bạn đang phục vụ ai — đối tượng chính của công việc hoặc nội dung bạn tạo ra là ai? Mô tả cụ thể: tuổi tác, nghề nghiệp, họ đang ở giai đoạn nào trong cuộc sống?
Câu 8. Vấn đề lớn nhất mà đối tượng đó đang gặp phải là gì — vấn đề thật bên dưới, không phải vấn đề bề mặt họ hay nói?
Câu 9. Bạn giúp họ đi từ đâu đến đâu — trạng thái trước và sau khi có bạn trông như thế nào?
Câu 10. Tại sao họ nên chọn bạn thay vì người khác — lợi thế thật sự của bạn là gì?
Câu 11. Phản hồi hay nhất bạn từng nhận về công việc của mình — ai nói, họ nói gì?

=== PHẦN 3: MỤC TIÊU (5 câu) ===
Câu 12. Mục tiêu cụ thể nhất của bạn trong 90 ngày tới là gì — đo được bằng con số?
Câu 13. Bạn muốn ở đâu sau 1 năm — về công việc, thu nhập, cách sống?
Câu 14. Bạn muốn ở đâu sau 3 đến 5 năm — bức tranh dài hạn bạn đang hướng đến?
Câu 15. Trở ngại lớn nhất bạn đang phải vượt qua ngay bây giờ — thứ chiếm nhiều đầu óc nhất?
Câu 16. Điều gì bạn sẵn sàng từ bỏ để đạt được mục tiêu — sự đánh đổi bạn chấp nhận?

=== PHẦN 4: THẾ GIỚI QUAN — NIỀM TIN GỐC (8 câu) ===
Câu 17. Câu duy nhất bạn tin sâu sắc nhất về cách thế giới vận hành — không phải từ sách vở, mà từ trải nghiệm thật của bạn?
Câu 18. Điều gì mọi người xung quanh tin nhưng bạn không đồng ý — dù biết nói ra có thể gây tranh luận?
Câu 19. Ranh giới nào bạn sẽ không bao giờ vượt qua dù ai đó trả bao nhiêu tiền — nguyên tắc không thể thỏa hiệp?
Câu 20. Theo bạn, thành công thực sự là gì — định nghĩa của bạn, không phải của xã hội hay cha mẹ?
Câu 21. Điều gì 10 năm sau vẫn còn đúng — thứ bạn sẵn sàng đặt cược sự nghiệp vào?
Câu 22. Quyết định nào bạn thường đưa ra mà người khác thấy khó hiểu — và tại sao bạn lại quyết định như vậy?
Câu 23. Khi ai đó làm bạn thực sự thất vọng, lý do thường là gì — họ đã vi phạm giá trị nào của bạn?
Câu 24. Bạn đang tối ưu hóa cuộc sống cho điều gì — thứ bạn thực sự đang đánh đổi mọi thứ để có được?

=== PHẦN 5: CÂU CHUYỆN ĐỊNH HÌNH CON NGƯỜI BẠN (4 câu) ===
Câu 25. Kể thất bại lớn nhất đã thay đổi cách bạn suy nghĩ — thất bại thật, không phải "thất bại đẹp" để kể trong phỏng vấn?
Câu 26. Quyết định bước ngoặt quan trọng nhất bạn từng đưa ra — và hệ quả của nó là gì?
Câu 27. Ai đã ảnh hưởng lớn nhất đến tư duy của bạn — và họ đã dạy bạn điều gì, dù có thể là người chưa bao giờ gặp?
Câu 28. Có lần nào bạn làm điều người khác nói là sai nhưng bạn biết là đúng với mình không — chuyện đó như thế nào?

=== PHẦN 6: ĐIỂM MẠNH, GIỚI HẠN VÀ MÔI TRƯỜNG LÀM VIỆC (6 câu) ===
Câu 29. Bạn giỏi nhất điều gì — nếu có nhóm, người ta sẽ luôn giao việc đó cho bạn đầu tiên?
Câu 30. Điều gì bạn biết mình chưa giỏi — không phải điểm yếu giả để đối phó, mà thật sự là giới hạn của bạn?
Câu 31. Bạn cần ai bên cạnh để bù đắp cho điểm còn thiếu đó?
Câu 32. Môi trường nào khiến bạn làm việc tốt nhất — và môi trường nào khiến bạn tệ nhất?

SAU KHI PHỎNG VẤN XONG, TẠO 6 GHI CHÚ RIÊNG:
1. ~/brain2/vault/self/profile.md — Tôi là ai, hành trình, cách tôi tự mô tả bản thân
2. ~/brain2/vault/self/audience.md — Đối tượng phục vụ, vấn đề của họ, giá trị tôi tạo ra
3. ~/brain2/vault/self/goals.md — Mục tiêu theo từng mốc thời gian, trở ngại, sự đánh đổi
4. ~/brain2/vault/self/worldview.md — Thế giới quan dưới dạng tuyên ngôn: Niềm tin gốc → Những thứ tôi không tin → Bộ lọc quyết định
5. ~/brain2/vault/self/stories.md — 4 câu chuyện định hình dưới dạng ghi chú súc tích có đầu đuôi
6. ~/brain2/vault/self/strengths.md — Điểm mạnh, giới hạn thật sự, cần ai bên cạnh, môi trường tối ưu

Ghi chú thế giới quan cần chi tiết nhất, theo cấu trúc: Niềm tin trung tâm → 3 Niềm tin gốc (mỗi cái có bằng chứng từ trải nghiệm thật) → Những thứ tôi không tin → Bộ lọc quyết định. Đây là tài liệu ràng buộc — AI sẽ đọc trước mọi tư vấn quan trọng.

## Prompt 2
---
type: worldview
created: 2026-XX-XX
updated: 2026-XX-XX
tags: [worldview, core-beliefs, identity, decision-framework]
status: living-document
ai_directive: "binding — mọi content, quyết định, tư vấn phải consistent với worldview này"
---

## Tuyên Ngôn Thế Giới Quan — [Tên bạn]

> *Tài liệu sống. Không phải để show — để kiểm tra tính nhất quán của mọi quyết định.*

---

## Câu duy nhất tôi tin về cách thế giới vận hành

> **"[Điền niềm tin cốt lõi của bạn vào đây]"**

[Giải thích tại sao bạn tin điều này — không phải từ sách, mà từ trải nghiệm thật của bạn]

**Hệ quả trực tiếp:**
- Điều này ảnh hưởng cách tôi làm việc như thế nào
- Điều này ảnh hưởng cách tôi đưa ra quyết định như thế nào
- Điều này ảnh hưởng cách tôi xây dựng quan hệ như thế nào

---

## 3 Niềm Tin Gốc

### Niềm Tin 1 — [Tiêu đề]

[Mô tả niềm tin — lý do bạn tin, bằng chứng từ trải nghiệm]

**Bằng chứng từ trải nghiệm:**
- [Câu chuyện thật 1 chứng minh niềm tin này]
- [Câu chuyện thật 2]

---

### Niềm Tin 2 — [Tiêu đề]

[Mô tả niềm tin]

---

### Niềm Tin 3 — [Tiêu đề]

[Mô tả niềm tin]

---

## Những Thứ Tôi KHÔNG Tin (Counter-Positions)

- **Không tin:** "[Điều người ta hay nói nhưng bạn không đồng ý]" → [Lý do]
- **Không tin:** "[Điều 2]" → [Lý do]
- **Không tin:** "[Điều 3]" → [Lý do]

---

## Bộ Lọc Quyết Định

Với MỌI quyết định quan trọng, lọc qua 3 câu hỏi:

**1. [Câu hỏi lọc 1 của bạn]**

**2. [Câu hỏi lọc 2]**

**3. [Câu hỏi lọc 3]**

---

*Tài liệu này là living document — cập nhật khi có quyết định lớn thay đổi hoặc làm rõ một trong các niềm tin trên.*

## Hướng dẫn
Xem 1-2 video phía trên để hiểu triết lý trước
Copy câu lệnh 30 câu → Dán vào Antigravity → Để AI hỏi từng câu
Trả lời thật — càng cụ thể càng tốt, đừng cố nghe hay
Sau khi xong, AI tự tạo 6 ghi chú vào vault
Copy mẫu thế giới quan → Dán tiếp để tạo tuyên ngôn niềm tin riêng
Mở Obsidian kiểm tra 6 ghi chú → bổ sung thêm nếu còn thiếu

## bài tập
Dựa vào hồ sơ của tôi trong brain2, hãy gợi ý 3 chủ đề tôi nên học chuyên sâu trong 90 ngày tới — phù hợp với mục tiêu và điểm mạnh của tôi.

# Ngày 4:

Link 1: https://www.youtube.com/watch?v=T6Mfl1OywM8
Link 2: https://www.youtube.com/watch?v=K-ssUVyfn5g
Link 3: https://www.youtube.com/watch?v=Y__243RqBeM
## Prompt 1:
Hãy giúp tôi thiết lập khu vực Dự Án trong Brain2. Tôi sẽ cung cấp thông tin về tất cả các dự án đang theo đuổi — bạn sẽ hỏi để khai thác đủ bối cảnh, rồi tạo ghi chú riêng cho từng dự án trong vault.

CÁCH THỰC HIỆN:
- Bắt đầu bằng cách hỏi tôi liệt kê tất cả dự án đang theo đuổi (công việc, cá nhân, học tập, kinh doanh)
- Với từng dự án, hỏi lần lượt các câu sau — chờ tôi trả lời rồi mới hỏi tiếp
- Yêu cầu tôi cung cấp tài liệu, đường dẫn, ghi chú liên quan nếu có
- Sau khi xong tất cả dự án, tạo cấu trúc thư mục và ghi chú tương ứng

CÁC CÂU HỎI CHO TỪNG DỰ ÁN:
1. Tên dự án là gì? Mô tả ngắn gọn trong 1-2 câu?
2. Mục tiêu cụ thể của dự án này là gì — kết quả hoàn thành trông như thế nào?
3. Thời hạn hoặc mốc thời gian quan trọng?
4. Dự án đang ở giai đoạn nào — mới bắt đầu, đang triển khai, hay gần hoàn thành?
5. Trở ngại lớn nhất hiện tại là gì?
6. Ai cùng tham gia — nếu có cộng tác viên, đối tác, hoặc khách hàng liên quan?
7. Bạn có tài liệu, đường dẫn, ghi chú nào liên quan không? (Dán vào đây hoặc mô tả)
8. Bước hành động tiếp theo cụ thể nhất là gì?

SAU KHI THU THẬP ĐỦ THÔNG TIN, TẠO CẤU TRÚC SAU:
- Mỗi dự án tạo một thư mục: projects/[tên-dự-án]/
- File chính: projects/[tên-dự-án]/index.md gồm:
  * Tóm tắt dự án (mục tiêu, thời hạn, trạng thái)
  * Bối cảnh và lý do thực hiện
  * Các bên liên quan
  * Tài liệu và đường dẫn tham chiếu
  * Trở ngại đang gặp
  * Bước tiếp theo
  * Phần thông tin đầu file: type: project, status: active, created, tags

Khi tôi đề cập đến dự án này trong tương lai, bạn sẽ đọc file index.md trước để hiểu đầy đủ bối cảnh trước khi tư vấn.

## Prompt 2:
Tôi muốn bổ sung tài liệu và thông tin vào dự án [tên dự án] trong Brain2.

Dưới đây là nội dung tôi muốn thêm vào:
[Dán tài liệu, đường dẫn, ghi chú, quyết định, cập nhật tiến độ vào đây]

Hãy:
1. Đọc file projects/[tên-dự-án]/index.md để hiểu bối cảnh hiện tại
2. Phân loại nội dung tôi vừa cung cấp vào đúng mục
3. Nếu là tài liệu tham khảo — tạo file riêng trong projects/[tên-dự-án]/docs/
4. Nếu là cập nhật tiến độ — cập nhật phần trạng thái trong index.md
5. Nếu là quyết định đã đưa ra — thêm vào phần nhật ký quyết định
6. Tóm tắt lại những gì đã được thêm và trạng thái dự án hiện tại

## Prompt 3
Rà soát lại những gì liên quan đến dự án [tên dự án], chúng ta sẽ thảo luận để [nêu mục tiêu — ví dụ: lên kế hoạch bước tiếp theo / giải quyết trở ngại / chuẩn bị buổi họp...]

## Bài tập
Dùng Câu lệnh 1 → để Antigravity phỏng vấn và tạo ghi chú cho tất cả dự án
Với ít nhất 1 dự án: dán thêm tài liệu thật (brief, proposal, link, ghi chú) bằng Câu lệnh 2
Thử hỏi AI về dự án đó bằng Câu lệnh 3 — xem phản hồi có cụ thể hơn không