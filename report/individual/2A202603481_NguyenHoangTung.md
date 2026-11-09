# Báo cáo cá nhân — 2A202603481_NguyenHoangTung

> Đổi tên file theo quy tắc `MSSV_HoTen.md`, ví dụ `20241234_NguyenVanAn.md` (MSSV trước, dấu `_`, họ tên viết liền không dấu). Sửa cả dòng tiêu đề phía trên cho khớp.
> Template chi tiết và prompt mẫu cho từng mục: [docs/01-worksheet.md](../../docs/01-worksheet.md).
> Mỗi thành viên một file trong `report/individual/` trên repo nhóm: copy template này thành file mới, điền, rồi commit bằng tài khoản GitHub của bạn. Không viết hộ người khác.

## 1. Thông tin học viên

- Họ tên: Nguyễn Hoàng Tùng
- MSSV: 2A202603481
- Email trường (không bắt buộc, repo có thể để public): 
- Tên nhóm: MH2T
- Link repo nhóm: https://github.com/nhtng0212/K5-L3A-Day02-MH2T-DiscoveryProblemFraming

---

## 2. Scan problem (CP1)

Lăng kính: **Lặp lại** · **Tốn thời gian** · **Cần đọc, tổng hợp nhiều thông tin** · **Pain từ người khác**.

| # | Lăng kính | Job Story: Khi… tôi muốn… để… | Ai chịu ảnh hưởng? | Dấu hiệu thật (thời gian, tần suất, số người, bằng chứng) |
|---:|---|---|---|---|
| 1 | Pain từ người khác | Khi nhân viên mới gia nhập công ty trong tuần đầu tiên, nhân viên muốn tra cứu nhanh chính sách nghỉ phép, bảo hiểm và quy định xin phê duyệt công tác, để không phải liên tục nhắn tin hỏi nhân sự | Nhân viên mới (Onboarding), Bộ phận Nhân sự (HR) | HR nhận 10–15 tin nhắn lặp lại mỗi tuần hỏi cùng một nội dung về ngày phép; nhân viên mới mất 2–3 ngày chờ phản hồi |
| 2 | Tốn thời gian | Khi nhận 200–300 hóa đơn đầu vào bằng ảnh/PDF mỗi tháng, tôi muốn nhập thông tin mã số thuế, số tiền, ngày lập vào phần mềm kế toán, để kịp lập tờ khai thuế GTGT trước ngày 20 | Kế toán viên thuế, Kế toán trưởng | Mất 3–4 ngày làm việc liên tục mỗi tháng; trung bình phát hiện 3–5 hóa đơn bị gõ nhầm mã số thuế hoặc tiền thuế |
| 3 | Cần đọc, tổng hợp |Khi chuẩn bị nộp bài tập lớn/bài lab kỹ thuật trước hạn chót, tôi muốn đối chiếu toàn bộ các mục trong rubric chấm điểm với các file hiện có trong repo, để không bị trừ điểm vì thiếu file hoặc đặt sai tên file | Sinh viên CNTT, Trợ giảng chấm bài | Mất 30–45 phút kiểm tra chéo thủ công từng tiêu chí; đợt lab trước có 20% sinh viên bị trừ điểm vì sai format nộp |
| 4 | Pain từ người khác | Khi khách hàng nhắn tin hỏi về chính sách bảo hành và đổi trả hàng trên fanpage lúc nửa đêm, khách hàng muốn biết đơn hàng của mình có đủ điều kiện đổi trả không, để kịp gửi hàng trả trong hạn quy định | Khách hàng mua sắm online, Chủ shop online | Shop nhận 20–30 tin nhắn đêm mỗi tuần; 15% khách hủy đơn hoặc đánh giá 1 sao vì sáng hôm sau mới nhận được phản hồi |
| 5 | Tốn thời gian | Khi nhận video/bản ghi âm cuộc họp dự án kéo dài 1–2 tiếng, tôi muốn trích xuất các quyết định chính và action items kèm người phụ trách, để gửi biên bản cuộc họp cho cả team | Project Coordinator, Thành viên dự án | Mất 1.5 đến 2 tiếng nghe lại và tua qua các đoạn thảo luận lan man; biên bản thường gửi trễ sau cuộc họp 1 ngày |

