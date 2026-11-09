# Báo cáo cá nhân — 2A202603471_NguyenVanTung

> Đổi tên file theo quy tắc `MSSV_HoTen.md`, ví dụ `20241234_NguyenVanAn.md` (MSSV trước, dấu `_`, họ tên viết liền không dấu). Sửa cả dòng tiêu đề phía trên cho khớp.
> Template chi tiết và prompt mẫu cho từng mục: [docs/01-worksheet.md](../../docs/01-worksheet.md).
> Mỗi thành viên một file trong `report/individual/` trên repo nhóm: copy template này thành file mới, điền, rồi commit bằng tài khoản GitHub của bạn. Không viết hộ người khác.

## 1. Thông tin học viên

- Họ tên: Nguyễn Văn Tùng
- MSSV: 2A202603471
- Email trường (không bắt buộc, repo có thể để public): tungnv.2a202603471@student.vinuni.edu.vn
- Tên nhóm: MH2T
- Link repo nhóm: https://github.com/nhtng0212/K5-L3A-Day02-MH2T-DiscoveryProblemFraming

---

## 2. Scan problem (CP1)

Lăng kính: **Lặp lại** · **Tốn thời gian** · **Cần đọc, tổng hợp nhiều thông tin** · **Pain từ người khác**.

| # | Lăng kính | Job Story: Khi… tôi muốn… để… | Ai chịu ảnh hưởng? | Dấu hiệu thật (thời gian, tần suất, số người, bằng chứng) |
|---:|---|---|---|---|
| 1 | Lặp lại | Hệ thống giám sát liên tục đẩy cảnh báo về tiến trình mạng kết nối bất thường, tôi muốn tự động gom nhóm, kiểm tra danh tính địa chỉ IP qua các log và loại bỏ các thông báo trùng lặp, để không phải bấm thủ công hàng trăm lần cho cùng 1 sự việc | SOC Tier 1 | Nhiều cảnh báo trùng lặp trong mỗi ca trực (150–200 cảnh báo/ca, mất 60–90 phút bấm đóng thủ công trên Wazuh SIEM) |
| 2 | Tốn thời gian | Khi có nhân viên viết ticket đẩy lên, tôi muốn hệ thống tự bóc tách log, cô lập tệp vào môi trường phân tích để không làm mất thời gian xây dựng môi trường kiểm thử mà vẫn kịp thời ngăn chặn mã độc | Đội ngũ ứng phó sự cố (Incident Response / Tier 2) | Tần suất 20–50 cảnh báo mỗi tuần và mất từ 15–25 phút để kiểm tra thủ công từng tệp |
| 3 | Cần đọc, tổng hợp nhiều | Khi các sự kiện bảo mật rời rạc xuất hiện cùng lúc trên nhiều máy trạm (như thay đổi khóa đăng ký, tạo dịch vụ ẩn và chạy lệnh mã hóa), tôi muốn xâu chuỗi các hành vi theo dòng thời gian, để phát hiện sớm chiến dịch tấn công trước khi dữ liệu bị mã hóa | Chuyên gia săn tìm mối đe dọa (Threat Hunter) | Xuất hiện trong các chiến dịch kiểm tra xâm nhập hoặc sự cố phức tạp (2–3 lần/tháng), mất 4–6 tiếng đối chiếu log giữa EDR và Firewall |
| 4 | Pain từ người khác | Khi một vụ việc tấn công đã được xử lý xong và cần đóng phiếu trên hệ thống quản lý sự cố, tôi muốn tự động tổng hợp toàn bộ dấu hiệu nhận diện (IoC) và diễn biến thành bản tường trình chuẩn chỉnh, để nộp cho cấp quản lý đúng hạn | Quản lý bộ phận (SOC Manager / CISO), Kỹ sư xử lý sự cố | Các báo cáo tuần thường bị trễ hạn nộp (2/4 tuần gần nhất) do nhân sự phải dồn thời gian soạn thảo thủ công vào cuối tuần (mất 30–45 phút/phiếu sự cố) |
| 5 | Tốn thời gian | Khi có bản tin cảnh báo lỗ hổng phần mềm mới (CVE) xuất hiện với điểm mức độ nghiêm trọng cao, tôi muốn tự động quét toàn bộ danh sách tài sản hiện có trong mạng nội bộ để lọc ra ngay các máy chủ đang sử dụng phiên bản phần mềm phơi nhiễm, để không phải dò tìm thủ công qua từng hệ thống | Kỹ sư quản trị hạ tầng (Sysadmin) | 3 đến 5 đợt công bố lỗ hổng lớn mỗi tháng; mất 3–4 tiếng rà soát thủ công danh sách gói phần mềm trên hơn 50 máy chủ |
| 6 | Lặp lại | Khi tiếp nhận ca trực SOC lúc 7h sáng, tôi muốn nắm ngay tóm tắt các sự cố còn mở và tiến trình xử lý từ ca đêm, để không phải đọc lại từng ticket và chat log rời rạc | SOC Tier 1, Trưởng ca trực | 20–25 phút mỗi lần giao ca, 3 ca/ngày; thỉnh thoảng sót thông tin bàn giao giữa 2 ca trực |
| 7 | Cần đọc, tổng hợp nhiều | Khi cần cấu hình luật tường lửa (firewall rule) mới cho dự án, tôi muốn tra cứu nhanh chính sách và quy hoạch mạng hiện tại, để không làm gián đoạn các dịch vụ đang chạy hoặc tạo lỗ hổng mới | Kỹ sư mạng, DevOps | 3–4 lần/tuần, mất 40 phút/lần tra cứu tài liệu quy hoạch mạng và kiểm tra xung đột rule |
| 8 | Pain từ người khác | Khi tài khoản nhân viên bị khóa do nhập sai mật khẩu nhiều lần, họ muốn được xác minh danh tính và mở khóa an toàn ngay, để tiếp tục làm việc mà không phải chờ IT hỗ trợ quá 30 phút | Nhân viên văn phòng, IT Helpdesk | 10–15 yêu cầu/tuần, thời gian chờ trung bình 35 phút/ticket do IT bận xử lý việc khác |

