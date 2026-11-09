# Báo cáo cá nhân — 2A202603470_lequanghuy

> Đổi tên file theo quy tắc `MSSV_HoTen.md`, ví dụ `20241234_NguyenVanAn.md` (MSSV trước, dấu `_`, họ tên viết liền không dấu). Sửa cả dòng tiêu đề phía trên cho khớp.
> Template chi tiết và prompt mẫu cho từng mục: [docs/01-worksheet.md](../../docs/01-worksheet.md).
> Mỗi thành viên một file trong `report/individual/` trên repo nhóm: copy template này thành file mới, điền, rồi commit bằng tài khoản GitHub của bạn. Không viết hộ người khác.

## 1. Thông tin học viên

- Họ tên:Lê Quang Huy
- MSSV:2A202603470
- Email trường (không bắt buộc, repo có thể để public):
- Tên nhóm:MH2T
- Link repo nhóm: https://github.com/nhtng0212/K5-L3A-Day02-2A202603481-NguyenHoangTung-DiscoveryProblemFraming

---

## 2. Scan problem (CP1)

Lăng kính: **Lặp lại** · **Tốn thời gian** · **Cần đọc, tổng hợp nhiều thông tin** · **Pain từ người khác**.

| # | Lăng kính | Job Story: Khi… tôi muốn… để… | Ai chịu ảnh hưởng? | Dấu hiệu thật (thời gian, tần suất, số người, bằng chứng) |
|---:|---|---|---|---|
| 1 |Tốn thời gian  |Khi cần mua đồ điện tử, tôi muốn bảng so sánh giá, cấu hình, thông số của từng sản phẩm của từng shop, trên từng trang thương mại điện tử để không phải xem đi xem lại từng sản phẩm qua từng tab |người mua sắm, sinh viên |Tốn 3–4 tiếng lướt web và chuyển qua lại các tab trước khi quyết định mua. |
| 2 |pain từ người khác |Khi nghe giảng về bộ môn AI có quá nhiều từ chuyên ngành Tiếng Anh, tôi muốn có danh mục giải thích nhanh ngữ cảnh, để không bị "mất gốc" và theo kịp bài giảng trên lớp. |học viên, sinh viên |Có 3–4 bạn trong nhóm than phiền không theo kịp thuật ngữ mỗi buổi học phần mới. |
| 3 |Cần đọc, tổng hợp |Khi chuẩn bị nộp bài Lab, tôi muốn rà soát toàn bộ bài đối chiếu với danh mục yêu cầu (Rubric), để đảm bảo không bỏ sót bất kỳ mục nào gây trừ điểm. |học viên, sinh viên |Mất 30 phút rà soát thủ công từng mục checklist trước khi nhấn Submit. |
| 4 |Lặp lại/ tốn thời gian |[Quản lý chi tiêu phòng trọ] Khi cuối tháng đến hạn tính tiền nhà, tôi muốn tự động phân loại chi tiêu chung/riêng và nhóm theo từng mục (đồ ăn, vệ sinh, đồ đạc) cho 3 người, để không phải ngồi cộng sổ thủ công và giải thích lại khi có thắc mắc. |người ở trọ |Mất 45–60 phút mỗi cuối tháng để gom hóa đơn, tính tiền và giải trình trong nhóm chat. |
| 5 |Cần đọc,tổng hợp |[Tổng hợp tin tức/số liệu bóng đá] Khi muốn cập nhật tình hình các trận đấu trong tuần, tôi muốn có bản tóm tắt nhanh về lịch thi đấu, kết quả, danh sách chấn thương và phong độ của đội bóng yêu thích, để không phải lướt qua nhiều ứng dụng/trang tin tức rời rạc. |người đam mê bóng đá |Tốn 30–40 phút mỗi sáng lướt qua 4–5 trang tin tức/app khác nhau để đọc tin. |
| 6 | | | | |
| 7 | | | | |
| 8 | | | | |

**Nếu có dùng AI để gợi ý thêm:** ý nào AI gợi ý mà bạn giữ lại, ý nào bỏ và vì sao.

-

---

## 3. Top 3 Problem Cards + quy trình nháp (CP2)

