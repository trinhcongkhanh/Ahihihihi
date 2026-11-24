---
title: "Worklog Tuần 5"
date: 2024-01-01
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---

### Mục tiêu tuần 5:

* **Chủ đề:** Amazon GuardDuty & Amazon Inspector
* **Mục tiêu chính:** Tìm hiểu cách AWS phát hiện hoạt động đáng ngờ trong tài khoản bằng GuardDuty, và cách Inspector tìm kiếm lỗ hổng phần mềm trong các máy chủ EC2, container images và Lambda functions

### Các công việc cần triển khai trong tuần này:
| Ngày | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| Ngày 1 | - **Kế hoạch:** Cơ bản về GuardDuty <br> - **Tác vụ chính:** Giới thiệu về GuardDuty <br> - **Hoạt động chi tiết:** Tìm hiểu những gì GuardDuty thực hiện và những nguồn dữ liệu mà nó phân tích: CloudTrail events, VPC Flow Logs và DNS logs. Bật GuardDuty trong tài khoản lab và khá bất ngờ khi không cần phải tự tay thiết lập các nguồn log đó | 05/10/2026 | 05/10/2026 | [Tài liệu hướng dẫn Amazon GuardDuty](https://docs.aws.amazon.com/guardduty/latest/ug/what-is-guardduty.html) <br> [Tài liệu hướng dẫn Amazon Inspector](https://docs.aws.amazon.com/inspector/latest/user/what-is-inspector.html) |
| Ngày 2 | - **Kế hoạch:** Phát hiện (Findings) <br> - **Tác vụ chính:** Đọc các Findings của GuardDuty <br> - **Hoạt động chi tiết:** Tạo các phát hiện mẫu (sample findings) và xem xét kỹ một vài phát hiện như `UnauthorizedAccess:EC2/SSHBruteForce` và `Recon:EC2/PortProbeUnprotectedPort`. Học cách đọc tên phát hiện, mức độ nghiêm trọng (severity) và tài nguyên bị ảnh hưởng | 06/10/2026 | 06/10/2026 | [Tài liệu hướng dẫn Amazon GuardDuty](https://docs.aws.amazon.com/guardduty/latest/ug/what-is-guardduty.html) <br> [Tài liệu hướng dẫn Amazon Inspector](https://docs.aws.amazon.com/inspector/latest/user/what-is-inspector.html) |
| Ngày 3 | - **Kế hoạch:** Cảnh báo & Tinh chỉnh <br> - **Tác vụ chính:** Cảnh báo EventBridge và Suppression Rules <br> - **Hoạt động chi tiết:** Tạo một EventBridge rule để gửi các phát hiện có mức độ nghiêm trọng cao về email thông qua SNS. Tìm hiểu suppression rules và danh sách IP tin cậy (trusted IP lists) để giảm nhiễu từ các hoạt động đã biết | 07/10/2026 | 07/10/2026 | [Tài liệu hướng dẫn Amazon GuardDuty](https://docs.aws.amazon.com/guardduty/latest/ug/what-is-guardduty.html) <br> [Tài liệu hướng dẫn Amazon Inspector](https://docs.aws.amazon.com/inspector/latest/user/what-is-inspector.html) |
| Ngày 4 | - **Kế hoạch:** Cơ bản về Inspector <br> - **Tác vụ chính:** Giới thiệu về Amazon Inspector <br> - **Hoạt động chi tiết:** Kích hoạt Inspector và tìm hiểu những gì nó quét: máy chủ EC2, ECR container images và Lambda functions. Chủ đích khởi tạo một máy chủ EC2 cũ để xem nó sẽ tìm thấy những lỗ hổng nào | 08/10/2026 | 08/10/2026 | [Tài liệu hướng dẫn Amazon GuardDuty](https://docs.aws.amazon.com/guardduty/latest/ug/what-is-guardduty.html) <br> [Tài liệu hướng dẫn Amazon Inspector](https://docs.aws.amazon.com/inspector/latest/user/what-is-inspector.html) |
| Ngày 5 | - **Kế hoạch:** Đánh giá Lỗ hổng <br> - **Tác vụ chính:** Các Findings của Inspector & So sánh <br> - **Hoạt động chi tiết:** Xem xét các phát hiện CVE, điểm rủi ro (risk score) của Inspector và các gợi ý khắc phục. Cập nhật các gói phần mềm (packages) trên máy chủ và kiểm tra xem các phát hiện đã được đóng lại hay chưa. So sánh trực tiếp GuardDuty và Inspector | 09/10/2026 | 09/10/2026 | [Tài liệu hướng dẫn Amazon GuardDuty](https://docs.aws.amazon.com/guardduty/latest/ug/what-is-guardduty.html) <br> [Tài liệu hướng dẫn Amazon Inspector](https://docs.aws.amazon.com/inspector/latest/user/what-is-inspector.html) |

### Kết quả đạt được tuần 5:

* **Amazon GuardDuty:** Phát hiện mối đe dọa không cần agent dựa trên CloudTrail, VPC Flow Logs và DNS logs (kèm bảo vệ mở rộng cho S3, EKS, RDS, Lambda)
* **Cảnh báo & Giảm nhiễu:** Chuyển tiếp cảnh báo mức độ cao qua EventBridge + SNS về email và lọc cảnh báo nhiễu bằng suppression rules / trusted IP lists
* **Amazon Inspector:** Tự động quét lỗ hổng CVE và độ phơi nhiễm mạng trên EC2, ECR images và Lambda kèm điểm rủi ro (risk score) để ưu tiên vá lỗi
* **GuardDuty vs. Inspector:** GuardDuty phát hiện các cuộc tấn công đang diễn ra; Inspector tìm kiếm điểm yếu phần mềm trước khi bị kẻ xấu khai thác

Dù cùng phục vụ mục tiêu bảo mật đám mây, hai dịch vụ này giải quyết hai mặt hoàn toàn khác nhau: **Inspector kiểm tra xem cánh cửa có đang mở khóa hay không, còn GuardDuty báo động khi có kẻ đang cố cạy cửa.** Thực hành khởi tạo một máy chủ EC2 cũ, nhìn thấy danh sách lỗi CVE mà Inspector phát hiện và chứng kiến các cảnh báo tự động đóng lại sau khi cập nhật gói phần mềm giúp tôi hiểu rõ giá trị của việc quét lỗ hổng liên tục kết hợp cảnh báo tự động qua EventBridge.

Điểm cốt lõi rút ra:

- **Phòng ngừa vs. Phát hiện:** Inspector giúp vá các lỗ hổng CVE trước khi bị tấn công, trong khi GuardDuty phát hiện hành vi tấn công tức thời như dò cổng hay brute-force SSH.
- **Giám sát không cần Agent:** GuardDuty tự động phân tích CloudTrail, VPC Flow Logs và DNS logs mà không cần cấu hình thu thập log thủ công.
- **Tự động hóa cảnh báo:** Kết nối GuardDuty và Inspector với EventBridge + SNS giúp đội ngũ nhận cảnh báo nghiêm trọng ngay lập tức thay vì phải kiểm tra console thủ công.
