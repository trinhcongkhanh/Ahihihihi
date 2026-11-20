---
title: "Worklog Tuần 6"
date: 2024-01-01
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
---

### Mục tiêu tuần 6:

* **Chủ đề:** Amazon EC2, Amazon Lightsail & AWS Lambda
* **Mục tiêu chính:** Nắm được kiến thức cơ bản về ba cách chính để chạy code trên AWS: máy chủ ảo với EC2, máy chủ đơn giản với Lightsail, và các hàm serverless với Lambda, đồng thời biết khi nào nên chọn từng dịch vụ

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| Ngày 1 | - **Kế hoạch:** Cơ bản về EC2 <br> - **Tác vụ chính:** Giới thiệu về Amazon EC2 <br> - **Hoạt động chi tiết:** Tìm hiểu các thành phần chính của một EC2 instance: AMI, instance type, key pair, security group và ổ đĩa EBS. Khởi chạy một máy chủ `t3.micro` chạy Amazon Linux và kết nối vào bằng SSH | 17/10/2026 | 17/10/2026 | [Tài liệu hướng dẫn Amazon EC2](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/concepts.html) <br> [Tài liệu hướng dẫn AWS Lambda](https://docs.aws.amazon.com/lambda/latest/dg/welcome.html) |
| Ngày 2 | - **Kế hoạch:** Thực hành EC2 <br> - **Tác vụ chính:** Security Groups, User Data & Chi phí <br> - **Hoạt động chi tiết:** Thêm inbound rules vào security group và dùng user data để tự động cài đặt web server khi máy chủ khởi động. Đọc về các mô hình tính phí: On-Demand, Savings Plans, Reserved Instances và Spot. Dừng instance vào cuối ngày để không bị tính phí liên tục | 18/10/2026 | 18/10/2026 | [Tài liệu hướng dẫn Amazon EC2](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/concepts.html) <br> [Tài liệu hướng dẫn AWS Lambda](https://docs.aws.amazon.com/lambda/latest/dg/welcome.html) |
| Ngày 3 | - **Kế hoạch:** Lightsail <br> - **Tác vụ chính:** Giới thiệu về Amazon Lightsail <br> - **Hoạt động chi tiết:** Tạo một Lightsail instance từ bản mẫu (blueprint) WordPress. Gắn địa chỉ IP tĩnh (static IP) và tìm hiểu các tùy chọn tường lửa (firewall) cũng như snapshot. Nhận thấy việc thiết lập nhanh hơn rất nhiều so với EC2 | 19/10/2026 | 19/10/2026 | [Tài liệu hướng dẫn Amazon EC2](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/concepts.html) <br> [Tài liệu hướng dẫn AWS Lambda](https://docs.aws.amazon.com/lambda/latest/dg/welcome.html) |
| Ngày 4 | - **Kế hoạch:** Cơ bản về Lambda <br> - **Tác vụ chính:** Giới thiệu về AWS Lambda <br> - **Hoạt động chi tiết:** Viết một hàm Python nhỏ trên Lambda console và kiểm thử bằng một test event. Tìm hiểu về triggers, execution role, timeout, cấu hình bộ nhớ (memory) và cách xem log trong CloudWatch | 21/10/2026 | 21/10/2026 | [Tài liệu hướng dẫn Amazon EC2](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/concepts.html) <br> [Tài liệu hướng dẫn AWS Lambda](https://docs.aws.amazon.com/lambda/latest/dg/welcome.html) |
| Ngày 5 | - **Kế hoạch:** Ôn tập & So sánh <br> - **Tác vụ chính:** So sánh EC2, Lightsail và Lambda <br> - **Hoạt động chi tiết:** Kết nối hàm Lambda với một API Gateway endpoint và gọi thử từ trình duyệt. Lập bảng so sánh ngắn gọn giữa ba dịch vụ và dọn dẹp toàn bộ tài nguyên đã tạo trong tuần | 22/10/2026 | 22/10/2026 | [Tài liệu hướng dẫn Amazon EC2](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/concepts.html) <br> [Tài liệu hướng dẫn AWS Lambda](https://docs.aws.amazon.com/lambda/latest/dg/welcome.html) |

### Kết quả đạt được tuần 6:

* **Amazon EC2 (IaaS):** Toàn quyền kiểm soát hệ điều hành qua AMI, instance type, EBS, tường lửa Security Group và các mô hình giá (On-Demand, Savings Plans, Spot)
* **Amazon Lightsail:** Máy chủ ảo đóng gói sẵn theo bản mẫu (như WordPress), kèm IP tĩnh, lưu trữ và mức giá cố định hàng tháng
* **AWS Lambda (Serverless):** Thực thi code theo sự kiện (tối đa 15 phút/lần chạy), tính phí theo số lượng request và thời gian chạy, phân quyền qua IAM Execution Role
* **Tiêu chí lựa chọn dịch vụ:** Chọn EC2 khi cần kiểm soát sâu, Lightsail cho website nhỏ chi phí cố định, và Lambda cho tác vụ ngắn chạy theo sự kiện

Tuần này giúp tôi định hình rõ tiêu chí chọn dịch vụ tính toán (compute) trên AWS. **EC2** cung cấp máy chủ ảo toàn quyền kiểm soát hệ điều hành nhưng tính phí theo thời gian bật máy—vì vậy cần tắt ngay khi không sử dụng. **Lightsail** đánh đổi khả năng tùy biến sâu để lấy tốc độ triển khai cực nhanh với chi phí trọn gói hàng tháng, trong khi **Lambda** loại bỏ hoàn toàn việc quản trị máy chủ để chỉ thực thi và tính phí khi có sự kiện kích hoạt từ API Gateway.

Điểm cốt lõi rút ra:

- **Kiểm soát vs. Tinh gọn:** Dùng EC2 cho các hệ thống lớn cần tùy chỉnh mạng/OS sâu, và dùng Lightsail khi cần dựng nhanh website hoặc dự án nhỏ.
- **Trả phí theo giờ bật máy vs. Theo lượt chạy:** EC2 vẫn tính phí khi máy rảnh rỗi, còn Lambda chỉ tính tiền đúng thời gian hàm thực thi.
- **Bảo mật thực thi:** Luôn giới hạn cổng SSH của EC2 theo IP cá nhân trên Security Group và cấp quyền tối thiểu cho từng hàm Lambda qua Execution Role.
