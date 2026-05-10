---
type: status
created: 2026-05-10
updated: 2026-05-10
tags:
  - status
  - progress
---

# Trạng thái Hiện tại

> Cập nhật từ `si-gt8-pm/docs/plan/20260509-complete.md`

## Tổng quan

| Component | Trạng thái | Chi tiết |
|-----------|------------|----------|
| **BE** | 90% Complete | Fastify + Prisma, 35 models, 17 API modules |
| **FE** | 80% Complete | React 19 + AntD, 35 pages, 38 mock files |
| **Docs** | Outdated | 48 specs - CHƯA ĐỒNG BỘ với implementation |

## Tech Stack

### Backend (construct-hub-backend)
- **Framework**: Fastify
- **ORM**: Prisma
- **Database**: PostgreSQL
- **Models**: 35 models
- **API Modules**: 17 modules

### Frontend (si-ht8-fe-demo)
- **Framework**: React 19
- **UI Library**: Ant Design
- **Pages**: 35 pages
- **Mock files**: 38 files

---

## Vấn đề Chính

1. **Tài liệu đặc tả OUTDATED** so với code thực tế
2. **FE M03/M04** vẫn dùng localStorage thay vì API
3. **Mock data FE** chưa migrate hết sang API calls

---

## Modules API Integration Status

### Đã dùng API (verify only)
- ✅ M01: Users, Roles
- ✅ M02: Owners, Projects, Contracts, Materials, BOQ
- ✅ M05: Dossiers, FormInstances

### Cần migrate localStorage → API
| Module | Component | Current | Target |
|--------|-----------|---------|--------|
| M03 | FormTemplates | localStorage | API `/form-templates` |
| M04 | DossierTemplates | localStorage | API `/dossier-templates` |
| M05 | SubmissionBatches | localStorage | API `/submission-batches` |
| M06 | Dashboard stats | Mock | API `/dashboards` |

---

## Seed Data (Đã có)

- 6 projects, 6 contracts
- 150-210 dossiers
- 300+ BOQ tasks
- Demo users:
  - admin@gt8.vn
  - qlda@gt8.vn
  - etc.

---

## Technical Debt

### ✅ Đã hoàn thành (9 items)
Xem: `si-gt8-pm/docs/debt/done/`

| File | Nội dung |
|------|----------|
| `M02_debt.md` | Module 02 debt |
| `M02_personnel_debt.md` | Personnel M02 |
| `M03_debt.md` | Module 03 debt |
| `M04_debt.md` | Module 04 debt |
| `database_debt.md` | Database issues |
| `hs_cl_quy_trinh_nop_nhieu_lan.md` | HS CL quy trình |
| `m02_fix.md` | M02 fixes |
| `mockdata_debt.md` | Mock data |
| `ui_global_debt.md` | UI global |

### ⏳ Chưa xử lý (12 items)
Xem: `si-gt8-pm/docs/debt/todo/`

| File | Nội dung |
|------|----------|
| `BE_owner_group_debt.md` | Owner group BE |
| `FE_owner_group_debt.md` | Owner group FE |
| `M01_debt.md` | Module 01 debt |
| `M02_debt.md` | Module 02 debt (new) |
| `M04_debt.md` | Module 04 debt (new) |
| `M05_debt.md` | Module 05 debt |
| `M06_debt.md` | Module 06 debt |
| `debt-20260508.md` | Debt tổng hợp 08/05 |
| `enum_debt.md` | Enum sync |
| `m03_05_debt.md` | M03-M05 debt |
| `system_debt.md` | System level |
| `ui_global_debt_20260425.md` | UI global |
