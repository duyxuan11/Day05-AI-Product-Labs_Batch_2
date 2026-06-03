
# Evidence Pack — WonderPath AI

Nộp kèm thin SPEC cuối Day 05.

## 1. Nhóm và track

**Tên nhóm:** Group C2  
**Thành viên nhóm:**
- Nguyễn Văn Đoan — 2A202600795 (Trưởng nhóm / Repo Owner)
- Nguyễn Huy Bảo — 2A202600997 (SPEC Lead & AI Engineer)
- Lê Duy Hùng — 2A202600718 (Frontend Developer)
- Phạm Ngọc Vinh — 2A202600563 (Backend Developer)
- Tạ Duy Xuân — 2A202600970 (Product Owner & Slide Demo)
**Track:** Travel & Hospitality (Khu vui chơi phức hợp / Theme Parks)  
**Product/app đã chọn:** WonderPath AI — Trợ lý dẫn đường ngữ cảnh (Context-Aware Micro-Itinerary / Zero-UI)  
**Build slice đang nghĩ:** Web App/Zalo Mini App kích hoạt qua mã QR tại các điểm chạm vật lý trong công viên, tự động thu thập vị trí hiện tại và thời gian thực (Zero-Input). Giao diện mở ra là một hội thoại siêu ngắn (Conversational UI sử dụng Gemini API) chào đón và đề xuất 2-3 lựa chọn phản hồi nhanh bằng nút bấm để sinh lịch trình ngắn hạn trong 1-2 tiếng tiếp theo thay vì bắt người dùng vào trình soạn lập lịch trình phức tạp.

## 2. Self-use evidence

Nhóm tự dùng app/workflow và ghi lại điểm gãy.

