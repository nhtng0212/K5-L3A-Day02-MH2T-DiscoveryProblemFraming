# Báo cáo nhóm — Day 02 Discovery & Problem Framing

> Bản chung của nhóm, viết trên repo do nhóm trưởng fork. Không copy file này sang repo cá nhân.
> Template chi tiết và prompt mẫu: [docs/01-worksheet.md](../../docs/01-worksheet.md). Bài mẫu: [docs/02-deliverable-example.md](../../docs/02-deliverable-example.md).

## 1. Thông tin nhóm

- Tên nhóm: **MH2T**
- Thành viên: xem `TEAM.md` (Đỗ Hoàng Minh, Lê Quang Huy, Nguyễn Văn Tùng, Nguyễn Hoàng Tùng - Nhóm trưởng)
- Candidate problem được chọn (1 câu): **Tự động hóa hỗ trợ tổng hợp mốc thời gian (Timeline) và dấu hiệu nhận diện (IoC) để sinh bản báo cáo sự cố an ninh mạng (Incident Post-Mortem Report) trên TheHive/Wazuh.**
- Quyết định cuối: **Go** (Phạm vi pilot nhỏ: Workflow bán tự động soạn thảo bản nháp có chuyên gia con người đọc duyệt, không dùng Full-Agent tự trị)

---

## 2. Hội tụ nhóm (CP3)

### 2.1. Pitch

| # | Người đưa ra | Candidate (Job Story ngắn) | Actor | Bottleneck | Câu hỏi phản biện nhận được (ai hỏi) |
|---:|---|---|---|---|---|
| 1 | Đỗ Hoàng Minh | Khi bắt đầu ngày mới, muốn có bản tóm tắt các tin công nghệ quan trọng từ nhiều nguồn để tiết kiệm thời gian | Content Creator, Nhà nghiên cứu | Lướt đọc chọn lọc và viết tóm tắt thủ công (50 phút/sáng) | *"Làm sao AI lọc được tin chuẩn xác, phân biệt được tin đồn và tin chính thống?"* (Nguyễn Hoàng Tùng hỏi) |
| 2 | Đỗ Hoàng Minh | Khi cần tìm nguồn xe đạp cũ trên Facebook/Chợ Tốt, muốn hệ thống tự động quét bài đăng để kịp thời chốt mua | Chủ cửa hàng xe đạp cũ | Lướt bảng tin thủ công liên tục (2–3 tiếng/ngày) | *"Facebook và Chợ Tốt chặn bot crawl dữ liệu (anti-scraping) thì giải quyết thế nào?"* (Lê Quang Huy hỏi) |
| 3 | Đỗ Hoàng Minh | Khi nhân viên hỏi lỗi trong thread chat, muốn hệ thống tự tra cứu kho tri thức cũ để trả lời ngay các lỗi quen thuộc | Thành viên QA, Quản lý dự án | Tra cứu lịch sử chat và gõ lại câu trả lời cũ (3–4 tiếng/ngày) | *"Nếu AI hiểu sai ngữ cảnh kỹ thuật và trả lời sai làm vỡ code thì ai chịu trách nhiệm?"* (Nguyễn Văn Tùng hỏi) |
| 4 | Lê Quang Huy | Khi mua đồ điện tử giá trị cao, muốn có bảng so sánh thông số, cấu hình và giá giữa các sàn để không phải mở nhiều tab | Người tiêu dùng, Sinh viên | So sánh cấu hình và giá thực tế qua nhiều shop (3–4 tiếng) | *"Giá và voucher trên sàn TMĐT thay đổi liên tục theo giờ, dữ liệu cào về có kịp cập nhật không?"* (Đỗ Hoàng Minh hỏi) |
| 5 | Lê Quang Huy | Khi cuối tháng đến hạn tính tiền nhà, muốn tự động phân loại chi tiêu chung/riêng và chia tiền cho từng người | Sinh viên ở ghép phòng trọ | Nhận diện khoản chi và tính toán chia tiền thủ công (45 phút/tháng) | *"Bài toán này dùng ứng dụng Splitwise hoặc Google Sheets lập sẵn công thức có đủ chưa?"* (Nguyễn Hoàng Tùng hỏi) |
| 6 | Lê Quang Huy | Khi muốn cập nhật tình hình đội bóng yêu thích, muốn có bản Daily Recap tóm tắt lịch thi đấu, tỷ số và phong độ | Người hâm mộ thể thao | Mở nhiều trang/app rải rác để gom tin chấn thương (30–40 phút/sáng) | *"Nhu cầu này thuộc về sở thích cá nhân, giá trị kinh tế (Value) để thương mại hóa là gì?"* (Nguyễn Văn Tùng hỏi) |
| 7 | Nguyễn Văn Tùng | Khi một vụ việc tấn công đã xử lý xong trên TheHive, muốn tự động tổng hợp mốc thời gian và IoC thành báo cáo chuẩn chỉnh để nộp CISO | Kỹ sư ứng cứu sự cố (Incident Responder Tier 2) | Mở nhiều tab gom log và tự gõ văn bản narrative mô tả sự cố (30–45 phút/phiếu) | *"Nếu AI bịa ra mốc thời gian hoặc ghi sai 1 địa chỉ IP trong báo cáo gửi CISO thì ai chịu trách nhiệm?"* (Nguyễn Hoàng Tùng hỏi) |
| 8 | Nguyễn Văn Tùng | Khi hệ thống SIEM đẩy cảnh báo lặp lại, muốn tự động gom nhóm, kiểm tra danh tính IP và loại bỏ thông báo trùng lặp | SOC Tier 1 Analyst | Tra cứu và kiểm tra thủ công từng cảnh báo lặp (150–200 cảnh báo/ca, mất 3–5 phút/cảnh báo) | *"Làm sao xác định ngưỡng an toàn để tự động đóng ticket mà không bỏ sót tấn công thật?"* (Đỗ Hoàng Minh hỏi) |
| 9 | Nguyễn Văn Tùng | Khi nhân viên báo cáo email lạ, muốn hệ thống tự động bóc tách headers và phân tích tệp đính kèm trong sandbox | SOC Analyst | Kiểm tra headers, bóc tách link và chờ chạy sandbox (15–25 phút/email) | *"Tốc độ phản hồi của API sandbox bên thứ ba có làm nghẽn hàng đợi lúc cao điểm không?"* (Lê Quang Huy hỏi) |
| 10 | Nguyễn Hoàng Tùng | Khi kết thúc cuộc họp dự án 1–2 tiếng, muốn trích xuất các quyết định chính và action items kèm người phụ trách để gửi biên bản trước 17h | Project Coordinator, Scrum Master | Vừa nghe lại audio vừa tua tốc độ 1.5x và ghi chép nháp (60–75 phút/buổi họp) | *"Làm sao AI phân biệt được câu nói đùa với cam kết giao việc chính thức?"* (Nguyễn Văn Tùng hỏi) |
| 11 | Nguyễn Hoàng Tùng | Khi chuẩn bị nộp bài lab trước hạn chót, muốn đối chiếu rubric với file repo để không bị trừ điểm oan vì sai cấu trúc | Sinh viên CNTT, Học viên | Mở từng file đọc rà soát đối chiếu thủ công từng tiêu chí (20–25 phút/bài) | *"Phần kiểm tra tên file và cấu trúc dùng shell script là đủ, AI can thiệp vào bước nào?"* (Lê Quang Huy hỏi) |
| 12 | Nguyễn Hoàng Tùng | Khi nhận 200–300 hóa đơn đầu vào mỗi tháng, muốn nhập thông tin mã số thuế và tiền thuế vào phần mềm kế toán | Kế toán viên thuế | Gõ tay thông tin và số tiền từ file PDF/ảnh scan (10–12 tiếng/kỳ thuế) | *"Hóa đơn viết tay hoặc mờ nhòe thì lấy dữ liệu chuẩn ở đâu để tránh bị phạt thuế?"* (Đỗ Hoàng Minh hỏi) |

