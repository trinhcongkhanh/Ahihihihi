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

- Trước buổi này, tôi chủ yếu nghĩ đến việc chọn mô hình nào. Giờ tôi sẽ bắt đầu từ việc bot cần làm gì và có thể sai ở đâu
- Độ trễ, chi phí và độ chính xác thường kéo ngược nhau, nên cần bàn trước khi xây dựng chứ không phải sau đó

#### Kiến Trúc Kỹ Thuật

- RAG, kiểm soát ngữ cảnh và guardrails giải quyết ba vấn đề khác nhau, và một bot đáng tin cần cả ba
- Các dịch vụ AWS được quản lý (Bedrock, Lambda, API Gateway, Secrets Manager) giúp dành nhiều thời gian hơn cho logic của bot
- Một secret đã lọt vào repository thì nên xem như đã bị lộ

#### Tư Duy Nghề Nghiệp

- Nói rõ điều mình chưa biết tốt hơn là đoán
- Một project nhỏ được trình bày tốt theo STAR có thể thuyết phục hơn một danh sách dài các công cụ

### Ứng Dụng Vào Công Việc

- **Thiết kế chatbot cho project** với RAG và quản lý ngữ cảnh có chọn lọc, thay vì gửi toàn bộ lịch sử cho mô hình
- **Thêm guardrails** như lọc đầu vào và kiểm tra prompt injection cho mọi bot tôi xây dựng
- **Thử Amazon Bedrock Knowledge Bases** cho một prototype hỏi đáp nhỏ
- **Dùng Lambda và API Gateway** làm backend nhẹ cho bot
- **Chuyển thông tin xác thực sang AWS Secrets Manager** trong các project
- **Luyện trả lời theo STAR** dựa trên các bài lab AWS và project ở trường

### Trải nghiệm trong event

Tôi đến với **“The Thinking Behind Building The Bot”** và nghĩ rằng sẽ chủ yếu nghe về mô hình và prompt. Điều đọng lại với tôi lại là có rất nhiều công việc cẩn thận diễn ra xung quanh mô hình.

#### Học hỏi từ diễn giả
- Diễn giả nhiều lần quay lại chuyện kiến trúc, nhờ đó tôi nhìn chatbot từ phía hệ thống thay vì chỉ từ phía prompt.
- Phần về quản lý ngữ cảnh và RAG giải thích vì sao một bot có thể trả lời rất tự tin mà vẫn sai.

#### Trải nghiệm kỹ thuật
- Khi thấy Bedrock, Lambda, API Gateway và Secrets Manager nằm trong cùng một bức tranh, tôi kết nối được những dịch vụ mà trước đó mình học riêng lẻ.

#### Mock interview và định hướng nghề nghiệp
- Xem phỏng vấn thử giúp tôi nhận ra cách ứng viên lập luận quan trọng hơn một câu trả lời hoàn hảo.
- STAR cho tôi một trình tự đơn giản để nói về các bài lab và project của mình.

#### Kết nối và trao đổi
- Trò chuyện với các kỹ sư từ CMC Global và mentor của AWS giúp tôi hình dung rõ hơn cloud và an toàn thông tin gặp nhau thế nào trong công việc thực tế.

#### Bài học rút ra
- Nên đánh giá một bot qua cách nó xử lý tình huống khó, không chỉ qua một bản demo đẹp.
- Là sinh viên An toàn thông tin, tôi nên hỏi sớm bot chạm tới được dữ liệu nào và ai chạm tới được bot.
- Tôi cần luyện cách giải thích công việc của mình thật đơn giản, vì làm kỹ thuật tốt vẫn phải để người khác hiểu được.

#### Một số hình ảnh khi tham gia sự kiện
![Hình ảnh check-in rõ mặt chứng minh tham gia sự kiện The Thinking Behind Building The Bot](../../../images/event1.jpg)

> Tôi rời buổi talkshow với một câu hỏi đầu tiên khác trước: không phải “nên dùng mô hình nào?”, mà là “hệ thống này cần gì để được tin tưởng?”
