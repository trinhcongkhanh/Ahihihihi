# Báo cáo kiểm tra template báo cáo thực tập FCAJ

- **Ngày kiểm tra:** 15/11/2026
- **Đối chiếu với:** `FCAJ-checklist-bao-cao-workshop.md`
- **Phạm vi đã đọc:** toàn bộ 62 file trong `content/` (bản Anh và bản Việt), `config.toml`, `layouts/`, workflow deploy, và các ảnh đang được dùng (avatar, 3 ảnh event, 3 ảnh chụp bài blog, sơ đồ blog).
- **Chưa làm:** không build Hugo và không mở các link Facebook / link tài liệu (để không ghi hay gửi gì ra ngoài). Link chỉ được kiểm tra bằng mắt.
- **Cam kết:** không sửa file nào. File duy nhất được tạo là báo cáo này.

Ký hiệu mức độ: 🔴 nghiêm trọng (mất điều kiện cứng hoặc 0 điểm) · 🟠 quan trọng (sai thông tin, dễ bị trừ điểm) · 🟡 nhỏ (câu chữ, trình bày).

---

## 1. Kết luận nhanh

| Phần | Trạng thái | Vấn đề lớn nhất |
|---|---|---|
| Thông tin sinh viên | Đủ 8 mục, còn lỗi nhỏ | "Vị trí thực tập" đang ghi tên chương trình; mã lớp theo năm 2025 |
| Worklog | Đủ 12 tuần, nhiều điểm bất hợp lý | 9 dòng ghi ngày trong tương lai; tuần 12 ghi sai thứ và điền "Day 1" vào ô Date |
| Proposal | 🔴 Trống | Chỉ có 1 câu, thiếu cả 7 mục |
| Blogs | Đủ 3 bài, có link và ảnh | Câu mở đầu Blog 1 bản Việt sai nghĩa; nguồn tham khảo Blog 2 trỏ về trang chủ |
| Events | 🔴 Chỉ đạt 2/3 | Event 3 không có ngày, không có ảnh check-in; Event 2 ảnh không rõ mặt |
| Workshop | 🔴 Trống | 4 trang lab giống hệt nhau, thiếu cả 7 mục, không có Cost và Demo |
| Self-evaluation | Thiếu nhận xét | Có mức chọn nhưng chưa có nhận xét cụ thể cho từng tiêu chí |
| Sharing and Feedback | Gần đủ | Thiếu "mức độ hài lòng"; tự ghi là "worklog hằng tuần" |
| Kỹ thuật / deploy | 🟠 | Toàn bộ thay đổi chưa commit; remote git vẫn là repo template gốc |

**Ba việc sẽ quyết định có được mộc hay không:** Workshop (trống), Proposal (trống), Event 3 (chưa hợp lệ).

---

## 2. Đối chiếu với checklist

### 2.1 Sáu điều kiện cứng (mục 1 của checklist)

| Điều kiện | Kết quả | Ghi chú |
|---|---|---|
| Workshop cá nhân đạt chuẩn | 🔴 Chưa | Xem mục 3.5 |
| Báo cáo đầy đủ theo template | 🔴 Chưa | Proposal và Workshop trống |
| Thực tập tối thiểu 3 tháng | Đạt trên giấy | 14/09/2026 – 14/12/2026 là đúng 3 tháng, nhưng worklog dừng ở 29/11 (xem 3.2) |
| Lên văn phòng ≥ 10 buổi | Không có minh chứng | Trong báo cáo không có chỗ nào ghi số buổi lên văn phòng. Cần tự đếm lại. |
| ≥ 3 sự kiện, ảnh check-in rõ mặt | 🔴 1/3 chắc chắn | Event 1 đạt. Event 2 ảnh tập thể. Event 3 không có ảnh chụp. |
| ≥ 3 bài blog đã đăng | Đạt 3/3 | Có link và ảnh chụp cả 3 bài |

### 2.2 Các lỗi 0 điểm (mục 2 của checklist)

| Yêu cầu | Kết quả |
|---|---|
| Có phần Cost trong báo cáo | 🔴 Không có ở Proposal lẫn Workshop |
| Có link demo / video | 🔴 Không có |
| Sơ đồ kiến trúc tự vẽ | 🔴 Proposal và Workshop chưa có sơ đồ nào |

### 2.3 Yêu cầu chung của template (mục 4)