### 2.2. Cluster

| Cluster | Các candidate | Pattern chung |
|---|---|---|
| **A — Tổng hợp & Tóm tắt thông tin phân tán (Information Aggregation)** | #1 (Tin công nghệ - Đỗ Hoàng Minh), #4 (So sánh đồ điện tử - Lê Quang Huy), #6 (Tin bóng đá - Lê Quang Huy), #10 (Tóm tắt cuộc họp - Nguyễn Hoàng Tùng) | Dữ liệu đầu vào dàn trải trên nhiều trang web/file âm thanh; người dùng mất hàng giờ lướt đọc và tổng hợp thủ công |
| **B — Ứng phó sự cố an ninh & Phân tích kỹ thuật (Security Incident & Threat Ops)** | #7 (Báo cáo sự cố TheHive - Nguyễn Văn Tùng), #8 (Gom cảnh báo SIEM - Nguyễn Văn Tùng), #9 (Phân tích email lừa đảo - Nguyễn Văn Tùng) | Xử lý trong trung tâm điều hành an ninh mạng (SOC); áp lực thời gian lớn, đòi hỏi trích xuất chính xác log kỹ thuật và giảm tải kiệt sức (Alert/Work Fatigue) |
| **C — Hỗ trợ quy trình vận hành & Kiểm tra tuân thủ (Workflow & Operations Support)** | #2 (Quét xe cũ - Đỗ Hoàng Minh), #3 (Hỏi đáp QA - Đỗ Hoàng Minh), #5 (Chi tiêu phòng trọ - Lê Quang Huy), #11 (Đối chiếu rubric - Nguyễn Hoàng Tùng), #12 (Nhập hóa đơn - Nguyễn Hoàng Tùng) | Tác vụ nghiệp vụ lặp đi lặp lại hàng ngày; quy trình có sẵn nhưng thao tác thủ công gây chậm trễ và sai sót |

### 2.3. Opportunity Solution Tree rút gọn

Gốc là **1 outcome**. Nhánh là **opportunity** (nhu cầu, pain), không phải tính năng hay công cụ.

```text
OUTCOME: Rút ngắn 75% thời gian lập hồ sơ báo cáo sau sự cố an ninh mạng mà vẫn đảm bảo 100% tính chính xác của dữ liệu chứng cứ kỹ thuật
├── Opportunity 1: Kỹ sư phải mở nhiều tab công cụ (Wazuh, EDR, TheHive) để copy thủ công mốc thời gian và IoC (mất 8-10 phút)
├── Opportunity 2: Soạn thảo văn bản mô tả diễn biến tấn công (narrative) tốn nhiều thời gian (15-20 phút) và kỹ sư dễ bị kiệt sức
└── Opportunity 3: Báo cáo thường xuyên bị dồn ứ vào cuối tuần dẫn đến 25% báo cáo tuần bị nộp trễ hạn cho CISO và kiểm toán
     ✗ "Xây dựng Multi-Agent tự động viết và gửi báo cáo cho CISO"  ← Solution, gạch khỏi cây OST
     ✗ "Chatbot AI trả lời tự động cho lãnh đạo"                   ← Solution, gạch khỏi cây OST
     ✗ "Hệ thống tự động đóng ticket trên TheHive"                 ← Solution, gạch khỏi cây OST
```

Những ý đã gạch bỏ vì là solution đội lốt opportunity:
- *"Xây dựng Multi-Agent tự động viết và gửi báo cáo cho CISO"* (đây là giải pháp kỹ thuật cụ thể, không phải nỗi đau của người dùng).
- *"Hệ thống tự động đóng ticket trên TheHive"* (tập trung vào tính năng tự động hóa thay vì giải quyết sự tắc nghẽn ở khâu tổng hợp thông tin).
- *"Chatbot AI tra cứu báo cáo"* (tính năng hỏi đáp, không giải quyết khâu lập báo cáo ban đầu).

### 2.4. Chấm điểm shortlist (1–5)

