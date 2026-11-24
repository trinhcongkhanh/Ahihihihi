---
title: "Event 1"
date: 2026-09-26
weight: 1
chapter: false
pre: " <b> 4.1. </b> "
---

# Bài thu hoạch “The Thinking Behind Building The Bot”

### Thông Tin Sự Kiện

- **Thời gian**: Thứ Bảy, 26/09/2026, 09:00 – 12:00
- **Địa điểm**: Tầng 26, Bitexco Financial Tower, TP. Hồ Chí Minh
- **Vai trò tham gia**: Người tham dự
- **Đơn vị tổ chức**: CMC Global phối hợp cùng AWS First Cloud Journey
- **Hình thức**: Talkshow trực tiếp, kết hợp khởi động Buildathon và phiên phỏng vấn thử

### Mục Đích Của Sự Kiện

- Cho thấy việc xây dựng bot doanh nghiệp không chỉ là gọi API của một mô hình ngôn ngữ lớn
- Giải thích tư duy thiết kế cho bot hoạt động ổn định: kiến trúc, xử lý ngữ cảnh, độ trễ, chi phí và bảo vệ dữ liệu
- Trình bày cách triển khai bot trên AWS với Amazon Bedrock và các dịch vụ serverless
- Đưa ra lời khuyên nghề nghiệp thực tế cho người tham dự thông qua phiên phỏng vấn thử

### Danh Sách Diễn Giả

- **Bùi Nhật Trường** - Technical Leader, CMC Global

### Lịch Trình

| Thời gian | Hoạt động | Chi tiết |
|---|---|---|
| 09:00 – 09:30 | Buildathon Kickoff | Khởi động chuỗi thử thách kỹ thuật, giải thích thể lệ và tiêu chí đánh giá, giao lưu giữa các đội |
| 09:30 – 11:15 | Talkshow: The Thinking Behind Building The Bot | Thiết kế hệ thống, luồng dữ liệu, kiến trúc RAG và điều phối LLM trên AWS |
| 11:15 – 12:00 | Mock Interview và định hướng nghề nghiệp | Phỏng vấn thử trực tiếp cho vị trí Cloud/AI, nhận xét về câu trả lời và hỏi đáp tự do |

### Nội Dung Nổi Bật

#### Tư duy xây dựng bot cấp doanh nghiệp

Bot dùng trong doanh nghiệp khác rất nhiều so với việc gõ prompt trên một giao diện chat:

- **Context management**: chỉ giữ những phần hữu ích của lịch sử hội thoại, giúp giảm chi phí token và tránh tràn cửa sổ ngữ cảnh
- **RAG (Retrieval-Augmented Generation)**: dựa câu trả lời trên dữ liệu riêng của công ty thông qua embedding model và vector database
- **Guardrails và an toàn**: lọc nội dung độc hại, phòng chống prompt injection và giữ câu trả lời trong phạm vi chính sách của công ty

#### Triển khai trên AWS

- **Amazon Bedrock và Knowledge Bases**: dùng nhiều foundation model qua một API chuẩn, có sẵn RAG
- **Serverless**: AWS Lambda và Amazon API Gateway xử lý webhook theo sự kiện, gần như không tốn chi phí khi không hoạt động
- **Bảo mật thông tin xác thực**: lưu API key và secret trong AWS Secrets Manager thay vì ghi cứng trong mã nguồn

#### Câu nói của diễn giả

> Một trợ lý AI xuất sắc không được quyết định bởi việc có mô hình lớn nhất, mà bởi kiến trúc đúng đắn: kiểm soát độ trễ thế nào, thông tin chính xác ra sao và hệ thống phục hồi tốt đến đâu khi gặp tình huống bất ngờ.

#### Phiên phỏng vấn thử