**Nếu có dùng AI để gợi ý thêm:** ý nào AI gợi ý mà bạn giữ lại, ý nào bỏ và vì sao.

- **Ý giữ lại:** Ý #6 (bàn giao ca trực SOC) và #7 (tra cứu kiểm tra firewall rule), vì đây là các tình huống thực tế thường gặp trong quản trị hệ thống và vận hành SOC, có quy trình và thời gian đo lường rõ ràng.
- **Ý bỏ:** AI từng gợi ý *"Trợ lý AI tự động phát hiện và ngăn chặn mọi cuộc tấn công mạng"* - Mình bỏ ý này vì phạm vi quá rộng, mơ hồ, không phản ánh đúng quy trình công việc cụ thể của một vai trò thực tế ngoài đời.

---

## 3. Top 3 Problem Cards + quy trình nháp (CP2)

### Bảng chọn top 3

| Rank | Problem | Vì sao chọn | Điều còn chưa chắc |
|---:|---|---|---|
| 1 | Phân loại và lọc cảnh báo SIEM trùng lặp | Chiếm nhiều thời gian nhất trong ca trực của SOC Tier 1 (150–200 cảnh báo/ca), gây mệt mỏi cảnh báo (Alert Fatigue) | Chưa rõ cách xác định ngưỡng an toàn để tự động đóng ticket mà không bỏ sót sự cố thật |
| 2 | Tổng hợp dữ liệu và soạn thảo báo cáo sự cố an ninh | Tốn 30–45 phút mỗi phiếu sau khi xử lý xong sự cố, khiến các báo cáo tuần thường xuyên bị dồn ứ và chậm trễ tiến độ nộp cho cấp quản lý | Chưa rõ dữ liệu log từ các nguồn khác nhau (TheHive, SIEM Wazuh) có đủ chuẩn hóa để trích xuất tự động không |
| 3 | Điều tra, phân tích tệp đính kèm và email lừa đảo | Là nguồn xâm nhập phổ biến của mã độc, đòi hỏi thao tác nhiều bước thủ công qua sandbox và kiểm tra headers mất 15-25 phút | Tốc độ phản hồi của các sandbox bên ngoài có kịp thời khi lượng email gửi về tăng đột biến vào giờ cao điểm không |

### Problem Card #1