| Observation | Screenshot/link | Path liên quan | Điều học được |
|---|---|---|---|
| Giao diện lập lịch trình trên các app du lịch bắt buộc người dùng tự thêm hoạt động, căn chỉnh giờ giấc, kéo thả sắp xếp phức tạp. Người đi chơi thường lười lục lọi và ngại nghiên cứu các công cụ lập lịch rườm rà này. | [Complex Planner Interface](file:///e:/Work/VIN%20AI/Gr%20D5/Day05-AI-Product-Labs_Batch_2/02-group-spec/evidence/complex_planner.png) | **Failure (Interaction Friction / Cognitive Load)** | Tránh đưa người dùng vào một trình soạn lập lịch trình. Dùng AI gợi ý lịch trình vi mô 1-2 tiếng ngay lập tức dựa trên ngữ cảnh quét QR. |
| Mô tả các trò chơi trên bản đồ và thông tin ứng dụng rất sơ sài (chỉ có tên và 1 dòng tóm tắt chung chung, không ghi rõ độ tuổi, mức độ cảm giác mạnh hay các lưu ý sức khỏe). User không đủ thông tin để quyết định đi đâu tiếp. | [Sketchy Game Details](file:///e:/Work/VIN%20AI/Gr%20D5/Day05-AI-Product-Labs_Batch_2/02-group-spec/evidence/sketchy_description.png) | **Low-confidence** | AI Bot cần cung cấp thông tin trò chơi thông minh, tóm tắt nhanh độ phù hợp (ví dụ: có trẻ nhỏ, người già) ngay trong hội thoại ngắn để hỗ trợ ra quyết định. |
| Lịch trình cố định lập từ nhà bị vỡ hoàn toàn khi trò chơi chủ chốt (Tàu lượn siêu tốc) bảo trì đột xuất lúc 10:00. App không cập nhật lại lộ trình tự động, user phải tự mò mẫm đổi hướng hoặc đi lòng vòng. | [Static Itinerary Error](file:///e:/Work/VIN%20AI/Gr%20D5/Day05-AI-Product-Labs_Batch_2/02-group-spec/evidence/itinerary_broken.png) | **Failure / Correction** | Bản kế hoạch tĩnh cả ngày quá dễ gãy. Lịch trình cần chia nhỏ thành các block ngắn hạn (1-2 tiếng tiếp theo) và cập nhật tức thời theo ngữ cảnh thực tế của công viên. |

## 3. User / review / social evidence

Nguồn có thể là review App Store/Play, group, comment, phỏng vấn nhanh, hoặc nguồn public khác.

| Quote / review / observation | Nguồn | User là ai? | Pain/failure mode |
|---|---|---|---|
| "Mấy app lập lịch trình phức tạp quá, bắt chọn điểm đi điểm đến rồi xếp giờ y như thời khóa biểu đi học. Đi chơi giải trí mà bắt đầu óc suy nghĩ nhiều thế tôi lười dùng lắm." | Review trên Google Play Store (App lập kế hoạch du lịch) | Khách du lịch trẻ muốn thư thả, tự do. | **High User Friction** (Người dùng lười nghiên cứu công cụ lập lịch trình thủ công, muốn có gợi ý ăn ngay). |
| "Bản đồ app chỉ ghi 'Tàu lượn siêu tốc' chứ không mô tả trò này lắc mạnh thế nào, có phù hợp với trẻ em hoặc người sợ độ cao không. Suýt nữa tôi cho con nhỏ vào chơi, may hỏi nhân viên đứng ngoài." | Review App Store (VinWonders App) | Phụ huynh đi cùng con nhỏ. | **Information Gap** (Mô tả trò chơi quá sơ sài, thiếu thông tin đánh giá độ phù hợp của trò chơi). |
| "Lên lịch đi xem Show nhạc nước lúc 19:00. Đang đi giữa đường thì trời đổ mưa giông lớn, show bị hủy. App không báo gì, vẫn chỉ đường ra hồ. Rốt cuộc cả nhà chạy tán loạn tìm chỗ trú mưa." | Group Facebook "Kinh nghiệm du lịch Phú Quốc" | Cặp đôi đi du lịch tự túc. | **Fragility of Static Plans** (Sự đổ vỡ của kế hoạch tĩnh trước biến số thời tiết đột ngột). |
| "Đứng ở ngã tư ngơ ngác không biết đi hướng nào tiếp. Mở app định vị GPS thì app xoay mòng mòng chỉ sai hướng. Rốt cuộc đi nhầm đường, cuốc bộ cả cây số mệt rã rời dưới trời trưa nắng gắt." | Phỏng vấn nhanh khách hàng tại VinWonders Nam Hội An | Khách du lịch nhóm bạn trẻ. | **Context & Timing Disconnect** (Bản đồ tĩnh và gợi ý không bắt kịp nhu cầu tức thời tại chỗ). |

Nếu chưa có nguồn ngoài nhóm, ghi rõ:

```text
Đây là giả định dựa trên khảo sát sơ bộ và phản hồi thu thập trực tuyến. Nhóm sẽ kiểm chứng thực tế bằng cách phỏng vấn nhanh 5-7 du khách trực tiếp tại khuôn viên khu vui chơi về hành vi sử dụng ứng dụng bản đồ trước checkpoint M1 Day 06.
```

## 4. Competitor / analog evidence

| App / mô hình tham khảo | Họ xử lý task này thế nào? | Pattern học được | Có áp dụng trong 1 ngày không? |
|---|---|---|---|
| **Disney Genie+ (My Disney Experience App)** | Cho phép chọn sở thích cá nhân, sau đó tự động gợi ý trò chơi tiếp theo dựa trên thời gian chờ xếp hàng thực tế (Wait Times) và vị trí của khách hàng. | **Dynamic Routing & Queue Optimization:** Định tuyến động dựa trên dữ liệu hàng đợi thời gian thực. | Cắt giảm scope: Disney Genie+ rất nặng và phức tạp. Nhóm sẽ học pattern gợi ý động dựa trên Wait Times nhưng triển khai dưới dạng gợi ý siêu ngắn thông qua hội thoại (Conversational UI) quét QR. |
| **Zalo Mini App / WeChat Mini Program (Analog)** | Cho phép người dùng quét mã QR tại các nhà hàng để tự động nhận biết số bàn, hiển thị menu gọi món và thanh toán ngay mà không cần tải ứng dụng hay đăng nhập. | **Physical Touchpoint Integration (Kết nối điểm chạm vật lý) & Zero-Install.** | Có. Đặt mã QR tại các bảng chỉ đường của từng khu vực. Khách quét mã để tự động truyền ID vị trí và thời gian thực vào chatbot, kích hoạt câu chào AI thông minh thay vì điền biểu mẫu. |

## 5. Evidence -> Insight

```text
Evidence nổi bật nhất:
Du khách cực kỳ lười và ngại nghiên cứu các công cụ lập lịch trình phức tạp hoặc tự tìm hiểu mô tả trò chơi sơ sài khi đi chơi. Đồng thời, mọi lịch trình lên sẵn (static plan) từ trước đều dễ dàng bị phá vỡ bởi các biến số thực tế: thời tiết thay đổi đột ngột, trò chơi bảo trì, hoặc hàng đợi quá dài khiến họ mệt mỏi.

Insight:
User không chỉ cần một công cụ chứa thông tin (surface need).
Thật ra họ cần một trợ lý hỗ trợ ra quyết định tức thời, cực kỳ tối giản (Zero-UI/Zero-Input) để có ngay gợi ý lịch trình ngắn hạn (1-2 tiếng) tối ưu phù hợp với vị trí và nhóm đi cùng, thay vì phải tự nghiên cứu và vào trình soạn lập lịch trình phức tạp.

Opportunity:
AI có thể giúp bằng cách kết hợp mã QR vật lý để lấy vị trí/thời gian tự động (Zero-Input), sử dụng Gemini API để tạo cuộc trò chuyện siêu ngắn (Conversational UI) cung cấp nhanh thông tin trò chơi và gợi ý lịch trình ngắn hạn (1-2 tiếng) thông qua các nút bấm phản hồi nhanh.
```

## 6. Evidence đổi SPEC như thế nào?

- [x] Đổi user chính.
- [ ] Đổi pain statement.
- [x] Đổi build slice.
- [x] Đổi Auto/Aug decision.
- [x] Đổi 4 paths.
- [ ] Đổi failure mode.
- [ ] Đổi owner/test plan.

Ghi rõ 1-2 thay đổi quan trọng:

```text
Trước evidence, nhóm định xây dựng một ứng dụng di động (Native App) đầy đủ tính năng giúp du khách lên lịch trình vui chơi chi tiết từ sáng đến tối trước khi đi, yêu cầu điền khảo sát sở thích cá nhân sâu để thiết kế lộ trình cố định cho cả ngày.

Sau evidence, nhóm đổi thành xây dựng một Web App/Zalo Mini App siêu nhẹ (Zero-Install). Khi quét mã QR tại các trạm vật lý hoặc định vị tại chỗ, hệ thống tự động nắm giữ vị trí & thời gian hiện tại, AI (Gemini API) lập tiếp đón bằng một cuộc hội thoại siêu ngắn chào đón và đưa ra các gợi ý lịch trình ngắn hạn trong 1-2 tiếng tiếp theo dưới dạng các nút bấm phản hồi nhanh (Zero-Input) thay vì bắt người dùng vào trình soạn lập lịch trình phức tạp.

Lý do: Khách hàng đi chơi muốn thư giãn tuyệt đối, cực kỳ lười tự nghiên cứu công cụ lập lịch hay tự đọc các mô tả trò chơi sơ sài. Việc gợi ý ngay lịch trình 1-2 tiếng thông qua hội thoại quét QR giúp tối thiểu hóa ma sát tương tác, phản ứng linh hoạt trước biến động vận hành thực tế của công viên.
```

