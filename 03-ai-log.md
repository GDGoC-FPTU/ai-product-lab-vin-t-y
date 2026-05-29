# 03 — AI Log (Nhật ký cá nhân)

Họ tên: Nguyễn Mạnh Hiếu
Nhóm / Lớp: Vin Tạy

---

### 1) AI giúp gì
- Brainstorm các ý tưởng và soạn danh sách cơ hội (Phase 1).
- Soạn và siết chặt `SYSTEM_PROMPT` (bắt buộc thẻ `[DRAFT_ONLY]`, quy tắc pin <5% => dispatch mobile charger).
- Soạn 3 Quick Problem Cards và phần Problem Statement / Future-State cho Deep-Dive.
- Viết mẫu `evaluate_prompt()` để gọi Gemini hoặc trả mock khi không có API key.

AI giúp tăng tốc công việc chuẩn bị tài liệu, cấu trúc nội dung và cung cấp các biến thể prompt để thử nghiệm.

---

### 2) AI sai gì / rủi ro quan sát được
- Hallucination / SDK mismatch: Một số gợi ý về API (ví dụ: hàm `configure` / `generate`) khác giữa các phiên bản SDK — có thể gây lỗi runtime nếu dùng trực tiếp.
- Prompt bypass risk: Nếu SYSTEM_PROMPT không đủ chặt, model có thể bị user cố tình lừa để bỏ thẻ `[DRAFT_ONLY]` hoặc đề xuất hành động nguy hiểm.

---

### 3) Tôi đã sửa đổi như thế nào
- Thêm fallback mock response khi SDK không khả dụng, tránh tin tưởng tuyệt đối vào đầu vào SDK từ LLM.
- Siết chặt `SYSTEM_PROMPT` bằng chỉ dẫn rõ ràng và ví dụ mẫu JSON để ép định dạng và hành vi.
- Thiết kế kiến trúc hybrid: rule engine cho các kiểm tra an toàn (battery/distance) trước khi gọi LLM; HITL cho quyết định cuối cùng.

---

### 4) Bài học rút ra
- Xác định ranh giới an toàn bằng rule-based gates trước LLM.
- Luôn kiểm chứng output của LLM và giữ con người ở vòng lặp cho quyết định critical.
- Viết prompt hệ thống rõ ràng và có ví dụ cụ thể để giảm prompt-injection.

---

### 5) Hành động tiếp theo
1. Chạy nhiều adversarial tests (mock + thật) và log mọi vi phạm.
2. Cập nhật bộ test và SYSTEM_PROMPT dựa trên kết quả.
3. Chuẩn hoá tài liệu nộp (slides, README) cho buổi đánh giá.

***
