# Báo cáo cá nhân — 2A202603507_DoHoangMinh

> Đổi tên file theo quy tắc `MSSV_HoTen.md`, ví dụ `20241234_NguyenVanAn.md` (MSSV trước, dấu `_`, họ tên viết liền không dấu). Sửa cả dòng tiêu đề phía trên cho khớp.
> Template chi tiết và prompt mẫu cho từng mục: [docs/01-worksheet.md](../../docs/01-worksheet.md).
> Mỗi thành viên một file trong `report/individual/` trên repo nhóm: copy template này thành file mới, điền, rồi commit bằng tài khoản GitHub của bạn. Không viết hộ người khác.

## 1. Thông tin học viên

- Họ tên: Đỗ Hoàng Minh
- MSSV: 2A202603507
- Email trường
- Tên nhóm:
- Link repo nhóm: https://github.com/nhtng0212/K5-L3A-Day02-2A202603481-NguyenHoangTung-DiscoveryProblemFraming

---

## 2. Scan problem (CP1)

Lăng kính: **Lặp lại** · **Tốn thời gian** · **Cần đọc, tổng hợp nhiều thông tin** · **Pain từ người khác**.

| # | Lăng kính | Job Story: Khi… tôi muốn… để… | Ai chịu ảnh hưởng? | Dấu hiệu thật (thời gian, tần suất, số người, bằng chứng) |
|---:|---|---|---|---|
| 1 | Tốn thời gian / Quá tải thông tin|Khi bắt đầu ngày mới, tôi muốn có sẵn bản tóm tắt các tin tức công nghệ quan trọng nhất từ nhiều nguồn, để nắm bắt thông tin nhanh chóng mà không phải lướt thủ công hàng chục trang web. | Content Creator công nghệ, nhà báo, Researcher| Tự bấm giờ mất khoảng 45–60 phút mỗi sáng để lướt qua báo chí, YouTube, X và Reddit nhưng vẫn lo bị bỏ sót tin.|
| 2 | Tìm kiếm nguồn hàng & Khách hàng thủ công (Tốn thời gian & dễ bỏ sót)|Khi cần tìm nguồn xe đạp cũ để thu mua hoặc tiếp cận khách hàng tiềm năng trên các hội nhóm Facebook, Chợ Tốt, tôi muốn có công cụ tự động quét bài đăng và thông tin khách hàng, để nhanh chóng liên hệ tư vấn mà không phải lướt thủ công hàng giờ. |Chủ cửa hàng xe đạp cũ |Mất 2–3 tiếng mỗi ngày lướt thủ công các nhóm |
| 3 | Tốn thời gian / Bỏ lỡ cơ hội mua hời|Khi cần tìm nguồn xe đạp cũ để nhập lại, tôi muốn hệ thống định giá nhanh các bài đăng trên hội nhóm dựa trên lịch sử giao dịch cũ, để không bị người khác mua mất món hời. |Chủ cửa hàng xe đạp cũ | Mất 1–2 tiếng mỗi ngày lướt group thủ công, thường xuyên bỏ lỡ xe giá tốt do đọc tin trễ.|
| 4 |Lặp lại câu hỏi / Quá tải hỗ trợ |Khi nhân viên liên tục hỏi lại các vấn đề kỹ thuật đã từng được QA xử lý trước đó, tôi muốn hệ thống tự động tra cứu tài liệu tổng hợp từ các thread cũ để trả lời ngay, và chỉ tạo ticket gửi QA khi gặp vấn đề hoàn toàn mới, để giảm tải cho đội ngũ QA. | Đội ngũ QA / Quản lý dự án| QA tốn 3–4 tiếng mỗi ngày để gõ lại các câu trả lời cho những sự cố từng được xử lý ở lần trước.|
| 5 | | | | |
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
| 1 | Tốn thời gian tổng hợp tin công nghệ mỗi sáng | Vì muốn tiết kiệm 45‑60 phút, giảm khả năng bỏ sót tin | Chưa chắc công cụ AI có thể lọc tin chính xác, giữ cân bằng giữa độ sâu và tốc độ |
| 2 | Tìm nguồn hàng và khách hàng thủ công trên Facebook/Chợ Tốt | Muốn tự động quét bài đăng, giảm 2‑3 giờ/lần, tránh bỏ sót cơ hội | Chưa chắc AI nhận dạng đúng ngữ cảnh và dữ liệu phi cấu trúc |
| 3 | Hỗ trợ trả lời câu hỏi kỹ thuật lặp lại của nhân viên | Muốn tự động tra cứu tài liệu, giảm 3‑4 giờ QA mỗi ngày | Chưa chắc AI hiểu đúng ngữ cảnh phức tạp, tránh trả lời sai |

