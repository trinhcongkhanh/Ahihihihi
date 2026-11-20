# Báo cáo rà soát template so với yêu cầu bắt buộc

Ngày rà soát: 11/11/2026. Phạm vi: toàn bộ thư mục `content/` (bản tiếng Anh và tiếng Việt), `config.toml` và ảnh trong `static/images/`. Site build bằng Hugo 0.166 không báo lỗi; mọi ảnh được tham chiếu đều có file.

## 1. Tổng quan

| # | Phần | Trạng thái | Nhận xét ngắn |
|---|---|---|---|
| 0 | Song ngữ Anh – Việt | Đạt | Cả 30 trang đều có đủ `_index.md` và `_index.vi.md` |
| 1 | Thông tin sinh viên | Đạt, cần sửa 1 chỗ | Đủ 8 mục; thời gian thực tập lệch với worklog |
| 2 | Worklog | Đạt cơ bản, cần sửa | Đủ 12 tuần, có ngày, kết quả, references; còn vài điểm yếu |
| 3 | Proposal | **Chưa có nội dung** | Chỉ có 1 câu giới thiệu, thiếu cả 7 mục |
| 4 | Blogs | Đạt cơ bản, thiếu minh chứng | Đủ 3 bài; chưa có link bài đăng |
| 5 | Events | Đạt 2/3 | Event 3 thiếu ngày và ảnh check-in; Event 2 sai địa điểm |
| 6 | Workshop | **Chưa đạt** | 4 trang lab giống hệt nhau, thiếu cả 7 mục bắt buộc |
| 7 | Self-evaluation | Thiếu nhận xét | Đủ 8 tiêu chí và mức chọn; chưa có nhận xét cụ thể |
| 8 | Sharing and Feedback | **Chưa có nội dung** | Chỉ có 1 câu, thiếu cả 4 mục |

Ba phần còn trống hoàn toàn là Proposal, Workshop và Feedback.

## 2. Chi tiết từng phần

### 2.1. Thông tin sinh viên — `content/_index.md`, `content/_index.vi.md`

Đã có đủ: họ tên, số điện thoại, email, trường, chuyên ngành, công ty thực tập, vị trí thực tập, thời gian thực tập, kèm ảnh đại diện.

Cần sửa:

- **Thời gian thực tập ghi "12/08/2025 – 12/11/2025"**, trong khi worklog chạy 15/09/2026 – 29/11/2026 và các event diễn ra tháng 9–10/2026. Hai mốc này phải khớp nhau.
- Mã lớp "AWS082025" cũng theo năm 2025; kiểm tra lại cho đúng đợt.
- Alt text của ảnh vẫn là chữ mẫu ("Your profile picture" / "Ảnh đại diện của bạn"). Không ảnh hưởng điểm, nên đổi cho gọn.

### 2.2. Worklog — `content/1-Worklog/`

Đã có:

- Đủ Week 1 → Week 12, mỗi tuần có mục tiêu, bảng công việc theo ngày, kết quả đạt được và tài liệu tham khảo.
- Mọi dòng đã có Start Date và Completion Date (cùng ngày), từ 15/09/2026 đến 29/11/2026.
- Đúng cấu trúc bảng 5 cột của template.

Chưa ổn:

- **Số ngày ghi nhận không đều.** Tuần 1, 2, 12 chỉ có 3 ngày; tuần 3 có 4 ngày; các tuần còn lại 5 ngày. Tổng 53 dòng trên 76 ngày. Tiêu chí chấm là "ghi nhận đều đặn tiến độ hàng ngày".
- **References lặp lại.** Trong mỗi tuần, mọi ngày đều dùng lại cùng 2 link (tuần 12 là 4 link). Nên gắn tài liệu đúng với nội dung từng ngày.
- **Tuần 2 và tuần 12 lệch format.** Hai tuần này không có dòng "Plan / Kế hoạch" như 10 tuần kia. Tuần 12 còn ghi cột đầu là "Monday / Tuesday / Wednesday" và có dòng "Date: Day 1".
- **Tuần 12 sai thứ.** Nhãn là Thứ Hai / Ba / Tư nhưng ngày thực tế là thứ Ba 24/11, thứ Năm 26/11 và Chủ nhật 29/11.
- **Có ngày trong tương lai.** Tính đến 11/11/2026, các dòng từ 12/11 đến 29/11 (phần lớn tuần 10, toàn bộ tuần 11 và 12) đang mô tả việc đã hoàn thành kèm kết quả cụ thể, ví dụ "giảm 25% chi phí". Quy định yêu cầu worklog thể hiện đúng quá trình học thực tế; cần cập nhật lại nội dung các tuần này khi làm xong.
- Front matter của mọi trang vẫn để `date: 2024-01-01` của template. Không hiển thị ra ngoài, không bắt buộc sửa.

