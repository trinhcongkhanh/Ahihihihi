---
title: "Worklog Tuần 9"
date: 2024-01-01
weight: 9
chapter: false
pre: " <b> 1.9. </b> "
---

### Mục tiêu tuần 9:

* **Chủ đề:** Amazon CloudWatch, AWS Auto Scaling, AWS CloudFormation & AWS Config
* **Mục tiêu chính:** Học cách giám sát tài nguyên, tự động co giãn (scale) chúng khi lưu lượng truy cập thay đổi, triển khai chúng bằng code, và theo dõi cấu hình của chúng

### Các công việc cần triển khai trong tuần này:
| Ngày | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| Ngày 1 | - **Kế hoạch:** Giám sát <br> - **Tác vụ chính:** Giới thiệu về CloudWatch <br> - **Hoạt động chi tiết:** Tìm hiểu về metrics, logs, alarms và dashboards. Tạo một cảnh báo (alarm) gửi email cho tôi khi mức CPU của máy chủ EC2 vượt quá 70% | 02/11/2026 | 02/11/2026 | [Tài liệu hướng dẫn Amazon CloudWatch](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/WhatIsCloudWatch.html) <br> [Tài liệu hướng dẫn AWS Config](https://docs.aws.amazon.com/config/latest/developerguide/WhatIsConfig.html) |
| Ngày 2 | - **Kế hoạch:** Co giãn (Scaling) <br> - **Tác vụ chính:** Giới thiệu về Auto Scaling <br> - **Hoạt động chi tiết:** Tạo một launch template và một Auto Scaling group với số lượng máy chủ tối thiểu (minimum), mong muốn (desired) và tối đa (maximum). Thêm một chính sách (policy) để giữ mức CPU trung bình quanh ngưỡng 50% | 03/11/2026 | 03/11/2026 | [Tài liệu hướng dẫn Amazon CloudWatch](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/WhatIsCloudWatch.html) <br> [Tài liệu hướng dẫn AWS Config](https://docs.aws.amazon.com/config/latest/developerguide/WhatIsConfig.html) |
| Ngày 3 | - **Kế hoạch:** Kiểm thử <br> - **Tác vụ chính:** Quan sát Auto Scaling hoạt động <br> - **Hoạt động chi tiết:** Tạo tải giả lập lên một máy chủ để đẩy CPU tăng cao và quan sát các máy chủ mới tự động được thêm vào. Chủ đích dừng một máy chủ và thấy Auto Scaling tự động thay thế nó | 04/11/2026 | 04/11/2026 | [Tài liệu hướng dẫn Amazon CloudWatch](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/WhatIsCloudWatch.html) <br> [Tài liệu hướng dẫn AWS Config](https://docs.aws.amazon.com/config/latest/developerguide/WhatIsConfig.html) |
| Ngày 4 | - **Kế hoạch:** Triển khai <br> - **Tác vụ chính:** Dùng CloudFormation cho thiết lập <br> - **Hoạt động chi tiết:** Viết một CloudFormation template cho Auto Scaling group và CloudWatch alarm, nhờ đó toàn bộ thiết lập có thể được tạo lại chỉ với một stack | 05/11/2026 | 05/11/2026 | [Tài liệu hướng dẫn Amazon CloudWatch](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/WhatIsCloudWatch.html) <br> [Tài liệu hướng dẫn AWS Config](https://docs.aws.amazon.com/config/latest/developerguide/WhatIsConfig.html) |
| Ngày 5 | - **Kế hoạch:** Tuân thủ (Compliance) <br> - **Tác vụ chính:** Giới thiệu về AWS Config <br> - **Hoạt động chi tiết:** Bật AWS Config và thêm một vài quy tắc quản lý sẵn (managed rules), chẳng hạn như kiểm tra các S3 buckets không bị công khai và cổng SSH không mở cho tất cả mọi người. Xem xét những tài nguyên nào tuân thủ (compliant) và những tài nguyên nào không tuân thủ | 06/11/2026 | 06/11/2026 | [Tài liệu hướng dẫn Amazon CloudWatch](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/WhatIsCloudWatch.html) <br> [Tài liệu hướng dẫn AWS Config](https://docs.aws.amazon.com/config/latest/developerguide/WhatIsConfig.html) |

### Kết quả đạt được tuần 9:

* **Amazon CloudWatch:** Thu thập metrics và logs từ tài nguyên, thiết lập dashboards và cấu hình cảnh báo (alarms) khi vượt ngưỡng
* **AWS Auto Scaling:** Duy trì số lượng và sức khỏe dàn máy chủ (min/desired/max) qua Launch Template và chính sách Target Tracking
* **AWS Config:** Ghi lại lịch sử thay đổi cấu hình và đối chiếu tính tuân thủ liên tục theo bộ quy tắc (như kiểm tra S3 public hay SSH mở rộng)
* **Vận hành kết hợp:** Đóng gói cả CloudWatch và Auto Scaling vào CloudFormation template để đồng bộ hóa việc xây dựng, giám sát và tự phục hồi

Tuần này chuyển trọng tâm của tôi từ việc dựng hạ tầng sang việc duy trì hệ thống luôn khỏe mạnh và đúng chuẩn sau khi vận hành. Bài thử nghiệm đẩy tải CPU cho thấy rõ lý do **CloudWatch** và **Auto Scaling** luôn đi đôi với nhau: một dịch vụ phát hiện bất thường, dịch vụ kia tự động thêm mới hoặc thay thế máy chủ hỏng mà không cần con người can thiệp. Trong khi đó, **AWS Config** đóng vai trò như một bảng kiểm tra (checklist) chạy liên tục—nó không trực tiếp chặn thao tác sai mà ghi nhận lịch sử cấu hình và chỉ điểm những tài nguyên đang vi phạm quy tắc để kịp thời khắc phục.

Điểm cốt lõi rút ra:

- **Tự động phát hiện & Phản ứng:** Kết hợp CloudWatch Alarms và Auto Scaling Target Tracking giúp hệ thống tự co giãn theo tải thực tế và tự thay thế instance lỗi.
- **Chuẩn hóa cụm vận hành bằng IaC:** Triển khai cả nhóm Auto Scaling và cảnh báo CloudWatch qua một CloudFormation stack giúp dễ dàng tái tạo hoặc dọn dẹp toàn bộ hệ thống.
- **Kiểm toán cấu hình liên tục:** AWS Config giúp theo dõi biến động cấu hình theo thời gian và phát hiện ngay các thiết lập lệch chuẩn bảo mật.
