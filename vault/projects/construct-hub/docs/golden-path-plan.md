---
type: plan
created: 2026-05-10
deadline: 2026-05-24
tags:
  - golden-path
  - mvp
  - 2-weeks
---

# Kế hoạch Golden Path — 2 tuần

> **Mục tiêu:** KH tự dùng thử 1 luồng hoàn chỉnh M02→M06 trên staging  
> **Bắt đầu:** 2026-05-11  
> **Deadline:** 2026-05-24 (2 tuần)  
> **Resource:** 50% × 2 người = 1 FTE  
> **Approach:** Option B — Golden path chất lượng, bỏ qua M01 (phân quyền)

## Phân công

| Người | Vai trò | Nhiệm vụ chính |
|-------|---------|----------------|
| **Hiệp** | Dev | Verify BE routes, fix gaps, deploy staging |
| **Hang** | BA | Test FE, chạy test cases, UAT |
| **AI** | Support | Review code, viết test cases, automation test FE |

---

## Phân tích Hiện trạng

### BE Modules đã có (20 modules) ✅

```
audit, auth, boq-tasks, contract-items, contracts, dashboards,
dossier-templates, dossiers, exports, form-attachments, form-instances,
form-templates, materials, owners, projects, role-assignments,
roles, submission-batches, supervision-companies, users
```

### FE Adapters đang dùng API (14) ✅

| Module | Adapter | Status |
|--------|---------|--------|
| M01 | UsersAdapter, RolesAdapter, RoleAssignmentsAdapter | ✅ API |
| M02 | OwnersAdapter, ProjectsAdapter, ContractsAdapter | ✅ API |
| M02 | ContractItemsAdapter, BOQTasksAdapter, MaterialsAdapter | ✅ API |
| M02 | SupervisionCompaniesAdapter | ✅ API |
| M05 | DossiersAdapter, FormInstancesAdapter, SubmissionBatchesAdapter | ✅ API |
| — | AuditAdapter | ✅ API |

### FE còn dùng Mock/localStorage (cần chuyển cho Golden Path)

| Entity | Cần cho Golden Path? | Priority |
|--------|---------------------|----------|
| formTemplates | ✅ Có (M03) | HIGH |
| dossierTemplates | ✅ Có (M04) | HIGH |
| ownerGroups | ⚠️ Optional | MEDIUM |
| signerAssignments | ⚠️ Optional | LOW |
| Còn lại (~15 entities) | ❌ Không | SKIP |

---

## Golden Path Definition

```
BƯỚC 1: [M02] Nhập dữ liệu cơ bản
├── Tạo/chọn Chủ đầu tư (Owner) ← API ✅
├── Tạo Dự án (Project) ← API ✅
├── Tạo Hợp đồng (Contract) ← API ✅
└── Import BOQ Tasks ← API ✅

BƯỚC 2: [M03] Xem thư viện biểu mẫu
└── Xem danh sách FormTemplates ← Cần API hoặc seed data

BƯỚC 3: [M04] Tạo bộ hồ sơ mẫu
├── Chọn hệ sinh thái (OwnerGroup)
├── Chọn công đoạn (WorkflowStage)
└── Thêm biểu mẫu vào bộ ← Cần DossierTemplates API

BƯỚC 4: [M05] Tạo và xử lý hồ sơ thực
├── Tạo Dossier từ DossierTemplate ← API ✅
├── Tạo FormInstance, điền form ← API ✅
├── Submit → SubmissionBatch ← API ✅
└── Duyệt hồ sơ

BƯỚC 5: [M06] Xem Dashboard
└── Xem tiến độ hồ sơ ← Cần Dashboard API
```

---

## Kế hoạch 2 tuần

### Tuần 1: BE Verification + Critical Gaps (11-15/05)

| Ngày | Hang (BA) | Hiệp (Dev) | AI Support |
|------|-----------|------------|------------|
| **11/05** | Test TC01-TC03 (M02) trên FE mock | Verify BE routes M02 (Postman) | Review code M02 |
| **12/05** | Test TC04 (M03) FormTemplates | Fix gaps M02 nếu có | — |
| **13/05** | Test TC05 (M04) DossierTemplates | Verify/fix M03-M04 routes | — |
| **14/05** | Test TC06-TC08 (M05) | Verify/fix M05 routes | — |
| **15/05** | Test TC09 (M06) Dashboard | Verify/fix Dashboard routes | — |

**Deliverable Tuần 1:**
- [ ] Tất cả BE routes cho golden path hoạt động
- [ ] Postman collection đầy đủ
- [ ] TC01-TC09 manual test pass (với mock hoặc real API)
- [ ] Danh sách bugs/gaps

