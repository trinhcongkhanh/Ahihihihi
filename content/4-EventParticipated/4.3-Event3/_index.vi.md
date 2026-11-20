---
title: "Event 3"
date: 2024-01-01
weight: 3
chapter: false
pre: " <b> 4.3. </b> "
---

# Bài thu hoạch “Ngày Hội AWS Cloud Immersion & GenAI Buildathon”

Nối tiếp chuỗi sự kiện và kiến thức đã tích lũy qua các tuần thực tập tại **Amazon Web Services**, ngày hội **AWS Cloud Immersion & GenAI Buildathon** là sân chơi kỹ thuật đỉnh cao, nơi các thực tập sinh trực tiếp áp dụng kiến thức lý thuyết và thực hành để giải quyết các bài toán kiến trúc thực tế. Sự kiện được thiết kế theo hình thức **Technical Sprint 9 tiếng liên tục**, yêu cầu các đội thi phải xây dựng một giải pháp đám mây hoàn chỉnh: từ phân tích bài toán, thiết kế kiến trúc Well-Architected, tích hợp Generative AI (Amazon Bedrock), xây dựng API phi máy chủ (Serverless), cho đến kiểm thử bảo mật khắt khe và bảo vệ trực tiếp trước Hội đồng Giám khảo AWS Solutions Architects.

* **Thời gian:** Toàn ngày (08:30 - 17:30) – Technical Sprint 9 Giờ
* **Địa điểm:** AWS Training Lab – Trung tâm Hợp tác Kỹ thuật
* **Thử thách:** Bedrock GenAI & RAG – IAM Security Hardening
* **Vai trò cá nhân:** Security & Cloud Lead – IAM & Infrastructure

### Nội Dung Nổi Bật

#### 08:30 - 09:00 – Khai mạc & Công bố đề bài thử thách

Hội đồng giám khảo công bố tiêu chuẩn chấm điểm bám sát 6 trụ cột của **AWS Well-Architected Framework** (Bảo mật, Độ tin cậy, Hiệu năng, Tối ưu chi phí, Vận hành xuất sắc, Tính bền vững) và bàn giao bài toán nghiệp vụ doanh nghiệp.

#### 09:00 - 12:00 – Architecture Design & Triển khai Sprint 1

Phác thảo sơ đồ kiến trúc hạ tầng; thiết lập VPC cô lập với Private Subnets; cấu hình Amazon S3 lưu trữ tài liệu doanh nghiệp được mã hóa SSE-KMS để phục vụ Vector Knowledge Base cho RAG:

- Thiết lập Security Groups chỉ mở cổng cần thiết, chặn truy cập công khai vào database.
- Khởi tạo S3 bucket với chính sách Bucket Policy chặn mọi kết nối không qua HTTPS.

#### 12:00 - 13:30 – Nghỉ trưa, Re-group & Tham vấn Mentors

Rà soát tiến độ toàn nhóm, trao đổi nhanh với các AWS Solutions Architect Mentors để thẩm định luồng dữ liệu và tối ưu cấu hình trước khi ghép nối hệ thống AI.

#### 13:30 - 15:30 – GenAI Integration & Triển khai Sprint 2

Tích hợp mô hình Foundation Model trên **Amazon Bedrock** (Claude 3 / Titan) thông qua các hàm **AWS Lambda**; tích hợp **AWS Secrets Manager** để lấy thông tin xác thực động tại runtime, đảm bảo zero hardcoded secrets:

- Kết nối API Gateway với Lambda làm proxy bảo mật cho client web.
- Thiết lập luồng RAG tự động embedding tài liệu mỗi khi có file mới tải lên S3.

#### 15:30 - 16:30 – Kiểm thử Bảo mật & Audit toàn diện

Đánh giá an toàn thông tin chuyên sâu: kiểm toán IAM Role đảm bảo nguyên tắc Least Privilege, kiểm tra CloudTrail logs phát hiện sự kiện bất thường, và chạy thử tải nhẹ kiểm tra độ trễ.

#### 16:30 - 17:30 – Demo & Bảo vệ kiến trúc trước Ban Giám khảo AWS

Trình diễn sản phẩm trực tiếp trước hội đồng giám khảo là các AWS Solutions Architects cao cấp; phản biện và giải thích các quyết định kiến trúc, cơ chế bảo mật và phương án tối ưu chi phí.

### Những Gì Học Được

#### An Toàn Thông Tin & Quản trị IAM

Với vai trò phụ trách bảo mật và kiến trúc hạ tầng trong nhóm dự án:

- **Nguyên tắc Least Privilege:** Tuyệt đối không dùng FullAccess policies; viết custom IAM Policy chỉ cấp đúng quyền đọc/ghi cần thiết trên từng S3 ARN và Lambda function.
- **Bảo vệ biến môi trường:** Không lưu hardcoded access keys trong mã nguồn, tích hợp lấy token động từ AWS Secrets Manager trong thời gian thực.
- **Mã hóa đầu cuối:** Bật mã hóa SSE-KMS cho dữ liệu lưu tại S3 và bảng Amazon DynamoDB.

#### Vận hành Kiến trúc Serverless & RAG

Làm chủ chuỗi dịch vụ hiện đại và mô hình vận hành phi máy chủ của AWS:

- **Amazon Bedrock:** Khởi tạo Knowledge Bases hỗ trợ Vector Search nhanh chóng mà không cần tự duy trì cụm máy chủ Vector DB riêng biệt.
- **Kiến trúc Event-Driven:** Sử dụng sự kiện S3 Event Notification để tự động kích hoạt Lambda xử lý nhúng tài liệu (embedding) ngay khi file được tải lên.
- **Tối ưu hóa tài nguyên:** Chọn đúng cấu hình bộ nhớ cho Lambda để cân bằng giữa chi phí (Cost) và tốc độ thực thi (Performance).

### Ứng Dụng Vào Công Việc

- **Kiểm chứng Kiến thức Thực tế**: Chuyển hóa toàn bộ chuỗi bài thực hành 12 tuần (VPC, EC2, S3, RDS, Secrets Manager, CloudWatch) thành một sản phẩm có tính ứng dụng thật, giải quyết trực tiếp bài toán kinh doanh.
- **Kỹ năng Phối hợp Agile & DevOps**: Trải nghiệm quy trình làm việc chuẩn DevOps: trunk-based git workflow, rà soát mã nguồn ngang hàng (peer review), và phân bổ tài nguyên hợp lý dưới áp lực thời gian thực.
- **Bản lĩnh Kỹ sư Cloud Security**: Củng cố vững chắc mục tiêu trở thành một Chuyên gia An toàn Đám mây (Cloud Security Specialist) có đủ bản lĩnh thiết kế, phòng vệ và bảo vệ hệ thống trước mọi nguy cơ.

#### Một số hình ảnh khi tham gia sự kiện

![AWS GenAI Buildathon and Immersion Day Banner](../../../images/event3.svg)

*Sơ đồ Kiến trúc Hệ thống — AWS GenAI Buildathon*

**Sơ đồ định vị chủ đề kỹ thuật:** Tích hợp Foundation Models (Amazon Bedrock), kiến trúc phi máy chủ Event-Driven và thiết lập ranh giới bảo mật Zero-Trust IAM tại ngày hội AWS Buildathon.

> "Một kiến trúc đám mây đẹp không chỉ nằm ở bản vẽ diagram hoàn hảo, mà được chứng minh qua khả năng chống chịu sự cố, bảo vệ an toàn từng byte dữ liệu và phản hồi người dùng trong tích tắc."
