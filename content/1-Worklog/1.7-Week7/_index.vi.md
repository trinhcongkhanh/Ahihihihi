---
title: "Worklog Tuần 7"
date: 2024-01-01
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---

### Mục tiêu tuần 7:

* **Chủ đề:** Amazon VPC, Amazon CloudFront & Amazon API Gateway
* **Mục tiêu chính:** Hiểu cách một mạng riêng được thiết lập trên AWS, cách nội dung được phân phối nhanh hơn tới người dùng, và cách một API được cung cấp ra internet

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| Ngày 1 | - **Kế hoạch:** Cơ bản về VPC <br> - **Tác vụ chính:** Giới thiệu về Amazon VPC <br> - **Hoạt động chi tiết:** Tìm hiểu VPC là gì và cách nó được chia thành public subnet và private subnet. Tạo một VPC đơn giản với một public subnet và một private subnet | 23/10/2026 | 23/10/2026 | [Tài liệu hướng dẫn Amazon VPC](https://docs.aws.amazon.com/vpc/latest/userguide/what-is-amazon-vpc.html) <br> [Tài liệu hướng dẫn Amazon CloudFront](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/Introduction.html) |
| Ngày 2 | - **Kế hoạch:** Mạng trong VPC <br> - **Tác vụ chính:** Internet Gateway & Route Tables <br> - **Hoạt động chi tiết:** Thêm một Internet Gateway và một route table để public subnet có thể kết nối ra internet. Khởi chạy một máy chủ EC2 trong mỗi subnet để quan sát sự khác biệt | 24/10/2026 | 24/10/2026 | [Tài liệu hướng dẫn Amazon VPC](https://docs.aws.amazon.com/vpc/latest/userguide/what-is-amazon-vpc.html) <br> [Tài liệu hướng dẫn Amazon CloudFront](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/Introduction.html) |
| Ngày 3 | - **Kế hoạch:** CloudFront <br> - **Tác vụ chính:** Giới thiệu về Amazon CloudFront <br> - **Hoạt động chi tiết:** Tìm hiểu CDN là gì và cách các edge locations lưu bản sao (cache) nội dung ở gần người dùng hơn. Đặt một CloudFront distribution phía trước S3 bucket đang lưu trữ một website tĩnh nhỏ | 25/10/2026 | 25/10/2026 | [Tài liệu hướng dẫn Amazon VPC](https://docs.aws.amazon.com/vpc/latest/userguide/what-is-amazon-vpc.html) <br> [Tài liệu hướng dẫn Amazon CloudFront](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/Introduction.html) |
| Ngày 4 | - **Kế hoạch:** API Gateway <br> - **Tác vụ chính:** Giới thiệu về Amazon API Gateway <br> - **Hoạt động chi tiết:** Tạo một API đơn giản với một route `GET` và kết nối nó với một hàm Lambda. Triển khai (deploy) nó lên một stage và gọi thử từ trình duyệt | 27/10/2026 | 27/10/2026 | [Tài liệu hướng dẫn Amazon VPC](https://docs.aws.amazon.com/vpc/latest/userguide/what-is-amazon-vpc.html) <br> [Tài liệu hướng dẫn Amazon CloudFront](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/Introduction.html) |
| Ngày 5 | - **Kế hoạch:** Ôn tập <br> - **Tác vụ chính:** Kết hợp các dịch vụ <br> - **Hoạt động chi tiết:** Ôn lại cách ba dịch vụ phối hợp trong cùng một ứng dụng web: CloudFront cho phần website, API Gateway cho phần backend, VPC cho các tài nguyên nội bộ. Xóa toàn bộ tài nguyên sau bài lab | 28/10/2026 | 28/10/2026 | [Tài liệu hướng dẫn Amazon VPC](https://docs.aws.amazon.com/vpc/latest/userguide/what-is-amazon-vpc.html) <br> [Tài liệu hướng dẫn Amazon CloudFront](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/Introduction.html) |

### Kết quả đạt được tuần 7:

* **Amazon VPC & Subnets:** Thiết kế mạng riêng ảo tách biệt giữa Public Subnet (định tuyến qua Internet Gateway) và Private Subnet cho tài nguyên nội bộ
* **Amazon CloudFront (CDN):** Lưu đệm (cache) nội dung tĩnh tại các Edge Locations toàn cầu kèm hỗ trợ sẵn HTTPS giúp tăng tốc độ tải trang
* **Amazon API Gateway:** Cung cấp cổng giao tiếp chuẩn HTTP/REST (`GET`, `POST`) theo từng stage để kết nối người dùng tới các hàm Lambda phía sau

Tuần này giúp tôi kết nối trọn vẹn luồng đi của một ứng dụng web trên AWS từ trình duyệt người dùng đến tận lớp mạng nội bộ. Hình ảnh ẩn dụ ngôi nhà giúp tôi hiểu ngay bản chất của **VPC**: VPC là ngôi nhà, các subnets là từng căn phòng và Internet Gateway là cửa chính—chỉ những phòng có đường dẫn ra cửa chính mới giao tiếp được với internet, còn cơ sở dữ liệu được bảo vệ kín trong phòng riêng. Ở lớp giao tiếp bên ngoài, **CloudFront** phân phối giao diện web từ các trạm biên gần người dùng nhất, còn **API Gateway** đóng vai trò cổng tiếp nhận yêu cầu an toàn cho hệ thống backend.

Điểm cốt lõi rút ra:

- **Cô lập mạng Public & Private:** Chỉ mở đường ra Internet Gateway cho public subnet, giữ toàn bộ cơ sở dữ liệu và dịch vụ nhạy cảm trong private subnet.
- **Tăng tốc phân phối nội dung:** CloudFront giảm độ trễ tải trang nhờ phân phối file tĩnh từ hệ thống Edge Locations gần người dùng.
- **Cổng API tập trung:** API Gateway giúp xuất bản các dịch vụ Lambda ra internet gọn gàng qua các routes và stages mà không làm lộ hạ tầng phía sau.