### 2.3. Proposal — `content/2-Proposal/`

Hiện chỉ có một câu: "Dưới đây là kiến trúc đề xuất và tiến độ cho dự án tốt nghiệp cuối khóa."

Thiếu toàn bộ 7 mục bắt buộc:

1. Tổng quan bài toán / giải pháp
2. Mục tiêu và phạm vi
3. Vấn đề cần giải quyết
4. Kiến trúc giải pháp sơ bộ
5. Kế hoạch và timeline thực hiện
6. Bảng dự toán ngân sách và chi phí
7. Rủi ro và phương án giảm thiểu

Lưu ý: `static/images/2-Proposal/` còn 2 ảnh kiến trúc của bài mẫu IoT Weather Platform, không thuộc đề tài của bạn.

### 2.4. Blogs — `content/3-BlogsPosted/`

Đã có:

- Đủ 3 bài, song ngữ: AWS Secrets Manager, Amazon Inspector, AWS FinOps Agent.
- Mỗi bài có ảnh chụp bài đăng trên nhóm AWS Study Group VN, sơ đồ kiến trúc và mục References.
- Chủ đề khớp với nội dung học trong worklog (tuần 4, 5, 11).

Chưa ổn:

- **Không có link tới bài đăng.** Minh chứng bắt buộc là "Link các bài Blog", nhưng trong cả 3 bài chỉ có link hashtag Facebook.
- **Ảnh chụp Blog 1 hiển thị người đăng là "Thành viên ẩn danh"**, nên ảnh không chứng minh được bài là của bạn. Link bài đăng càng cần thiết. Tôi chưa mở ảnh chụp của Blog 2 và Blog 3 để kiểm tra điểm này.
- **References của Blog 3 chỉ trỏ về trang chủ** (`aws.amazon.com/new/`, `infoq.com`, trang blog chung), không phải bài viết cụ thể.
- Mục menu "AWS Study Group - Blog" hiện trỏ tới AWS Architecture Blog, tên và link không còn khớp nhau.

### 2.5. Events — `content/4-EventParticipated/`

| Mục bắt buộc | Event 1 | Event 2 | Event 3 |
|---|---|---|---|
| Tên sự kiện | Có | Có | Có (ở tiêu đề) |
| Thời gian | 26/09/2026 | 02/10/2026 | **Thiếu ngày**, chỉ ghi giờ |
| Địa điểm | Bitexco Tower | **Sai** | "AWS Training Lab" |
| Vai trò | Student | Student | Security & Cloud Lead |
| Nội dung chính tiếp thu | Có | Có, khá mỏng | Có, chi tiết |
| Ảnh check-in rõ mặt | Có | Chưa chắc đạt | **Không có** |
| Bài học rút ra | Có | Có, khá mỏng | Có |

Cần sửa:

- **Event 2: địa điểm đang ghi "The Thinking Behind Building The Bot"**, là tên của Event 1 bị chép nhầm. Lỗi này có ở trang Event 2 và trang danh sách, cả hai ngôn ngữ.
- **Event 2: ảnh là ảnh tập thể vài trăm người**, khó nhận ra mặt bạn. Yêu cầu là "check-in rõ mặt"; nên thêm một ảnh cá nhân.
- **Event 3: ảnh minh chứng là file `event3.svg`**, một banner vẽ tay, không phải ảnh chụp. Cần thay bằng ảnh check-in thật và bổ sung ngày tổ chức.
- Event 2 có phần nội dung lặp lại cùng một câu ở ba chỗ (mô tả, nội dung chính, bài học).
- File `content/4-EventParticipated/image.png` không được trang nào dùng.

