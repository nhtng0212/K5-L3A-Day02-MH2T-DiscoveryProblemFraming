# Team

> Điền file này trên repo chung do nhóm trưởng fork. Nhóm điền phần **Thông tin nhóm** và **Thành viên**. Mỗi người tự điền phần của mình trong **Cá nhân**. Không copy file này sang repo khác.

## Thông tin nhóm

- Tên nhóm: **MH2T**
- Candidate problem nhóm chọn (1 câu): **Tự động hóa hỗ trợ tổng hợp mốc thời gian (Timeline) và dấu hiệu nhận diện (IoC) để sinh bản báo cáo sự cố an ninh mạng (Incident Post-Mortem Report) trên TheHive/Wazuh.**
- Quyết định cuối (Go / Not Yet / No-Go): **Go** (Pilot phạm vi nhỏ: Workflow soạn thảo bản nháp bán tự động có con người duyệt, không dùng Agent tự trị)

## Thành viên

| STT | Họ và tên | MSSV | Vai trò trong nhóm | Tài khoản GitHub |
|---:|---|---|---|---|
| 1 | Đỗ Hoàng Minh | | Phụ trách research công cụ & phản biện kỹ thuật | |
| 2 | Lê Quang Huy | | Phụ trách kiểm chứng (The Mom Test) & ghi chép | |
| 3 | Nguyễn Văn Tùng | 2A202603471 | Đề xuất bài toán chọn (Card #2), vẽ quy trình & Problem Statement | nguyenvantung-sec |
| 4 | Nguyễn Hoàng Tùng | 2A202603481 | Nhóm trưởng, điều phối tiến trình & đánh giá 4 rủi ro | nhtng0212 |

Không ghi email hay số điện thoại vào bảng này, vì repo có thể để public.

Gợi ý vai trò: điều phối thời gian, ghi chép, người phản biện chính, phụ trách kiểm chứng (phỏng vấn/survey), phụ trách research, vẽ quy trình, viết Problem Statement.

## Phân công theo checkpoint

| Checkpoint | Người chính | Người hỗ trợ | Sản phẩm |
|---|---|---|---|
| CP3 — Hội tụ nhóm | Nguyễn Hoàng Tùng | Nguyễn Văn Tùng | Cluster, cây OST, bảng chấm điểm shortlist |
| CP4 — Kiểm chứng | Lê Quang Huy | Nguyễn Văn Tùng | Assumption map, 2 interview snapshots theo The Mom Test |
| CP4 — Research | Đỗ Hoàng Minh | Nguyễn Hoàng Tùng | Bảng research 3 công cụ (TheHive, Cortex XSOAR, D3 SOAR) có link |
| CP5 — Quy trình trước/sau | Nguyễn Văn Tùng | Đỗ Hoàng Minh | Sơ đồ quy trình Before/After + bảng so sánh before/after |
| CP5 — Problem Statement v0 | Nguyễn Văn Tùng | Lê Quang Huy | Problem Statement v0 có boundary rõ ràng |
| CP6 — Mức can thiệp + Problem Statement v1 | Nguyễn Hoàng Tùng | Nguyễn Văn Tùng | Ma trận, AI Canvas, 4 tiêu chí eval, Problem Statement v1 |
| CP6 — Quyết định | Cả nhóm thảo luận | Nguyễn Hoàng Tùng | Đánh giá 4 rủi ro, kết luận Go + pilot scope và ngưỡng dừng |

## Cá nhân

Mỗi thành viên thêm một mục theo mẫu dưới đây, tiêu đề là `HoVaTen-MSSV`.

### NguyenVanTung-2A202603471

**Phần việc phụ trách:**

- Đề xuất và trình bày pitch Problem Card #2 (Tự động hóa tổng hợp mốc thời gian và IoC để viết báo cáo sự cố an ninh mạng) — ý tưởng được nhóm MH2T chọn làm bài toán chung của cả nhóm.
- Phụ trách chính khâu kiểm chứng thực tế (CP4): Phối hợp cùng Lê Quang Huy thiết lập Assumption Map và trực tiếp phỏng vấn Kỹ sư Incident Response theo phương pháp The Mom Test.
- Trực tiếp vẽ sơ đồ quy trình Before (40 phút) và After (10 phút) chi tiết từng bước có cơ chế Human-in-the-loop.
- Soạn thảo Problem Statement v0 và phối hợp cùng Nhóm trưởng Nguyễn Hoàng Tùng hoàn thiện Problem Statement v1.

**Đóng góp cụ thể** (mình đã làm gì, ra sản phẩm gì):

- Bảo vệ thành công bài toán viết báo cáo sự cố trước các câu hỏi phản biện của Minh, Huy và Hoàng Tùng; đưa ra giải pháp Locked Schema và On-premise LLM để giải quyết triệt để nỗi lo ảo giác dữ liệu và rò rỉ thông tin.
- Hoàn thành 2 Interview Snapshots trong `group_report.md` với các trích dẫn câu nói và bài học hành vi thực tế.
- Đóng góp vào bảng so sánh 4 mức No AI / Rule / Workflow / Agent để bảo vệ mức chọn Workflow.
- Cùng nhóm chốt quyết định Go với pilot 2 tuần trên sự cố Low/Medium.

**Bằng chứng** (phần nào trong `group_report.md`, file nào trong `report/assets/`, commit nào):

- Đề cử candidate #2 trong bảng pitch mục 2.1 của `group_report.md`.
- Mục 3.1 (Assumption Map) và mục 3.2 (Kiểm chứng The Mom Test) trong `group_report.md`.
- Sơ đồ quy trình mục 4.1-4.2 và Problem Statement v0 (mục 5) trong `group_report.md`.
- Phần đánh giá 4 rủi ro và quyết định Go (mục 8) trong `group_report.md`.

**Điều mình học được từ phần nhóm:**

- Thấm thía sự khác biệt giữa tư duy "Solution-first" (chưa hiểu nỗi đau đã đòi làm Agent tự trị) và "Problem-first" (đi từ sự kiệt sức của kỹ sư khi gõ báo cáo thủ công lúc 2h sáng).
- Học được cách phỏng vấn khách hàng theo The Mom Test: hỏi về sự việc cụ thể và hành vi trong quá khứ mang lại giá trị kiểm chứng cao hơn gấp nhiều lần so với việc hỏi những câu hỏi giả định trong tương lai.

---

### NguyenHoangTung-2A202603481

**Phần việc phụ trách:**

- Nhóm trưởng, điều phối tiến trình buổi lab của nhóm MH2T, phân công nhiệm vụ và kiểm soát thời gian.
- Trình bày pitch Problem Card và đóng góp phản biện chính cho các bài toán của Minh, Huy và Văn Tùng.
- Phối hợp cùng bạn Nguyễn Văn Tùng hoàn thiện sơ đồ quy trình tương lai và kiểm tra ranh giới an toàn (Boundary).
- Chịu trách nhiệm chính hoàn thiện Problem Statement v1 kèm 4 tiêu chí eval và tổng kết đánh giá 4 rủi ro.

**Đóng góp cụ thể** (mình đã làm gì, ra sản phẩm gì):

- Đặt câu hỏi phản biện then chốt giúp bạn Nguyễn Văn Tùng bổ sung cơ chế khóa cứng dữ liệu kỹ thuật (Locked Schema) để chống ảo giác (hallucination).
- Cùng nhóm hoàn thành cây OST rút gọn (loại bỏ triệt để các solution trá hình).
- Xây dựng bảng so sánh 4 mức độ can thiệp AI và thiết lập các tiêu chí eval định lượng trong Problem Statement v1.
- Chốt quyết định Go kèm phạm vi pilot và ngưỡng dừng (Stopping Threshold) cụ thể.

**Bằng chứng** (phần nào trong `group_report.md`, file nào trong `report/assets/`, commit nào):

- Đề cử candidate trong bảng pitch mục 2.1 của `group_report.md`.
- Sơ đồ cây OST mục 2.3 và bảng chấm điểm mục 2.4 của `group_report.md`.
- Mục 6.2 (So sánh 4 mức can thiệp) và Mục 7 (Problem Statement v1 + eval) trong `group_report.md`.
- Mục 8 (Đánh giá 4 rủi ro và quyết định Go) trong `group_report.md`.

**Điều mình học được từ phần nhóm:**

- Nhận thức rõ ràng rằng trong an ninh mạng, việc giữ bí mật dữ liệu nội bộ (Data Privacy) và tính chính xác tuyệt đối của chứng cứ pháp lý quan trọng hơn việc chạy theo các công nghệ AI phức tạp.
- Hiểu được giá trị của việc đặt ra ranh giới (Boundary): AI chỉ nên đóng vai trò trợ lực (Augmentation) cho con người ở khâu soạn thảo văn bản, còn dữ liệu kỹ thuật và quyền phê duyệt cuối cùng bắt buộc phải thuộc về chuyên gia.
