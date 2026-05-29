

## Phase 1 — SCAN (5 opportunities)

Áp dụng 4 lenses: Repetitive / Time-consuming / AI-upgrade / Stakeholder Pain

| # | Subsidiary | Lens | Mô tả ngắn bài toán |
|---:|---|---|---|
| 1 | Xanh SM | Repetitive / Time-consuming | Tài xế phải xác nhận, chỉnh sửa và gửi báo cáo lộ trình thủ công sau mỗi ca — tốn thời gian và dễ sai sót. |
| 2 | VinFast | AI-upgrade | Hệ thống cảnh báo pin đôi khi không chính xác, dẫn tới đề xuất trạm sạc không phù hợp với tình trạng thực tế. |
| 3 | Vinhomes | Time-consuming | Nhân viên CSKH soạn phản hồi khiếu nại (1-star) thủ công, mất nhiều thời gian và thiếu nhất quán. |
| 4 | Vinmec | Stakeholder Pain | Phân loại hồ sơ khám bệnh thủ công mất thời gian, làm chậm luồng xử lý bệnh nhân. |
| 5 | VinFast / Xanh SM | Repetitive | Điều phối mobile charger khi sự cố pin yêu cầu lựa chọn thủ công, dẫn đến chậm trễ và quyết định không nhất quán. |

---

## Phase 2 — QUICK-ASSESS (3 Quick Problem Cards)

Chọn top 3 ưu tiên từ danh sách SCAN và hoàn thiện thẻ bài dưới đây.

```
QUICK PROBLEM CARD #1

Tên bài toán: Tối ưu hoá quy trình xác nhận báo cáo lộ trình ca
Công ty thành viên: Xanh SM
Ai đang đau (Actor)? Tài xế và điều phối viên vận hành
Workflow thủ công hiện tại:
 1) Tài xế gửi log thô → 2) Điều phối viên kiểm tra/chỉnh sửa → 3) Gửi báo cáo cuối ca
Bước tốn thời gian nhất: Bước 2 — 8–12 phút/lượt
AI hỗ trợ: Tự động chuẩn hoá dữ liệu, phát hiện anomalies và gợi ý sửa
Metric: Giảm thời gian kiểm tra từ 10 phút → <=2 phút; Tỉ lệ lỗi <2%
Kiến trúc: LLM + HITL
```

```
QUICK PROBLEM CARD #2

Tên bài toán: Ranh giới an toàn trong đề xuất trạm sạc khi pin thấp
Công ty: VinFast
Ai đang đau? Khách hàng EV, CSKH, đội cứu hộ
Workflow hiện tại: 1) Telemetry → 2) System suggests → 3) Human review → 4) Dispatcher decision
Bước tốn thời gian nhất: Bước 3 (⏱ ~5–10 phút khi lỗi)
AI hỗ trợ: Cross-check sensor data; enforce rule: pin <5% -> dispatch mobile charger
Metric: Giảm sai sót gợi ý trạm từ 6% → <=1%; Phản hồi khẩn cấp <1 phút
Kiến trúc: Rule + LLM + HITL
```

```
QUICK PROBLEM CARD #3

Tên bài toán: Tự động hoá soạn thảo phản hồi khiếu nại cư dân
Công ty: Vinhomes
Ai đang đau? Nhân viên CSKH, quản lý tòa nhà
Workflow: 1) Cư dân gửi khiếu nại → 2) Nhân viên soạn nháp → 3) Quản lý phê duyệt → 4) Gửi trả lời
Bước tốn thời gian nhất: Bước 2–3 (⏱ ~15–25 phút)
AI hỗ trợ: Phân loại, tạo draft, gợi ý chỉnh sửa
Metric: Rút ngắn 20 phút → <=5 phút; 90% phản hồi phù hợp
Kiến trúc: LLM + Rule templates + HITL
```

---

## Ghi chú cá nhân
- Lý do chọn 3 bài trên: tác động lớn, dễ đo lường, phù hợp để thử prototype prompt-boundary.
- Next step: thảo luận nhóm chọn 1 vấn đề để deep-dive (khuyến nghị: VinFast battery boundary).

***