| Yêu cầu | Kết quả |
|---|---|
| Dùng template FCAJ | Đạt |
| Có mục lục, navigation | Đạt (menu trái + mục lục trang chủ) |
| Song ngữ Việt – Anh | Đạt về số file (31 cặp), nhưng nhiều chỗ hai bản không khớp nhau (xem mục 4) |
| Code trong code block có highlight | Blog 3 có khối `bash` đúng chuẩn. Workshop chưa có code nào. |
| Ảnh rõ, có chú thích | Ảnh blog không có chú thích; chú thích ảnh Event 2 và Event 3 sai nội dung |

---

## 3. Chi tiết từng phần

### 3.1 Trang chủ – Thông tin sinh viên (`content/_index.md`, `content/_index.vi.md`)

Đủ 8 mục bắt buộc, có ảnh đại diện rõ mặt.

| Mức | Dòng | Vấn đề |
|---|---|---|
| 🟠 | 26 | **"Vị trí thực tập: Workforce Bootcamp - First Cloud AI Journey"** là tên chương trình, không phải vị trí. Ô này nên là một chức danh (ví dụ Cloud Engineer Intern). |
| 🟠 | 22 | **Lớp "AWS082025"** mang nghĩa tháng 08/2025, trong khi kỳ thực tập là 09–12/2026. Cần kiểm tra lại mã lớp. |
| 🟡 | 24 | Bản Anh ghi "Amazon Web Services Viet Nam", bản Việt ghi "Công ty TNHH Amazon Web Services Viet Nam". Hai bản không cùng tên pháp nhân, và bản Việt viết "Viet Nam" không dấu. |
| 🟡 | 30 | Alt text ảnh vẫn là chữ mẫu: "Your profile picture" / "Ảnh đại diện của bạn". |
| 🟡 | 36 (EN) | Mục lục ghi "BlogsPosted" dính liền, trong khi tiêu đề trang là "Blogs Posted". |
| 🟡 | 39 (EN) | Mục lục ghi "Self-evaluation", tiêu đề trang lại là "Self-Assessment". |
| 🟡 | 34–35 (VI) | Mục lục ghi "Worklog", "Proposal"; tiêu đề trang lại là "Nhật ký công việc", "Bản đề xuất". |
| 🟡 | — | Tên chương trình không thống nhất trong toàn site: "First Cloud AI Journey" (trang chủ, footer), "AWS First Cloud Journey (Workforce Bootcamp)" (trang Events), "FCAJ" (hashtag). |

### 3.2 Worklog (`content/1-Worklog/`)

Đủ 12 tuần, 53 dòng, mỗi dòng có ngày bắt đầu, ngày hoàn thành và link tham khảo. Mỗi tuần có mục kết quả đạt được.

#### a) Lỗi về ngày tháng

| Mức | Vị trí | Vấn đề |
|---|---|---|
| 🔴 | Tuần 10 dòng 21, toàn bộ tuần 11, toàn bộ tuần 12 | **9 dòng ghi ngày trong tương lai** (16/11 → 29/11/2026) nhưng viết ở thì quá khứ, kèm kết quả cụ thể như "Reduced projected monthly cost by 25%", "Identified 3 high-risk issues". Hôm nay mới là 15/11. Đây là dấu hiệu worklog viết trước, người chấm rất dễ thấy. |
| 🔴 | Tuần 12, dòng 17–19 | **Ghi sai thứ.** Cột đầu ghi Monday / Tuesday / Wednesday (Thứ Hai / Ba / Tư) nhưng ngày thực tế là 24/11 = thứ Ba, 26/11 = thứ Năm, 29/11 = Chủ nhật. |
| 🔴 | Tuần 12 EN, dòng 17–19 | **Ô "Date" điền "Day 1", "Day 2", "Day 3"** thay vì ngày tháng (`- **Date:** Day 1`). Bản Việt cùng chỗ đó lại là `- **Kế hoạch:** Ngày 1`, tức ô Kế hoạch chứa số thứ tự ngày chứ không phải kế hoạch. |
| 🟠 | Tuần 4–12 | **"Tuần" không phải tuần lịch.** Tuần 4 bắt đầu Chủ nhật 04/10, tuần 5 bắt đầu thứ Bảy 10/10, tuần 7 bắt đầu thứ Sáu 23/10, tuần 9 bắt đầu thứ Năm 05/11, tuần 12 bắt đầu thứ Ba 24/11. Mỗi "tuần" chỉ dài khoảng 6 ngày, nên 12 tuần chỉ phủ 76 ngày (15/09 → 29/11), chưa tới 11 tuần lịch. |
| 🟠 | Toàn bộ | **Không khớp thời gian thực tập ở trang chủ.** Trang chủ ghi 14/09 – 14/12/2026. Worklog bắt đầu 15/09 và kết thúc 29/11, bỏ trống 15 ngày cuối (30/11 – 14/12). |
| 🟠 | Toàn bộ | **15/53 dòng rơi vào thứ Bảy hoặc Chủ nhật** (ví dụ 20/09, 27/09, 04/10, 18/10, 25/10, 01/11, 15/11, 29/11). Nếu thực tế không làm cuối tuần thì các ngày này sai. |
| 🟠 | Tuần 1, 2, 12 | Chỉ có 3 dòng mỗi tuần; tuần 3 có 4 dòng. Checklist yêu cầu "Daily Worklog ghi đều". |
| 🟡 | Mọi tuần | Ngày bắt đầu luôn bằng ngày hoàn thành ở cả 53 dòng, nên hai cột này không mang thêm thông tin. |
| 🟡 | Mọi tuần (VI) | Tiêu đề cột là "Thứ" nhưng giá trị là "Ngày 1, Ngày 2…" (trừ tuần 12 ghi "Thứ Hai…"). |

