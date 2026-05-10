---
type: reference
created: 2026-05-10
tags:
  - docs
  - repo-structure
---

# Tài liệu Tham chiếu

## Repos

| Repo | Path | Mục đích |
|------|------|----------|
| **si-gt8-pm** | `/Users/hangdo/Documents/GitHub/si-gt8-pm` | Specs & Documentation |
| **construct-hub-backend** | `/Users/hangdo/Documents/GitHub/construct-hub-backend` | BE (Fastify + Prisma) |
| **si-ht8-fe-demo** | `/Users/hangdo/Documents/GitHub/si-ht8-fe-demo` | FE (React 19 + AntD) |

---

## Cấu trúc Tài liệu (si-gt8-pm/docs/)

### Trình tự đọc (cho Dev & AI)
Xem chi tiết: `si-gt8-pm/docs/README.md`

### 00_overview/ — Tổng quan
| File | Nội dung |
|------|----------|
| `yeu_cau.md` | Mục tiêu, vấn đề, yêu cầu nghiệp vụ |
| `giai_phap.md` | Kiến trúc giải pháp, module, luồng nghiệp vụ |
| `mvp.md` | Phạm vi MVP và những phần không làm |
| `cau_truc_bieu_mau.md` | Cấu trúc biểu mẫu |
| `core_logic_due_date.md` | Logic tính deadline |

### 01_be_spec/ — Đặc tả Backend
| Folder | Nội dung |
|--------|----------|
| `00_shared/` | core_database.md, core_api.md, core_enums.md |
| `M01_quan_tri/` | Module quản trị |
| `M02_du_lieu_dau_vao/` | Module dữ liệu đầu vào |
| `M03_bieu_mau/` | Module biểu mẫu + data_sources, tag_definitions |
| `M04_ho_so_mau/` | Module hồ sơ mẫu |
| `M05_ho_so_thuc/` | Module hồ sơ thực (state_machine, render_engine) |
| `M06_dashboard_bao_cao/` | Module dashboard & báo cáo |

### 02_ui_design/ — Thiết kế UI
| Folder | Nội dung |
|--------|----------|
| `00_shared/` | ui_design.md, ui_style_rules.md |
| `M02_du_lieu_dau_vao/` | 6 screens (S01-S06) |
| `M03_bieu_mau/` | 2 screens |
| `M04_ho_so_mau/` | 3 screens (S00-S01) |
| `M05_ho_so_thuc/` | 8 screens (S01-S04) + button_visibility_rules |
| `M06_dashboard_bao_cao/` | 6 screens (S00-S05) |

### 04_test/ — Test
| Folder | Nội dung |
|--------|----------|
| `00_shared/` | test_strategy, test_environment, ci_cd_pipeline |
| `be/` | test_guidelines_be, testcases_m02_be |
| `fe/` | test_guidelines_fe, testcases_m02_fe, results/ |
| `integration/` | e2e_scenarios, fe_be_integration |

### 05_sales/ — Sales & Demo
| File | Nội dung |
|------|----------|
| `solution_overview.md` | Tổng quan giải pháp |
| `sales_process.md` | Quy trình sales |
| `proposal.md` | Proposal template |
| `demo_script.md` | Kịch bản demo |
| `chien_luoc_chot_sale.md` | Chiến lược chốt sale |

### debt/ — Technical Debt
| Folder | Files |
|--------|-------|
| `done/` | 9 files đã xử lý |
| `todo/` | 12 files cần xử lý |

### plan/ — Kế hoạch
| File | Nội dung |
|------|----------|
| `20260509-complete.md` | **PLAN CHÍNH** - 2 tuần hoàn thiện |
| `20260509-m02-*.md` | Plan chi tiết M02 (overview, fe, be) |
| `20260509-m03-*.md` | Plan chi tiết M03 |
| `20260509-m04-*.md` | Plan chi tiết M04 |

---

## Hồ sơ Dự án Mẫu

| Folder | Dự án |
|--------|-------|
| `ho-so-quang-tri/` | KCT tòa TTTM Quảng Trị (HĐ 2201.2024) |
| `ho-so-vu-yen/` | Nhà đón tiếp Vũ Yên Hải Phòng (HĐ 2612.2023) |

---

## Biểu mẫu
- **Location**: `si-gt8-pm/bieu-mau/`
- **Số lượng**: ~50 biểu mẫu mẫu