Event 1 đạt đầy đủ: ảnh đứng cạnh standee sự kiện, thấy rõ mặt, ngày trên standee khớp 26/09/2026.

### 2.6. Workshop — `content/5-Workshop/`

Hiện có trang tổng quan một câu ("Tài liệu chi tiết về hơn 20+ bài thực hành labs") và 4 trang Lab 1–4.

Vấn đề:

- **Bốn trang lab có nội dung giống hệt nhau**, chỉ khác một từ ở tiêu đề (Infrastructure / Security / Networking / DevOps). Môi trường, 3 bước thực hiện, kết quả và bài học đều trùng từng chữ.
- Trang tổng quan nói "20+ labs" nhưng chỉ có 4 trang.
- Không có ảnh chụp màn hình, lệnh hay cấu hình nào.

Thiếu cả 7 mục bắt buộc:

1. Overview của workshop
2. Prerequisite (tài khoản, công cụ, quyền hạn)
3. Kiến trúc chi tiết và luồng dữ liệu
4. Các bước triển khai step-by-step
5. Kiểm thử và đo lường qua Logs, Metrics, Alerts
6. Dọn dẹp tài nguyên
7. Minh chứng chạy thực tế (link demo hoặc video)

Lưu ý: `static/images/5-Workshop/` còn khoảng 80 ảnh của bài mẫu S3 VPC Endpoint, không còn trang nào dùng.

### 2.7. Self-evaluation — `content/6-Self-evaluation/`

Đã có đủ 8 tiêu chí đúng tên yêu cầu, mỗi tiêu chí chọn một mức (5 Tốt, 3 Khá).

Thiếu: **nhận xét cụ thể cho từng tiêu chí.** Cột "Mô tả chi tiết" hiện chỉ giải thích tiêu chí là gì, chưa nói bạn đã làm gì để tự chấm mức đó.

### 2.8. Sharing and Feedback — `content/7-Feedback/`

Hiện chỉ có một câu: "Phản hồi thu thập được trong quá trình thực tập."

Thiếu cả 4 mục:

1. Cảm nhận về chương trình thực tập FCAJ
2. Mức độ hài lòng
3. Những điểm cần cải thiện
4. Có giới thiệu chương trình cho bạn bè không, vì sao

## 3. Đối chiếu tiêu chí chấm Worklog / Blog (tối đa 1.0 điểm)

Điều kiện tiên quyết đã qua: có cả Blog và Daily Worklog, nên nhóm điểm này không bị 0.

| Tiêu chí | Hiện trạng | Rủi ro |
|---|---|---|
| Có tối thiểu 3 bài Blog | Đủ 3 bài | Thấp |
| Blog chia sẻ kiến thức đã học | Khớp nội dung worklog | Thấp |
| Blog tự viết, không sao chép | Tôi không kiểm chứng được từ repo | Cần link bài đăng làm minh chứng |
| Worklog ghi nhận đều đặn hàng ngày | 53 dòng / 76 ngày, có tuần chỉ 3 ngày | Trung bình |
| Dùng đúng template | Đúng bảng 5 cột; tuần 2 và 12 lệch format | Có thể mất tới 0.2 |
| Nội dung rõ, đúng chủ đề, có references | Rõ ràng; references lặp, Blog 3 link chung chung | Có thể mất tới 0.3 |

## 4. Việc cần làm, theo thứ tự ưu tiên

1. Viết Proposal đủ 7 mục.
2. Viết lại Workshop thành một bài lab thật với đủ 7 mục, có ảnh chụp và link demo.
3. Viết Sharing and Feedback đủ 4 mục.
4. Thêm link bài đăng thật cho 3 blog.
5. Event 3: thêm ngày và ảnh check-in thật. Event 2: sửa địa điểm, thêm ảnh rõ mặt.
6. Thêm nhận xét cụ thể cho 8 tiêu chí tự đánh giá.
7. Sửa thời gian thực tập ở trang chủ cho khớp worklog.
8. Worklog: thống nhất format tuần 2 và 12, sửa nhãn thứ ở tuần 12, đa dạng hóa references, cập nhật các tuần 10–12 theo việc đã làm thật.
9. Dọn file thừa: ảnh mẫu trong `static/images/2-Proposal/` và `static/images/5-Workshop/`, `content/4-EventParticipated/image.png`.