#### b) Lỗi về khuôn mẫu, không đồng nhất giữa các tuần

| Mức | Vị trí | Vấn đề |
|---|---|---|
| 🟠 | Tuần 2, tuần 12 | Hai tuần này dùng khuôn khác 10 tuần còn lại: không có dòng "Plan / Kế hoạch" thật, có thêm dòng "Result / Kết quả". Bản Anh ghi "Focus:" còn 10 tuần kia ghi "Main Objective:". |
| 🟠 | Tuần 12 VI, dòng 12 | "Mục tiêu chính: Vận hành xuất sắc, Bảo mật, Tin cậy, Hiệu năng, và Tối ưu chi phí (5 Trụ cột)" là một danh sách, không phải mục tiêu. |
| 🟠 | Tuần 12 dòng 12 so với Event 3 dòng 22 | **Tuần 12 ghi "5 Trụ cột", Event 3 ghi "6 Pillars".** AWS Well-Architected Framework có 6 trụ cột; tuần 12 thiếu Sustainability. |
| 🟡 | Tuần 12 | Phần kết quả chỉ có 2 gạch đầu dòng và dùng tiêu đề "Key points learned / Các điểm chính đã học", trong khi 11 tuần kia dùng "Key takeaways / Điểm cốt lõi rút ra" với 3 ý in đậm. |
| 🟡 | Tuần 12, dòng 24 | Kết quả nhắc "AWS Cost Explorer" và "Reserved Instances" nhưng bảng công việc không có việc nào liên quan. |

#### c) Nội dung bất hợp lý

| Mức | Vị trí | Vấn đề |
|---|---|---|
| 🔴 | Tuần 12, dòng 17, 26, 33 | Ghi đã làm Well-Architected Review cho "our final project" và "Delivering a production-ready, well-documented cloud architecture". Trong khi đó trang Proposal và Workshop đang trống. Hai phần mâu thuẫn trực tiếp. |
| 🟠 | Tuần 12 EN dòng 19 | "purchased Savings Plans" nghĩa là đã mua cam kết chi tiêu 1–3 năm bằng tiền thật. Bản Việt ghi "cấu hình Savings Plans". Hai bản khác nghĩa, và việc thực tập sinh mua Savings Plans là khó tin. |
| 🟠 | Toàn bộ | **Worklog không ghi bất kỳ hoạt động nào ngoài học dịch vụ.** Không có dòng nào về 3 sự kiện (26/09, 02/10), viết 3 bài blog, làm proposal, làm workshop, họp nhóm, lên văn phòng. Blog 3 (AWS Backup Vault Lock) và Blog 2 (FinOps Agent) không xuất hiện trong tuần nào. |
| 🟠 | Trang mục lục Worklog, dòng 9 | Giới thiệu là ghi "challenges faced / thử thách", nhưng không tuần nào ghi khó khăn hay lỗi đã gặp. Checklist mục 3 và 7.6 yêu cầu ghi lỗi kỹ thuật và cách xử lý. |
| 🟡 | Thứ tự chủ đề | Tuần 2 học Firewall Manager, tuần 3 chia sẻ VPC subnet qua RAM, tuần 4 gắn Cognito vào API Gateway và Lambda; nhưng EC2/Lambda mới học ở tuần 6 và VPC/API Gateway ở tuần 7. Trình tự dùng trước, học sau này dễ bị hỏi. |
| 🟡 | Tuần 9 | Chủ đề lặp lại CloudFormation đã học ở tuần 8. |
| 🟡 | Tuần 3, dòng 24 | "Route 53 rules" nên là "Route 53 Resolver rules". |

#### d) Tài liệu tham khảo

