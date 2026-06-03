# Workshop — Mổ App AI Thật: Moni (MoMo)

**Sản phẩm được chọn:** MoMo — Moni
**AI feature:** Trợ thủ tài chính, phân tích chi tiêu, chatbot trong app.
**Thời gian thực hiện:** 40 phút.
**Output:** Finding note + Sketch `as-is / to-be`.

---

## 1. Dùng thử: Promise vs Reality

### 1.1. Product hứa gì?
Moni hứa hỗ trợ 5 khía cạnh chính:
* Theo dõi chi tiêu (ngày/tháng/năm).
* Phân loại chi tiêu thông minh.
* Gợi ý tiết kiệm, đầu tư phù hợp mục tiêu.
* Tư vấn ngân sách để tránh "cháy ví".
* Phân tích xu hướng chi tiêu.

### 1.2. Kỳ vọng AI làm được task nào?
1. **Tra cứu chi tiêu:** Cung cấp con số chính xác dựa trên dữ liệu giao dịch thực tế của người dùng MoMo.
2. **Tư vấn tài chính:** Đưa ra kế hoạch tiết kiệm dựa trên thu nhập và lịch sử chi tiêu thực tế, thay vì chỉ đưa ra lời khuyên lý thuyết chung.

---

## 2. Prompt/input đã thử

* **Query 1:** "Tháng rồi mình chi bao nhiêu cho ăn uống?"
* **Query 2:** "Làm sao để mình tiết kiệm được 1 triệu/tháng với thu nhập hiện tại?"

---

## 3. Hành vi quan sát được & Điểm gãy (Observations)

* **Observation 1 (Tra cứu):** Moni trả lời tốt về số liệu (238.000đ cho ăn uống). Tuy nhiên, luồng tương tác kết thúc bằng câu hỏi đóng, thiếu các bộ lọc (filter) hoặc nhãn (tag) nhanh để người dùng đi sâu hơn vào dữ liệu.
* **Observation 2 (Tư vấn):** Moni đưa ra nguyên tắc "Pay Yourself First". Đây là kiến thức đúng nhưng mang tính lý thuyết, thiếu cá nhân hóa. AI không chỉ ra được các khoản chi cụ thể (vd: ăn vặt, giải trí) mà user có thể cắt giảm ngay dựa trên lịch sử giao dịch.

---

## 4. Vẽ 4 Paths

| Path | Quan sát trên Moni |
| :--- | :--- |
| **Happy** | AI hiểu intent và trả lời con số/lý thuyết đúng trọng tâm. |
| **Low-confidence** | Chưa rõ ràng; AI thường "chém" theo lý thuyết khi thiếu dữ liệu cá nhân thay vì hỏi lại user. |
| **Failure** | Khi AI đưa ra lời khuyên không sát, không có cơ chế "Sửa" hoặc "Báo thông tin sai". |
| **Correction** | User phải chat lại từ đầu, không có sự ghi nhớ preference trong hội thoại. |

---

## 5. Finding thành quyết định product

### Finding chính: AI "Lý thuyết hóa" thay vì "Thực thi hóa"
Khi user hỏi về kế hoạch tiết kiệm, AI đưa ra nguyên tắc chung thay vì dùng dữ liệu giao dịch thực tế để thiết lập hành động cụ thể (ví dụ: đặt lệnh chuyển tiền tiết kiệm).
Lỗi thuộc layer: Intent (thiếu khả năng thực thi hành động) + UX Recovery (thiếu cơ chế tiếp nối hành động).
* **Product decision:** Chuyển đổi Moni từ "Trợ lý tư vấn" sang "Trợ lý thực thi" bằng cách nhúng Interactive Widgets (Nút: "Đặt lịch tiết kiệm ngay", "Xem chi tiết giao dịch") trực tiếp vào khung chat.

---

## 6. Sketch As-is / To-be

### As-is
`User hỏi` -> `AI trả lời lý thuyết` -> `AI hỏi tiếp (đóng)` -> **[KẸT]** (User phải tự thoát chat, đi tìm tính năng cài đặt tiết kiệm trong menu MoMo).

### To-be
`User hỏi` -> `AI phân tích dữ liệu thực` -> `AI trả lời + Hiển thị nút "Đặt lịch ngay"` -> `User nhấn nút` -> `Mở sẵn màn hình cài đặt với con số gợi ý` -> `Hoàn tất trong luồng chat`.

---

## 7. Đề xuất SPEC change

* **Requirement 1 (Action-Oriented):** Mọi lời khuyên tài chính phải đi kèm ít nhất một "Quick Action" dẫn thẳng đến tính năng tương ứng trong MoMo.
* **Requirement 2 (Context-Aware):** Ưu tiên sử dụng dữ liệu lịch sử giao dịch thực tế để đưa ra lời khuyên thay vì văn bản thuần túy.