### Tuần 2: FE Integration + Automation + Deploy (18-24/05)

| Ngày | Hang (BA) | Hiệp (Dev) | AI Support |
|------|-----------|------------|------------|
| **18/05** | Re-test TC01-TC05 với real API | Fix integration issues | Setup Playwright |
| **19/05** | Re-test TC06-TC09 với real API | Fix integration issues | Implement TC01-TC05 automation |
| **20/05** | TC10: E2E full flow | Deploy staging | Implement TC06-TC10 automation |
| **21/05** | **UAT Internal** | Fix blocker bugs | Run automation on staging |
| **22-23/05** | Buffer cho bugs | Buffer | — |
| **24/05** | Prepare hướng dẫn KH | Final deploy + verify | — |

**Deliverable Tuần 2:**
- [ ] Golden path hoạt động end-to-end trên staging
- [ ] Automation test suite (Playwright)
- [ ] Seed data có sẵn (1 bộ hoàn chỉnh)
- [ ] Hướng dẫn sử dụng cơ bản

---

## Checklist BE Routes cần Verify

### M02: Dữ liệu đầu vào
- [x] `GET/POST/PUT/DELETE /owners`
- [x] `GET/POST/PUT/DELETE /projects`
- [x] `GET/POST/PUT/DELETE /contracts`
- [x] `GET/POST/PUT/DELETE /contract-items`
- [x] `GET/POST/PUT/DELETE /boq-tasks`
- [x] `GET/POST/PUT/DELETE /materials`

### M03: Biểu mẫu
- [ ] `GET /form-templates` — Verify hoạt động
- [ ] `GET /form-templates/:id` — Verify hoạt động

### M04: Hồ sơ mẫu
- [ ] `GET /dossier-templates`
- [ ] `POST /dossier-templates`
- [ ] `PUT /dossier-templates/:id`
- [ ] `POST /dossier-templates/:id/items` — Thêm biểu mẫu

### M05: Hồ sơ thực
- [x] `GET/POST /dossiers`
- [x] `GET/POST /form-instances`
- [x] `PUT /form-instances/:id` — Điền form
- [x] `GET/POST /submission-batches`
- [ ] `PUT /submission-batches/:id/approve` — Duyệt

### M06: Dashboard
- [ ] `GET /dashboards/officer` — Dashboard nhân viên
- [ ] `GET /dashboards/manager` — Dashboard quản lý

---

## Scope BỎ QUA (cho bản dùng thử)

| Tính năng | Lý do bỏ |
|-----------|----------|
| M01: Phân quyền, quản lý user | Login cứng admin |
| OwnerGroups CRUD | Dùng seed data có sẵn |
| SignerAssignments | Không critical cho golden path |
| Full validation/error handling | Dùng thử, không production |
| Enum migration 32 files | Dùng mock labels |

---

## Seed Data cần chuẩn bị

KH sẽ tự khai báo, nhưng hệ thống có sẵn 1 bộ:

```
1 Chủ đầu tư (OwnerGroup) — VD: "Ban QLDA tỉnh Quảng Trị"
├── 1 Dự án — VD: "TTTM Quảng Trị"
│   └── 1 Hợp đồng — VD: "HĐ 2201.2024"
│       ├── BOQ Tasks (import từ file)
│       └── Materials (import từ file)
├── FormTemplates — 10-15 biểu mẫu nghiệm thu cơ bản
└── DossierTemplates — 1 bộ hồ sơ mẫu cho công đoạn "Nghiệm thu vật tư"
```

---

## Test Credentials (cho KH dùng thử)

| User | Password | Ghi chú |
|------|----------|---------|
| admin@gt8.vn | Admin@123 | Full quyền |

---

## Rủi ro & Mitigation

| Rủi ro | Xác suất | Mitigation |
|--------|----------|------------|
| BE routes thiếu/lỗi | Medium | Verify sớm (Tuần 1 ngày 1-2) |
| FE-BE integration issues | High | Test từng module riêng trước khi ghép |
| Deploy staging lỗi | Low | Test local trước, deploy sớm (ngày 8) |
| KH đổi yêu cầu | Low | Scope đã confirm, communicate rõ |

---

## Communication với KH

| Thời điểm | Nội dung |
|-----------|----------|
| Ngày 1 | Confirm timeline 2 tuần, scope golden path |
| Ngày 5 | Update progress tuần 1 (optional) |
| Ngày 10 | Bàn giao link staging + hướng dẫn |