### Bảng chọn top 3

| Rank | Problem | Vì sao chọn | Điều còn chưa chắc |
|---:|---|---|---|
| 1 |so sánh thông tin cấu hình đồ điện tử |tốn nhiều thời gian lướt web và so sánh sản phẩm, khó lựa chọn sản phẩm phù hợp  |có thể hàng đã hết nhưng chưa cập nhật trên web |
| 2 |chi tiêu phòng trọ |Quy trình thủ công, nhiều bước tính toán, dễ gây mâu thuẫn |Cách tự động nhận diện khoản chung/riêng từ ảnh chuyển khoản/hóa đơn |
| 3 |tổng hơp tin tức bóng đá |Thông tin giải đấu/đội bóng bị phân tán trên nhiều app và trang tin rời rạc |Cách AI chọn lọc nguồn tin chính thống, tránh tin đồn/tin giả |

### Problem Card #1

| Trường | Nội dung |
|---|---|
| Job Story | Khi cần mua đồ điện tử, tôi muốn bảng so sánh giá, cấu hình, thông số của từng sản phẩm của từng shop, trên từng trang thương mại điện tử để không phải xem đi xem lại từng sản phẩm qua từng tab |
| Actor |sinh viên, người tiêu dùng mua hàng trên các trang thương mại điện tử |
| Thời điểm / bối cảnh |trước khi ra quyết định mua hàng điện tử giá trị cao |
| Quy trình hiện tại (3–7 bước) |1. Tra cứu thông tin sản phẩm 2. Xem sản phẩm trên một vài các shop, đại lý 3.So sánh thông tin cấu hình giữa các phiên bản, các dòng khác nhau 4.Xem đánh giá review trên shop hoặc qua các video 5.so sánh giá sản phẩm 6.Lựa chọn sản phẩm đảm bảo cấu hình và phù hợp giá tiền. |
| Bottleneck (bước nào, mất bao nhiêu phút) |bước 3,4 và 5, mất 3 đến 4 tiếng |
| Impact (nếu không giải thì sao) |dành ra 3 đến 4 tiếng để tìm sản phẩm phù hợp, dễ nhầm lẫn và khó đưa ra lựa chọn |
| Success metric (baseline → target) |thời gian nghiên cứu và chốt sản phẩm giảm từ 180 đến 240 phút xuống còn 15 đến 20 phút |
| Phương án không dùng AI |đến trực tiếp cửa hàng xem và nhờ người có chuyên môn tư vấn. |
| Giả thuyết về AI (nếu có) |AI trích xuất thông số cấu hình kèm theo giá tiền của từng shop theo ngân sách đưa ra |
| Cảm nhận nhanh | No AI / Rule / Workflow / Agent / Chưa biết | Workflow

Quy trình nháp hiện tại:

```[1. Tra cứu thông tin: 15'] ➔ [2. Xem sản phẩm trên các shop và đại lý: 30'] 
➔ [3. So sánh cấu hình các phiên bản: 45'] ◄── BOTTLENECK
➔ [4. Xem đánh giá review/video: 45'] ➔ [5. So sánh giá thực tế: 35'] ◄── BOTTLENECK 
➔ [6. Lựa chọn sản phẩm chốt mua: 10']

```

### Problem Card #2

| Trường | Nội dung |
|---|---|
| Job Story | Khi cuối tháng đến hạn tính tiền nhà, tôi muốn tự động phân loại chi tiêu chung/riêng và nhóm theo từng mục (đồ ăn, vệ sinh, đồ đạc) cho 3 người, để không phải ngồi cộng sổ thủ công và giải thích lại khi có thắc mắc. |
| Actor |các sinh viên ở chung trọ |
| Thời điểm / bối cảnh |cuối tháng tổng kết chi tiêu chung |
| Quy trình hiện tại (3–7 bước) |1.Ghi chi tiêu hàng ngày 2.phân loại khoản chung riêng, phân chia theo các mục 3.chia tiền từng phần cho từng thành viên có tham gia vào phần đó. 4.nhập excel và tính tiền 5.Tổng kết số tiền cho mỗi thành viên |
| Bottleneck (bước nào, mất bao nhiêu phút) |bước 2 mất tầm 45 phút |
| Impact (nếu không giải thì sao) |thì mỗi lần tổng kết làm mất thời gian, dễ sai sót dẫn đến tranh cãi |
| Success metric (baseline → target) |giảm thời gian tổng kết từ 45 phút xuống còn 10 phút |
| Phương án không dùng AI |Dùng file Google Sheets cố định lập sẵn công thức chia tiền theo tỷ lệ hoặc dùng ứng dụng quản lý chi tiêu nhóm cố định (như Splitwise). |
| Giả thuyết về AI (nếu có) |AI phân loại tiền cho từng mục và từng thành viên sau đó xuất bảng chia tiền |
| Cảm nhận nhanh | No AI / Rule / Workflow / Agent / Chưa biết | Workflow