- **Góc nhìn nhà tuyển dụng**: Tech Lead và Solution Architect đề cao khả năng giải quyết vấn đề, sự trung thực về những gì mình biết và khả năng tự học, hơn là học thuộc cú pháp
- **Phương pháp STAR**: mô tả bài lab và dự án theo thứ tự Situation → Task → Action → Result
- **Kết nối**: có cơ hội trao đổi trực tiếp với các kỹ sư từ CMC Global và AWS

### Những Gì Học Được

#### Tư Duy Thiết Kế

- Xem bot là một hệ thống cần được thiết kế kỹ lưỡng, không chỉ là một prompt bọc quanh mô hình
- Tính đến độ trễ, chi phí, độ chính xác và khả năng xảy ra lỗi ngay từ đầu

#### Kiến Trúc Kỹ Thuật

- Kết hợp RAG, kiểm soát ngữ cảnh và guardrails để câu trả lời phù hợp và an toàn
- Dùng các dịch vụ AWS được quản lý (Bedrock, Lambda, API Gateway, Secrets Manager) để triển khai đơn giản và tiết kiệm
- Không để secret trong repository

#### Tư Duy Nghề Nghiệp

- Thể hiện cách mình suy nghĩ, không chỉ những gì mình nhớ
- Dùng cấu trúc STAR để trình bày rõ ràng các dự án thực hành trên AWS

### Ứng Dụng Vào Công Việc

- **Thiết kế chatbot cho project** với RAG và quản lý ngữ cảnh có chọn lọc, thay vì gửi toàn bộ lịch sử cho mô hình
- **Thêm guardrails** như lọc đầu vào và kiểm tra prompt injection cho mọi bot tôi xây dựng
- **Thử Amazon Bedrock Knowledge Bases** cho một prototype hỏi đáp nhỏ
- **Dùng Lambda và API Gateway** làm backend nhẹ cho bot
- **Chuyển thông tin xác thực sang AWS Secrets Manager** trong các project
- **Luyện trả lời theo STAR** dựa trên các bài lab AWS và project ở trường

### Trải nghiệm trong event

Tham gia **“The Thinking Behind Building The Bot”** giúp tôi hiểu thực tế điều gì nằm sau một bot hoạt động ổn định trong doanh nghiệp.

#### Học hỏi từ diễn giả
- Bài nói cho thấy việc chọn mô hình chỉ là một phần, các quyết định về kiến trúc cũng quan trọng không kém.
- Các ví dụ về quản lý ngữ cảnh và RAG giúp các ý tưởng trở nên cụ thể.

#### Trải nghiệm kỹ thuật
- Tôi thấy cách Bedrock, Lambda, API Gateway và Secrets Manager có thể kết hợp trong một bản triển khai bot.

#### Mock interview và định hướng nghề nghiệp
- Xem phỏng vấn thử trực tiếp giúp tôi biết nhà tuyển dụng tìm kiếm điều gì ở ứng viên fresher.
- Phương pháp STAR cho tôi một cách rõ ràng để nói về các project của mình.

#### Kết nối và trao đổi
- Tôi có cơ hội gặp các kỹ sư từ CMC Global và mentor của AWS, hỏi về lộ trình nghề nghiệp trong điện toán đám mây và an toàn thông tin.

#### Bài học rút ra
- Một bot tốt đến từ thiết kế có kỷ luật, không chỉ từ một mô hình mạnh.
- Thói quen bảo mật, như quản lý secret đúng cách, nên được xây dựng ngay từ đầu.
- Trình bày rõ ràng và trung thực cách mình giải quyết vấn đề rất quan trọng khi phỏng vấn.

#### Một số hình ảnh khi tham gia sự kiện
![Hình ảnh check-in rõ mặt chứng minh tham gia sự kiện The Thinking Behind Building The Bot](../../../images/event1.jpg)

> Tổng thể, buổi talkshow thay đổi cách tôi nhìn các project chatbot: đó là những hệ thống cần được thiết kế để nhanh, chính xác, an toàn và tiết kiệm.
