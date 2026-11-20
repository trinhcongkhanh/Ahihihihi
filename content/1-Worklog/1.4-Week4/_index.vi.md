---
title: "Worklog Tuần 4"
date: 2024-01-01
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---

### Mục tiêu tuần 4:

* **Chủ đề:** Amazon Cognito & AWS Secrets Manager
* **Mục tiêu chính:** Tìm hiểu cách thêm tính năng đăng ký và đăng nhập người dùng vào ứng dụng với Cognito, và cách lưu trữ mật khẩu cùng API keys an toàn với Secrets Manager thay vì đặt trực tiếp trong mã nguồn

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| Ngày 1 | - **Kế hoạch:** Cơ bản về Cognito <br> - **Tác vụ chính:** Cognito User Pools <br> - **Hoạt động chi tiết:** Tìm hiểu Cognito là gì và sự khác biệt giữa User Pools và Identity Pools. Tạo một User Pool, thiết lập chính sách mật khẩu và bật xác minh qua email | 04/10/2026 | 04/10/2026 | [Tài liệu hướng dẫn Amazon Cognito](https://docs.aws.amazon.com/cognito/latest/developerguide/what-is-amazon-cognito.html) <br> [Tài liệu hướng dẫn AWS Secrets Manager](https://docs.aws.amazon.com/secretsmanager/latest/userguide/intro.html) |
| Ngày 2 | - **Kế hoạch:** Đăng ký & Đăng nhập <br> - **Tác vụ chính:** App Client, Login Page & MFA <br> - **Hoạt động chi tiết:** Tạo một app client và kiểm thử đăng ký, đăng nhập với trang đăng nhập của Cognito. Bật MFA với ứng dụng xác thực (authenticator app). Xem xét ID token, access token và refresh token trả về sau khi đăng nhập | 05/10/2026 | 05/10/2026 | [Tài liệu hướng dẫn Amazon Cognito](https://docs.aws.amazon.com/cognito/latest/developerguide/what-is-amazon-cognito.html) <br> [Tài liệu hướng dẫn AWS Secrets Manager](https://docs.aws.amazon.com/secretsmanager/latest/userguide/intro.html) |
| Ngày 3 | - **Kế hoạch:** Phân quyền (Authorization) <br> - **Tác vụ chính:** Identity Pools & API Gateway <br> - **Hoạt động chi tiết:** Tìm hiểu cách Identity Pools cấp cho người dùng đã đăng nhập thông tin xác thực AWS tạm thời thông qua IAM roles. Thêm Cognito authorizer vào một API Gateway endpoint để chỉ người dùng có token hợp lệ mới có thể gọi API | 06/10/2026 | 06/10/2026 | [Tài liệu hướng dẫn Amazon Cognito](https://docs.aws.amazon.com/cognito/latest/developerguide/what-is-amazon-cognito.html) <br> [Tài liệu hướng dẫn AWS Secrets Manager](https://docs.aws.amazon.com/secretsmanager/latest/userguide/intro.html) |
| Ngày 4 | - **Kế hoạch:** Lưu trữ Bí mật (Secrets) <br> - **Tác vụ chính:** Cơ bản về Secrets Manager <br> - **Hoạt động chi tiết:** Tạo một secret để lưu trữ thông tin đăng nhập cơ sở dữ liệu và một secret khác cho API key. Tìm hiểu cách các secrets được mã hóa bằng AWS KMS. Đọc lại secret bằng AWS CLI | 08/10/2026 | 08/10/2026 | [Tài liệu hướng dẫn Amazon Cognito](https://docs.aws.amazon.com/cognito/latest/developerguide/what-is-amazon-cognito.html) <br> [Tài liệu hướng dẫn AWS Secrets Manager](https://docs.aws.amazon.com/secretsmanager/latest/userguide/intro.html) |
| Ngày 5 | - **Kế hoạch:** Sử dụng Secrets An toàn <br> - **Tác vụ chính:** Xoay vòng (Rotation) & Quyền truy cập Lambda <br> - **Hoạt động chi tiết:** Tìm hiểu về xoay vòng secret tự động với Lambda function. Cấp cho Lambda function quyền chỉ đọc đúng một secret và gọi nó từ code thay vì gán cứng (hard-coding) giá trị | 09/10/2026 | 09/10/2026 | [Tài liệu hướng dẫn Amazon Cognito](https://docs.aws.amazon.com/cognito/latest/developerguide/what-is-amazon-cognito.html) <br> [Tài liệu hướng dẫn AWS Secrets Manager](https://docs.aws.amazon.com/secretsmanager/latest/userguide/intro.html) |

### Kết quả đạt được tuần 4:

* **Cognito User Pools & Tokens:** Quản lý đăng ký/đăng nhập, MFA và bộ 3 JWT tokens (ID, Access, Refresh token) để xác thực người dùng ứng dụng
* **Identity Pools & Bảo mật API:** Quy đổi phiên đăng nhập hợp lệ thành quyền AWS tạm thời và bảo vệ API Gateway bằng Cognito Authorizer
* **AWS Secrets Manager:** Mã hóa mật khẩu DB/API key bằng KMS, xoay vòng khóa tự động (rotation) và giới hạn quyền `GetSecretValue` theo từng ARN

Tuần này tập trung vào hai trụ cột bảo mật của mọi ứng dụng thực tế: định danh người dùng với Amazon Cognito và loại bỏ thông tin nhạy cảm khỏi mã nguồn với AWS Secrets Manager. Thực hành cả hai dịch vụ giúp tôi phân biệt rõ: **User Pools** giải quyết bài toán xác thực ("bạn là ai?" qua JWT tokens), **Identity Pools** giải quyết bài toán phân quyền AWS ("bạn được truy cập tài nguyên nào?" qua IAM role tạm thời), còn **Secrets Manager** giúp hàm Lambda lấy mật khẩu động khi chạy thay vì gán cứng trong file cấu hình.

Điểm cốt lõi rút ra:

- **Xác thực vs. Phân quyền:** User Pools cấp token để đăng nhập và gọi API Gateway, trong khi Identity Pools cấp quyền truy cập tạm thời vào dịch vụ AWS.
- **Loại bỏ Hard-coded Secrets:** Mật khẩu và API key được lưu tập trung, mã hóa bằng KMS và có thể cập nhật hoặc xoay vòng tự động mà không cần sửa code.
- **Phân quyền tối thiểu cho Secret:** Mỗi hàm Lambda chỉ được cấp quyền đọc đúng một ARN secret mà nó cần và mọi lượt truy cập đều được ghi vết trên CloudTrail.
