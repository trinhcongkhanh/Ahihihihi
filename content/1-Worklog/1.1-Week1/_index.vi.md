---
title: "Worklog Tuần 1"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.1. </b> "
---

### Mục tiêu tuần 1:

* **Chủ đề:** AWS Fundamentals & IAM
* **Mục tiêu chính:** Hiểu các khái niệm cơ bản về AWS và cách quyền truy cập được quản lý bằng IAM

### Các công việc cần triển khai trong tuần này:
| Ngày | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| Ngày 1 | - **Kế hoạch:** AWS Basics <br> - **Tác vụ chính:** AWS Fundamentals <br> - **Hoạt động chi tiết:** Tìm hiểu về AWS Management Console, Regions, Availability Zones và các dịch vụ AWS phổ biến | 14/09/2026 | 14/09/2026 | [AWS IAM Management Console](https://console.aws.amazon.com/iam/home?region=us-east-1) <br> [Tài liệu hướng dẫn AWS IAM (User Guide)](https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction.html) |
| Ngày 2 | - **Kế hoạch:** Quản lý người dùng <br> - **Tác vụ chính:** IAM Users & Groups <br> - **Hoạt động chi tiết:** Tìm hiểu cách tạo IAM Users, User Groups và phân quyền | 15/09/2026 | 15/09/2026 | [AWS IAM Management Console](https://console.aws.amazon.com/iam/home?region=us-east-1) <br> [Tài liệu hướng dẫn AWS IAM (User Guide)](https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction.html) |
| Ngày 3 | - **Kế hoạch:** Quản lý truy cập <br> - **Tác vụ chính:** IAM Roles & Policies <br> - **Hoạt động chi tiết:** Tìm hiểu về IAM Roles, Policies và Nguyên tắc đặc quyền tối thiểu | 16/09/2026 | 16/09/2026 | [AWS IAM Management Console](https://console.aws.amazon.com/iam/home?region=us-east-1) <br> [Tài liệu hướng dẫn AWS IAM (User Guide)](https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction.html) |

### Kết quả đạt được tuần 1:

* **Hạ tầng toàn cầu AWS:** Cách AWS tổ chức dịch vụ qua các Regions và Availability Zones để đảm bảo tính sẵn sàng cao và cô lập sự cố
* **Định danh & Chính sách IAM:** Quản lý quyền truy cập thông qua IAM Users, User Groups, IAM Roles tạm thời và các chính sách JSON
* **Bảo mật tài khoản nền tảng:** Bảo vệ tài khoản Root, bắt buộc xác thực đa yếu tố (MFA) và áp dụng nguyên tắc đặc quyền tối thiểu (Least Privilege)

Tuần đầu tiên giúp tôi nắm rõ cách hạ tầng toàn cầu của AWS được tổ chức và lý do quản lý định danh luôn là lớp phòng thủ đầu tiên trên đám mây. Thay vì dùng chung tài khoản gốc hoặc cấp quyền tràn lan, AWS IAM tách biệt rõ người dùng, nhóm người dùng và các vai trò (Roles) tạm thời cho dịch vụ để mỗi đối tượng chỉ nhận đúng những quyền hạn cần thiết.

Điểm cốt lõi rút ra:

- **Tổ chức hạ tầng:** Regions và Availability Zones giúp cô lập rủi ro phần cứng và đặt ứng dụng gần người dùng hơn.
- **Phân quyền theo nhóm & vai trò:** Quản lý quyền qua User Groups và dùng IAM Roles cho dịch vụ an toàn, dễ bảo trì hơn nhiều so với gắn quyền lẻ cho từng cá nhân.
- **Bảo vệ Root & Đặc quyền tối thiểu:** Tài khoản Root cần được khóa chặt bằng MFA và không dùng cho công việc hàng ngày; mọi tác vụ đều phải tuân theo nguyên tắc Least Privilege.
