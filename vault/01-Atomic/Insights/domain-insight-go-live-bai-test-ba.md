---
title: "Tuần go-live không test sản phẩm — nó test BA"
created: 2026-09-21
updated: 2026-09-21
type: insight
status: atomic
source: "KBC Community go-live T9/2026"
discovered_from: "15 người, đối tác Hàn, requirements tiếng Hàn — mọi thứ 'dev done' nhưng tuần go-live là tuần bận nhất"
confidence: high
related:
  - "[[pm-insight-negotiation-scope-decoupling]]"
  - "[[tech-insight-ai-multiplies-ba-value]]"
used_count: 0
used_in:
  - "[[../../00-Inbox/2026-09-20-linkedin-go-live-la-bai-test-ba]]"
tags: ["ba-pm", "go-live", "project-management", "outsourcing", "kbc", "domain-knowledge"]
maturity: seed
review_interval: 14
next_review: 2026-10-05
reuse_count: 0
evolution_log:
  - date: 2026-09-21
    change: "Tạo từ KBC Community go-live + LinkedIn draft 2026-09-20"
---

# Tuần go-live không test sản phẩm — nó test BA

## The Insight

Sau months của spec, sprint, review — go-live week là giai đoạn lộ ra **tất cả những gì BA chưa làm rõ**.

Không phải bug của developer. Không phải thiếu feature. Mà là những assumption mơ hồ trong spec mà cả team đã ngầm chấp nhận — và thực tế production không chấp nhận.

Trong tuần đó:
- Stakeholder hỏi những câu không có trong user story nào
- Đối tác ở múi giờ khác, ngôn ngữ khác — cần xác nhận trong 2 giờ
- Có 3 cách handle cùng 1 tình huống — và team nhìn vào BA để chọn

**Curriculum BA/PM dạy deliver đúng spec. Go-live test khả năng quyết định khi spec không đủ.**

## Evidence

### KBC Community — T9/2026
- Team: 15 người, outsource với Quantit (partner Hàn Quốc)
- Requirements gốc viết bằng tiếng Hàn, design từ team khác
- Tháng 5: đàm phán tách Admin scope khỏi contract chính — scope chưa rõ, không ký
- Tháng 9 go-live: Admin scope thành CR riêng, team không bị kéo ngoài phạm vi
- Quyết định 1 buổi đàm phán → bảo vệ 4 tháng sprint của 15 người

### ConstructHub — gần go-live
- Team 2 người + AI
- Câu hỏi go-live thực tế: *"Tính năng này user có thực sự dùng không, hay chỉ nghe hay trong demo?"*
- AI không trả lời được — BA phải trả lời dựa trên thời gian đã ngồi với user

## Pattern: BA Skills được test trong go-live

| Skill | Được test như thế nào |
|---|---|
| Scope clarity | Những gì "ngầm hiểu" trong spec bị thực tế bóc trần |
| Decision under uncertainty | Phải chọn trong 2 giờ, không có đủ thông tin |
| Stakeholder translation | Bridge giữa đối tác nước ngoài và team local |
| Scope protection | Quyết định tháng 5 bảo vệ được team tháng 9 |

## Implication

**Chuẩn bị cho go-live từ sprint đầu tiên, không phải sprint cuối.**

Mỗi assumption mơ hồ trong spec là một câu hỏi sẽ xuất hiện trong go-live. BA giỏi reduce số lượng câu hỏi đó — không phải bằng cách spec dày hơn, mà bằng cách validate assumption sớm hơn.

## Applications

- **Junior BA/PM**: Go-live không phải finish line — là stress test cho mọi assumption bạn đã làm từ sprint 1. Audit lại spec trước go-live: câu nào "ngầm hiểu"?
- **IT Freelancers outsourcing**: Scope protection không phải để khó khăn với khách hàng — là điều kiện để cả hai deliver được cam kết. Scope mơ hồ → go-live thảm họa cho cả hai.
- **Career changers**: Kỹ năng có giá trị nhất trong go-live: **ra quyết định nhanh khi thiếu thông tin đầy đủ**. Không cần background kỹ thuật để học kỹ năng này.