Quy trình nháp hiện tại:

```[1. gom chi tiêu hàng ngày: 10'] ➔ [2. Phân loại khoản chung/riêng, phân chia theo các mục : 15'] ◄── BOTTLENECK
➔ [3.chia tiền từng phần cho từng thành viên tham gia vào phần đó: 15'] ➔ [4. Nhập Excel & tính chia tiền: 15'] ◄── BOTTLENECK
➔ [5. tổng kết chia tiền cho từng thành viên: 5']

```

### Problem Card #3

| Trường | Nội dung |
|---|---|
| Job Story | Khi muốn cập nhật tình hình các trận đấu trong tuần, tôi muốn có bản tóm tắt nhanh về lịch thi đấu, kết quả, danh sách chấn thương và phong độ của đội bóng yêu thích, để không phải lướt qua nhiều ứng dụng/trang tin tức rời rạc. |
| Actor |người đam mê bóng đá |
| Thời điểm / bối cảnh |đầu tuần và sau các trận đấu khi không thể xem trực tiếp và muốn nắm bắt tình hình đội bóng yêu thích |
| Quy trình hiện tại (3–7 bước) |1. Xem tỷ số & BXH: Mở ứng dụng Livescore/Flashscore để check kết quả. 2. Đọc bài tổng hợp: Mở Facebook/Báo thể thao đọc bài phân tích trận đấu. 3. Xem clip Highlight: Mở YouTube tìm clip tình huống nổi bật. 4. Gom tin lực lượng: Đọc tin tức chấn thương, thẻ phạt, chuyển nhượng trên các trang/fanpage fanclub. 5. Tổng hợp bức tranh chung: Sắp xếp lại thông tin để nắm tình hình đội bóng. |
| Bottleneck (bước nào, mất bao nhiêu phút) |bước 2 và 4, Mở nhiều trang/app rải rác để đọc tin và tự tổng hợp dữ liệu phong độ, lực lượng (tốn khoảng 30–40 phút mỗi sáng).  |
| Impact (nếu không giải thì sao) |mất thời gian mỗi sáng, dễ nhầm hoặc đọc phải thông tin giả |
| Success metric (baseline → target) |giảm thời gian tổng hợp thông tin từ 30-40 phút xuống còn 5-10 phút |
| Phương án không dùng AI |Đăng ký nhận bản tin (Newsletter) thể thao tự động hoặc chỉ theo dõi 1 kênh tổng hợp cố định. |
| Giả thuyết về AI (nếu có) |AI tự động cào dữ liệu từ các nguồn uy tín (Livescore, trang chủ giải đấu), cô đọng thành 1 bản Daily Recap (Lịch thi đấu + Tỷ số + Lực lượng + Link highlight official) theo đúng đội bóng quan tâm. |
| Cảm nhận nhanh | No AI / Rule / Workflow / Agent / Chưa biết | Workflow

Quy trình nháp hiện tại:

```[1. Xem tỷ số & BXH: 5'] ➔ [2. Đọc bài tổng hợp báo/FB: 15'] ◄── BOTTLENECK
➔ [3. Xem Highlight: 10'] ➔ [4. Gom tin chấn thương/chuyển nhượng: 10'] ◄── BOTTLENECK
➔ [5. Tổng hợp thông tin: 5']

```