| Mức | Vị trí | Vấn đề |
|---|---|---|
| 🟠 | Mọi tuần | Trong mỗi tuần, mọi ngày dùng lại đúng 2 link giống nhau (tuần 12 là 4 link). Checklist yêu cầu "mỗi việc gắn với nguồn trích dẫn cụ thể". |
| 🟠 | Tuần 1, 2, 3, 12 | Dùng **link AWS Console** (`console.aws.amazon.com/...`) làm tài liệu tham khảo. Đây là trang đăng nhập, không phải tài liệu. |
| 🟠 | Nhiều dòng | Link không khớp nội dung ngày đó: tuần 1 ngày 1 (Regions, AZ) dẫn tài liệu IAM; tuần 6 ngày 3 (Lightsail) không có link Lightsail; tuần 7 ngày 4 (API Gateway) không có link API Gateway; tuần 9 ngày 2–4 (Auto Scaling, CloudFormation) không có link tương ứng; tuần 10 (CodeDeploy, GitHub Actions) cũng vậy. |

#### e) Chính tả

| Mức | Vị trí | Vấn đề |
|---|---|---|
| 🟡 | Tuần 5 EN, dòng 19 | "high- severity" thừa dấu cách sau gạch nối. |
| 🟡 | Mọi tuần | Tiêu đề "Tasks to be carried out this week / Các công việc cần triển khai" là thì tương lai, nội dung bên dưới là việc đã làm. |

### 3.3 Proposal (`content/2-Proposal/`) 🔴

Toàn trang chỉ có một câu. Thiếu cả 7 mục: tổng quan bài toán, mục tiêu và phạm vi, vấn đề cần giải quyết, kiến trúc sơ bộ, kế hoạch và timeline, dự toán chi phí, rủi ro.

| Mức | Vị trí | Vấn đề |
|---|---|---|
| 🟠 | VI dòng 9 | "dự án **tốt nghiệp** cuối khóa" là sai. Đây là project thực tập, không phải đồ án tốt nghiệp. Bản Anh ghi "final capstone project". |
| 🟡 | `static/images/2-Proposal/` | Còn 2 ảnh kiến trúc của bài mẫu, không phải của anh. |

### 3.4 Blogs (`content/3-BlogsPosted/`)

Đủ 3 bài song ngữ. Cả 3 bài đều có link bài đăng và ảnh chụp hiện tên "Trịnh Công Khanh" trong nhóm AWS Study Group VN. Chủ đề đúng gợi ý của checklist.

| Mức | Vị trí | Vấn đề |
|---|---|---|
| 🟠 | Blog 1 VI dòng 14; trang danh sách VI dòng 12 | **Câu mở đầu sai nghĩa.** Bản Việt: "Bảo mật chủ yếu là chuyện phân quyền IAM và đóng bớt port." Bản Anh: "Security is *often thought of* mainly as…". Bản Việt thiếu ý "thường bị nghĩ là", nên thành khẳng định ngược với nội dung bài. Ảnh chụp cho thấy bài đã đăng trên Facebook cũng mang câu này. |
| 🟠 | Blog 2, dòng 103–107 | **5 nguồn tham khảo đều trỏ về trang chủ**, không phải bài cụ thể: `aws.amazon.com/new/`, `aws.amazon.com/blogs/aws-cloud-financial-management/` (dùng cho 2 tiêu đề khác nhau), `aws.amazon.com/aws-cost-management/`, `infoq.com`. Người đọc không kiểm chứng được mốc "public preview ngày 09/06/2026" nêu trong bài. |
| 🟠 | Blog 1, ảnh `architecture.jpg` | Sơ đồ không dùng AWS Architecture Icons và có dáng sơ đồ sinh tự động. Quy tắc khóa điểm về sơ đồ GenAI áp cho Proposal/Workshop, nhưng nên chuẩn bị giải thích nếu bị hỏi. |
| 🟠 | Cả 3 bài, bản Anh | Sơ đồ kiến trúc trên trang tiếng Anh có nhãn tiếng Việt. Ảnh chụp bài đăng cũng là tiếng Việt (điều này chấp nhận được), nhưng sơ đồ thì nên có bản Anh. |
| 🟡 | Cả 3 bài | Không ghi ngày đăng bài. Ảnh chụp chỉ hiện "6 giờ", "1 phút", "9 giờ". |
| 🟡 | Cả 3 bài | Tiêu đề trong menu chỉ là "Blog 1", "Blog 2", "Blog 3", không cho biết chủ đề. |
| 🟡 | Blog 2 | Mục "CONCLUSION / KẾT LUẬN" không đánh số, trong khi các mục khác đánh số 1–6. Blog 3 đánh số "7. CONCLUSION". |
| 🟡 | Hashtag | Blog 1 có `#FCAJ`, Blog 2 dùng `#AWSStudyGroup` và không có `#FCAJ`, Blog 3 không có hashtag nào. |
| 🟡 | Blog 3 | Ảnh rộng 900, hai bài kia 700. Tiêu đề dùng dấu "-" còn Blog 1 dùng "–". |
| 🟡 | Link bài đăng | Em chưa mở link. Nếu nhóm Facebook là nhóm kín, người chấm không phải thành viên sẽ không xem được. |

