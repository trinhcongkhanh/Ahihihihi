---
title: "Worklog Tuần 12"
date: 2024-01-01
weight: 12
chapter: false
pre: " <b> 1.12. </b> "
---

### Mục tiêu tuần 12:

* **Chủ đề:** AWS Key Management Service (KMS) & AWS CloudHSM
* **Mục tiêu chính:** Hiểu cách AWS tạo và bảo vệ các khóa mã hóa, và khi nào nên dùng dịch vụ KMS được quản lý hoặc CloudHSM chuyên dụng

### Các công việc cần triển khai trong tuần này:
| Ngày | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| Ngày 1 | - **Kế hoạch:** Cơ bản về KMS <br> - **Tác vụ chính:** Giới thiệu về AWS KMS <br> - **Hoạt động chi tiết:** Tìm hiểu KMS làm gì và ba loại khóa: AWS owned, AWS managed và customer managed. Tạo customer managed key đầu tiên của tôi | 23/11/2026 | 23/11/2026 | [Tài liệu hướng dẫn AWS KMS](https://docs.aws.amazon.com/kms/latest/developerguide/overview.html) <br> [Tài liệu hướng dẫn AWS CloudHSM](https://docs.aws.amazon.com/cloudhsm/latest/userguide/introduction.html) |
| Ngày 2 | - **Kế hoạch:** Sử dụng khóa <br> - **Tác vụ chính:** Mã hóa tài nguyên AWS <br> - **Hoạt động chi tiết:** Bật mã hóa cho một S3 bucket và một EBS volume bằng KMS key của chính tôi. Tìm hiểu ý tưởng cơ bản của envelope encryption: data key khóa dữ liệu, còn KMS key khóa data key | 24/11/2026 | 24/11/2026 | [Tài liệu hướng dẫn AWS KMS](https://docs.aws.amazon.com/kms/latest/developerguide/overview.html) <br> [Tài liệu hướng dẫn AWS CloudHSM](https://docs.aws.amazon.com/cloudhsm/latest/userguide/introduction.html) |
| Ngày 3 | - **Kế hoạch:** Kiểm soát truy cập <br> - **Tác vụ chính:** Key Policies & Rotation <br> - **Hoạt động chi tiết:** Chỉnh sửa key policy để chỉ một số users và roles nhất định được dùng khóa. Bật xoay vòng khóa tự động và kiểm tra CloudTrail để xem ai đã dùng khóa | 25/11/2026 | 25/11/2026 | [Tài liệu hướng dẫn AWS KMS](https://docs.aws.amazon.com/kms/latest/developerguide/overview.html) <br> [Tài liệu hướng dẫn AWS CloudHSM](https://docs.aws.amazon.com/cloudhsm/latest/userguide/introduction.html) |
| Ngày 4 | - **Kế hoạch:** CloudHSM <br> - **Tác vụ chính:** Giới thiệu về AWS CloudHSM <br> - **Hoạt động chi tiết:** Tìm hiểu rằng CloudHSM cung cấp một hardware security module chuyên dụng mà chỉ tài khoản của tôi kiểm soát. Đọc về các cluster trải trên nhiều Availability Zones và các vai trò người dùng HSM | 26/11/2026 | 26/11/2026 | [Tài liệu hướng dẫn AWS KMS](https://docs.aws.amazon.com/kms/latest/developerguide/overview.html) <br> [Tài liệu hướng dẫn AWS CloudHSM](https://docs.aws.amazon.com/cloudhsm/latest/userguide/introduction.html) |
| Ngày 5 | - **Kế hoạch:** Ôn tập <br> - **Tác vụ chính:** KMS vs. CloudHSM <br> - **Hoạt động chi tiết:** So sánh hai dịch vụ theo mức độ kiểm soát, chi phí và công sức. Tìm hiểu vì sao nên vô hiệu hóa khóa hoặc lên lịch xóa với thời gian chờ thay vì xóa ngay | 27/11/2026 | 27/11/2026 | [Tài liệu hướng dẫn AWS KMS](https://docs.aws.amazon.com/kms/latest/developerguide/overview.html) <br> [Tài liệu hướng dẫn AWS CloudHSM](https://docs.aws.amazon.com/cloudhsm/latest/userguide/introduction.html) |

### Kết quả đạt được tuần 12:

* **AWS KMS:** KMS là dịch vụ được quản lý để tạo và kiểm soát các khóa mã hóa. Khóa nằm bên trong KMS và được dùng để mã hóa dữ liệu trong các dịch vụ như S3, EBS, RDS và Secrets Manager
* **Các loại khóa:** AWS owned key và AWS managed key do AWS quản lý. Customer managed key cho tôi quyền kiểm soát policy, việc xoay vòng và việc xóa khóa
* **Envelope Encryption:** Thay vì gửi dữ liệu lớn đến KMS, một data key nhỏ mã hóa dữ liệu, và KMS key mã hóa data key đó
* **Bảo mật khóa:** Dùng key policy với đặc quyền tối thiểu, bật xoay vòng tự động, kiểm tra việc sử dụng khóa trong CloudTrail, và dùng thời gian chờ trước khi xóa khóa
* **AWS CloudHSM:** CloudHSM là thiết bị phần cứng chuyên dụng, single-tenant trong VPC của tôi. Tôi tự quản lý khóa và người dùng, và AWS không thể thấy các khóa
* **KMS vs. CloudHSM:** KMS dễ dùng và rẻ hơn trong hầu hết trường hợp. CloudHSM dành cho các quy định tuân thủ nghiêm ngặt hoặc khi công ty cần toàn quyền kiểm soát phần cứng

Trong tuần cuối, tôi học về thứ nằm bên dưới gần như mọi thứ tôi đã học trước đó: khóa mã hóa. S3, EBS, RDS và Secrets Manager đều phụ thuộc vào chúng, nhưng đến giờ tôi chưa từng xem các khóa thực sự đến từ đâu.

KMS hóa ra đơn giản hơn tôi nghĩ. Tôi tạo một khóa, quyết định ai được dùng nó, và AWS lo việc giữ nó an toàn. Envelope encryption là phần tôi mất nhiều thời gian nhất. Hình dung nó như "một chiếc chìa khóa nằm trong chiếc hộp bị khóa" giúp tôi hiểu ra: data key mở dữ liệu, còn KMS key mở chiếc hộp đựng data key.

CloudHSM cho cảm giác ngược lại. Nó cho nhiều quyền kiểm soát hơn, nhưng tôi cũng phải chịu nhiều trách nhiệm hơn. Nếu tôi làm mất thông tin đăng nhập HSM, không ai có thể khôi phục khóa cho tôi, kể cả AWS. Điều đó giúp tôi thấy rõ vì sao hầu hết dự án dùng KMS, và vì sao CloudHSM chủ yếu dành cho các công ty có quy định bảo mật nghiêm ngặt.

Các điểm chính đã học:

- KMS là gì và ba loại khóa
- Mã hóa S3 và EBS bằng customer managed key
- Ý tưởng cơ bản của envelope encryption
- Bảo vệ khóa bằng key policy, xoay vòng khóa và log CloudTrail
- CloudHSM là gì và khác KMS như thế nào
- Lựa chọn giữa KMS và CloudHSM dựa trên mức độ kiểm soát, chi phí và tuân thủ