### Card muốn pitch nhất

- Card số:1
- Vì sao: Đây là bài toàn có nỗi đau rõ ràng về mặt thời gian. Quá trình lướt web đọc thông số cấu hình và giá cả qua nhiều tab khác nhau làm thông tin bị phân tán, có baseline đo lường được ngay và rất gần gũi với người tiêu dùng
- Câu hỏi muốn nhóm phản biện:Việc cào dữ liệu (crawl data) giá thực tế và mã giảm giá theo thời gian thực từ các sàn TMĐT có rủi ro cao về mặt kỹ thuật (anti-scraping, thay đổi giao diện/voucher liên tục). Liệu giải pháp AI có thực sự khả thi (Feasibility) hơn một công cụ so sánh giá cố định (No AI) không?

### AI đã phản biện card thế nào

| Điểm yếu AI chỉ ra | Đồng ý? | Đã sửa gì |
|---|---|---|
|1	Số liệu tự mâu thuẫn. Bước 3, 4, 5 cộng lại chỉ 45 + 45 + 35 = 125 phút (~2 tiếng), không phải “3 đến 4 tiếng”. Con số 180 phút chỉ đủ khi cộng cả 6 bước. Sơ đồ cũng chỉ đánh dấu bước 3 và 5 là bottleneck, còn bước 4 thì không. |Đồng ý |Ghi rõ 3 tiếng là tổng cả quy trình, bottleneck là bao nhiêu phút, và thống nhất bước 4 có phải bottleneck hay không. |
|2	Baseline có vẻ là ước lượng, chưa đo thật. Các số 15'/30'/45' và khoảng 180–240 phút đều tròn, dễ bị hỏi “đo ở đâu ra”. |Đồng ý một phần |Bấm giờ thật 3–5 lần mua (hoặc phỏng vấn người vừa mua), ghi range và nguồn. |
|3	Job Story chứa sẵn giải pháp. “Tôi muốn bảng so sánh” là giải pháp, không phải động lực, nên khóa bài toán vào một sản phẩm và làm yếu lập luận “tại sao cần AI”.|Không đồng ý |Viết lại theo kết quả mong muốn, ví dụ: “…tôi muốn biết nhanh phiên bản nào đáng tiền nhất trong ngân sách để chốt mua mà không lo chọn nhầm.” |
---

## 4. Tôi đã tham gia phần nào (CP3 → CP7)