**Nếu có dùng AI để gợi ý thêm:** ý nào AI gợi ý mà bạn giữ lại, ý nào bỏ và vì sao.

- *Ý giữ lại:* Giữ lại ý #2 (Nhập liệu hóa đơn) và ý #5 (Trích xuất quyết định cuộc họp) vì đây là các công việc tốn rất nhiều thời gian thực tế lặp lại, có quy trình tương đối rõ ràng.
- *Ý bỏ đi:* Bỏ ý "Trợ lý AI tự động quản lý toàn bộ dự án" và "Chatbot trả lời chung chung" vì quá rộng, không chỉ ra được bước nghẽn cụ thể và là giải pháp đội lốt vấn đề.

---

## 3. Top 3 Problem Cards + quy trình nháp (CP2)

### Bảng chọn top 3

| Rank | Problem | Vì sao chọn | Điều còn chưa chắc |
|---:|---|---|---|
| 1 | Trích xuất quyết định và action items từ bản ghi âm/video cuộc họp (#5) | Nỗi đau lặp lại hàng tuần của mọi dự án; quy trình nghe lại và soạn biên bản tốn 1.5–2 tiếng; có bottleneck rất cụ thể; impact đo lường được bằng thời gian gửi biên bản và tỷ lệ sót việc | Độ chính xác khi cuộc họp có nhiều người nói chèn nhau, tiếng ồn môi trường hoặc từ ngữ chuyên ngành (jargon) đặc thù |
| 2 | Đối chiếu rubric chấm điểm & kiểm tra format nộp bài lab (#3) | Actor rõ (sinh viên CNTT, TA), quy trình các bước nộp bài và tiêu chí chấm cụ thể, impact đo được ngay bằng tỷ lệ trừ điểm và thời gian kiểm tra | Cách parse các tiêu chí rubric định tính hoặc rubric phức tạp có nhiều điều kiện ràng buộc chéo |
| 3 | Nhập liệu hóa đơn đầu vào ảnh/PDF vào phần mềm kế toán (#2) | Vấn đề quen thuộc kế toán viên, tần suất lặp lại nhiều hàng ngày, hàng tháng, sai sót gây hậu quả tài chính/phạt thuế trực tiếp | Hóa đơn scan chất lượng kém hoặc hóa đơn viết tay có thể gây sai sót số liệu, sai sót là cực kì nguy hiểm trong ngành kế toán |

### Problem Card #1

| Trường | Nội dung |
|---|---|
| Job Story | Khi kết thúc cuộc họp dự án kéo dài 1–2 tiếng, tôi muốn trích xuất các quyết định chính và danh sách việc cần làm (action items) kèm người phụ trách, để gửi biên bản cuộc họp cho cả team trước 17h cùng ngày |
| Actor | Project Coordinator / Scrum Master / Thư ký cuộc họp / Team Lead |
| Thời điểm / bối cảnh | Ngay sau khi kết thúc cuộc họp liên phòng ban hoặc họp sprint (thường vào chiều thứ Ba hoặc thứ Năm) |
| Quy trình hiện tại (3–7 bước) | 1. Tải bản ghi âm/video từ Google Meet / Zoom về · 2. Mở file vừa nghe vừa tua tốc độ 1.5x · 3. Ghi chép nháp các nội dung trao đổi ra Google Docs · 4. Lọc ra các quyết định đã chốt và các đầu việc cần làm · 5. Format lại thành biên bản cuộc họp chuẩn · 6. Gửi email/Slack cho các thành viên dự họp xác nhận |
| Bottleneck (bước nào, mất bao nhiêu phút) | **Bước 2 & 3 (Vừa nghe lại vừa tua và ghi chép nháp):** mất từ 60–75 phút vì phải liên tục tua lại những đoạn âm thanh không rõ, tranh luận lan man hoặc bị ngắt lời |
| Impact (nếu không giải thì sao) | Mất 1.5–2 tiếng cho mỗi cuộc họp; biên bản thường gửi trễ sau 24h khiến thành viên quên ngữ cảnh hoặc triển khai chậm trễ các task quan trọng |
| Success metric (baseline → target) | Tổng thời gian soạn biên bản giảm từ 90 phút xuống dưới 15 phút; 100% biên bản được gửi trong vòng 1 giờ sau họp; tỷ lệ sót action items giảm về 0% |
| Phương án không dùng AI | Thư ký gõ trực tiếp biên bản trong lúc họp; cuối buổi dành 5 phút cho chủ tọa đọc to chốt lại các action items để ghi nhận |
| Giả thuyết về AI (nếu có) | Dùng Speech-to-Text chuyển băng sang văn bản, sau đó dùng LLM trích xuất các quyết định, action items (kèm người nhận việc và hạn chót) theo cấu trúc mẫu |
| Cảm nhận nhanh | **Workflow** (STT bóc băng → LLM trích xuất & format draft → Thư ký/PM duyệt trước khi gửi) |

Quy trình nháp hiện tại:

```text
[1. Tải file ghi âm/video: 5'] 
       ↓
[2 & 3. VỪA NGHE VỪA TUA & GHI CHÉP NHÁP (BOTTLENECK): 75'] 
       ↓
[4. Phân loại quyết định & task: 15'] 
       ↓
[5. Format biên bản cuộc họp: 10'] 
       ↓
[6. Gửi email/Slack xác nhận: 5']
```

### Problem Card #2

| Trường | Nội dung |
|---|---|
| Job Story | Khi chuẩn bị nộp bài tập lớn/bài lab kỹ thuật trước hạn chót, tôi muốn đối chiếu toàn bộ các mục trong rubric chấm điểm với các file hiện có trong repo, để không bị trừ điểm vì thiếu file hoặc đặt sai tên file |
| Actor | Sinh viên CNTT, Học viên VinAI |
| Thời điểm / bối cảnh | 1–2 tiếng trước deadline nộp bài (23h59) trên LMS hoặc GitHub Classroom |
| Quy trình hiện tại (3–7 bước) | 1. Mở file đề bài/rubric đọc từng tiêu chí checklist · 2. Mở trình duyệt file trong VS Code đối chiếu tên từng thư mục/file · 3. Mở từng file báo cáo đọc rà soát xem đã điền đủ các mục yêu cầu chưa · 4. Chạy lệnh git status/log kiểm tra commit và push · 5. Copy link repo nộp lên LMS |
| Bottleneck (bước nào, mất bao nhiêu phút) | Bước 3 (Đọc rà soát từng mục trong file báo cáo): mất 20–25 phút, rất dễ hoa mắt bỏ sót mục bắt buộc do áp lực thời gian sát giờ nộp |
| Impact (nếu không giải thì sao) | Mất 30–45 phút/bài; khoảng 20% sinh viên từng bị trừ 5–10 điểm chỉ vì sai tên file hoặc thiếu một mục nhỏ |
| Success metric (baseline → target) | Tổng thời gian kiểm tra giảm từ 40 phút xuống dưới 5 phút; tỷ lệ sinh viên bị trừ điểm vì lỗi cấu trúc/format giảm về 0% |
| Phương án không dùng AI | Dùng checklist giấy tự tích tay hoặc viết script bash/powershell kiểm tra sự tồn tại của file và regex tên file |
| Giả thuyết về AI (nếu có) | AI đọc rubric dạng markdown, đối chiếu với nội dung các file báo cáo để chỉ ra những mục chưa điền hoặc điền chưa đủ ý |
| Cảm nhận nhanh | Workflow (Script kiểm tra tên file/folder + AI kiểm tra nội dung bài viết) |

Quy trình nháp hiện tại:

```text
[1. Đọc Rubric: 5'] 
       ↓
[2. Đối chiếu tên file/folder: 5'] 
       ↓
[3. ĐỌC RÀ SOÁT TỪNG MỤC BÁO CÁO (BOTTLENECK): 20'] 
       ↓
[4. Kiểm tra Git commit/push: 5'] 
       ↓
[5. Copy link nộp LMS: 5']
```

### Problem Card #3

| Trường | Nội dung |
|---|---|
| Job Story | Khi nhận 200–300 hóa đơn đầu vào bằng ảnh/PDF mỗi tháng, tôi muốn nhập thông tin mã số thuế, số tiền, ngày lập vào phần mềm kế toán, để kịp lập tờ khai thuế GTGT trước ngày 20 |
| Actor | Kế toán viên thuế tại doanh nghiệp vừa và nhỏ |
| Thời điểm / bối cảnh | Từ ngày 10 đến ngày 18 hàng tháng (kỳ kê khai thuế) |
| Quy trình hiện tại (3–7 bước) | 1. Tải hóa đơn từ email/Zalo về một thư mục máy tính · 2. Mở từng file PDF/ảnh hóa đơn lên màn hình · 3. Gõ mã số thuế người bán, số hóa đơn, ngày lập vào phần mềm · 4. Tra cứu tính hợp lệ của MST trên trang Thuế · 5. Nhập tiền trước thuế, thuế suất và tiền thuế · 6. Lưu chứng từ và đối chiếu tổng tiền |
| Bottleneck (bước nào, mất bao nhiêu phút) | Bước 3 & Bước 5 (Gõ tay thông tin và số tiền): mất 2–3 phút/hóa đơn (~10–12 tiếng tổng cộng), lặp lại gây mỏi mắt, dễ bấm nhầm số 0 |
| Impact (nếu không giải thì sao) | Mất 3–4 ngày công mỗi tháng; sai 1 chữ số tiền thuế có thể bị truy thu và phạt hành chính từ 5–10 triệu đồng |
| Success metric (baseline → target) | Giảm thời gian nhập liệu từ 3 ngày xuống dưới 4 tiếng; tỷ lệ sai lệch số liệu nhập tay giảm từ 2% xuống 0% |
| Phương án không dùng AI | Yêu cầu đối tác gửi kèm file XML của hóa đơn điện tử để import trực tiếp vào phần mềm kế toán |
| Giả thuyết về AI (nếu có) | Dùng mô hình OCR/Vision bóc tách trường thông tin từ ảnh scan/PDF tự động map vào các trường trên phần mềm |
| Cảm nhận nhanh | Workflow (OCR trích xuất dữ liệu + Kế toán viên duyệt trước khi ghi sổ) |

Quy trình nháp hiện tại:

```text
[1. Tải hóa đơn về máy: 60'] 
       ↓
[2. Mở từng file hóa đơn: 30'] 
       ↓
[3. GÕ TAY MST, SỐ HĐ, NGÀY LẬP (BOTTLENECK 1): 300'] 
       ↓
[4. Tra cứu MST trên trang thuế: 60'] 
       ↓
[5. GÕ TAY SỐ TIỀN VÀ TIỀN THUẾ (BOTTLENECK 2): 300'] 
       ↓
[6. Đối soát tổng tiền & lưu chứng từ: 120']
```

### Card muốn pitch nhất

- Card số: 1 (Trích xuất quyết định và action items từ bản ghi âm/video cuộc họp)
- Vì sao: Đây là nỗi đau thực tế diễn ra hàng tuần ở mọi tổ chức, dự án; bottleneck tốn 60–75 phút nghe lại là rất rõ ràng; dữ liệu kiểm chứng và phỏng vấn hành vi người dùng cực kỳ phong phú; ranh giới và vai trò can thiệp của AI/con người rất tách bạch.
- Câu hỏi muốn nhóm phản biện: *"Làm thế nào để hệ thống trích xuất chính xác các quyết định ngầm (implicit decisions) và phân biệt được giữa việc 'thảo luận một ý tưởng' với việc 'đã chính thức chốt giao task'?"*

### AI đã phản biện card thế nào

| Điểm yếu AI chỉ ra | Đồng ý? | Đã sửa gì |
|---|---|---|
| AI dễ bị ảo giác (hallucination), tự bịa ra người nhận việc hoặc gán nhầm deadline nếu trong cuộc họp mọi người chỉ nói bâng quơ như 'tuần tới làm nhé'. Ngoài ra, cho AI tự động gửi email biên bản là cực kỳ rủi ro. | Hoàn toàn đồng ý | Thiết lập Boundary nghiêm ngặt: AI chỉ tạo bản nháp (draft meeting minutes) có đánh dấu mức độ tin cậy; bắt buộc Thư ký/PM phải review và bấm nút gửi (Human-in-the-loop). Bổ sung quy tắc: nếu câu thoại không có tên người nhận rõ ràng thì AI gắn cờ '[Cần chỉ định người phụ trách]'. |

---

## 4. Tôi đã tham gia phần nào (CP3 → CP7)

| Hoạt động | Tôi đã làm gì? | Kết quả / ảnh hưởng tới bài nhóm |
|---|---|---|
| Pitch Problem Card | Pitch Card #1 về bài toán trích xuất quyết định & action items từ bản ghi âm/video cuộc họp | Nhóm chọn làm candidate problem chính vì tính phổ biến và nỗi đau tốn thời gian rất lớn |
| Phản biện bài của bạn khác | Câu hỏi tôi đã đặt: *"Nếu làm tool OCR nhập hóa đơn thuế thì team giải quyết thế nào với các hóa đơn scan bị mờ hoặc chữ viết tay mà không bị phạt vi phạm hành chính?"* | Giúp bạn trong nhóm nhận ra tính khả thi thấp của việc đưa OCR hóa đơn vào phạm vi lab 4 tiếng |
| Nhận phản biện | Câu hỏi tôi nhận được: *"Làm thế nào để AI phân biệt được người nói đang đề xuất một ý tưởng bâng quơ với một quyết định chính thức đã chốt giao việc?"* | Tôi đã sửa gì: Thêm bước phân loại mức độ tin cậy (Confidence Score) và quy định Boundary: AI chỉ sinh bản nháp, Thư ký/PM bắt buộc review trước khi phát hành |
| Gom cluster / cây OST | Cùng nhóm gom các candidate vào 2 cluster chính: "Tự động hóa tác vụ nghe/tóm tắt lặp lại" và "Chuẩn hóa định dạng bàn giao công việc" | Xây dựng được cây OST với 1 Outcome chung: "Cắt giảm 80% thời gian xử lý thông tin hành chính sau cuộc họp để tập trung vào triển khai" |
| Chọn candidate problem | Cùng chấm điểm ma trận 7 tiêu chí cho 3 bài toán shortlist | Chốt bài toán "Trích xuất quyết định và action items từ cuộc họp" đạt điểm cao nhất (33/35) |
| Kiểm chứng / research | Phỏng vấn trực tiếp 2 bạn làm Project Coordinator và Scrum Master theo phương pháp The Mom Test | Xác nhận nỗi đau mất 60–90 phút nghe lại file ghi âm và phát hiện 40% cuộc họp bị trôi task vì biên bản gửi muộn |
| Quy trình nhóm | Đóng góp xây dựng sơ đồ As-is và To-be cho quy trình lập biên bản cuộc họp | Thiết kế quy trình To-be: STT bóc băng → LLM trích xuất & map template → Con người duyệt và gửi |
| Problem Statement | Phụ trách viết bản nháp Problem Statement v0 và v1 | Xác định rõ boundary (AI không tự ý gửi email/Slack, không tự tạo task trên Jira mà chưa có xác nhận) |
| Mức can thiệp AI | Phân tích ma trận độ mơ hồ × độ phức tạp | Thuyết phục nhóm chọn mức **Workflow** (quy trình định sẵn) thay vì Agent tự hành |
| Quyết định | Tham gia đánh giá 4 rủi ro và xác lập ngưỡng dừng | Thống nhất quyết định **Go, phạm vi hẹp** (bắt đầu từ các cuộc họp nội bộ 30–45 phút) |

---

## 5. Dùng AI

| Checkpoint | Tôi dùng AI để làm gì? | AI hữu ích ở đâu? | AI sai hoặc hời hợt ở đâu? | Tôi sửa gì bằng nhận định của mình? |
|---|---|---|---|---|
| CP1 Scan | Gợi ý thêm các góc nhìn và nhóm ngành ngoài trải nghiệm kỹ thuật của tôi | Mở rộng được các bối cảnh mới như nhân sự, kế toán, chăm sóc khách hàng | Đưa ra các ý kiến giải pháp trá hình như "AI quản lý dự án", "AI tự động phân task" | Tôi lọc bỏ toàn bộ các giải pháp trá hình, chỉ giữ lại các vấn đề có quy trình và bottleneck thật |
| CP2 Problem Card | Đóng vai "PM hoài nghi" để phản biện điểm yếu của Card #1 | Chỉ ra nguy cơ AI bị ảo giác và tự gán nhầm người nhận task nếu hội thoại không rõ ràng | Đề xuất giải pháp Agent tự động gửi email cho cả team (quá rủi ro và thiếu kiểm soát) | Giữ mức Workflow, bổ sung bước bắt buộc con người xác nhận (HITL) trước khi gửi biên bản |
| CP4 Research | Tìm kiếm các công cụ meeting assistant và transcription hiện có trên thị trường | Liệt kê nhanh các công cụ như Otter.ai, Fireflies.ai, Fathom, Microsoft Teams Copilot | Đánh giá hời hợt về rào cản ngôn ngữ tiếng Việt và chi phí doanh nghiệp | Tôi tự tìm hiểu thêm về Whisper và các mô hình mã nguồn mở hỗ trợ tiếng Việt tốt |
| CP5 Quy trình | Chuyển sơ đồ quy trình dạng text sang cú pháp Mermaid | Sinh cú pháp Mermaid nhanh, không bị lỗi cú pháp | Bỏ quên nhánh rẽ khi file ghi âm bị lỗi âm thanh hoặc có quá nhiều tạp âm | Tôi bổ sung phương án quay về (fallback): cảnh báo đoạn âm thanh mờ để thư ký tự kiểm tra thủ công |
| CP5–6 Problem Statement | Rà soát xem Problem Statement có bị lẫn giải pháp vào problem không | Phát hiện câu chữ trong phần bottleneck còn hơi hướng kỹ thuật | Gợi ý thêm các metric chung chung như "tăng hiệu suất làm việc" | Tôi sửa lại metric thành con số định lượng cụ thể: từ 90 phút xuống dưới 15 phút, 100% biên bản gửi trong vòng 1h |
| CP6 Mức can thiệp / quyết định | So sánh giữa mức Workflow và mức Agent | Phân tích rõ các rủi ro về chi phí token và tính ổn định nếu dùng Agent | Đánh giá thấp rủi ro Viability (vấn đề bảo mật thông tin nội bộ cuộc họp) | Tôi nâng mức rủi ro Viability lên Trung bình và ghi chú giải pháp tự host mô hình hoặc che dữ liệu nhạy cảm |

---

## 6. Reflection (CP7)

Trả lời bằng trải nghiệm thật của bạn, tối thiểu 200 từ cho các câu 6.1–6.6 (không tính 6.7, câu này được chấm riêng ở tiêu chí C5). **Không dùng AI để viết thay.**

**6.1. Tôi học được gì khi nghe top 3 problems của các bạn khác?**
Thường các bạn nghĩ ra ý tưởng, nghĩ ra vấn đề nhưng chưa rõ 100% vấn đề. Khi hỏi sâu hơn thì thường sẽ chưa trả lời và tự giải thích, phản biện được. 

**6.2. Nhóm có lúc nào bị "solution-first" (nghĩ giải pháp trước khi hiểu vấn đề) không? Lúc đó nhóm nhận ra và xử lý thế nào?**
Có mới đầu mọi người thường tập trung vào kể ra tính năng công nghệ chứ chưa phân tích kĩ vấn đề. Để kéo nhóm quay lại, chúng tôi thống nhất dừng nói về các tính năng của bot, cùng nhau vẽ lại cây vấn đề (cây OST) và xóa hết những từ như "AI", "bot", "tự động" để chỉ tập trung vào nỗi đau thật của người dùng.

**6.3. Tôi có đổi ý sau khi bị phản biện không? Kể một lần cụ thể.**
Trong bài Lab hôm nay là chưa.

**6.4. Kết quả kiểm chứng (phỏng vấn/survey/research) có làm tôi bất ngờ không? Điều gì?**
Nhân viên chỉ cần công cụ chỉ rõ: ai nhận việc gì, hạn chót ngày nào, và bấm vào nghe lại đúng đoạn đó được không. Điều này làm tôi nhận ra mình không cần làm cái gì quá phức tạp, chỉ cần giải quyết đúng cái việc gỡ băng và nhặt ra các đầu việc là người ta đã rất mừng rồi.

**6.5. Điều khó nhất khi viết Problem Statement là gì?**
Khó nhất với tôi là đặt ra các con số đo lường (Metric) và ranh giới (Boundary). Lúc đầu rất hay quen tay viết chung chung kiểu *"giúp tiết kiệm thời gian"* hay *"nâng cao hiệu quả họp"*. Nhưng viết như vậy thì không biết thế nào là thành công. Cả nhóm phải ngồi tính xem bình thường nghe lại mất 90 phút, giờ muốn giảm xuống còn bao nhiêu phút (dưới 15 phút), biên bản phải gửi trong bao lâu (trong 1 tiếng). Việc đặt ranh giới cũng khó vì phải nghĩ trước xem AI được làm đến đâu và tuyệt đối không được phép tự làm những việc gì để tránh gây họa cho người dùng.

**6.6. Nếu làm lại, tôi sẽ đổi gì? Tôi sẽ phản biện nhóm mạnh hơn ở điểm nào?**
Nếu được làm lại từ đầu buổi lab, tôi sẽ chủ động thu thập ngay một file ghi âm cuộc họp thực tế (khoảng 15–20 phút) kèm theo biên bản tương ứng để làm dữ liệu mẫu đối chứng ngay tại lớp. Ngoài ra, trong phiên pitch CP3, tôi sẽ phản biện quyết liệt hơn đối với các ý tưởng có phạm vi quá rộng hoặc phụ thuộc vào dữ liệu của bên thứ ba khó tiếp cận (như hóa đơn thuế hay hồ sơ bệnh án) để giúp nhóm tiết kiệm thời gian hội tụ nhanh hơn, tập trung toàn lực vào bài toán có sẵn người dùng và dữ liệu kiểm chứng ngay tại chỗ.

**6.7. Hiểu bài:** giải thích bằng 5–8 câu, không nhìn tài liệu, chuỗi *problem → quy trình → metric → boundary → mức can thiệp AI → quyết định* của bài nhóm mình.
Bài toán nhóm chọn là vấn đề của thư ký và người điều phối dự án khi mất từ 60–90 phút nghe lại các bản ghi âm cuộc họp dài để chắt lọc quyết định và action items, dẫn đến việc biên bản thường gửi trễ sau 24h và làm thất lạc đầu việc. Quy trình giải quyết bắt đầu bằng việc nạp file âm thanh cuộc họp, chuyển thành văn bản, trích xuất danh sách quyết định cùng action items theo mẫu chuẩn, sau đó để người dùng duyệt và bấm gửi. Metric thành công được đo bằng việc cắt giảm thời gian soạn biên bản từ 90 phút xuống dưới 15 phút, và 100% biên bản được gửi đi trong vòng 1 giờ sau họp. Ranh giới (boundary) nghiêm ngặt là hệ thống chỉ tạo bản nháp đề xuất, tuyệt đối không được tự ý gửi email/Slack ra ngoài và không tự tạo task trên hệ thống quản lý khi chưa có con người duyệt (HITL). Mức can thiệp tối ưu được chọn là **Workflow** (kết hợp Speech-to-Text để chuyển âm thanh thành văn bản và LLM để phân loại, trích xuất cấu trúc quyết định). Quyết định cuối cùng của nhóm là **Go, phạm vi hẹp**, triển khai thử nghiệm trên các cuộc họp nội bộ ngắn trước khi mở rộng.

---

## 7. Tài liệu tham khảo
