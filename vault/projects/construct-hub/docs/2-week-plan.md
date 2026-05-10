---
type: plan
created: 2026-05-10
updated: 2026-05-10
source: si-gt8-pm/docs/plan/
tags:
  - plan
  - timeline
  - tasks
---

# Kế hoạch 2 tuần Hoàn thiện

> **Ngày bắt đầu**: 2026-05-09  
> **Timeline**: 2 tuần  
> **Priority**: M02 → M03 → M04 → M05

---

## Tổng quan Trạng thái theo Module

| Module | FE UI | FE-BE Integration | BE Schema | BE Routes | Docs |
|--------|-------|-------------------|-----------|-----------|------|
| M02 | ✅ Done | ⏳ Pending | ⚠️ Gap | ⚠️ Gap | ✅ Done |
| M03 | ✅ Done | ⏳ Pending | ⚠️ Gap | ⚠️ Gap | ✅ Done |
| M04 | ✅ Done | ⏳ Pending | ⚠️ Gap | ⚠️ Gap | ✅ Done |
| M05 | — | — | — | — | — |
| M06 | — | — | — | — | — |

---

## M02: Dữ liệu Đầu vào

### FE Phase 1: UI/UX ✅ DONE
- ✅ 8 pages, 10 tabs hoàn thành
- ✅ Owner Groups inline selector
- ✅ Quantity Breakdowns UI (6 components)
- ✅ SignersSection (3 bên, 2 scope types)

### FE Phase 2: API Integration ⏳ PENDING

**Entities đã dùng API:**
- ✅ Owner, Project, Contract, ContractItem, BOQTask, Material

**Entities cần chuyển từ Mock → API (13 items):**

| Entity | Priority | BE Status |
|--------|----------|-----------|
| PaymentTerm | High | ⏳ Pending |
| DrawingTask | High | ⏳ Pending |
| MaterialRequest | High | ⏳ Pending |
| OwnerGroup | High | ⏳ Pending |
| OrderBatch | High | ⏳ Pending |
| ContractMaterial | High | ⏳ Pending |
| SignerAssignment | Medium | ⏳ Pending |
| QuantityBreakdown | Low | ⏳ Pending |
| PaymentInstallment | — | ⏳ Pending |
| DrawingTaskImage | — | ⏳ Pending |
| MappingBOQTask | — | ⏳ Pending |
| OwnerGroupPersonnel | — | ⏳ Pending |
| ComponentMaterial | — | ⏳ Pending |

### BE Tasks (từ m02-be.md)

**Schema có, Routes thiếu:**
| Entity | Routes Needed |
|--------|---------------|
| PaymentTerm | CRUD |
| DrawingTask | CRUD + sync BOQ |
| MaterialRequest | CRUD + order flow |
| OwnerGroup | CRUD |
| SignerAssignment | CRUD |
| QuantityBreakdown | CRUD |

**System features cần làm:**
- [ ] JWT token validation middleware
- [ ] Role-based access control (RBAC)
- [ ] Permission check per route
- [ ] Token refresh endpoint
- [ ] File upload endpoint (`POST /files/upload`)
- [ ] Swagger/OpenAPI spec (`GET /api/docs`)
- [ ] Request/Response logging
- [ ] Error tracking

---

## M03: Biểu mẫu

### FE Phase 1: UI/UX ⏳ PENDING

| Task | File | Status |
|------|------|--------|
| Filter logic: HST + "Dùng chung" | `ThuVienBieuMau.tsx:205-210` | ⏳ |
| Actions: ẩn Edit/Delete nếu !isUserCreated | `ThuVienBieuMau.tsx:439-473` | ⏳ |

### FE Phase 2: API Integration ⏳ PENDING

**Vấn đề: FE dùng localStorage thay vì API**

| File | Storage hiện tại |
|------|------------------|
| `TemplateManager.ts` | `localStorage.saved_templates` |
| `TemplateDesigner.tsx` | localStorage |
| `ThuVienBieuMau.tsx` | localStorage |

**Cần làm:**
1. Tạo `TemplateConfigsAdapter` → API `/template-configs`
2. Tạo `FormTemplatesAdapter` → API `/form-templates`
3. Tạo `TagDefinitionsAdapter` → API `/tag-definitions`
4. Update `TemplateManager.ts` sync với BE

### BE Tasks (từ m03-be.md)

**Schema cần sửa:**
- [ ] Enum `DossierCategory`: SCHEDULE → PRELIMINARY
- [ ] Enum `EntityStatus`: thêm DRAFT
- [ ] Thêm `ownerGroupId` vào `form_templates`

**Routes thiếu:**
- [ ] `/tag-definitions` CRUD
- [ ] `/template-configs` CRUD
- [ ] Export routes