| Hoạt động | Tôi đã làm gì? | Kết quả / ảnh hưởng tới bài nhóm |
|---|---|---|
| Pitch Problem Card | Viết Problem Card #1: người mua đồ điện tử giá trị cao mất 3–4 tiếng so sánh cấu hình, review và giá qua nhiều tab. Vẽ quy trình nháp 6 bước, chỉ ra bottleneck ở bước 3 và 5, đề xuất mức Workflow. | Bài được đưa vào danh sách ứng viên của nhóm [không được chọn]. |
| Phản biện bài của bạn khác | Câu hỏi tôi đã đặt: [ví dụ: "Con số tiết kiệm 45–60 phút lấy từ đâu, đã bấm giờ thật chưa?", "Nếu AI lọc sai tin / trả lời sai thì ai chịu rủi ro, boundary ở đâu?"] | [Bạn đó bổ sung baseline / rủi ro / boundary gì sau khi nghe câu hỏi]. |
| Nhận phản biện | Câu hỏi tôi nhận được: (1) Bottleneck "3–4 tiếng" mâu thuẫn với phép cộng 45 + 45 + 35 = 125 phút. (2) Baseline là ước lượng, chưa đo thật. (3) Job Story đã chứa sẵn giải pháp ("tôi muốn bảng so sánh"). | Tôi đã sửa gì: ghi rõ 3 tiếng là tổng cả quy trình và thống nhất lại bottleneck; chuyển sang bấm giờ thật để thay số ước lượng; viết lại Job Story theo kết quả mong muốn ("biết nhanh phiên bản nào đáng tiền nhất trong ngân sách để chốt mua mà không lo chọn nhầm"). |
| Gom cluster / cây OST | [Tôi đã làm gì: ví dụ gom các problem card giống nhau, đề xuất nhánh cluster, nối vấn đề với outcome] | [Cluster nhóm chốt, vd: "tổng hợp / so sánh thông tin từ nhiều nguồn" và tôi góp phần nào]. |
| Chọn candidate problem | [Tôi đề xuất / bảo vệ bài nào, dùng tiêu chí nào: tần suất, quy mô thời gian, dữ liệu có sẵn, rủi ro AI] | [Bài nhóm chọn và lý do chọn]. |
| Kiểm chứng / research | [Tôi đã phỏng vấn / survey / bấm giờ bao nhiêu người, hỏi gì] | [Kết quả: số liệu thật so với ước lượng ban đầu, điều gì làm tôi bất ngờ]. Nếu chưa kiểm chứng: "chưa kiểm chứng được, đây là giả định cần xác nhận". |
| Quy trình nhóm | [Tôi vẽ / sửa quy trình as-is: các bước, số phút mỗi bước, bước bottleneck] | [Quy trình cuối của nhóm và chỗ tôi chỉnh so với bản nháp]. |
| Problem Statement | [Tôi viết / góp ý câu nào; tách vấn đề khỏi giải pháp, thu hẹp actor] | [Câu Problem Statement cuối của nhóm]. |
| Mức can thiệp AI | [Tôi đề xuất mức nào: No AI / Rule / Workflow / Agent, và tại sao. Gợi ý: phần scraping/lọc theo rule, LLM chỉ dùng chuẩn hóa và tóm tắt] | Boundary tôi đề xuất: AI chỉ trích xuất và tổng hợp, mọi thông số/giá kèm link nguồn, người dùng tự xác nhận trước khi quyết định. |
| Quyết định | [Tôi tham gia chốt: tiếp tục / đổi hướng / dừng, dựa trên bằng chứng nào] | [Quyết định cuối của nhóm và điều kiện kèm theo, vd: kiểm chứng baseline trước khi build]. |

---

## 5. Dùng AI

