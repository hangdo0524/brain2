---
type: testcase
created: 2026-05-10
tags:
  - testing
  - golden-path
  - manual
  - automation
---

# Test Cases — Golden Path

> **Mục đích:** Verify luồng M02→M03→M04→M05→M06 hoạt động end-to-end  
> **Tester:** Hang (FE), Hiệp (BE)  
> **Automation:** AI hỗ trợ

---

## Pre-conditions

- [ ] BE server running (port 3000)
- [ ] FE server running (port 5173)
- [ ] Database có seed data
- [ ] Login thành công với admin@gt8.vn / Admin@123

---

## TC01: M02 — Tạo Chủ đầu tư (Owner)

### Manual Test

| Step | Action | Expected Result |
|------|--------|-----------------|
| 1 | Vào menu "Dữ liệu đầu vào" → "Quản lý dự án" | Hiển thị danh sách Chủ đầu tư |
| 2 | Click "Thêm mới" | Hiển thị form tạo mới |
| 3 | Nhập: Tên = "CĐT Test Golden Path" | Field được fill |
| 4 | Click "Lưu" | Toast success, item xuất hiện trong list |
| 5 | Refresh page | Item vẫn còn (persist qua API) |

### Automation Script (Playwright)

```typescript
// tests/golden-path/tc01-create-owner.spec.ts
import { test, expect } from '@playwright/test';

test('TC01: Create Owner', async ({ page }) => {
  // Login
  await page.goto('/login');
  await page.fill('[data-testid="email"]', 'admin@gt8.vn');
  await page.fill('[data-testid="password"]', 'Admin@123');
  await page.click('[data-testid="login-btn"]');
  
  // Navigate to Owner management
  await page.click('text=Dữ liệu đầu vào');
  await page.click('text=Quản lý dự án');
  
  // Create new owner
  await page.click('text=Thêm mới');
  await page.fill('[data-testid="owner-name"]', 'CĐT Test Golden Path');
  await page.click('text=Lưu');
  
  // Verify
  await expect(page.locator('text=CĐT Test Golden Path')).toBeVisible();
  
  // Verify persistence
  await page.reload();
  await expect(page.locator('text=CĐT Test Golden Path')).toBeVisible();
});
```

---

## TC02: M02 — Tạo Dự án (Project)

### Manual Test

| Step | Action | Expected Result |
|------|--------|-----------------|
| 1 | Trong danh sách Chủ đầu tư, click vào "CĐT Test Golden Path" | Hiển thị chi tiết + danh sách Dự án |
| 2 | Click "Thêm dự án" | Hiển thị form |
| 3 | Nhập: Tên = "Dự án Test GP", Mã = "DA-GP-001" | Fields được fill |
| 4 | Click "Lưu" | Toast success, dự án xuất hiện |

### Automation Script

```typescript
test('TC02: Create Project', async ({ page }) => {
  // Assume logged in, navigate to owner
  await page.click('text=CĐT Test Golden Path');
  
  // Create project
  await page.click('text=Thêm dự án');
  await page.fill('[data-testid="project-name"]', 'Dự án Test GP');
  await page.fill('[data-testid="project-code"]', 'DA-GP-001');
  await page.click('text=Lưu');
  
  // Verify
  await expect(page.locator('text=Dự án Test GP')).toBeVisible();
});
```

---

## TC03: M02 — Tạo Hợp đồng (Contract)

### Manual Test

| Step | Action | Expected Result |
|------|--------|-----------------|
| 1 | Click vào "Dự án Test GP" | Hiển thị chi tiết + danh sách Hợp đồng |
| 2 | Click "Thêm hợp đồng" | Hiển thị form |
| 3 | Nhập thông tin hợp đồng cơ bản | Fields được fill |
| 4 | Click "Lưu" | Toast success |
| 5 | Vào tab "Hạng mục & BOQ" | Hiển thị BOQ tree (có thể rỗng) |

### Automation Script

```typescript
test('TC03: Create Contract', async ({ page }) => {
  await page.click('text=Dự án Test GP');
  await page.click('text=Thêm hợp đồng');
  
  await page.fill('[data-testid="contract-code"]', 'HD-GP-001');
  await page.fill('[data-testid="contract-name"]', 'Hợp đồng Test GP');
  await page.click('text=Lưu');
  
  await expect(page.locator('text=HD-GP-001')).toBeVisible();
});
```