### 3.5 Events (`content/4-EventParticipated/`)

Bảng 7 thông tin bắt buộc:

| Thông tin | Event 1 | Event 2 | Event 3 |
|---|---|---|---|
| Tên sự kiện | Có | Có | Chỉ có ở tiêu đề, không có dòng "Event Name" |
| Thời gian | 26/09/2026 (không có giờ) | 02/10/2026 (không có giờ) | 🔴 **Không có ngày**, chỉ có "Full Day (08:30 - 17:30)" |
| Địa điểm | Bitexco Tower | Bitexco Tower | "AWS Training Lab", ba chỗ ghi ba kiểu |
| Vai trò | Student | Student | Security & Cloud Lead |
| Nội dung chính tiếp thu | Có | Có nhưng rất mỏng | Có, chi tiết |
| Ảnh check-in rõ mặt | Đạt | 🔴 Không rõ mặt | 🔴 Không có ảnh chụp |
| Bài học / đóng góp | Có | Mỏng | Có |

#### Event 1 – đạt

Ảnh đứng cạnh standee, thấy rõ mặt; standee ghi 26.09.2026 và Bitexco Financial Tower, khớp nội dung trang (26/09/2026 là thứ Bảy).

| Mức | Vị trí | Vấn đề |
|---|---|---|
| 🟡 | Dòng 23, 30, 41 | Hai câu in đậm được lặp lại nguyên văn trong khối trích dẫn cuối trang, đặt trong ngoặc kép như lời người khác nói, nhưng đó là câu của chính anh. |
| 🟡 | Dòng 17 | "Core Learning: Practical AI Agent Mindset" chỉ là một cụm từ. |
| 🟡 | Dòng 30 | "fast-track career acceleration" bị lặp nghĩa; bản Việt "cơ hội fast-track tăng tốc sự nghiệp" cũng vậy. |

#### Event 2 – chưa chắc đạt

| Mức | Vị trí | Vấn đề |
|---|---|---|
| 🔴 | Ảnh `event2.jpg` | Ảnh tập thể vài trăm người, không thể nhận ra anh. Alt text lại ghi "Check-in photo with visible face". Cần thêm ảnh cá nhân rõ mặt. |
| 🟠 | Dòng 11, 17, 25 | **Cùng một câu lặp 3 lần** ("Developing systems thinking and mastering technological architecture…"): ở phần mô tả, ở "Core Learning" và ở gạch đầu dòng. Câu "Renaissance Developer" cũng lặp 2 lần. Thực chất trang chỉ có 2 ý. |
| 🟠 | Dòng 11 | Phần mô tả sự kiện không mô tả sự kiện: không nói ai tổ chức, ai trình bày, nội dung gồm gì. |
| 🟡 | Dòng 32 | Chú thích ảnh ghi "Community Workshop / Hội thảo Cộng đồng", không khớp tên sự kiện. |
| 🟡 | Dòng 34 | Ngoặc kép lồng ngoặc kép: `"…resilient "Renaissance Developer" in…"`. |
| 🟡 | Dòng 26 | Bản Anh "end-to-end engineering capabilities", bản Việt "năng lực giải quyết vấn đề". Hai bản khác ý. |

#### Event 3 – chưa hợp lệ