### Problem Card #1 — Tổng hợp tin công nghệ mỗi sáng

| Trường | Nội dung |
| --- | --- |
| **Job Story** | Khi bắt đầu ngày mới, tôi muốn có bản tóm tắt các tin công nghệ quan trọng từ nhiều nguồn, để tiết kiệm thời gian và không bỏ lỡ thông tin quan trọng. |
| **Actor** | Content creator công nghệ, nhà báo, nhà nghiên cứu |
| **Thời điểm / bối cảnh** | Sáng mỗi ngày, trước khi bắt đầu công việc |
| **Quy trình hiện tại** | 1. Mở 5–6 trang tin / mạng xã hội (YouTube, X, Reddit, báo công nghệ) · 2. Lướt tiêu đề, mở các bài nổi bật · 3. Đọc nội dung, chọn lọc thông tin · 4. Viết tóm tắt thủ công · 5. Tổng hợp thành bản tin chung |
| **Bottleneck** | Bước 3 và Bước 4 (đọc và viết tóm tắt thủ công): mất khoảng 50 phút |
| **Impact** | Tốn 45–60 phút mỗi sáng, dễ bị bỏ sót tin quan trọng do lượng thông tin quá tải |
| **Success metric** | Giảm thời gian tổng hợp từ 3-4 giờ xuống dưới 30 phút - 1 giờ mỗi ngày |
| **Phương án không dùng AI** | Dùng Google Search gom tin, tự lọc và viết tóm tắt thủ công |
| **Giả thuyết về AI** | Hệ thống tự động quét nguồn, gom cụm tin cùng sự kiện và tạo bản tóm tắt ngắn để người dùng duyệt |
| **Cảm nhận nhanh** | Workflow |

**Quy trình nháp hiện tại:**

1. Mở 5–6 nguồn tin công nghệ (YouTube, X, Reddit, báo điện tử)
2. Lướt tiêu đề, chọn lọc các bài có lượng tương tác cao
3. Đọc nội dung chi tiết từng bài
4. Tự viết tóm tắt ngắn cho từng chủ đề
5. Tổng hợp thành bản tin hoàn chỉnh gửi đi

---

### Problem Card #2 — Tìm nguồn hàng và khách hàng thủ công

| Trường | Nội dung |
| --- | --- |
| **Job Story** | Khi cần tìm nguồn xe đạp cũ để thu mua hoặc tiếp cận khách hàng tiềm năng trên Facebook và Chợ Tốt, tôi muốn hệ thống tự động quét bài đăng, để nhanh chóng liên hệ mà không phải lướt thủ công hàng giờ. |
| **Actor** | Chủ cửa hàng xe đạp cũ kiêm kinh doanh online |
| **Thời điểm / bối cảnh** | Trong ngày, rải rác các khung giờ cao điểm người dùng đăng bán đồ cũ |
| **Quy trình hiện tại** | 1. Mở lần lượt các nhóm Facebook và ứng dụng Chợ Tốt · 2. Lướt bảng tin (Newsfeed) thủ công · 3. Dừng lại khi thấy bài đăng bán xe hoặc người hỏi mua · 4. Đọc nội dung, kiểm tra giá và vị trí · 5. Nhắn tin liên hệ hoặc lưu lại thông tin |
| **Bottleneck** | Bước 2 và Bước 3 (lướt thủ công liên tục): mất 2–3 tiếng mỗi ngày nhưng dễ bỏ sót bài đăng trôi nhanh |
| **Impact** | Tốn 2–3 giờ/ngày; thường xuyên bỏ lỡ xe giá tốt hoặc khách tiềm năng do đọc tin muộn |
| **Success metric** | Giảm thời gian tìm kiếm từ 2–3 giờ xuống dưới 30 phút; tỷ lệ bỏ sót tin giảm về 0 |
| **Phương án không dùng AI** | Lưu bài viết post trên hội nhóm thủ công, cài đặt thông báo về tin mua bán |
| **Giả thuyết về AI** | Tự động quét các bài đăng theo từ khóa, lọc ra danh sách xe cần mua / khách cần bán và gửi thông báo tập trung |
| **Cảm nhận nhanh** | Workflow |