| Checkpoint | Tôi dùng AI để làm gì? | AI hữu ích ở đâu? | AI sai hoặc hời hợt ở đâu? | Tôi sửa gì bằng nhận định của mình? |
|---|---|---|---|---|
| CP1 Scan | [Nhờ AI gợi ý các việc lặp lại, tốn thời gian trong đời sống/học tập có thể tối ưu bằng AI, trong đó có việc so sánh sản phẩm điện tử trước khi mua.] | Gợi ý nhanh nhiều hướng và cách phân nhóm, giúp tôi có danh sách ban đầu để chọn. | Gợi ý chung chung, nhiều ý chưa gắn với trải nghiệm thật hay số liệu cụ thể. | Chỉ giữ bài toán tôi từng trải qua và có thể mô tả quy trình thật: mua đồ điện tử giá trị cao. |
| CP2 Problem Card | Nhờ AI phản biện Problem Card #1 theo khung "Điểm yếu AI chỉ ra / Đồng ý? / Đã sửa gì", rồi chọn ra 3 điểm đáng giữ nhất. | Phát hiện lỗi tôi không tự thấy: bottleneck "3–4 tiếng" mâu thuẫn với phép cộng (45 + 45 + 35 = 125 phút); baseline là số ước lượng; Job Story đã chứa sẵn giải pháp ("tôi muốn bảng so sánh"). | AI đưa ra 8 điểm, trong đó có điểm không phù hợp (ví dụ "lệch khỏi bài toán Vingroup" trong khi bài của tôi là bài toán người tiêu dùng). Các gợi ý sửa cũng chỉ là ví dụ, chưa dựa trên dữ liệu thật của tôi. | Tôi lọc còn 3 điểm ảnh hưởng trực tiếp đến độ tin cậy, tự quyết định đồng ý hay không, rồi sửa lại cách ghi bottleneck, baseline và Job Story. [Ghi điểm bạn không đồng ý.] |
| CP4 Research | [Nhờ AI soạn câu hỏi phỏng vấn người từng mua đồ điện tử: họ so sánh ở đâu, mất bao lâu, bước nào mệt nhất.] | Có sẵn bộ câu hỏi mở, tránh hỏi dẫn dắt, tiết kiệm thời gian chuẩn bị. | AI không biết ngữ cảnh người được hỏi; câu hỏi chung chung và không thay được số liệu bấm giờ thật. | Tôi chỉnh câu hỏi theo từng người, ghi lại thời gian thật từng bước và chỉ kết luận từ điều họ nói. [Ghi số liệu thật nếu có.] |
| CP5 Quy trình | Nhờ AI kiểm tra tính nhất quán của quy trình 6 bước: tổng thời gian, số phút từng bước, bước nào là bottleneck. | Chỉ ra: 15 + 30 + 45 + 45 + 35 + 10 = 180 phút là tổng cả quy trình, không phải riêng bottleneck; sơ đồ chỉ đánh dấu bước 3 và 5 trong khi bảng ghi bước 3, 4, 5. | Số phút từng bước là số tròn do tôi ước lượng; AI không biết số thật nên không kiểm chứng được. | Tôi thống nhất lại bottleneck giữa bảng và sơ đồ, và thay số ước lượng bằng số đo thật. [Ghi bottleneck cuối cùng và số thật.] |
| CP5–6 Problem Statement | Nhờ AI gợi ý cách viết lại Job Story theo kết quả mong muốn và thu hẹp Actor ("sinh viên, người tiêu dùng" quá rộng). | Chỉ ra lỗi "solution-first" và đề xuất khung câu rõ hơn, ví dụ hướng tới "biết nhanh phiên bản nào đáng tiền nhất trong ngân sách mà không lo chọn nhầm". | Câu AI viết nghe trơn tru nhưng chung chung; persona và con số AI gợi ý (ví dụ laptop 15–20 triệu) chưa chắc đúng với nhóm của tôi. | Tôi chọn persona và bối cảnh từ dữ liệu thật, viết lại bằng lời của mình và chỉ giữ con số có nguồn. [Ghi Problem Statement cuối cùng.] |
| CP6 Mức can thiệp / quyết định | Nhờ AI phân tích mức can thiệp (No AI / Rule / Workflow / Agent), rủi ro khi AI sai và boundary. | Giúp tách phần nào chỉ cần rule/scraping (lấy thông số và giá), phần nào cần LLM (chuẩn hóa tên cấu hình giữa các shop, tóm tắt review); nhắc rủi ro sai thông số/giá trong quyết định chi tiêu lớn. | AI chưa tính đến việc giá thay đổi theo voucher, flash sale, phí ship nên bảng giá có thể lỗi thời; target giảm từ 180–240 xuống 15–20 phút chưa có căn cứ. | Tôi giữ mức Workflow, đặt boundary: mọi thông số và giá phải kèm link nguồn, người dùng tự xác nhận trước khi mua, AI không tự đặt hàng. Tôi cũng sẽ đặt target theo từng bước thay vì một con số chung. [Ghi quyết định cuối.] |

---

## 6. Reflection (CP7)

Trả lời bằng trải nghiệm thật của bạn, tối thiểu 200 từ cho các câu 6.1–6.6 (không tính 6.7, câu này được chấm riêng ở tiêu chí C5). **Không dùng AI để viết thay.**

**6.1. Tôi học được gì khi nghe top 3 problems của các bạn khác?** Sau khi nghe qua top3 problems của các bạn khác, tôi học được rằng bài toán hay là bài có con số tiết kiệm cụ thể, xảy ra thường xuyên và nêu rõ AI có thể sai ở đâu, từ đó mình sẽ chỉnh lại baseline, actor và boundary trong bài của mình.

**6.2. Nhóm có lúc nào bị "solution-first" (nghĩ giải pháp trước khi hiểu vấn đề) không? Lúc đó nhóm nhận ra và xử lý thế nào?** Có. Ngay trong Job Story của tôi: "tôi muốn bảng so sánh giá, cấu hình..." đã là giải pháp chứ chưa phải vấn đề. Một số thành viên cũng đề xuất ngay công cụ, kỹ thuật (thu thập dữ liệu từ các sàn, dùng LLM) khi chưa trả lời được các câu hỏi về nguồn dữ liệu và độ tin cậy của giá, thông số.  