| Mức | Vị trí | Vấn đề |
|---|---|---|
| 🔴 | Dòng 13; trang danh sách dòng 36 | **Ô "Date & Time / Thời gian" không có ngày tháng năm**, chỉ ghi "Full Day (08:30 - 17:30)". Không ai biết sự kiện diễn ra ngày nào. |
| 🔴 | Dòng 76 | **Không có ảnh check-in.** File `event3.svg` là banner tự vẽ, không phải ảnh chụp. Checklist ghi rõ ảnh check-in "không thể làm bù vào phút cuối". |
| 🟠 | Dòng 76–80 | Alt text ghi "Banner", chú thích ghi "System Architecture Blueprint / Sơ đồ Kiến trúc Hệ thống", nhưng hình không phải sơ đồ kiến trúc. Mục lại tên là "Some event photos". |
| 🟠 | Địa điểm | Ba chỗ ghi ba kiểu: EN "AWS Training Lab – Engineering Hub **& Virtual**"; VI "AWS Training Lab – Trung tâm Hợp tác Kỹ thuật" (mất chữ Virtual); trong banner ghi "BITEXCO TOWER". |
| 🟠 | Tên sự kiện | Bản Anh: "AWS GenAI Buildathon & Cloud Immersion Day". Bản Việt và phần mô tả tiếng Anh: "AWS Cloud Immersion & GenAI Buildathon". Thứ tự tên bị đảo. |
| 🟠 | Dòng 70 | "Unifying 12 weeks of modular hands-on labs" ngụ ý sự kiện diễn ra sau tuần 12, tức sau 29/11/2026. Hôm nay là 15/11. Danh sách dịch vụ có **RDS**, nhưng worklog không tuần nào học RDS. |
| 🟠 | Dòng 11 | "internship at Amazon Web Services" và "elite technical proving ground", "battle-tested deliverable": giọng văn quảng cáo, khác hẳn Event 1–2 và worklog. |
| 🟠 | Bản Anh so với bản Việt | Nhiều ý không khớp: dòng 33 (EN "IAM boundaries, latency budgets" / VI "tối ưu cấu hình trước khi ghép nối hệ thống AI"); dòng 44 (EN "profiling Lambda cold starts" / VI "chạy thử tải nhẹ kiểm tra độ trễ"); dòng 56 (EN "S3 prefixes and Bedrock invoke models" / VI "S3 ARN và Lambda function"); dòng 57 (EN "Zero Hardcoded Credentials" / VI "Bảo vệ biến môi trường"). |
| 🟠 | VI dòng 58 | "Mã hóa đầu cuối" là sai thuật ngữ. SSE-KMS là mã hóa dữ liệu lưu trữ (at rest), không phải end-to-end. Bản Anh ghi đúng là "Data Encryption". |
| 🟡 | Dòng 80 | Câu trích dẫn cuối trang không ghi của ai. |

#### Trang danh sách Events

| Mức | Vị trí | Vấn đề |
|---|---|---|
| 🟡 | EN | Trang danh sách dùng "Location" và "Role"; trang chi tiết dùng "Venue" và "Participation Role". |
| 🟡 | VI | Trang danh sách dùng "Vai trò trong sự kiện"; trang chi tiết dùng "Vai trò tham gia" / "Vai trò cá nhân". |
| 🟡 | `content/4-EventParticipated/image.png` | File thừa, không trang nào dùng. Đây là ảnh chụp màn hình bản blog cũ (AWS Secrets Manager). |

### 3.6 Workshop (`content/5-Workshop/`) 🔴

| Mức | Vị trí | Vấn đề |
|---|---|---|
| 🔴 | 4 trang Lab | **Bốn trang giống nhau từng chữ**, chỉ khác một từ ở tiêu đề (Infrastructure / Security / Networking / DevOps). Môi trường, 3 bước, kết quả, bài học đều trùng. Lab "DevOps" và lab "Networking" có cùng các bước "Configure security groups and NACLs". |
| 🔴 | Toàn bộ | Thiếu cả 7 mục bắt buộc: Overview, Prerequisite, Architecture & Data Flow, Step-by-step, Testing & Validation, Clean-up, Demo. |
| 🔴 | Toàn bộ | Không có Cost (0 điểm mục Trình bày), không có demo (0 điểm mục Demo), không có sơ đồ kiến trúc. |
| 🔴 | Toàn bộ | Không có nội dung cho các mục 7.3–7.6 của checklist: Security, Reliability, dự toán chi phí, khó khăn đã gặp, hướng phát triển. |
| 🟠 | Trang tổng quan, dòng 11 | Ghi "20+ hands-on labs" nhưng chỉ có 4 trang. Bản Việt "hơn 20+" bị lặp nghĩa. |
| 🟠 | Cấu trúc | Yêu cầu là **một workshop** theo một use-case thực tế dùng ≥ 3 dịch vụ. Hiện trạng là danh sách bài lab rời. |
| 🟡 | VI | Tiêu đề 4 lab không dịch ("Lab 1: Cloud Infrastructure"). |
| 🟡 | `static/images/5-Workshop/` | Còn khoảng 80 ảnh của bài mẫu S3 VPC Endpoint, không trang nào dùng. |

### 3.7 Self-evaluation (`content/6-Self-evaluation/`)