| Trường | Nội dung |
|---|---|
| Job Story | Khi hệ thống SIEM liên tục đẩy cảnh báo lặp lại, tôi muốn tự động gom nhóm, kiểm tra danh tiếng IP/domain và loại bỏ ngay các thông báo trùng lặp, để không phải bấm thủ công hàng trăm lần cho cùng một sự việc và tập trung xử lý cảnh báo nguy hiểm |
| Actor | SOC Tier 1 Analyst |
| Thời điểm / bối cảnh | Đầu ca trực hoặc vào các khung giờ cao điểm khi hệ thống ghi nhận lượng log đột biến từ các quy tắc phát hiện |
| Quy trình hiện tại (3–7 bước) | 1. Mở giao diện bảng điều khiển Wazuh SIEM để kiểm tra danh sách cảnh báo mới.<br>2. Bấm mở từng cảnh báo để đọc thông tin chi tiết (IP nguồn, tài khoản, tiến trình).<br>3. Mở tab mới tra cứu thủ công IP trên VirusTotal/AbuseIPDB.<br>4. Đối chiếu lịch sử xem cảnh báo này đã được xử lý ở ca trước chưa.<br>5. Đánh dấu trạng thái False Positive để đóng hoặc chuyển tiếp lên Tier 2 nếu có nghi vấn. |
| Bottleneck (bước nào, mất bao nhiêu phút) | Bước 2 và 3: Tra cứu và kiểm tra từng cảnh báo lặp, mất 3–5 phút cho mỗi cảnh báo |
| Impact (nếu không giải thì sao) | Kỹ sư bị quá tải thông báo (Alert Fatigue), dễ bỏ sót các đợt tấn công thực sự nguy hiểm |
| Success metric (baseline → target) | Giảm 70% lượng cảnh báo rác phải xử lý tay, rút ngắn thời gian xử lý ban đầu từ 5 phút xuống dưới 10 giây/cảnh báo |
| Phương án không dùng AI | Viết regex cố định, tinh chỉnh ngưỡng kích hoạt (threshold) của quy tắc trên SIEM, hoặc viết script Python định kỳ whitelist các IP an toàn |
| Giả thuyết về AI (nếu có) | Dùng Agent tự động gom nhóm log theo ngữ cảnh và tham chiếu lịch sử xử lý của các ca trước để đề xuất đóng các ticket trùng lặp |
| Cảm nhận nhanh | Workflow / Agent |

Quy trình nháp hiện tại:

```text
[Bắt đầu ca trực] 
    ↓
[Wazuh SIEM đẩy 500+ cảnh báo] 
    ↓
[Điểm nghẽn: Tier-1 Analyst mở từng cảnh báo tra cứu thủ công (3-5 phút/cảnh báo)] 
    ↓
[Quá tải / Alert Fatigue / Dễ bỏ sót True Positive] 
    ↓
[Kết thúc ca: Báo cáo tồn đọng / Sự cố thực bị che lấp]
```

### Problem Card #2

| Trường | Nội dung |
|---|---|
| Job Story | Khi một vụ việc tấn công đã được xử lý xong trên hệ thống quản lý, tôi muốn tự động tổng hợp toàn bộ mốc thời gian, dấu hiệu nhận diện (IoC) và hành động khắc phục thành một bản tường trình chuẩn chỉnh, để bàn giao cho quản lý mà không phải ngồi gõ lại từng mục thủ công |
| Actor | Kỹ sư ứng phó sự cố (Incident Responder / SOC Tier 2) |
| Thời điểm / bối cảnh | Ngay sau khi một phiếu sự cố (ticket trên TheHive) được đóng (Closed) hoặc khi cần tổng hợp báo cáo định kỳ hàng tuần |
| Quy trình hiện tại (3–7 bước) | 1. Mở trang TheHive để lấy thông tin chi tiết của vụ việc.<br>2. Mở thêm Wazuh và EDR để kiểm tra lại dòng thời gian (timeline) sự kiện.<br>3. Mở tài liệu Word/Notion, copy-paste thủ công các IP độc hại, mã hash file, tài khoản liên quan.<br>4. Tự gõ lại phần tóm tắt diễn biến tấn công và các bước đội ngũ đã xử lý.<br>5. Chỉnh lại định dạng, soát lỗi chính tả và gửi file cho quản lý. |
| Bottleneck (bước nào, mất bao nhiêu phút) | Bước 2, 3 và 4: Mất từ 30 đến 45 phút cho mỗi báo cáo sự cố |
| Impact (nếu không giải thì sao) | Kỹ sư mất nhiều thời gian làm việc hành chính giấy tờ; 25% báo cáo tuần bị nộp trễ hạn |
| Success metric (baseline → target) | Rút ngắn thời gian viết báo cáo từ 30–45 phút xuống dưới 10 phút/phiếu, tỷ lệ trễ hạn báo cáo tuần giảm về 0% |
| Phương án không dùng AI | Tạo sẵn biểu mẫu form cố định, viết script Python gọi API của TheHive để kéo trường dữ liệu thô vào các ô có sẵn |
| Giả thuyết về AI (nếu có) | Dùng LLM kết nối API lấy dữ liệu thô từ TheHive/Wazuh, đọc hiểu diễn biến chuỗi tấn công và soạn bản nháp tóm tắt theo văn phong kỹ thuật chuẩn |
| Cảm nhận nhanh | Workflow |