| Candidate | Actor rõ | Quy trình rõ | Pain có bằng chứng | Impact đo được | Vừa sức lab | So sánh được No AI/Rule/Workflow/Agent | Nhóm hiểu domain | Tổng |
|---|---:|---:|---:|---:|---:|---:|---:|---:|
| **1. Viết báo cáo sự cố an ninh mạng (#7 - Nguyễn Văn Tùng)** | 5 | 5 | 5 | 5 | 5 | 5 | 4 | **34** |
| **2. Trích xuất quyết định & action items cuộc họp (#10 - Nguyễn Hoàng Tùng)** | 5 | 5 | 5 | 4 | 4 | 5 | 4 | 32 |
| **3. Hỗ trợ giải đáp câu hỏi kỹ thuật cho QA (#3 - Đỗ Hoàng Minh)** | 4 | 4 | 4 | 4 | 4 | 4 | 4 | 28 |

**Candidate được chọn:**
Candidate #7 (Problem Card #2 của bạn **Nguyễn Văn Tùng**) — Tự động hóa hỗ trợ tổng hợp mốc thời gian (Timeline) và dấu hiệu nhận diện (IoC) để sinh bản báo cáo sự cố an ninh mạng (Incident Post-Mortem Report) trên TheHive/Wazuh.

**Vì sao chọn:**
1. **Nỗi đau có thật và đo lường được:** Mỗi phiếu sự cố ngốn của kỹ sư từ 30–45 phút làm giấy tờ hành chính; 25% báo cáo tuần bị nộp trễ hạn cho CISO.
2. **Dữ liệu đầu vào rõ ràng và tập trung:** Dữ liệu sự kiện, địa chỉ IP, mốc thời gian đã nằm sẵn trong database của TheHive và Wazuh SIEM, truy xuất được trực tiếp qua REST API.
3. **Phân định ranh giới công nghệ cực kỳ sắc nét:** Cho phép kết hợp hoàn hảo giữa **Rule-based** (khóa cứng dữ liệu kỹ thuật IP/mã băm để chống ảo giác 100%) và **LLM** (soạn thảo đoạn văn diễn biến tấn công), dưới sự kiểm duyệt và phê duyệt của **Con người (Human-in-the-loop)**.

**Vì sao loại các candidate còn lại:**
- **Loại Candidate #10 (Tóm tắt cuộc họp - Nguyễn Hoàng Tùng):** Dù nỗi đau rõ ràng, nhưng các cuộc họp có nhiều tạp âm, người nói ngắt lời nhau và tiếng lóng, dẫn đến rủi ro trích xuất nhầm việc hoặc gán nhầm người cao hơn nhiều so với dữ liệu nhật ký sự cố có cấu trúc của an ninh mạng.
- **Loại Candidate #3 (Hỏi đáp QA - Đỗ Hoàng Minh):** Kho tri thức trong chat thread thường bị phân tán, không có cấu trúc cố định và rủi ro AI trả lời sai dẫn đến việc lập trình viên triển khai nhầm tính năng.
- **Loại Candidate #1 & #6 (Tin công nghệ / Bóng đá - Đỗ Hoàng Minh & Lê Quang Huy):** Thuộc về thói quen tin tức cá nhân, khó đo lường impact kinh tế và khó thương mại hóa.
- **Loại Candidate #4 (So sánh đồ điện tử - Lê Quang Huy):** Vướng rào cản kỹ thuật anti-scraping của các sàn thương mại điện tử lớn.

**Xử lý bất đồng (nếu có):**
Ban đầu, bạn Đỗ Hoàng Minh và bạn Lê Quang Huy muốn ưu tiên các bài toán gần gũi với đời sống như tổng hợp tin tức hay so sánh giá mua hàng. Nhóm trưởng Nguyễn Hoàng Tùng đã điều phối buổi thảo luận, cùng nhóm phân tích theo ma trận 4 rủi ro của Marty Cagan. Cả nhóm nhận thấy các bài toán tiêu dùng gặp khó khăn lớn về tính khả thi (Feasibility - bị chặn cào dữ liệu) và tính khả dụng kinh doanh (Viability). Trong khi đó, bài toán Báo cáo an ninh mạng của bạn Nguyễn Văn Tùng có quy trình khép kín, khách hàng B2B doanh nghiệp sẵn sàng chi trả và đo lường được hiệu quả tiết kiệm thời gian ngay lập tức. Cả 4 thành viên đã đồng thuận 100% chọn đề tài của Nguyễn Văn Tùng.

---

## 3. Kiểm chứng + research giải pháp đã có (CP4)

### 3.1. Assumption Map

| # | Giả định | Loại | Quan trọng (1–5) | Đã có bằng chứng (1–5) | Kiểm chứng trước? |
|---:|---|---|---:|---:|---|
| 1 | Dữ liệu log trên TheHive và Wazuh có đủ các trường thời gian và IoC để tái hiện chuỗi tấn công | Feasibility | 5 | 4 | Không (đã rõ qua API schema) |
| 2 | Kỹ sư ứng cứu sự cố sẵn sàng dùng bản nháp do AI sinh nếu các số liệu IoC được đảm bảo chính xác 100% | Value / Usability | 5 | 2 | **Có (Cần kiểm chứng ngay)** |
| 3 | CISO / Quản lý kiên quyết từ chối để máy tự động phát hành báo cáo mà không có chữ ký duyệt của kỹ sư | Viability / Safety | 5 | 2 | **Có (Cần kiểm chứng ngay)** |
| 4 | Việc gửi log sự cố nội bộ lên các dịch vụ AI Public Cloud vi phạm nghiêm trọng chính sách bảo mật công ty | Viability / Privacy | 5 | 3 | Có |
| 5 | Các mẫu template báo cáo Word/Notion hiện tại của công ty quá rời rạc và thiếu tính đồng bộ | Usability | 4 | 3 | Không |

Giả định nhóm kiểm chứng trong buổi này: **Giả định #2 và Giả định #3** (Mức độ chấp nhận của kỹ sư đối với bản nháp AI và ranh giới bắt buộc có con người phê duyệt - Human-in-the-loop).

### 3.2. Kiểm chứng

Cách đã dùng: **Phỏng vấn nhanh theo phương pháp The Mom Test** (Hỏi về hành vi và sự việc cụ thể đã xảy ra trong quá khứ, không hỏi ý kiến giả định tương lai).

#### Interview Snapshot #1
| Trường | Nội dung |
|---|---|
| Người được hỏi (vai trò, không ghi tên thật) | Kỹ sư ứng phó sự cố (Incident Response Specialist - Tier 2), Doanh nghiệp Thương mại Điện tử |
| Câu nói đáng nhớ nhất (nguyên văn) | *"Xử lý mã độc xong lúc 2 giờ sáng mệt đứt hơi, nhưng sáng hôm sau vẫn phải ngồi mở 4 tab copy từng cái IP, hash file rồi gõ văn bản báo cáo mất gần 45 phút, nhiều lúc mắt hoa copy nhầm luôn cả địa chỉ IP máy chủ nội bộ vào mục IoC độc hại."* |
| Lần gần nhất gặp vấn đề này: chuyện gì đã xảy ra? | Thứ Sáu tuần trước, công ty bị một máy trạm dính mã độc đánh cắp thông tin (InfoStealer). Bạn đã dập xong lúc 16h, nhưng mất từ 16h30 đến 17h15 chỉ để tổng hợp lại nhật ký EDR, Wazuh và gõ văn bản giải trình cho quản lý, dẫn đến trễ giờ về và nộp báo cáo muộn. |
| Hiện đang xử lý bằng cách nào (workaround)? | Dùng một file Word mẫu có sẵn, mở từng tab copy thủ công các trường vào bảng, sau đó tự viết văn xuôi mô tả diễn biến sự cố. |
| Mất bao lâu, bao lần? | Trung bình mất 35–45 phút cho mỗi sự cố; mỗi tuần xử lý khoảng 3–5 sự cố phức tạp (chiếm gần 4 tiếng/tuần chỉ để gõ báo cáo). |
| Insight / opportunity rút ra | Nhu cầu có một công cụ tự động gom sẵn mốc thời gian và danh sách IoC vào khung mẫu là cực kỳ cấp bách; kỹ sư chỉ muốn đóng vai trò người rà soát (Reviewer) chứ không muốn làm người đánh máy. |

#### Interview Snapshot #2
| Trường | Nội dung |
|---|---|
| Người được hỏi (vai trò, không ghi tên thật) | Trưởng bộ phận An ninh mạng (SOC Lead / CISO), Công ty Tài chính Công nghệ |
| Câu nói đáng nhớ nhất (nguyên văn) | *"Báo cáo sự cố an ninh mạng là hồ sơ pháp lý phục vụ kiểm toán và báo cáo cổ đông. Tôi tuyệt đối không bao giờ chấp nhận một bản báo cáo do AI tự động gửi đi mà không có chữ ký xác nhận của kỹ sư phụ trách. Một lỗi sai về địa chỉ IP trong báo cáo có thể dẫn đến kiện tụng."* |
| Lần gần nhất gặp vấn đề này: chuyện gì đã xảy ra? | Tháng trước trong đợt kiểm toán bảo mật ISO 27001, báo cáo sự cố của tháng bị auditor chỉ ra 2 mốc thời gian không khớp nhau giữa bảng tổng kết và file log kỹ thuật, khiến đội ngũ mất 2 ngày giải trình lại. |
| Hiện đang xử lý bằng cách nào (workaround)? | Bắt buộc kỹ sư phải tự ký nháy vào báo cáo trước khi Lead duyệt chính thức. |
| Mất bao lâu, bao lần? | Mất khoảng 15 phút mỗi báo cáo để Lead rà soát lại các số liệu kỹ thuật. |
| Insight / opportunity rút ra | **Ranh giới (Boundary) bất di bất dịch:** AI không được phép tự động phát hành báo cáo. Dữ liệu kỹ thuật (IoC, Timestamp) phải được khóa cứng chính xác từ log gốc; AI chỉ được hỗ trợ diễn đạt văn phong (narrative drafting) và chuyên gia con người phải là người bấm nút xuất báo cáo cuối cùng. |

Tổng hợp:

| Nguồn | Số người / số mẫu | Tín hiệu xác nhận | Tín hiệu phản bác |
|---|---:|---|---|
| Phỏng vấn Kỹ sư IR và SOC Lead | 2 người (1 Tier 2, 1 CISO) | Cả hai đều xác nhận việc viết báo cáo thủ công mất từ 35–45 phút/phiếu và dễ xảy ra sai sót dữ liệu do copy paste | Cực lực phản đối việc để AI tự động gửi báo cáo mà không có người ký duyệt; phản đối việc đưa dữ liệu log nội bộ lên Public Cloud |

**Nhóm đã sửa problem thế nào sau kiểm chứng:**
1. **Khóa cứng dữ liệu kỹ thuật (Locked Schema):** Tách bạch rõ ràng trong báo cáo: Bảng IoC và mốc thời gian (Timeline) do code tự động trích xuất trực tiếp 100% từ API của TheHive/Wazuh, AI tuyệt đối không được tự ý sửa hay sinh thêm dữ liệu kỹ thuật này.
2. **Quy định ranh giới bảo mật:** Đặt ranh giới bắt buộc giải pháp phải chạy trên mô hình nội bộ (On-premise / Local LLM) để đảm bảo không vi phạm quy định bảo mật thông tin nội bộ của doanh nghiệp.

### 3.3. Research giải pháp đã có

| Công cụ / case / pattern | Link | Giải bước nào trong quy trình? | Điểm mạnh | Khoảng trống / rủi ro | Bài học cho nhóm |
|---|---|---|---|---|---|
| **TheHive (Security Incident Response Platform)** | https://thehive-project.org/ | Quản lý vòng đời sự cố, xuất báo cáo tổng quan dạng mẫu tĩnh qua template | Quản lý case tập trung rất tốt, liên kết sẵn các IoC (Observables) và task xử lý | Mẫu báo cáo hoàn toàn là template tĩnh (Static Template), không tự viết được phần diễn biến văn xuôi (narrative); dữ liệu vẫn rời rạc | Khai thác trực tiếp API của TheHive để lấy danh sách observables và timeline của vụ việc |
| **Palo Alto Cortex XSOAR (War Room & Reporting)** | https://docs-cortex.paloaltonetworks.com/r/Cortex-XSOAR/8/Cortex-XSOAR-Administrator-Guide/Reports | Ghi lại toàn bộ hành động xử lý trong 'War Room' và xuất báo cáo tự động | Tích hợp sâu, tự động ghi log từng câu lệnh và thao tác của kỹ sư | Chi phí bản quyền doanh nghiệp cực kỳ đắt đỏ; văn bản tóm tắt mang tính chắp vá các dòng log lệnh chứ không thành một bài tường trình mạch lạc | Cần một lớp mô hình ngôn ngữ (LLM) để kết nối các dòng log rời rạc thành câu chuyện diễn biến hoàn chỉnh |
| **D3 Security Smart SOAR (Automated Case Summary)** | https://d3security.com/blog/generative-ai-in-soar-automated-case-summaries/ | Ứng dụng Generative AI để tóm tắt case và sinh báo cáo sơ bộ cho ban giám đốc | Sử dụng AI tóm tắt diễn biến khá trực quan, tiết kiệm thời gian đọc log | Rủi ro ảo giác (hallucination) nếu prompt không chặt; gửi dữ liệu ra cloud tiềm ẩn nguy cơ lộ lọt IP/tài sản nội bộ | Bắt buộc phải có cơ chế Grounding (buộc chặt dữ liệu thô) và sử dụng mô hình Local LLM |

---

## 4. Quy trình trước/sau (CP5)

### 4.1. Quy trình hiện tại

Sơ đồ:

```text
HIỆN TẠI — Tổng thời gian: ~40 phút/phiếu sự cố

[Bước 1: Chuyên viên chuyển trạng thái phiếu sự cố sang Resolved/Closed trên TheHive] (2 phút)
       │
       ▼
[Bước 2: Mở 4 tab công cụ (Wazuh SIEM, nhật ký EDR, Threat Intel) rà soát lại dữ liệu] (8 phút)
       │
       ▼
[Bước 3: Mở file Word mẫu, copy/paste thủ công từng địa chỉ IP, hash file và mốc giờ] (10 phút)
       │
       ▼
[Bước 4: Tự gõ tay đoạn văn diễn biến tấn công, hành động khắc phục và khuyến nghị] (15 phút) ◄── [BOTTLENECK]
       │
       ▼
[Bước 5: Định dạng văn bản, kiểm tra lỗi chính tả và gửi email bàn giao cho CISO/Quản lý] (5 phút)
```

| Bước | Actor | Input | Output | Thời gian / tần suất | Ghi chú |
|---:|---|---|---|---|---|
| 1 | Kỹ sư ứng cứu sự cố | Phiếu sự cố đã xử lý xong | Trạng thái phiếu được đóng | 2 phút/phiếu | Thao tác trên TheHive |
| 2 | Kỹ sư ứng cứu sự cố | Mã sự cố (Case ID) | Log thô từ Wazuh, EDR, Threat Intel | 8 phút/phiếu | Phải mở nhiều tab trình duyệt riêng biệt |
| 3 | Kỹ sư ứng cứu sự cố | Log thô trên các màn hình | Bảng IoC và Timestamp trong file Word | 10 phút/phiếu | Copy paste thủ công, rất dễ nhầm lẫn dữ liệu |
| 4 | Kỹ sư ứng cứu sự cố | Trí nhớ và ghi chú của kỹ sư | Đoạn văn narrative mô tả diễn biến sự cố | 15 phút/phiếu | **BOTTLENECK CHÍNH:** Tốn sức gõ bài, dễ bị "trang trắng" |
| 5 | Kỹ sư ứng cứu sự cố | Bản thảo Word hoàn chỉnh | File PDF báo cáo gửi qua email | 5 phút/phiếu | Chờ cấp quản lý phản hồi |

**Bottleneck chính:** Bước 3 và Bước 4 (chiếm 25/40 phút). Việc sao chép thủ công các chỉ số kỹ thuật và ngồi gõ lại toàn bộ bài văn tường trình diễn biến sự cố làm kỹ sư kiệt sức và dễ dẫn đến sai lệch thông số kiểm toán.

### 4.2. Quy trình tương lai

Quy trình kết hợp: **Rule** gọi API trích xuất & khóa cứng IoC, **AI (LLM)** sinh bản nháp narrative theo schema, **Con người (HITL)** đọc duyệt và xuất báo cáo.

```text
TƯƠNG LAI — Tổng thời gian: ~10 phút/phiếu sự cố

[Bước 1: Kỹ sư bấm nút "Sinh báo cáo sự cố" trên giao diện quản trị TheHive]
       │
       ▼
[Bước 2 (RULE): Code tự động gọi API TheHive/Wazuh trích xuất 100% IoC & Timeline vào Locked Schema] (5 giây)
       │
       ▼
[Bước 3 (AI / LOCAL LLM): Đọc dữ liệu đã chuẩn hóa, sinh bản nháp diễn biến Narrative theo cấu trúc chuẩn] (30 giây)
       │
       ▼
[Bước 4 (CON NGƯỜI - HITL): Kỹ sư rà soát văn phong, kiểm tra tính toàn vẹn và bấm XUẤT BÁO CÁO] ◄── [BOUNDARY] (8–9 phút)
       │
   ┌───┴────────────────────────┐
   │ Bản nháp đạt yêu cầu?      │
   ├──────────────┬─────────────┤
   ▼ Đạt          ▼ Không đạt (AI viết lủng củng)
[Xuất file PDF    [BẬT PHƯƠNG ÁN QUAY VỀ: Kỹ sư bấm "Chỉnh sửa thủ công" trên form có sẵn]
 và gửi CISO]
```

- **Bước Rule xử lý:** Bóc tách toàn bộ địa chỉ IP, tên miền, mã băm mã độc và mốc thời gian từ cơ sở dữ liệu TheHive/Wazuh qua REST API trong vòng 5 giây, điền sẵn vào bảng dữ liệu tĩnh (không qua AI để chống ảo giác).
- **Bước AI hỗ trợ (Workflow):** Mô hình On-premise LLM tiếp nhận schema dữ liệu thô, tự động xâu chuỗi thành đoạn văn tường trình hoàn chỉnh (Nguyên nhân gốc rễ, Diễn biến từng bước, Hành động ngăn chặn đã làm, Khuyến nghị phòng ngừa).
- **Bước Con người vẫn làm (HITL & Boundary):** Kỹ sư rà soát lại đoạn văn, chỉnh sửa các thuật ngữ đặc thù nếu cần, và **trực tiếp ký tên / bấm nút xuất bản báo cáo**. Tuyệt đối không cho phép AI tự động gửi báo cáo cho CISO.
- **Phương án quay về (Fallback):** Nếu AI sinh nội dung không đạt yêu cầu hoặc lỗi cú pháp, hệ thống có nút "Chuyển sang chế độ thủ công" — giữ nguyên bảng IoC đã trích xuất từ Rule và để trống phần narrative để kỹ sư tự gõ như quy trình truyền thống.

### 4.3. Before / after

| Chỉ số | Trước | Sau (kỳ vọng) | Ghi chú |
|---|---:|---:|---|
| **Số bước** | 5 bước thủ công rời rạc | 4 bước liền mạch (2 bước tự động) | Tự động hóa khâu thu thập log |
| **Tổng thời gian** | ~40 phút/phiếu | ~10 phút/phiếu | Giảm 75% thời gian làm báo cáo |
| **Số bước thủ công** | 4 bước (mở tab, copy IoC, gõ văn bản, format) | 1 bước (đọc duyệt và ký bấm xuất file) | Kỹ sư chỉ đóng vai trò Reviewer |
| **Bottleneck chính** | Ngồi gõ tay văn bản narrative từ đầu | Tốc độ rà soát và kiểm chứng của kỹ sư | Chuyển từ việc nặng chân tay sang việc kiểm soát chất lượng |
| **Rủi ro mới phát sinh** | Gõ sai mốc giờ, sót IoC do mắt hoa | Kỹ sư đọc lướt, không phát hiện lỗi hành văn của AI | Đặt cờ kiểm tra (Checklist UI) buộc kỹ sư phải tick xác nhận trước khi xuất file |

---

## 5. Problem Statement v0 (CP5)

| Trường | Nội dung |
|---|---|
| **Actor** | Chuyên gia ứng phó sự cố an ninh mạng (Incident Responder / SOC Tier 2) |
| **Quy trình** | Đóng phiếu sự cố trên TheHive → Gom log từ nhiều tab công cụ → Sao chép thủ công mốc thời gian và IoC → Gõ văn bản báo cáo → Gửi CISO |
| **Bottleneck** | Khâu sao chép dữ liệu kỹ thuật và tự gõ văn bản narrative mô tả sự cố mất từ 25–35 phút/phiếu |
| **Impact** | Tốn ~40 phút cho mỗi phiếu sự cố (chiếm 4–6 tiếng/tuần/kỹ sư); 25% báo cáo tuần bị nộp trễ hạn; rủi ro ghi sai lệch IoC làm ảnh hưởng tới audit tuân thủ |
| **Success Metric** | - Thời gian hoàn thành 1 báo cáo sự cố giảm từ **40 phút** xuống **dưới 12 phút**.<br>- Tỷ lệ trễ hạn báo cáo tuần giảm từ **25%** xuống **0%**.<br>- Độ chính xác của các mốc thời gian và IoC trích xuất đạt **100%**. |
| **Boundary** | AI chỉ được phép soạn thảo bản nháp narrative; **AI KHÔNG ĐƯỢC PHÉP tự ý gửi báo cáo đi hoặc đóng ticket trên hệ thống**. Kỹ sư con người bắt buộc phải đọc duyệt và ký xác nhận. Bắt buộc chạy mô hình nội bộ, không đưa dữ liệu ra ngoài Internet. |

**Phản biện nhận được (từ AI hoặc nhóm khác) và nhóm có đồng ý không:**
- Phản biện: *"Nếu AI sinh văn bản narrative mà vô tình thêm thắt một nhận định không có trong log (ví dụ: 'kẻ tấn công đã chiếm quyền Domain Admin' trong khi log chỉ ghi nhận 'quét cổng'), kỹ sư đọc lướt gửi đi sẽ gây hoang mang cho toàn bộ ban giám đốc!"*
- Nhóm hoàn toàn đồng ý: Nhóm đã cập nhật vào quy trình một cơ chế **Grounding Verification**: Mô hình AI chỉ được phép tóm tắt dựa trên các thẻ sự kiện (Event Tags) đã được xác thực trong phiếu TheHive; các câu văn do AI sinh ra phải có trích dẫn mã Log ID tương ứng để kỹ sư hover chuột kiểm tra đối chiếu ngay lập tức.

---

## 6. Mức can thiệp AI (CP6)

### 6.1. Ma trận độ mơ hồ × độ phức tạp

Bài của nhóm nằm ở ô: **Độ mơ hồ Thấp — Độ phức tạp Trung bình**

Vì sao:
- **Độ mơ hồ Thấp:** Dữ liệu kỹ thuật đầu vào (IP, mã băm, tên máy, mốc thời gian) đã được cấu trúc hóa rõ ràng trong cơ sở dữ liệu của TheHive và Wazuh. Mục tiêu đầu ra là một bản báo cáo sự cố theo mẫu chuẩn mực (Cấu trúc cố định: Mục tiêu, Phạm vi, Diễn biến, Biện pháp xử lý, Khuyến nghị).
- **Độ phức tạp Trung bình:** Cần kết hợp giữa việc trích xuất dữ liệu tĩnh bằng API code, tiền xử lý chuẩn hóa schema, và dùng mô hình ngôn ngữ tự nhiên để kết nối các sự kiện rời rạc thành văn bản mạch lạc.

### 6.2. So sánh 4 mức

| Mức | Phương án cho bài của nhóm | Đủ khi nào | Rủi ro | Chọn? |
|---|---|---|---|---|
| **No AI** (sửa quy trình) | Thiết kế lại template Word với các bảng biểu cố định, đào tạo kỹ sư gõ vắn tắt | Đủ khi các sự cố đều đơn giản, lặp lại và ban giám đốc chỉ cần đọc các gạch đầu dòng ngắn | Không giải quyết được khâu tốn thời gian ngồi gõ văn bản; báo cáo thiếu tính mạch lạc và vẫn tốn 25–30 phút/phiếu | Không |
| **Rule** | Viết script Python tự động lấy dữ liệu từ API TheHive điền vào form PDF/Word mẫu có sẵn | Đủ khi chỉ cần xuất bảng danh sách IoC và log thô dạng bảng | Không thể tự động viết phần diễn biến (narrative) dạng văn xuôi mô tả hành vi tấn công; người đọc không hiểu được ngữ cảnh vụ việc | Không |
| **Workflow** | Pipeline kết hợp: Rule bóc tách IoC/Timeline vào Locked Schema → LLM tổng hợp diễn biến narrative → Kỹ sư duyệt và ký xuất báo cáo | Đủ khi cần kết hợp độ chính xác tuyệt đối của Rule cho dữ liệu số liệu và khả năng diễn đạt ngôn ngữ linh hoạt của AI dưới sự kiểm soát của con người | Phụ thuộc vào chất lượng mô hình LLM nội bộ và prompt grounding | **CHỌN** |
| **Agent** | AI Agent tự trị: Tự đọc case trên TheHive, tự điều tra bổ sung, tự sinh báo cáo và tự động gửi email cho CISO rồi đóng case | Đủ khi hệ thống hoàn toàn tự động và không có nhân sự con người vận hành | **Cực kỳ nguy hiểm (Rủi ro Viability & Legal cao):** Nguy cơ ảo giác sai lệch thông tin pháp lý an ninh mạng; vi phạm nghiêm trọng quy trình kiểm toán ISO 27001 | Không |

**Mức chọn:** **Workflow** (kết hợp Rule + AI hỗ trợ dưới sự kiểm soát của Con người).

**Vì sao không chọn mức đơn giản hơn (Rule):**
Nếu chỉ dùng Rule, hệ thống chỉ có thể xuất ra các bảng số liệu khô khan (IP: 1.2.3.4, Action: Blocked). Ban giám đốc và các kiểm toán viên không thể đọc hiểu được toàn bộ bức tranh vụ việc nếu thiếu phần diễn giải văn xuôi (kẻ tấn công đi qua con đường nào, đã cố gắng làm gì và hệ thống đã ngăn chặn ở bước nào). AI giải quyết xuất sắc phần việc tốn nhiều chất xám và thời gian nhất của kỹ sư là biến số liệu thành câu chuyện có nghĩa.

**Vì sao không chọn mức phức tạp hơn (Agent):**
Báo cáo sự cố an ninh mạng là tài liệu chịu trách nhiệm pháp lý trước ban điều hành và pháp luật. Một Agent tự trị tự ý gửi báo cáo đi mà không qua sự thẩm định của chuyên gia an ninh con người sẽ tạo ra lỗ hổng kiểm soát khổng lồ nếu mô hình gặp lỗi ảo giác hoặc diễn đạt sai lệch mức độ thiệt hại. Mức Workflow là điểm cân bằng hoàn hảo: máy làm phần soạn thảo thô, con người giữ quyền quyết định cuối cùng.

### 6.3. AI Canvas rút gọn

| Thành phần | Nội dung |
|---|---|
| **Prediction** — AI dự đoán / tạo ra gì? | Bản thảo văn bản tường trình diễn biến sự cố (Incident Narrative Summary) và các khuyến nghị phòng ngừa dựa trên các mốc log sự kiện. |
| **Judgment** — con người cân nhắc, quyết định gì? | Kỹ sư cân nhắc xem diễn biến AI mô tả có đúng với thực tế đã xử lý không; văn phong có chuẩn mực và các kết luận có xác đáng không. |
| **Action** — hành động cuối cùng là gì, ai làm? | Kỹ sư bấm nút "Xác nhận và Xuất báo cáo PDF" để gửi cho CISO / Quản lý. |
| **Outcome** — đo kết quả bằng gì? | Thời gian trung bình để hoàn thành một bản báo cáo; tỷ lệ báo cáo đúng hạn 100%; tỷ lệ chuyên gia phải chỉnh sửa lại văn bản do AI sinh. |
| **Input** — AI cần dữ liệu đầu vào gì mỗi lần chạy? Có sẵn không? | - Log chi tiết vụ việc và ghi chú từ TheHive Case (có sẵn qua REST API).<br>- Danh sách IoC đã được xác thực từ Wazuh SIEM (có sẵn).<br>- Schema mẫu báo cáo chuẩn của tổ chức. |
| **Feedback** — lấy phản hồi ở đâu để cải thiện? | Hệ thống lưu lại phiên bản văn bản trước và sau khi kỹ sư chỉnh sửa (Diff text) để làm dữ liệu Few-shot Prompting tinh chỉnh mô hình cho các lần sau. |

### 6.4. Hai câu hỏi của Google PAIR

- **Người dùng muốn được hỗ trợ (augment) hay giao hẳn việc (automate)? Bằng chứng:**
  - **Người dùng muốn được HỖ TRỢ (Augment).**
  - *Bằng chứng từ phỏng vấn:* Cả kỹ sư xử lý lẫn CISO đều khẳng định việc làm báo cáo an ninh mạng đòi hỏi trách nhiệm cá nhân cao. Kỹ sư không muốn giao hẳn cho máy vì sợ mất kiểm soát, nhưng cực kỳ muốn được máy hỗ trợ soạn sẵn bản nháp để tiết kiệm 70% thời gian gõ văn bản cơ bắp.
- **AI sai kiểu nào tệ hơn, báo nhầm / ảo giác (False Information) hay bỏ sót (Omission)? Vì sao, và thiết kế đã xử lý thế nào:**
  - **Ảo giác thông tin kỹ thuật (Hallucination) tệ hơn rất nhiều**. Nếu AI tự bịa ra một địa chỉ IP hoặc tự kết luận sai về thiệt hại dữ liệu, hậu quả có thể dẫn đến báo động sai toàn công ty hoặc vi phạm pháp luật kiểm toán.
  - *Cách xử lý trong thiết kế:* **Khóa cứng dữ liệu kỹ thuật (Locked Schema)**: Toàn bộ bảng danh sách IoC và mốc giờ được tách riêng, lấy trực tiếp từ database log bằng Rule code; AI chỉ được tóm tắt văn phong dựa trên các sự kiện đã có ID xác thực, có cờ trích dẫn trực tiếp để kỹ sư hover chuột đối chiếu.

---

## 7. Problem Statement v1 + tiêu chí đánh giá (CP6)

| Trường | Nội dung |
|---|---|
| **Actor** | Chuyên gia ứng phó sự cố an ninh mạng (Incident Responder / SOC Tier 2) |
| **Quy trình** | Đóng case trên TheHive → Hệ thống tự trích xuất IoC/Timeline vào schema cố định → On-premise LLM sinh bản nháp tường trình diễn biến → Kỹ sư rà soát văn bản và bấm 1-click xuất báo cáo |
| **Bottleneck** | Thời gian kỹ sư rà soát và kiểm chứng bản thảo narrative (giảm xuống còn 6–8 phút/phiếu) |
| **Impact** | Tiết kiệm 30 phút cho mỗi phiếu sự cố; giải phóng 3–5 tiếng/tuần/kỹ sư; triệt tiêu hoàn toàn 100% tình trạng trễ hạn báo cáo tuần; đảm bảo tính toàn vẹn của dữ liệu kỹ thuật |
| **Success Metric** | - Thời gian hoàn thành báo cáo giảm từ **40 phút** xuống **dưới 10 phút/phiếu**.<br>- Tỷ lệ trễ hạn báo cáo tuần: **0%**.<br>- Độ chính xác dữ liệu IoC và mốc thời gian: **100%** (không có lỗi ảo giác).<br>- Tỷ lệ nội dung AI sinh được giữ nguyên không cần viết lại đạt **≥ 80%**. |
| **Boundary** | - AI không được phép tự động phát hành báo cáo; không được tự ý sửa trạng thái phiếu sự cố.<br>- Tuyệt đối cấm AI tự ý thay đổi hoặc sinh thêm các chỉ số kỹ thuật (IP, Domain, Hash, Timestamp).<br>- Bắt buộc chạy mô hình mã nguồn mở trên máy chủ nội bộ (On-premise / Local LLM); cấm truyền dữ liệu log nội bộ lên Cloud công cộng. |
| **AI intervention point** | Bước 3 trong quy trình: Đọc dữ liệu schema đã chuẩn hóa và sinh đoạn văn tường trình diễn biến sự cố (Narrative Generation) kèm khuyến nghị phòng ngừa. |
| **Mức chọn** | **Workflow** (Rule trích xuất dữ liệu cứng + On-premise LLM sinh narrative + Human Approval) |
| **Rủi ro & người kiểm tra** | Rủi ro kỹ sư chủ quan đọc lướt không phát hiện lỗi diễn đạt của AI. Người kiểm tra: SOC Lead thực hiện kiểm toán ngẫu nhiên 10% số báo cáo xuất bản mỗi tháng. |

**Thay đổi so với v0 và lý do:**

| Trường | v0 | v1 | Vì sao đổi |
|---|---|---|---|
| **Boundary** | Chỉ ghi "cần con người kiểm tra (HITL)" chung chung | Bổ sung quy định kỹ thuật nghiêm ngặt: **Khóa cứng dữ liệu kỹ thuật (Locked Schema)** và **Bắt buộc dùng On-premise LLM** | Sau kiểm chứng và phản biện, rủi ro ảo giác số liệu kỹ thuật và rò rỉ dữ liệu log ra ngoài Internet là 2 rủi ro chí mạng bắt buộc phải chặn đứng |
| **Success Metric** | Chỉ đo thời gian (40' → 12') và độ chính xác IoC | Bổ sung thêm metric: **Tỷ lệ nội dung AI sinh được giữ lại ≥ 80%** | Đo lường trực tiếp chất lượng văn phong và mức độ hữu dụng thực tế của bản nháp do AI soạn |
| **AI intervention point** | Nhắc đến AI tổng hợp chung chung | Xác định vị trí can thiệp duy nhất là khâu sinh văn bản narrative từ dữ liệu đã chuẩn hóa | Giúp kiến trúc kỹ thuật rõ ràng, không làm phức tạp hóa các khâu trích xuất dữ liệu vốn đã có Rule giải quyết tốt |

**Tiêu chí đánh giá đầu ra của AI (Eval Criteria):**

| # | Tiêu chí | Đạt khi | Không đạt khi |
|---:|---|---|---|
| 1 | **Tính toàn vẹn dữ liệu kỹ thuật (Data Fidelity)** | 100% các địa chỉ IP, mã băm, tên máy chủ xuất hiện trong đoạn văn narrative đều khớp chính xác với log thô từ TheHive/Wazuh. | AI tự ý bịa thêm một địa chỉ IP hoặc sửa mốc thời gian không có trong nhật ký sự kiện (Hallucination). |
| 2 | **Độ mạch lạc văn phong (Narrative Coherence)** | Đoạn văn mô tả rõ ràng theo cấu trúc 4 phần: Điểm khởi đầu tấn công → Hành vi lây lan → Biện pháp cô lập đã làm → Kết quả hiện tại (ngắn gọn dưới 300 từ, chuẩn thuật ngữ kỹ thuật). | Câu văn lủng củng, lặp từ, hoặc diễn đạt sai lệch bản chất kỹ thuật (ví dụ nhầm lẫn giữa tấn công Brute-force và SQL Injection). |
| 3 | **Độ phù hợp của khuyến nghị (Actionable Recommendations)** | Đưa ra ít nhất 2 khuyến nghị phòng ngừa kỹ thuật sát với lỗ hổng thực tế của vụ việc (ví dụ: vá lỗ hổng cụ thể, cập nhật rule WAF, đổi mật khẩu tài khoản bị lộ). | Khuyến nghị chung chung, sáo rỗng kiểu "cần nâng cao cảnh giác" hoặc không liên quan đến nguyên nhân gốc rễ. |
| 4 | **Bảo mật và cô lập dữ liệu (Data Privacy Compliance)** | Toàn bộ quá trình suy luận của mô hình diễn ra 100% trong mạng nội bộ, không có bất kỳ gói tin nào gửi ra các API đám mây công cộng. | Có kết nối mạng ra bên ngoài trong quá trình xử lý văn bản báo cáo. |

---

## 8. Quyết định (CP6)

### 8.1. Bốn rủi ro (Marty Cagan Framework)

| Rủi ro | Câu hỏi | Mức độ rủi ro | Lý do / bằng chứng |
|---|---|---|---|
| **Value** | Người dùng có thật sự cần và sẽ dùng không? | **Thấp** (An toàn) | Kỹ sư đang phải mất 30–45 phút mỗi phiếu chỉ để gõ văn bản báo cáo. Phỏng vấn thực tế cho thấy họ cực kỳ mong mỏi một giải pháp giúp họ giải phóng khỏi công việc bàn giấy nhàm chán này. |
| **Usability** | Người dùng có dùng được, có hiểu và sửa được đầu ra của AI không? | **Thấp** (An toàn) | Giao diện hiển thị trực tiếp bản nháp trong trình soạn thảo Rich-text, bảng IoC được điền sẵn; kỹ sư có thể đọc lướt, chỉnh sửa trực tiếp từng câu chữ như trên Word và bấm nút xuất PDF trong vài phút. |
| **Feasibility** | Có đủ dữ liệu, công cụ, kỹ năng để làm không? | **Trung bình** | Dữ liệu trên TheHive và Wazuh đều có REST API rõ ràng. Thách thức kỹ thuật nằm ở việc dựng mô hình Local LLM (như Llama-3-8B hoặc Qwen-2.5-7B) đủ mạnh trên máy chủ GPU nội bộ và tối ưu Prompt để không bị ảo giác. Đội ngũ kỹ thuật hoàn toàn khả thi thực hiện. |
| **Viability** | Có hợp chi phí, pháp lý, quy định tổ chức không? Ai vận hành? | **Thấp** (An toàn) | Giải pháp tuân thủ 100% chính sách bảo mật vì chạy On-premise, không mất phí subscription cloud định kỳ, giữ nguyên con người ký duyệt (HITL) nên hoàn toàn đáp ứng các tiêu chuẩn kiểm toán an ninh mạng quốc tế. |

### 8.2. Kết luận

**Quyết định:** **GO (Triển khai giai đoạn Pilot nhỏ)**

**Lý do:**
1. Bài toán giải quyết một nỗi đau có thật, đo lường được thời gian lãng phí cụ thể (40 phút/phiếu, 25% trễ hạn).
2. Kiểm chứng với người thật (The Mom Test) xác nhận giá trị giải pháp là rất lớn và đã xác lập được ranh giới an toàn (Human-in-the-loop, On-premise LLM).
3. Cả 4 rủi ro đều nằm trong tầm kiểm soát an toàn; mức can thiệp Workflow là tối ưu nhất.
4. Tận dụng tối đa sức mạnh tóm tắt của Generative AI mà vẫn khóa chặt được rủi ro sai lệch dữ liệu chứng cứ kỹ thuật.

**Nếu Go — pilot nhỏ nhất (MVP / Pilot scope):**
- Thử nghiệm trên **các sự cố an ninh mức độ Low và Medium** (chiếm 80% tổng số lượng phiếu sự cố hàng tuần, ít rủi ro pháp lý nhất).
- Triển khai cho **đội ngũ Incident Response nội bộ (3 kỹ sư)** sử dụng thử nghiệm trong vòng 2 tuần (khoảng 15–20 báo cáo sự cố).
- Đánh giá thời gian soạn thảo thực tế và tỷ lệ chấp nhận nội dung bản nháp trước khi xin phê duyệt mở rộng cho các sự cố nghiêm trọng (High/Critical).

**Ngưỡng dừng (Stopping Threshold):**
> *Nếu sau 2 tuần thử nghiệm pilot, tỷ lệ kỹ sư phải xóa bỏ toàn bộ đoạn văn AI sinh để viết lại từ đầu vượt quá **30%**, hoặc nếu phát hiện **bất kỳ 01 trường hợp nào** mô hình AI tự ý đưa ra nhận định sai lệch về thiệt hại dữ liệu hoặc làm sai lệch IoC kỹ thuật, nhóm sẽ **LẬP TỨC DỪNG PILOT** và quay về giải pháp biểu mẫu tĩnh truyền thống.*

---

## 9. Hạn chế và hướng tiếp theo

- **Hạn chế:**
  - Mô hình On-premise đòi hỏi máy chủ nội bộ có tối thiểu 1 GPU chuyên dụng (VRAM 16GB–24GB) để đảm bảo tốc độ phản hồi dưới 30 giây.
  - Chất lượng bản nháp ban đầu phụ thuộc vào việc kỹ sư có nhập đầy đủ ghi chú ban đầu vào phiếu TheHive hay không.
- **Hướng tiếp theo:**
  - Tích hợp thêm tính năng tự động trích xuất sơ đồ mạng (Network Topology Attack Graph) vào file báo cáo PDF.
  - Sau khi pilot thành công với các sự cố Low/Medium, mở rộng hệ thống sang tự động tổng hợp báo cáo tuần/tháng cấp quản lý cho CISO.

---

## 10. Tài liệu tham khảo

1. TheHive Project. *Security Incident Response Platform Documentation*. https://thehive-project.org/
2. Wazuh Documentation. *Open Source SIEM and XDR Platform*. https://documentation.wazuh.com/
3. Palo Alto Networks. *Cortex XSOAR Administrator Guide: War Room and Incident Reporting*. https://docs-cortex.paloaltonetworks.com/
4. D3 Security. *Generative AI in SOAR: Automated Case Summaries*. https://d3security.com/blog/generative-ai-in-soar-automated-case-summaries/
5. Rob Fitzpatrick. *The Mom Test: How to talk to customers & learn if your business is a good idea when everyone is lying to you*.
6. Google People + AI Research (PAIR). *People + AI Guidebook*. https://pair.withgoogle.com/
7. Marty Cagan. *Inspired: How to Create Tech Products Customers Love* (4 Product Risks Framework).