Đủ 8 tiêu chí, mỗi tiêu chí đã chọn một mức (5 Tốt, 3 Khá).

| Mức | Vị trí | Vấn đề |
|---|---|---|
| 🟠 | Cột "Description / Mô tả chi tiết" | **Chưa có nhận xét cụ thể.** Cột này chỉ định nghĩa tiêu chí, không nói anh đã làm gì để tự chấm mức đó. Checklist yêu cầu "viết nhận xét cụ thể". |
| 🟠 | Dòng 13, 19 | Tự chấm "Tốt" cho Kiến thức chuyên môn và Giải quyết vấn đề, trong khi Workshop và Proposal trống. |
| 🟠 | Dòng 20 | Mô tả tiêu chí "Đóng góp cho Workshop" là "Hiệu quả công việc, ý tưởng đổi mới, sự công nhận từ nhóm", không nhắc gì tới workshop. |
| 🟡 | Dòng 14 | Tự chấm "Khá" cho Khả năng tự học, nhưng trang Feedback lại nêu tự học là điều học được rõ nhất. |
| 🟡 | Tên tiêu chí EN | Không khớp bản Việt và checklist: "Ability to learn" (thiếu "nghiên cứu"), "Proactiveness" (thiếu "trong công việc"), "Professional knowledge & skills" (thừa "skills"). |
| 🟡 | Tiêu đề | Trang ghi "Self-Assessment", thư mục và mục lục ghi "Self-evaluation". |
| 🟡 | Dòng 15 | Thứ tự hai ý trong mô tả bị đảo giữa bản Anh và bản Việt. |

### 3.8 Sharing and Feedback (`content/7-Feedback/`)

| Yêu cầu | Kết quả |
|---|---|
| Cảm nhận về chương trình | Có |
| Mức độ hài lòng | 🟠 **Thiếu.** Có mục "Điều em hài lòng" nhưng không nêu mức độ (ví dụ rất hài lòng, 8/10). |
| Điểm cần cải thiện | Có, 3 ý cụ thể |
| Có giới thiệu cho bạn bè không, vì sao | Có, nhưng chỉ một câu nằm trong mục "Lời nhắn". Nên tách thành mục riêng. |

| Mức | Vị trí | Vấn đề |
|---|---|---|
| 🟠 | Dòng 17 | **"Weekly worklogs / Viết worklog hằng tuần".** Yêu cầu là Daily Worklog. Câu này tự xác nhận anh ghi theo tuần. |
| 🟠 | Dòng 11 | "After 12 weeks / Sau 12 tuần" trong khi hôm nay mới ở tuần 10, và thời gian thực tập là 3 tháng (13 tuần). |
| 🟡 | Xưng hô | Trang này xưng "em", toàn bộ worklog xưng "tôi". |
| 🟡 | EN | Dùng chính tả Anh-Anh ("realised", "organising"), các trang khác dùng Anh-Mỹ ("organizations", "optimizing"). |

---

## 4. Lỗi xuyên suốt nhiều trang

| Mức | Vấn đề |
|---|---|
| 🟠 | **Mọi trang đều có `date: 2024-01-01`** trong front matter (62 file). Đây là ngày mẫu của template, không phải ngày viết. |
| 🟠 | **Bản Anh và bản Việt không phải bản dịch của nhau** ở nhiều chỗ (Event 3, tuần 12, Blog 1, Event 2). Chi tiết ở từng mục phía trên. |
| 🟡 | Giọng văn không đồng đều: worklog tuần 1–11 và Feedback viết tự nhiên; Event 3 và phần "Key takeaways" của worklog dùng nhiều từ khoa trương. |
| 🟡 | Bản Việt dùng dấu gạch dài dính liền chữ ("bật máy—vì vậy"), không đúng quy ước tiếng Việt. |

---

## 5. Kỹ thuật, cấu hình, deploy