**Quy trình nháp hiện tại:**

1. Mở danh sách các hội nhóm xe đạp trên facebook và Chợ Tốt
2. Lướt thủ công liên tục trên màn hình điện thoại/máy tính
3. Lọc bằng mắt các bài đăng bán xe hoặc người tìm mua
4. Nhắn tin hỏi giá hoặc lưu link vào bảng ghi chú cá nhân
5. Chủ động liên hệ tư vấn hoặc chốt mua

---

### Problem Card #3 — Hỗ trợ trả lời câu hỏi kỹ thuật lặp lại

| Trường | Nội dung |
| --- | --- |
| **Job Story** | Khi nhân viên hỏi lỗi trong thread, tôi muốn hệ thống tự đối chiếu kho tri thức cũ để trả lời ngay nếu là lỗi quen, và chỉ đẩy ticket cho QA khi phát sinh vấn đề mới, để cắt giảm công sức giải đáp lặp lại. |
| **Actor** | Thành viên đội ngũ QA / Quản lý dự án |
| **Thời điểm / bối cảnh** | Suốt giờ làm việc, khi nhân viên gặp sự cố và đặt câu hỏi liên tục trên kênh chat |
| **Quy trình hiện tại** | 1. Nhân viên đặt câu hỏi/gửi lỗi vào thread chung · 2. QA đọc lịch sử và nội dung lỗi · 3. QA kiểm tra xem lỗi này đã từng xuất hiện chưa · 4. QA tự gõ lại câu trả lời hoặc hướng dẫn xử lý cũ · 5. Nếu là lỗi mới hoàn toàn thì tạo ticket xử lý |
| **Bottleneck** | Bước 3 và Bước 4 (tra cứu thủ công và gõ lại câu trả lời quen thuộc): tốn 3–4 tiếng mỗi ngày |
| **Impact** | Đội ngũ QA bị quá tải, mất 3–4 giờ/ngày chỉ để giải đáp những vấn đề đã từng được xử lý từ các tuần trước |
| **Success metric** | Giảm 70% số lượng câu hỏi trùng lặp mà QA phải trả lời thủ công hằng ngày |
| **Phương án không dùng AI** | Xây dựng file Excel hoặc các docs (FAQ) và tra cứu thủ công bằng từ khóa |
| **Giả thuyết về AI** | Bot tự động đọc câu hỏi của nhân viên, tìm trong dữ liệu các thread cũ để trả lời ngay, nếu không khớp sẽ tự chuyển thành ticket cho QA |
| **Cảm nhận nhanh** | Workflow |

**Quy trình nháp hiện tại:**

1. Nhận câu hỏi/lỗi từ nhân viên qua thread chung
2. Đọc và phân tích mô tả lỗi
3. Nhớ lại hoặc tìm kiếm thủ công trong lịch sử chat xem lỗi này từng gặp chưa
4. Gõ lại câu trả lời hoặc hướng dẫn khắc phục
5. Tạo ticket mới trên hệ thống nếu là sự cố lần đầu xuất hiện

### Card muốn pitch nhất

- Card số: 3
- Vì sao: Nhân viên mong muốn được nhận câu trả lời nhanh nhất, chính xác nhất cho vấn đề mà họ gặp phải. Đưa ra yêu cầu chatbot có thể quyết định đưa ra câu trả lời nếu gặp 1 vấn đề đã được xử lý, giải quyết trước đó. Nếu gặp 1 vấn đề mới thì được request chuyển đến bộ phận QA.
- Câu hỏi muốn nhóm phản biện: Độ chính xác của AI có đảm bảo không? AI có thể phân biệt được vấn đề mới và cũ khi có nhiều điểm tương đồng

### AI đã phản biện card thế nào