Quy trình nháp hiện tại:

```text
[Đóng phiếu sự cố trên TheHive] 
    ↓
[Mở nhiều tab công cụ khác nhau gom log thủ công: 8 phút] 
    ↓
[Điểm nghẽn: Gõ tay báo cáo, mất 30-45 phút/phiếu] ◄── BOTTLENECK
    ↓
[Báo cáo chậm trễ / Dễ nhầm lẫn số liệu IoC] 
    ↓
[Chuyển bàn giao cho CISO / Quản lý: 2 phút]
```

### Problem Card #3

| Trường | Nội dung |
|---|---|
| Job Story | Khi có nhân viên báo cáo nhận được email lạ chứa tệp đính kèm hoặc link đáng ngờ, tôi muốn hệ thống tự động bóc tách headers, kiểm tra tệp trong môi trường cô lập (sandbox) và phân tích hành vi, để không phải dựng máy ảo kiểm tra thủ công mà vẫn ra kết luận chính xác |
| Actor | Chuyên viên phân tích an ninh mạng (SOC Analyst) |
| Thời điểm / bối cảnh | Khi người dùng bấm nút Phishing Report trên hòm thư hoặc gửi thông báo đến kênh SOC |
| Quy trình hiện tại (3–7 bước) | 1. Tiếp nhận email báo cáo dạng tệp gốc (.eml).<br>2. Mở công cụ phân tích headers để kiểm tra SPF, DKIM, DMARC và link redirect.<br>3. Tải tệp đính kèm, tính mã hash và tra cứu trên VirusTotal.<br>4. Đưa tệp hoặc URL vào sandbox ảo để theo dõi hành vi chạy ngầm.<br>5. Tổng hợp kết quả, kết luận (Clean / Phishing / Malware) rồi phản hồi cho người dùng và tạo ticket ghi nhận. |
| Bottleneck (bước nào, mất bao nhiêu phút) | Bước 2, 3 và 4: Kiểm tra headers, bóc tách link và chờ chạy sandbox kiểm thử mất từ 15 đến 25 phút/email |
| Impact (nếu không giải thì sao) | Xử lý chậm trễ làm tăng nguy cơ nhân viên khác click phải link độc; hàng đợi phân tích email bị dồn ứ |
| Success metric (baseline → target) | Rút ngắn thời gian phản hồi từ 20 phút xuống dưới 3 phút/email, độ chính xác nhận diện đạt > 95% |
| Phương án không dùng AI | Dùng hệ thống Gateway bảo vệ thư điện tử (SEG) kết hợp regex chặn cứng các link/domain trong blacklist |
| Giả thuyết về AI (nếu có) | Dùng mô hình ngôn ngữ phân tích nội dung văn cảnh email kết hợp dữ liệu hành vi sandbox để tự động phân loại mức độ nguy hiểm |
| Cảm nhận nhanh | Workflow |

Quy trình nháp hiện tại:

```text
[Nhân viên báo cáo email lạ qua nút Phishing Report] 
    ↓
[Tiếp nhận file .eml và mở công cụ phân tích: 3 phút] 
    ↓
[Điểm nghẽn: Kiểm tra headers, bóc tách URL và chạy sandbox mất 15-25 phút] ◄── BOTTLENECK
    ↓
[Chậm trễ xử lý / Nguy cơ nhân viên khác click nhầm] 
    ↓
[Đưa ra kết luận và tạo phiếu ghi nhận sự cố: 2 phút]
```

### Card muốn pitch nhất

- Card số: 2
- Vì sao: Bài này giải quyết trực tiếp bước nghẽn tốn thời gian hành chính nhất sau khi xử lý xong sự cố (30–45 phút/phiếu). Quy trình và dữ liệu đã có sẵn trên TheHive/Wazuh nên khả thi cao để tự động hóa, dễ thuyết phục nhóm hơn các bài toán can thiệp sâu vào mạng.
- Câu hỏi muốn nhóm phản biện: *"Làm thế nào để đảm bảo mô hình AI khi sinh văn bản báo cáo không bị ảo giác (hallucination) làm sai lệch các thông số kỹ thuật nhạy cảm như địa chỉ IP, mã hash hay mốc thời gian vi phạm?"*