---

## TC04: M03 — Xem Thư viện Biểu mẫu

### Manual Test

| Step | Action | Expected Result |
|------|--------|-----------------|
| 1 | Vào menu "Hồ sơ mẫu" → "Thư viện biểu mẫu" | Hiển thị danh sách biểu mẫu |
| 2 | Kiểm tra có dữ liệu | Có ít nhất 10 biểu mẫu (từ seed) |
| 3 | Filter theo "Nhóm nghiệp vụ" | Danh sách được filter |
| 4 | Click vào 1 biểu mẫu | Hiển thị drawer chi tiết |

### Automation Script

```typescript
test('TC04: View Form Templates', async ({ page }) => {
  await page.click('text=Hồ sơ mẫu');
  await page.click('text=Thư viện biểu mẫu');
  
  // Verify list has items
  const rows = page.locator('table tbody tr');
  await expect(rows).toHaveCount({ minimum: 5 });
  
  // Click first item
  await rows.first().click();
  
  // Verify drawer opens
  await expect(page.locator('.ant-drawer')).toBeVisible();
});
```

---

## TC05: M04 — Tạo Bộ Hồ sơ Mẫu

### Manual Test

| Step | Action | Expected Result |
|------|--------|-----------------|
| 1 | Vào menu "Hồ sơ mẫu" → "Khai báo hồ sơ mẫu" | Hiển thị form tạo mới |
| 2 | Chọn Hệ sinh thái (OwnerGroup) | Dropdown có dữ liệu |
| 3 | Chọn Công đoạn = "Nghiệm thu vật tư" | Selected |
| 4 | Click "Tạo" hoặc "Tiếp tục" | Chuyển sang màn cấu hình |
| 5 | Thêm biểu mẫu từ thư viện vào bộ | Biểu mẫu xuất hiện trong list |
| 6 | Click "Lưu" | Toast success |

### Automation Script

```typescript
test('TC05: Create Dossier Template', async ({ page }) => {
  await page.click('text=Hồ sơ mẫu');
  await page.click('text=Khai báo hồ sơ mẫu');
  
  // Select owner group
  await page.click('[data-testid="owner-group-select"]');
  await page.click('.ant-select-item >> nth=0');
  
  // Select workflow stage
  await page.click('[data-testid="workflow-stage-select"]');
  await page.click('text=Nghiệm thu vật tư');
  
  // Create
  await page.click('text=Tạo');
  
  // Add form template
  await page.click('text=Thêm biểu mẫu');
  await page.click('.form-template-item >> nth=0');
  await page.click('text=Thêm');
  
  // Save
  await page.click('text=Lưu');
  await expect(page.locator('.ant-message-success')).toBeVisible();
});
```

---

## TC06: M05 — Tạo Hồ sơ Thực

### Manual Test

| Step | Action | Expected Result |
|------|--------|-----------------|
| 1 | Vào menu "Quản lý hồ sơ" → "Tạo hồ sơ mới" | Hiển thị form |
| 2 | Chọn Hợp đồng = "HD-GP-001" | Selected |
| 3 | Chọn Bộ hồ sơ mẫu vừa tạo | Selected |
| 4 | Click "Tạo hồ sơ" | Tạo thành công, chuyển sang workspace |

### Automation Script

```typescript
test('TC06: Create Dossier', async ({ page }) => {
  await page.click('text=Quản lý hồ sơ');
  await page.click('text=Tạo hồ sơ mới');
  
  // Select contract
  await page.click('[data-testid="contract-select"]');
  await page.click('text=HD-GP-001');
  
  // Select dossier template
  await page.click('[data-testid="dossier-template-select"]');
  await page.click('.dossier-template-item >> nth=0');
  
  // Create
  await page.click('text=Tạo hồ sơ');
  
  // Verify workspace opens
  await expect(page.locator('[data-testid="dossier-workspace"]')).toBeVisible();
});
```

---

## TC07: M05 — Điền Form và Submit

### Manual Test

| Step | Action | Expected Result |
|------|--------|-----------------|
| 1 | Trong workspace, click vào form đầu tiên | Hiển thị form editor |
| 2 | Điền các trường bắt buộc | Fields được fill |
| 3 | Click "Lưu nháp" | Toast success, status = Draft |
| 4 | Click "Gửi duyệt" | Toast success, status = Pending |