| Mức | Vị trí | Vấn đề |
|---|---|---|
| 🔴 | Git | **Toàn bộ nội dung chưa được commit.** Khoảng 70 file ở trạng thái đã sửa hoặc chưa theo dõi (Event 3, 4 trang Lab, ảnh blog, ảnh event, avatar). Nếu site đã deploy thì đang là bản cũ. |
| 🔴 | Git remote | `origin` vẫn là `github.com/thienluhoan/fcj-workshop-template` (repo template gốc), trong khi `baseURL` là `trinhcongkhanh.github.io/tck-Internship-report/`. Push bằng remote này sẽ không lên repo của anh. |
| 🟠 | `layouts/partials/custom-footer.html` | Còn mã Google Analytics `UA-158079754-2` của tác giả template. Lượt xem site của anh đang gửi về tài khoản của người khác. |
| 🟠 | `config.toml` dòng 33, 50 | Menu "AWS Study Group - Blog" trỏ tới `aws.amazon.com/blogs/architecture/`. Tên và link không khớp. |
| 🟠 | `config.toml` dòng 39 và footer | Link nhóm Facebook là `groups/awsstudygroupfcj`; footer mục "Team" lại trỏ `groups/660548818043427`. Cần kiểm tra cả hai có đúng nhóm "AWS Study Group VN" nơi anh đăng bài không. |
| 🟡 | `báo cáo.md` ở thư mục gốc | Bản rà soát cũ ngày 11/11, nhiều nội dung đã lỗi thời (ví dụ ghi thời gian thực tập là 2025, Feedback trống, Event 2 sai địa điểm). File chưa được git theo dõi; nếu `git add .` nó sẽ lên repo công khai. File báo cáo này cũng vậy. |
| 🟡 | `config.toml` dòng 18 | `description = ""` để trống. |
| 🟡 | `menu-footer.html` | "Last Updated" lấy ngày build, không phải ngày anh sửa nội dung. |
| 🟡 | File thừa | `static/images/avatar.png` (ảnh mẫu), `layouts/_shortcodes/ghcontributors.html` (trùng với bản trong `layouts/shortcodes/`). |
| 🟡 | Quyền riêng tư | Số điện thoại và email cá nhân hiển thị công khai trên trang chủ. Đây là mục bắt buộc, chỉ lưu ý để anh biết. |

Không phát hiện access key hay secret nào trong repo (đã dò mẫu `AKIA…`, `aws_secret`, private key).

---

## 6. Những điểm đã đạt

- Đủ 31 cặp file song ngữ, đường dẫn ảnh ở cả hai ngôn ngữ đều trỏ đúng file có thật.
- Thông tin sinh viên đủ 8 mục, ảnh đại diện rõ.
- Worklog tuần 3–11 có nội dung cụ thể, có thao tác thực hành, bản Anh và Việt khớp nhau.
- 3 bài blog có nội dung tốt, đúng chủ đề gợi ý, có link và ảnh chụp mang tên anh. Blog 3 có code block đúng chuẩn và nguồn tham khảo cụ thể.
- Event 1 đầy đủ, ảnh check-in hợp lệ và khớp ngày, địa điểm.
- Feedback viết chân thật, có góp ý cụ thể.

---

## 7. Thứ tự ưu tiên xử lý

1. **Workshop:** viết lại thành một workshop thật với đủ 7 mục, có sơ đồ tự vẽ, Cost, Security, demo.
2. **Proposal:** viết đủ 7 mục, có bảng dự toán chi phí và sơ đồ.
3. **Event 3:** bổ sung ngày tháng năm và ảnh check-in thật. Nếu không có ảnh thì cần một sự kiện khác thay thế.
4. **Event 2:** thêm ảnh cá nhân rõ mặt, viết lại nội dung cho hết lặp.
5. **Worklog:** xử lý 9 dòng ngày tương lai; sửa tuần 12 (thứ, ô Date, khuôn mẫu, 5/6 trụ cột); bổ sung phần còn thiếu đến 14/12; thêm dòng cho event, blog, workshop.
6. **Worklog references:** gắn link đúng nội dung từng ngày, bỏ link Console.
7. **Self-evaluation:** thêm nhận xét cụ thể cho 8 tiêu chí.
8. **Feedback:** thêm mức độ hài lòng, sửa "hằng tuần", tách mục giới thiệu cho bạn bè.
9. **Trang chủ:** sửa "Vị trí thực tập", kiểm tra mã lớp.
10. **Blog:** sửa câu mở đầu Blog 1 bản Việt, thay nguồn tham khảo Blog 2 bằng link cụ thể.
11. **Git và deploy:** đổi remote về repo của anh, commit, gỡ mã Google Analytics của người khác.
12. Các lỗi 🟡 còn lại.

## 8. Việc cần anh tự xác nhận (em không kiểm chứng được từ repo)

- Số buổi đã lên văn phòng (yêu cầu ≥ 10).
- Ngày diễn ra thật của Event 3 và có ảnh chụp tại chỗ hay không.
- Mã lớp "AWS082025" có đúng đợt không.
- Ba link Facebook của blog có mở được với người ngoài nhóm không.
- Mốc "AWS FinOps Agent public preview ngày 09/06/2026" trong Blog 2 lấy từ nguồn nào.
- Các ngày thứ Bảy, Chủ nhật trong worklog có thật sự làm việc không.