### Docs cần tạo
- [ ] `S03_template_designer.md` — UI spec cho 4-step wizard

---

## M04: Hồ sơ Mẫu

### FE Phase 1: UI/UX ⏳ PENDING

| Task | Status |
|------|--------|
| Verify UI vs Spec (3 pages) | ⏳ |

### FE Phase 2: API Integration ⏳ PENDING

**Vấn đề: FE dùng localStorage**

| File | Storage |
|------|---------|
| `DataStore.ts` | localStorage |
| `DataContext.tsx` | Memory wrapper |

**Cần làm:**
1. Tạo `DossierTemplatesAdapter`
2. Update 3 pages dùng adapter
3. Remove mock từ DataStore

### BE Tasks (từ m04-be.md)

**Schema cần sửa:**
- [ ] Enum `WorkflowStage`: 7 → 9 stages
  - HANDOVER → PREPARATION
  - Thêm MATERIAL_APPROVAL
  - Thêm COMPLETION_INSPECTION
  - PROGRESS_PAYMENT → PAYMENT
  - FINAL_SETTLEMENT → SETTLEMENT
- [ ] Thêm `owner_group_id` FK (thay vì contractId)
- [ ] DossierCategory: SCHEDULE → PRELIMINARY

**Routes thiếu:**
- [ ] `/dossier-templates/copy`
- [ ] `/dossier-templates/:id/items/reorder`

---

## Enum Centralization (Cross-module)

> File: `20260509-enum-centralization.md`

### Phase 1: BE ⏳
- [ ] Tạo `/src/shared/constants/enum-labels.ts`
- [ ] Tạo `/src/modules/app-config/routes.ts`
- [ ] Tạo `/src/modules/app-config/service.ts`

### Phase 2: FE Mock ⏳
- [ ] Update `_mockEnumLabels.ts` → UPPERCASE
- [ ] Sentinel: `'common' → 'COMMON'`

### Phase 3: FE Config ⏳
- [ ] Update `dossierStateMachine.ts`
- [ ] Update `contractStateMachine.ts`

### Phase 4: FE Pages (32+ files, 500+ lines) ⏳
- [ ] M02 pages
- [ ] M03 pages
- [ ] M04 pages
- [ ] M05 pages
- [ ] M06 pages
- [ ] Components: dossier/, templateDesigner/, forms/
- [ ] Services: TemplateDesignerService.ts, TableDetector.ts

### Phase 5: Switch to API ⏳
- [ ] Update `appConfig.ts` → use API
- [ ] Delete `_mockEnumLabels.ts`

---

## Phase 4 & 5: UI Fixes & Verification

### Known bugs (từ debt-20260508.md)

| Bug | Module |
|-----|--------|
| Filter "Nhóm nghiệp vụ" sai enum | M03 |
| Drawer xem biểu mẫu lỗi | M03 |
| Buttons thừa (Xem phối, Preview, In) | M03 |
| Click "Tạo hồ sơ mẫu" không fill công đoạn | M04 |

### Test checklist
- [ ] M02: 8 pages - CRUD operations
- [ ] M03: 4 pages - Template management
- [ ] M04: 3 pages - Dossier template config
- [ ] M05: 7 pages - Dossier workflow
- [ ] M06: 5 pages - Dashboard views

### Verification
- [ ] Test CRUD cho từng entity
- [ ] Verify error handling (4xx, 5xx)
- [ ] Check loading states
- [ ] Verify pagination
- [ ] Test filter/search
- [ ] Remove all mock data

---

## Test Credentials

| User | Password | Role |
|------|----------|------|
| admin@gt8.vn | Admin@123 | Admin |
| qlda@gt8.vn | — | Quản lý dự án |

## Test Flow

1. Run dev servers: BE port 3000, FE port 5173
2. Login: admin@gt8.vn / Admin@123
3. Test flow: M02 → M03 → M04 → M05
4. Verify: Data persist qua API, không dùng localStorage

---

## Quick Reference

| Plan File | Module | Nội dung |
|-----------|--------|----------|
| `20260509-complete.md` | All | Overview 5 phases |
| `20260509-m02-overview.md` | M02 | Tổng quan + decisions |
| `20260509-m02-fe.md` | M02 | FE tasks chi tiết |
| `20260509-m02-be.md` | M02 | BE implementation |
| `20260509-m03-overview.md` | M03 | Tổng quan + decisions |
| `20260509-m03-fe.md` | M03 | FE tasks chi tiết |
| `20260509-m03-be.md` | M03 | BE implementation |
| `20260509-m04-overview.md` | M04 | Tổng quan + decisions |
| `20260509-m04-fe.md` | M04 | FE tasks chi tiết |
| `20260509-m04-be.md` | M04 | BE implementation |
| `20260509-enum-centralization.md` | All | Enum UPPERCASE migration |