### Automation Script

```typescript
test('TC07: Fill Form and Submit', async ({ page }) => {
  // Assume in dossier workspace
  await page.click('.form-item >> nth=0');
  
  // Fill required fields
  await page.fill('[data-testid="field-date"]', '2026-05-15');
  await page.fill('[data-testid="field-description"]', 'Test description');
  
  // Save draft
  await page.click('text=Lưu nháp');
  await expect(page.locator('.ant-message-success')).toBeVisible();
  
  // Submit
  await page.click('text=Gửi duyệt');
  await expect(page.locator('text=Pending')).toBeVisible();
});
```

---

## TC08: M05 — Duyệt Hồ sơ

### Manual Test

| Step | Action | Expected Result |
|------|--------|-----------------|
| 1 | Vào "Hồ sơ của tôi" hoặc "Duyệt hồ sơ" | Thấy hồ sơ pending |
| 2 | Click vào hồ sơ | Hiển thị chi tiết |
| 3 | Click "Duyệt" | Dialog confirm |
| 4 | Confirm | Toast success, status = Approved |

### Automation Script

```typescript
test('TC08: Approve Dossier', async ({ page }) => {
  await page.click('text=Hồ sơ của tôi');
  await page.click('.dossier-item.pending >> nth=0');
  
  await page.click('text=Duyệt');
  await page.click('text=Xác nhận');
  
  await expect(page.locator('.ant-message-success')).toBeVisible();
  await expect(page.locator('text=Approved')).toBeVisible();
});
```

---

## TC09: M06 — Xem Dashboard

### Manual Test

| Step | Action | Expected Result |
|------|--------|-----------------|
| 1 | Vào menu "Dashboard" | Hiển thị dashboard |
| 2 | Kiểm tra số liệu | Có hiển thị số hồ sơ (>0) |
| 3 | Kiểm tra biểu đồ | Có render chart |

### Automation Script

```typescript
test('TC09: View Dashboard', async ({ page }) => {
  await page.click('text=Dashboard');
  
  // Verify stats cards
  await expect(page.locator('[data-testid="stats-total"]')).toBeVisible();
  
  // Verify chart renders
  await expect(page.locator('canvas, svg.recharts-surface')).toBeVisible();
});
```

---

## TC10: End-to-End Golden Path

### Manual Test

Chạy tuần tự TC01 → TC09 trong 1 session, không refresh giữa chừng.

**Expected:** Tất cả pass, data persist xuyên suốt.

### Automation Script

```typescript
// tests/golden-path/e2e-full-flow.spec.ts
import { test, expect } from '@playwright/test';

test.describe('Golden Path E2E', () => {
  test.beforeAll(async ({ browser }) => {
    // Login once
  });

  test('Full flow M02→M06', async ({ page }) => {
    // TC01-TC09 combined
    // ... (call each step)
  });
});
```

---

## Test Execution Checklist

### Tuần 1 (Manual Testing)

| TC | Description | Hang | Hiệp | Status |
|----|-------------|------|------|--------|
| TC01 | Create Owner | FE | BE verify | ⏳ |
| TC02 | Create Project | FE | BE verify | ⏳ |
| TC03 | Create Contract | FE | BE verify | ⏳ |
| TC04 | View Form Templates | FE | BE verify | ⏳ |
| TC05 | Create Dossier Template | FE | BE verify | ⏳ |
| TC06 | Create Dossier | FE | BE verify | ⏳ |
| TC07 | Fill Form & Submit | FE | BE verify | ⏳ |
| TC08 | Approve Dossier | FE | BE verify | ⏳ |
| TC09 | View Dashboard | FE | BE verify | ⏳ |
| TC10 | E2E Full Flow | FE | — | ⏳ |

### Tuần 2 (Automation)

| Task | Owner | Status |
|------|-------|--------|
| Setup Playwright | AI | ⏳ |
| Implement TC01-TC05 | AI | ⏳ |
| Implement TC06-TC10 | AI | ⏳ |
| Run on staging | Hang | ⏳ |

---

## Bug Report Template

```markdown
### Bug ID: BUG-XXX
**TC:** TCxx
**Severity:** Critical / High / Medium / Low
**Module:** M0x

**Steps to reproduce:**
1. ...
2. ...

**Expected:** ...
**Actual:** ...

**Screenshot/Video:** [link]
**Console errors:** [paste]
```