**6.3. Tôi có đổi ý sau khi bị phản biện không? Kể một lần cụ thể.** Có. Ban đầu tôi ghi bottleneck là bước 3, 4, 5 mất "3 đến 4 tiếng". Khi bị chỉ ra 45 + 45 + 35 chỉ khoảng 125 phút,tôi nhận ra 3 tiếng là tổng cả quy trình (180 phút), không phải riêng bottleneck, và bảng với sơ đồ đang đánh dấu bottleneck không thống nhất. Tôi đã sửa lại cho khớp và chuyển sang bấm giờ thật thay vì dùng số ước lượng. Tôi cũng không còn xem mục tiêu 15–20 phút là chắc chắn, vì nó chưa có căn cứ.

**6.4. Kết quả kiểm chứng (phỏng vấn/survey/research) có làm tôi bất ngờ không? Điều gì?** Có. Tôi nhận được nhiều câu hỏi từ các bạn nhóm khác, giúp tôi thấy thêm các trường hợp thực tế mà tôi chưa nghĩ tới: giá thay đổi theo voucher, flash sale, phí ship nên bảng giá dễ lỗi thời; cùng một sản phẩm có tên cấu hình khác nhau giữa các shop; hàng trôi nổi hoặc sai thông số. [Nếu có số liệu thật, thêm vào: thời gian thực tế bước nào lâu nhất, khác bao nhiêu so với ước lượng 180 phút.]

**6.5. Điều khó nhất khi viết Problem Statement là gì?** Khó nhất là tách vấn đề khỏi giải pháp: viết câu nào cũng tự thành "cần một công cụ so sánh". Tôi cũng khó thu hẹp đối tượng (ban đầu quá rộng: "sinh viên, người tiêu dùng") và viết sao cho vừa thực tế, vừa chi tiết, vừa ngắn gọn dễ hiểu.

**6.6. Nếu làm lại, tôi sẽ đổi gì? Tôi sẽ phản biện nhóm mạnh hơn ở điểm nào?** Tôi sẽ đo baseline thật trước khi viết số, chọn đối tượng cụ thể hơn (ví dụ sinh viên mua laptop trong một mức ngân sách), và phân tích rủi ro, định nghĩa tiêu chí trước khi đề xuất tính năng. Về phản biện, tôi sẽ hỏi nhóm mạnh hơn hai câu: "Phần nào thật sự cần LLM, phần nào chỉ là rule hay thu thập dữ liệu?" và "Nếu AI trích sai thông số hoặc giá thì ai chịu rủi ro, boundary ở đâu?"

**6.7. Hiểu bài:** giải thích bằng 5–8 câu, không nhìn tài liệu, chuỗi *problem → quy trình → metric → boundary → mức can thiệp AI → quyết định* .Vấn đề là người mua đồ điện tử giá trị cao mất khoảng 3–4 tiếng để nghiên cứu vì phải xem đi xem lại từng sản phẩm, từng shop qua nhiều tab. Quy trình hiện tại có 6 bước (tra cứu, xem trên các shop, so sánh cấu hình, xem review, so sánh giá, chốt mua), tổng khoảng 180 phút, trong đó bước so sánh cấu hình (~45 phút) và so sánh giá (~35 phút) là bottleneck. Metric là thời gian nghiên cứu và chốt sản phẩm, dự kiến giảm từ 180–240 phút xuống 15–20 phút, nhưng baseline này vẫn là ước lượng và cần bấm giờ thật để xác nhận. Boundary là AI chỉ trích xuất và tổng hợp, mọi thông số và giá phải kèm link nguồn, người dùng tự xác nhận trước khi mua, AI không tự đặt hàng. Mức can thiệp là Workflow, phần lấy thông số và giá dùng rule hoặc thu thập dữ liệu, LLM chỉ dùng để chuẩn hóa tên cấu hình giữa các shop và tóm tắt review. Quyết định là tiếp tục bài toán này nhưng có điều kiện, đo baseline thật và thu hẹp đối tượng trước khi xây bản thử.

---

## 7. Tài liệu tham khảo

-
