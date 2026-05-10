---
type: project
status: active
category: work
created: 2026-05-10
updated: 2026-05-10
deadline: 2026-06-30
tags:
  - construction
  - web-app
  - workflow
  - fastify
  - react
  - prisma
---

# ConstructHub — Hồ sơ Xây dựng

## Tóm tắt
Hệ thống web quản lý toàn bộ vòng đời hồ sơ công trình cho công ty thi công xây dựng — từ ký hợp đồng đến thanh lý hợp đồng.

| Mục tiêu | Ký hợp đồng + Go-live |
|----------|----------------------|
| Deadline | Ký HĐ: cuối T5/2026, Go-live: cuối T6/2026 |
| Giai đoạn | BE 90%, FE 80%, Docs outdated |
| Team | 2 người + AI |
| Plan hiện tại | [[docs/golden-path-plan\|Kế hoạch Golden Path]] (2 tuần đến 24/05) |

## Trạng thái Chi tiết

| Component | Progress | Tech |
|-----------|----------|------|
| **Backend** | 90% | Fastify + Prisma, 35 models, 17 API modules |
| **Frontend** | 80% | React 19 + AntD, 35 pages |
| **Docs** | Outdated | 48 specs cần sync |

→ Xem chi tiết: [[docs/current-status|Trạng thái hiện tại]]

## Bối cảnh và lý do thực hiện
Hệ thống giúp phối hợp giữa bộ phận hồ sơ, công trường và kho vật liệu. Các loại hồ sơ bao gồm:
- Trình phê duyệt tiến độ, bàn giao mặt bằng, phê duyệt vật liệu
- Nhập vật liệu
- Nghiệm thu (vật liệu, công việc chế tác cấu kiện tại xưởng, cấu kiện, công việc thi công tại công trường)
- Hồ sơ thanh toán, quyết toán, bàn giao đưa vào sử dụng

## Các module cần hoàn thành

| Module | FE UI | FE-BE | BE | Docs |
|--------|-------|-------|-----|------|
| M01: Quản trị | — | — | — | — |
| M02: Dữ liệu đầu vào | ✅ | ⏳ | ⚠️ | ✅ |
| M03: Biểu mẫu | ✅ | ⏳ | ⚠️ | ✅ |
| M04: Hồ sơ mẫu | ✅ | ⏳ | ⚠️ | ✅ |
| M05: Hồ sơ thực | — | — | — | — |
| M06: Dashboard | — | — | — | — |

**Chú thích:** ✅ Done | ⏳ Pending | ⚠️ Gap cần sửa

## Các bên liên quan
| Vai trò | Người | Nhiệm vụ |
|---------|-------|----------|
| BA | 1 người | Đầu mối KH, thu thập yêu cầu, vibe code FE, định nghĩa tính năng, test |
| Developer | 1 người | Dựng nền tảng, code BE + FE |

## Tài liệu và đường dẫn

### Repos
| Repo | Path | Mục đích |
|------|------|----------|
| **si-gt8-pm** | `/Users/hangdo/Documents/GitHub/si-gt8-pm` | Specs & Documentation |
| **construct-hub-backend** | `/Users/hangdo/Documents/GitHub/construct-hub-backend` | BE (Fastify + Prisma) |
| **si-ht8-fe-demo** | `/Users/hangdo/Documents/GitHub/si-ht8-fe-demo` | FE (React 19 + AntD) |

### Tài liệu trong Brain2
- [[docs/references|Tài liệu Tham chiếu]] — Cấu trúc docs chi tiết
- [[docs/current-status|Trạng thái Hiện tại]] — Progress & tech debt
- [[docs/golden-path-plan|Kế hoạch Golden Path]] — Plan 2 tuần (11-24/05)
- [[docs/testcases-golden-path|Test Cases Golden Path]] — 10 TCs + automation
- [[docs/2-week-plan|Kế hoạch 2 tuần (cũ)]] — Reference

### Entry points trong repo
- `si-gt8-pm/docs/README.md` — Trình tự đọc tài liệu
- `si-gt8-pm/docs/00_overview/mvp.md` — Phạm vi MVP
- `si-gt8-pm/docs/plan/20260509-complete.md` — Plan chính hiện tại

## Trở ngại đang gặp
- Resource hạn chế: chỉ có 2 người + AI
- Timeline gấp (ký HĐ cuối T5, go-live cuối T6)
- FE dùng localStorage/mock thay vì API (M03, M04)
- BE schema gaps: enum sai, thiếu FK
- Enum UPPERCASE migration: 32+ files, 500+ lines

## Bước tiếp theo — Golden Path 2 tuần

### Tuần 1: BE Verification + Critical Gaps
1. Chạy thử golden path trên FE mock, ghi lại gaps
2. Verify BE routes M02-M06 hoạt động (Postman)
3. Fix gaps nếu có

### Tuần 2: FE Integration + Deploy Staging
4. FE: Test với real API, fix integration issues
5. Deploy staging
6. UAT Internal — chạy full golden path
7. Chuẩn bị seed data + hướng dẫn

**Deadline:** 24/05/2026 — Bàn giao cho KH dùng thử

→ Chi tiết: [[docs/golden-path-plan|Kế hoạch Golden Path]]

---

## Nhật ký Quyết định

### 2026-05-09: Plan 2 tuần hoàn thiện
| Câu hỏi | Quyết định |
|---------|------------|
| Phase 1 priority | Core specs trước → Module specs sau |
| M03/M04 API | BE đã đủ endpoints - chỉ cần FE migrate |
| UI bugs | Fix trong Phase 4 (sau API integration) |
| Timeline | 2 tuần |

### 2026-05-10: Tích hợp Brain2
- Tạo cấu trúc docs trong Brain2 để theo dõi
- Sync thông tin từ repo tài liệu

### 2026-05-10: Quyết định Golden Path
| Câu hỏi | Quyết định |
|---------|------------|
| Scope | Golden path M02→M06, bỏ M01 (phân quyền) |
| Timeline | 2 tuần, deadline 24/05 |
| Resource | 50% × 2 = 1 FTE |
| Approach | Option B — chất lượng cao, scope hẹp |
| Deploy | Staging server, KH tự dùng thử |
| Data | Seed 1 bộ hoàn chỉnh + KH tự khai báo |
| Communication | Báo KH 2 tuần nữa gửi hệ thống |

**Phát hiện quan trọng:**
- BE đã có 20 modules, FE có 14 adapters dùng API
- Chỉ cần verify + fix gaps, không cần build từ đầu
- M03/M04 là gaps lớn nhất (FormTemplates, DossierTemplates)