| Điểm yếu AI chỉ ra | Đồng ý? | Đã sửa gì |
| --- | --- |---|
|Thiếu metric đánh giá độ chính xác và thời gian trả lời|v|Thêm các metric phù hợp liên quan đến độ chính xác, % đồng ý passable của nhân viên
|Chưa có giám sát kiểm tra câu trả lời của chatbot | v | thêm "Review của con người trước khi trả lời và ghi rõ quy trình kiểm soát chất lượng |

---

## 4. Tôi đã tham gia phần nào (CP3 → CP7)

| Hoạt động | Tôi đã làm gì? | Kết quả / ảnh hưởng tới bài nhóm |
|---|---|---|
| Pitch Problem Card | Chuẩn bị và trình bày 3 Problem Cards (Tech news, Source hunting, QA support) | Được nhóm chấp nhận top 3, nhận phản biện để cải thiện |
| Phản biện bài của bạn khác | Đặt câu hỏi về độ chính xác AI và khả năng phân biệt vấn đề mới/cũ (Card 3) | Nhận phản biện về metric và quy trình review |
| Nhận phản biện | Trả lời phản biện, bổ sung success metric và quy trình kiểm soát | Cải thiện độ rõ ràng, chuẩn bị cho AI triển khai |
| Gom cluster / cây OST | Thu thập và nhóm các vấn đề tương tự thành cây OST | Giúp xác định các nhóm chính, hỗ trợ lựa chọn candidate problem |
| Chọn candidate problem | Dựa trên CP1 scan, chọn 3 vấn đề ưu tiên | Đạt tiêu chí ưu tiên, chuẩn bị cho CP2 |
| Kiểm chứng / research | Thực hiện phỏng vấn 5 người dùng, thu thập nhu cầu và phản hồi | Xác nhận nhu cầu thực tế, hỗ trợ quyết định giải pháp |
| Quy trình nhóm | Thảo luận sprint, lập kế hoạch triển khai các Card | Định hướng rõ ràng, phân công công việc |
| Problem Statement | Viết mô tả chi tiết, success metric cho mỗi Card | Sẵn sàng cho CP5‑6, tài liệu đầy đủ |
| Mức can thiệp AI | Đánh giá phạm vi AI có thể tự động hoá (70% công việc) | Đề xuất mức can thiệp phù hợp |
| Quyết định | Chọn giải pháp AI cho Card 1 và Card 2, đề xuất MVP | Được nhóm chấp nhận, tiến hành prototype| Pitch Problem Card | | |
| Phản biện bài của bạn khác | Câu hỏi tôi đã đặt: | |
| Nhận phản biện | Câu hỏi tôi nhận được: | Tôi đã sửa gì: |
| Gom cluster / cây OST | | |
| Chọn candidate problem | | |
| Kiểm chứng / research | | |
| Quy trình nhóm | | |
| Problem Statement | | |
| Mức can thiệp AI | | |
| Quyết định | | |

---

## 5. Dùng AI

| Checkpoint | Tôi dùng AI để làm gì? | AI hữu ích ở đâu? | AI sai hoặc hời hợt ở đâu? | Tôi sửa gì bằng nhận định của mình? |
|---|---|---|---|---|
| CP1 Scan | Dùng AI tổng hợp tin công nghệ mỗi sáng | Nhanh chóng thu thập, lọc và tóm tắt tin từ nhiều nguồn | Bỏ sót tin quan trọng, lọc không chính xác khi từ khoá không đủ | Kiểm tra thủ công đầu ra, tinh chỉnh keyword và threshold |
| CP2 Problem Card | AI tự động quét các bài đăng mua bán xe đạp trên FB/Chợ Tốt | Giảm 2‑3 giờ/lần, nhanh chóng lấy thông tin liên hệ | Nhận dạng sai ngữ cảnh, bỏ sót bài đăng do đa dạng format | Thêm bước xác thực dữ liệu, human‑in‑the‑loop trước khi gửi |
| CP4 Research | AI hỗ trợ phân tích nhu cầu qua phỏng vấn và tài liệu | Tự động trích xuất ý chính, thống kê xu hướng | Sai lệch do bias trong dữ liệu, hiểu sai câu trả lời mở | Review kết quả, điều chỉnh mô hình và tiêu chí đánh giá |
| CP5 Quy trình | AI tự động hoá quy trình tóm tắt tin (5‑6 bước) | Tự động thực hiện các bước thu thập, lọc, tóm tắt | Lỗi parsing nội dung, định dạng không đồng nhất | Có fallback thủ công, kiểm tra định dạng output |
| CP5–6 Problem Statement | AI đề xuất mô tả problem và success metric | Tạo draft ngắn gọn, đề xuất metric dựa trên dữ liệu | Thiếu nuance, không phản ánh đầy đủ bối cảnh | Chỉnh sửa thủ công, bổ sung chi tiết và ràng buộc |