### AI đã phản biện card thế nào

| Điểm yếu AI chỉ ra | Đồng ý? | Đã sửa gì |
|---|---|---|
| Rủi ro ảo giác (Hallucination) làm sai lệch dữ liệu kỹ thuật | Hoàn toàn đồng ý | Tách riêng phần dữ liệu cứng: bắt buộc lấy thông số IP, mã hash trực tiếp từ API hệ thống và khóa không cho AI sửa, chỉ để AI viết đoạn tóm tắt diễn biến |
| Thiếu sự chuẩn hóa dữ liệu đầu vào | Đồng ý một phần | Chuẩn hóa schema các trường log đầu vào từ TheHive/Wazuh trước khi ném vào prompt |
| Nguy cơ rò rỉ dữ liệu an ninh nội bộ (Data Privacy) | Hoàn toàn đồng ý | Bắt buộc chạy mô hình On-premise (như Llama nội bộ), tuyệt đối không gửi log sự cố lên các API đám mây công cộng |

---

## 4. Tôi đã tham gia phần nào (CP3 → CP7)

| Hoạt động | Tôi đã làm gì? | Kết quả / ảnh hưởng tới bài nhóm |
|---|---|---|
| Pitch Problem Card | Trình bày Problem Card #2 (Tự động tổng hợp và viết báo cáo sự cố an ninh mạng) với baseline 30–45 phút/phiếu | Thuyết phục cả nhóm chọn đây làm candidate chính vì giải quyết trực tiếp nỗi đau tốn thời gian hành chính của kỹ sư |
| Phản biện bài của bạn khác | Câu hỏi tôi đã đặt: <br>1. Hỏi bạn Hoàng Tùng (bài lọc cảnh báo SIEM #10): *"Nếu dùng Agent tự động đóng ticket mà bỏ sót một cảnh báo tấn công thật thì ai chịu trách nhiệm?"*<br>2. Hỏi bạn Hoàng Minh (bài mở khóa tài khoản #3): *"Bài này dùng form OTP nội bộ là đủ, có cần giải pháp AI phức tạp không?"* | Đóng góp phản biện then chốt giúp nhóm nhận ra rủi ro pháp lý của việc tự động hóa hoàn toàn; định hướng chọn giải pháp Workflow hỗ trợ (Augment) |
| Nhận phản biện | Câu hỏi tôi nhận được: <br>Bạn Hoàng Tùng hỏi: *"Nếu AI bịa ra một mốc thời gian hoặc ghi sai 1 địa chỉ IP trong báo cáo gửi CISO thì ai chịu trách nhiệm?"* | Tôi đã sửa gì: <br>Bổ sung cơ chế **Locked Schema**: tách riêng bảng IoC/Timeline (trích xuất 100% nguyên bản từ API) và chỉ dùng AI cho đoạn văn tóm tắt diễn biến, có con người ký duyệt |
| Gom cluster / cây OST | Cùng nhóm gom 12 candidate thành 3 cụm; cùng Nhóm trưởng Hoàng Tùng dựng cây OST rút gọn | Tách bạch rõ ràng giữa Outcome và Opportunity, loại bỏ 2 giải pháp trá hình ("Chatbot viết báo cáo", "Multi-Agent tự trị") |
| Chọn candidate problem | Cùng nhóm chấm điểm 7 tiêu chí cho shortlist 3 bài toán | Thống nhất chọn Candidate #2 với số điểm cao nhất (34/35 điểm) |
| Kiểm chứng / research | Soạn câu hỏi phỏng vấn theo phương pháp The Mom Test và phối hợp cùng Quang Huy trực tiếp phỏng vấn 1 Kỹ sư Incident Response | Thu được bằng chứng thực tế: kỹ sư mất 40 phút/báo cáo và cực kỳ mong muốn có công cụ tự gom log vào khung mẫu sẵn |
| Quy trình nhóm | Phối hợp cùng bạn Hoàng Tùng vẽ sơ đồ Before/After bằng ASCII | Xác định chính xác bottleneck nằm ở khâu gom log thủ công và gõ tay văn bản |
| Problem Statement | Soạn thảo bản Problem Statement v0 và cùng hoàn thiện bản v1 | Định nghĩa đầy đủ 6 trường thông tin, đặc biệt là boundary cấm AI tự ý phát hành báo cáo và bắt buộc dùng On-premise LLM |
| Mức can thiệp AI | Phân tích ma trận độ mơ hồ × độ phức tạp; so sánh 4 mức No AI / Rule / Workflow / Agent | Thuyết phục nhóm chọn mức **Workflow** thay vì Agent tự trị để triệt tiêu rủi ro ảo giác và rò rỉ dữ liệu |
| Quyết định | Tham gia đánh giá 4 rủi ro và xác lập phạm vi pilot kèm ngưỡng dừng (Stopping Threshold) | Đưa ra quyết định **Go** cho pilot nhỏ 2 tuần trên các sự cố mức độ Low/Medium |

---

## 5. Dùng AI

| Checkpoint | Tôi dùng AI để làm gì? | AI hữu ích ở đâu? | AI sai hoặc hời hợt ở đâu? | Tôi sửa gì bằng nhận định của mình? |
|---|---|---|---|---|
| CP1 Scan | Gợi ý thêm các tình huống thường gặp trong quản trị hệ thống và vận hành SOC | Gợi ý các góc nhìn thực tế về bàn giao ca trực và kiểm tra rule firewall | AI đưa ra ý quá rộng kiểu "AI tự động ngăn chặn mọi cuộc tấn công" | Bỏ các ý viển vông, tự viết lại thành các Job Story cụ thể có đo lường thời gian thực tế |
| CP2 Problem Card | Đóng vai "PM hoài nghi" để phản biện điểm yếu của Problem Card #2 | Chỉ ra rủi ro nghiêm trọng về ảo giác dữ liệu (hallucination) và lộ lọt dữ liệu nội bộ | AI khuyên nên dùng Agent tự động đăng bài báo cáo lên hệ thống mà không cần người duyệt | Nhận định bài toán an ninh cần tính pháp lý cao; bổ sung cơ chế khóa dữ liệu thô (Locked Schema) và giữ con người phê duyệt |
| CP4 Research | Tìm kiếm các tài liệu và giải pháp công nghệ hiện có về tự động hóa báo cáo sự cố an ninh | Giúp tìm nhanh tính năng War Room của Cortex XSOAR và SIRP TheHive | AI trích dẫn thiếu link nguồn trực tiếp hoặc đưa link chung chung | Tự tra cứu link tài liệu chính thức từ Palo Alto Networks và TheHive Project để đưa vào bài |
| CP5 Quy trình | Chuyển đổi mô tả các bước thành sơ đồ dạng text/ASCII trực quan | Định dạng sơ đồ luồng dữ liệu nhanh, căn lề thẳng hàng | AI vẽ thiếu bước Fallback (phương án quay về khi AI sinh văn bản không đạt) | Tự bổ sung nhánh rẽ [Phương án quay về: Trả về template trống để kỹ sư gõ tay như cũ] vào sơ đồ |
| CP5–6 Problem Statement | Gợi ý các tiêu chí đánh giá (Eval criteria) cho bài toán sinh báo cáo tự động | Gợi ý tiêu chí về độ bao phủ thông tin và thời gian phản hồi | AI không tính đến khía cạnh bảo mật an toàn (bảo toàn 100% tính chính xác của IoC) | Bổ sung tiêu chí bắt buộc: Data Integrity (100% IoC và Timestamp phải khớp tuyệt đối với log thô) |
| CP6 Mức can thiệp / quyết định | So sánh ưu nhược điểm giữa Workflow và Multi-Agent | Liệt kê các góc nhìn về chi phí vận hành và rủi ro lỗi kỹ thuật | AI thiên vị việc dùng Agent phức tạp cho hợp xu hướng | Nhận định bài toán pháp lý an ninh mạng đòi hỏi tính kiểm soát tuyệt đối nên kiên quyết chốt mức Workflow |

---

## 6. Reflection (CP7)

Trả lời bằng trải nghiệm thật của bạn, tối thiểu 200 từ cho các câu 6.1–6.6 (không tính 6.7, câu này được chấm riêng ở tiêu chí C5). **Không dùng AI để viết thay.**

**6.1. Tôi học được gì khi nghe top 3 problems của các bạn khác?**

Khi nghe 3 bạn trong nhóm MH2T (Hoàng Tùng, Hoàng Minh, Quang Huy) trình bày, mình thấy ban đầu anh em đều có xu hướng chọn những bài toán nghe rất "đao to búa lớn" kiểu hệ thống tự động ngăn chặn tấn công diện rộng hoặc tự cô lập máy trạm. Nhưng khi cùng nhau mổ xẻ từng bước, mình nhận ra những bài toán đó đụng chạm rất nhiều rủi ro vận hành ngoài đời, ví dụ lỡ chặn nhầm dải IP của khách hàng thật hoặc không có quyền can thiệp vào switch mạng. Ngược lại, khi các bạn chất vấn về bài toán làm báo cáo sự cố của mình, mình thấy rõ là bài toán nào có quy trình khép kín, dữ liệu đầu vào đã nằm sẵn trong công cụ (TheHive, Wazuh) và đo đếm được thời gian lãng phí cụ thể thì lại dễ giải quyết và ít rủi ro hơn hẳn.

**6.2. Nhóm có lúc nào bị "solution-first" (nghĩ giải pháp trước khi hiểu vấn đề) không? Lúc đó nhóm nhận ra và xử lý thế nào?**

Nhóm mình bị "solution-first" khá nặng ở đầu buổi CP3. Lúc vừa xong phần cá nhân, bạn Hoàng Minh hào hứng rủ: *"Tụi mình làm luôn con Multi-Agent đi: một Agent đọc log, một Agent tự viết báo cáo rồi tự gửi mail cho sếp luôn"*. Lúc đó cả nhóm nghe thấy rất ngầu nên định làm thật. May là khi bắt tay vẽ cây Opportunity Solution Tree (OST), mình với bạn Hoàng Tùng khựng lại nhận ra đây rõ ràng là giải pháp công nghệ đang đội lốt nhu cầu người dùng. Nỗi đau thật của kỹ sư là việc phải mất 30–45 phút mỗi phiếu chỉ để copy-paste thủ công giữa 4-5 tab và gõ lại văn bản lặp đi lặp lại, chứ người ta không hề cần một con bot tự quyết định mọi thứ sau lưng họ. Thế là nhóm quyết định gạch cụm từ "Multi-Agent tự trị" khỏi cây OST và quay về bám chặt vào bước nghẽn thực tế.

**6.3. Tôi có đổi ý sau khi bị phản biện không? Kể một lần cụ thể.**

Mình đã thay đổi hoàn toàn thiết kế sau câu hỏi phản biện của bạn Hoàng Tùng: *"Nếu AI bịa ra sai một mốc thời gian hoặc sai một địa chỉ IP trong báo cáo gửi CISO thì ai là người chịu trách nhiệm?"*. Ban đầu mình cứ nghĩ đơn giản là ném hết log thô vào một mô hình ngôn ngữ lớn (LLM) để nó tự viết từ đầu đến cuối. Nhưng câu hỏi của Tùng làm mình giật mình: trong ngành an ninh mạng, nếu sai lệch dù chỉ 1 địa chỉ IP hay hash mã độc thì người bị kỷ luật đầu tiên là người trực tiếp xử lý ticket chứ không phải con AI. Sau pha tranh luận đó, mình đổi ý ngay: chuyển sang làm theo mô hình lai (Hybrid). Các dữ liệu kỹ thuật nhạy cảm như bảng IoC và mốc thời gian bắt buộc dùng code kéo thẳng từ API ra và khóa cứng lại, tuyệt đối không cho AI sửa; AI chỉ được hỗ trợ soạn đoạn tóm tắt diễn biến (narrative), và cuối cùng kỹ sư con người bắt buộc phải đọc duyệt và bấm nút gửi thì mới xong.

**6.4. Kết quả kiểm chứng (phỏng vấn/survey/research) có làm tôi bất ngờ không? Điều gì?**

Điều làm mình bất ngờ nhất khi cùng Huy đi hỏi thử một anh Kỹ sư Incident Response theo phương pháp The Mom Test là anh ấy hoàn toàn không mặn mà với việc để AI tự động gửi báo cáo đi. Anh ấy chia sẻ rất thẳng thắn rằng báo cáo sự cố liên quan trực tiếp đến trách nhiệm pháp lý và uy tín cá nhân, sai một li là ăn biên bản ngay. Cái anh ấy thực sự cần chỉ là một công cụ giúp anh ấy không phải nhảy qua nhảy lại giữa 5 tab trình duyệt để nhặt từng dòng IP, mã hash với timestamp. Anh bảo chỉ cần có cái gì gom sẵn dữ liệu vào một khung sạch sẽ để anh ấy đọc lướt qua, gõ thêm 2-3 câu nhận định rồi ký tên gửi đi là đã tiết kiệm được nửa tiếng mỗi sự cố rồi.

**6.5. Điều khó nhất khi viết Problem Statement là gì?**

Điều khó nhất với mình là lúc xác định ranh giới (Boundary) và tiêu chí đánh giá (Eval Criteria) cho AI. Nếu làm phần mềm thông thường thì chỉ cần test xem nút bấm có chạy không, API có trả về dữ liệu không. Nhưng với AI, cái khó là phải định lượng được thế nào là một bản nháp "đạt chuẩn", và quan trọng hơn là phải vạch ra ranh giới: AI tuyệt đối không được phép làm những việc gì. Việc nhóm mình phải thống nhất các quy định khắt khe như: bắt buộc chạy mô hình mã nguồn mở nội bộ (On-premise) để không gửi dữ liệu mật của công ty ra ngoài, và cấm AI tự ý phát hành báo cáo là điểm mà cả nhóm phải ngồi bàn bạc và cân nhắc rất nhiều lần.

**6.6. Nếu làm lại, tôi sẽ đổi gì? Tôi sẽ phản biện nhóm mạnh hơn ở điểm nào?**

Nếu được làm lại buổi lab này, mình sẽ giục nhóm đi hỏi người thật sớm hơn ngay từ CP1 chứ không để dồn đến tận CP4. Có thông tin thực tế từ người làm nghề sớm sẽ giúp cả nhóm đỡ mất thời gian tranh cãi về những ý tưởng viển vông ở CP2 và CP3. Ngoài ra, mình sẽ phản biện quyết liệt hơn với cái tâm lý thích công nghệ phức tạp: trong lúc làm bài, nhóm đã tốn gần 40 phút chỉ để bàn xem có nên dựng hệ thống Agent tự trị không, trong khi một quy trình Workflow rõ ràng có con người tham gia duyệt (Human-in-the-loop) đã giải quyết được phần lớn nỗi đau với chi phí rẻ hơn và an toàn hơn rất nhiều.

**6.7. Hiểu bài:** giải thích bằng 5–8 câu, không nhìn tài liệu, chuỗi *problem → quy trình → metric → boundary → mức can thiệp AI → quyết định* của bài nhóm mình.

Bài toán của nhóm mình bắt nguồn từ **nỗi đau tốn thời gian hành chính** của chuyên gia ứng cứu sự cố khi phải mất 30–45 phút gõ tay báo cáo sau mỗi vụ việc, khiến 25% báo cáo tuần bị nộp muộn. **Quy trình giải quyết** gồm: trích xuất tự động dữ liệu IoC và mốc thời gian qua API TheHive/Wazuh, đưa vào LLM để viết nháp đoạn tóm tắt diễn biến, và chuyên gia con người đọc soát lại trước khi bấm xuất file gửi quản lý. **Success metric** đặt ra là cắt giảm thời gian viết báo cáo xuống dưới 10 phút/phiếu, xóa bỏ tình trạng trễ hạn và đảm bảo độ chính xác của dữ liệu kỹ thuật trích xuất đạt 100%. **Boundary an toàn** quy định các thông số IP/hash phải được khóa cứng lấy từ API gốc (AI không được tự sửa), bắt buộc dùng mô hình On-premise để tránh rò rỉ dữ liệu mật và AI tuyệt đối không được tự ý gửi báo cáo. Nhóm chọn **mức can thiệp Workflow** vì mức Rule quá cứng nhắc không viết được văn bản tóm tắt, còn mức Agent tự trị lại tiềm ẩn rủi ro bịa thông tin và rủi ro pháp lý. Cuối cùng, nhóm thống nhất **quyết định Go** để chạy thử nghiệm pilot 2 tuần cho các sự cố mức Low/Medium, đi kèm **ngưỡng dừng** rõ ràng: nếu tỷ lệ chuyên gia phải viết lại bản nháp vượt quá 30% hoặc phát hiện dù chỉ 01 lỗi sai lệch thông số kỹ thuật thì lập tức dừng dự án để đánh giá lại.

---

## 7. Tài liệu tham khảo

1. TheHive Project Documentation. *Security Incident Response Platform Administrator Guide*. https://thehive-project.org/
2. Wazuh Documentation. *Open Source Security Platform & SIEM Capabilities*. https://documentation.wazuh.com/
3. Palo Alto Networks. *Incident War Room and Post-Incident Reporting in Cortex XSOAR*. https://docs-cortex.paloaltonetworks.com/
4. Rob Fitzpatrick. *The Mom Test: How to talk to customers & learn if your business is a good idea when everyone is lying to you*.
5. Google People + AI Research (PAIR). *People + AI Guidebook: Designing human-centered AI products*. https://pair.withgoogle.com/
6. Marty Cagan. *Inspired: How to Create Tech Products Customers Love* (4 Product Risks Framework).
