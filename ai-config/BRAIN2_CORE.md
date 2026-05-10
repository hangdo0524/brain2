# BRAIN2 CORE SYSTEM — THE SINGLE SOURCE OF TRUTH

## PHẦN 1: ĐỊNH NGHĨA & NGUYÊN TẮC CỐT LÕI (CORE PRINCIPLES)

Brain2 = hệ thống quản lý tri thức cá nhân trong Obsidian vault, bao gồm:
1. **Obsidian vault** — tri thức gốc, atomic notes (Đường dẫn gốc: `/Users/hangdo/brain2/vault`)
2. **Obsidian MCP** — AI đọc/ghi vault qua MCP protocol

Từ khóa **"brain2"** hoặc **"second brain"** mà người dùng nhắc tới chính là vault tại `/Users/hangdo/brain2/vault`.

### Nguyên tắc Brain2-first (BẮT BUỘC)

Khi người dùng hỏi bất kỳ điều gì liên quan đến kiến thức, trải nghiệm, hoặc tri thức:

1. **Bước 1 — Search vault TRƯỚC**: dùng Obsidian MCP (`search-vault`, `search-by-tags`, `search-by-title`) để tìm notes liên quan
2. **Bước 2 — Đọc chi tiết**: dùng `read-note` để đọc full nội dung notes tìm được
3. **Bước 3 — Tổng hợp**: kết hợp kiến thức vault + kiến thức AI → trả lời

- Knowledge đã có trong vault → **dùng nó**. Chưa có → nghiên cứu + tạo mới
- **KHÔNG ĐƯỢC** bỏ qua vault search. Vault chứa tri thức cá nhân quý giá mà AI không thể biết.

### Proactive Reflection Capture

- Trong BẤT KỲ cuộc hội thoại nào, nếu người dùng nói gì mang tính **insight / suy ngẫm / bài học**, chủ động hỏi: *"Cái này hay — lưu vào Brain2 không?"*
- Đồng ý → chạy workflow `/reflect` ngay. "Khoan" → bỏ qua.

## PHẦN 2: KIẾN TRÚC HỆ THỐNG (SYSTEM ARCHITECTURE)

### Vault Structure

```
vault/
├── 00-Inbox/              ← Raw thoughts chưa xử lý
├── 01-Atomic/             ← Knowledge atoms đã chuẩn hóa
│   ├── Stories/           ← Câu chuyện thật (Wisdom layer)
│   ├── Concepts/          ← Khái niệm (Information layer)
│   ├── Insights/          ← Nhận thức sâu (Knowledge layer)
│   ├── Frameworks/        ← Mô hình tư duy (Knowledge layer)
│   ├── Quotes/            ← Trích dẫn (Data layer)
│   ├── Reflections/       ← Suy ngẫm cá nhân
│   ├── People/            ← CRM
│   ├── Resources/         ← Sách, khóa học
│   └── Research/          ← Nghiên cứu sâu
├── 02-Sources/            ← Raw sources
├── 03-MOCs/               ← Maps of Content
└── _Templates/            ← Templates chuẩn
```

### Naming Convention

`{topic}-{type}-{slug}.md`

- ⚠️ **BẮT BUỘC:** Tên file và tên thư mục (đặc biệt là phần `slug`) **PHẢI 100% bằng tiếng Anh**, viết chữ thường, nối bằng dấu gạch ngang (kebab-case). 
- **Tuyệt đối KHÔNG** dùng tiếng Việt (kể cả tiếng Việt không dấu) cho tên file. 
  *Ví dụ đúng: `parenting-story-bedtime-crisis.md`*
  *Ví dụ sai: `parenting-story-khung-hoang-gio-ngu.md`*
- **Độ dài thư mục:** Tối đa 1-2 từ (dưới 20 ký tự), dùng danh từ chung.
- **Độ dài tên file:** Phần `slug` chỉ dùng 3-5 từ khóa (keywords) cốt lõi nhất. Tổng độ dài tên file KHÔNG vượt quá 60 ký tự để tối ưu việc gõ liên kết `[[ ]]` và hiển thị UI.
- **Dấu nối (Hyphens vs Underscores):**
  - Dùng dấu gạch ngang (`-`) cho **Content Notes** (file nội dung như câu chuyện, khái niệm, dự án). VD: `parenting-story-bedtime-crisis.md`
  - Dùng dấu gạch dưới (`_`) và CHỮ HOA cho **System Files / Folders** (file/thư mục hệ thống, cấu hình) để chúng tự động hiển thị ở đầu/cuối danh sách. VD: `BRAIN2_CORE.md`, `_Templates`, hoặc `_SAMPLE-career-story.md` (nếu là file mẫu).
- Nội dung bên trong file (Tiêu đề H1, nội dung văn bản) vẫn dùng tiếng Việt bình thường.
- Topics: career, content, productivity, mindset, relationship, decision, learning, business, marketing, writing, life, philosophy, money, health, technology
- Types: concept, insight, framework, story, quote, reflection

## PHẦN 3: TIÊU CHUẨN ĐẦU VÀO (INPUT & CREATION RULES)

### Note Creation Rules

1. Luôn tạo notes theo template trong `_Templates/`
2. Luôn cross-link với ≥ 2 notes hiện có
3. Frontmatter YAML đầy đủ theo template
4. Trình bày nội dung note TRONG CHAT — người dùng không cần mở Obsidian để đọc

## PHẦN 4: VẬN HÀNH & ĐẦU RA (OPERATIONS & OUTPUTS)

### Workflows có sẵn

| Lệnh | Mô tả |
|---|---|
| `/reflect [suy ngẫm]` | Bắt insight nhanh → atomic note |
| `/deep-research [chủ đề]` | Nghiên cứu sâu + atomize vào vault |
| `/brain-gym` | Ôn luyện tri thức hàng ngày |
| `/story-bank [story]` | Nhập câu chuyện → structured atom |
| `/keystone-scan` | Gap analysis → gợi ý concept mới |
| `/spaced-usage [bài/vấn đề]` | Dùng tri thức cũ trong context mới |

### Viết Content từ Brain2 (AI Content Factory)

Khi người dùng muốn viết content:
1. **Scan vault** tìm Stories, Insights, Concepts liên quan
2. **Inject theo DIKW layers:**
   - WISDOM (Stories) → dùng trực tiếp, rewrite theo giọng người dùng
   - KNOWLEDGE (Insights, Frameworks) → backbone cho deep dive
   - INFORMATION (Concepts) → giải thích thuật ngữ
   - DATA (Quotes) → gia vị, evidence
3. **KHÔNG BỊA stories** — nếu vault không có → bỏ qua hoặc dùng famous stories
4. Content có vault knowledge = content có chiều sâu trí tuệ, không phải AI generic
