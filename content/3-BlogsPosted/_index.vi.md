---
title: "Các bài blogs đã đăng"
date: 2024-01-01
weight: 3
chapter: false
pre: " <b> 3. </b> "
---

Danh sách các bài viết kỹ thuật được viết trong chương trình thực tập.

###  [Blog 1 - Amazon Inspector](3.1-blog1/)
Bảo mật thường được nghĩ chủ yếu là chuyện phân quyền IAM và đóng bớt port. Server có thể cấu hình rất ổn mà vẫn bị tấn công, chỉ vì phần mềm bên trong chưa được vá. Một thư viện cũ, một gói hệ điều hành lâu chưa cập nhật là đủ để hacker có đường vào.

###  [Blog 2 - AWS FinOps Agent](3.2-blog2/)
Trong nhiều tổ chức, việc quản lý chi phí cloud vẫn diễn ra theo chu kỳ. Cuối tháng, đội FinOps mở dashboard và phát hiện chi phí một service tăng bất thường. Sau đó họ phải lọc dữ liệu trong Cost Explorer, đối chiếu với lịch sử thay đổi hạ tầng, rồi đi hỏi từng team xem ai đã tạo hoặc thay đổi tài nguyên.

###  [Blog 3 - AWS Backup Vault Lock](3.3-blog3/)
Câu hỏi đặt ra: nếu kẻ tấn công đã có quyền admin, liệu có bản backup nào mà chính admin cũng không xoá được? AWS Backup Vault Lock được thiết kế để trả lời đúng câu hỏi này.