---

## 6. Reflection (CP7)

Trả lời bằng trải nghiệm thật của bạn, tối thiểu 200 từ cho các câu 6.1–6.6 (không tính 6.7, câu này được chấm riêng ở tiêu chí C5). **Không dùng AI để viết thay.**

**6.1. Tôi học được gì khi nghe top 3 problems của các bạn khác?**

Em thấy AI Agent rất tiềm năng khi tính ứng dựng và triển khai rộng rãi để giải quyết các vấn đề.

**6.2. Nhóm có lúc nào bị "solution-first" (nghĩ giải pháp trước khi hiểu vấn đề) không? Lúc đó nhóm nhận ra và xử lý thế nào?**

Có. Một số thành viên nhóm đã đề xuất ngay về các công cụ, mặt kỹ thuật mà chưa hiểu rõ về nghiệp vụ, chưa trả lời được câu hỏi đặc thù về nguồn dữ liệu hay rủi ro bảo mật quyền riêng tư. 

Nhóm tiến hành bàn bạc, liệt kê yêu cầu nghiệp vụ, phân tích rủi ro, xác định tiêu chí, chỉ số đánh giá phù hợp. Nhóm tránh đầu tư vào giải pháp chưa kiểm chứng và đi sâu hiểu rõ vấn đề

**6.3. Tôi có đổi ý sau khi bị phản biện không? Kể một lần cụ thể.**

Có. Khi được 1 thành viên hỏi về CARD 2: AI có thể quét tự động các bài đăng trong hội nhóm mà không cần xác thực không? 

Về câu hỏi trên, em chưa nghĩ về câu hỏi đó khi triển khai ý tưởng. Khi được bạn giúp đỡ và hiểu ra vấn đề, em đã điều chỉnh lại và kiểm tra lại nguy cơ sai sót, giảm độ chính xác xuống mức hợp lý (thay vì 100% là 1 con số lý tưởng)

**6.4. Kết quả kiểm chứng (phỏng vấn/survey/research) có làm tôi bất ngờ không? Điều gì?**

Có. Em nhận được nhiều câu hỏi từ các bạn nhóm khác, điều này giúp em có được bức tranh tổng thể với đa dạng nhiều Edge case thực tế.

**6.5. Điều khó nhất khi viết Problem Statement là gì?**

Về tính thực tế, độ chi tiết và ngắn gọn và dễ hiểu

**6.6. Nếu làm lại, tôi sẽ đổi gì? Tôi sẽ phản biện nhóm mạnh hơn ở điểm nào?**

Em sẽ đầu tư thời gian thêm vào phần khai phá vấn đề sâu hơn, về phân tích rủi ro, định nghĩa tiêu chí trước khi đề xuất giải pháp, các tính năng.

**6.7. Hiểu bài:** giải thích bằng 5–8 câu, không nhìn tài liệu, chuỗi *problem → quy trình → metric → boundary → mức can thiệp AI → quyết định* của bài nhóm mình

Problem: xác định rõ ràng nhu cầu và các khó khăn cần giải quyết

Process – các bước hiện tại thực hiện để đối mặt với vấn đề

Metric – các chỉ số đo lường (thời gian, độ chính xác, năng suất) để đánh giá cải tiến

Boundary – tính toán độ phức tạp và độ tin cậy mà hệ thống có thể xử lý

mức can thiệp AI – xác định tỷ lệ tự động hóa (ví dụ 70 %) và các bước cần có con người
Decision – Lựa chọn giải pháp thực thi

---

## 7. Tài liệu tham khảo

