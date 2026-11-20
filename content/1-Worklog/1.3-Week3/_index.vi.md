---
title: "Worklog Tuần 3"
date: 2024-01-01
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---

### Mục tiêu tuần 3:

* **Chủ đề:** AWS Resource Access Manager (RAM)
* **Mục tiêu chính:** Tìm hiểu cách chia sẻ tài nguyên AWS giữa các tài khoản mà không cần sao chép hoặc tạo thêm người dùng IAM

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| Ngày 1 | - **Kế hoạch:** Tổng quan về RAM <br> - **Tác vụ chính:** Giới thiệu về AWS RAM <br> - **Hoạt động chi tiết:** Đọc về RAM là gì và tại sao nó được sử dụng trong môi trường đa tài khoản. Tìm hiểu 3 thành phần của một resource share: resources, principals và permissions | 28/09/2026 | 28/09/2026 | [AWS Resource Access Manager (RAM) Console](https://console.aws.amazon.com/ram/home?region=us-east-1) <br> [Tài liệu hướng dẫn AWS RAM (User Guide)](https://docs.aws.amazon.com/ram/latest/userguide/what-is.html) |
| Ngày 2 | - **Kế hoạch:** Chia sẻ Tài nguyên <br> - **Tác vụ chính:** Tạo một Resource Share <br> - **Hoạt động chi tiết:** Tạo một resource share trên console, thêm một VPC subnet và chia sẻ nó với một tài khoản khác. Kiểm tra lời mời trên tài khoản kia và chấp nhận nó | 30/09/2026 | 30/09/2026 | [AWS Resource Access Manager (RAM) Console](https://console.aws.amazon.com/ram/home?region=us-east-1) <br> [Tài liệu hướng dẫn AWS RAM (User Guide)](https://docs.aws.amazon.com/ram/latest/userguide/what-is.html) |
| Ngày 3 | - **Kế hoạch:** RAM với Organizations <br> - **Tác vụ chính:** Chia sẻ trong AWS Organizations <br> - **Hoạt động chi tiết:** Tìm hiểu cách bật chia sẻ với AWS Organizations để các tài khoản trong cùng một tổ chức không cần phải chấp nhận lời mời. So sánh việc chia sẻ cho một OU và một tài khoản đơn lẻ | 01/10/2026 | 01/10/2026 | [AWS Resource Access Manager (RAM) Console](https://console.aws.amazon.com/ram/home?region=us-east-1) <br> [Tài liệu hướng dẫn AWS RAM (User Guide)](https://docs.aws.amazon.com/ram/latest/userguide/what-is.html) |
| Ngày 4 | - **Kế hoạch:** Thực hành & Ôn tập <br> - **Tác vụ chính:** AWS CLI và cài đặt bảo mật <br> - **Hoạt động chi tiết:** Thực hành các lệnh `aws ram` cơ bản. Xem xét tùy chọn "Allow external principals" và cách giới hạn việc chia sẻ chỉ trong phạm vi tổ chức | 03/10/2026 | 03/10/2026 | [AWS Resource Access Manager (RAM) Console](https://console.aws.amazon.com/ram/home?region=us-east-1) <br> [Tài liệu hướng dẫn AWS RAM (User Guide)](https://docs.aws.amazon.com/ram/latest/userguide/what-is.html) |

### Kết quả đạt được tuần 3:

* **Resource Shares (AWS RAM):** Chia sẻ tài nguyên theo Region (VPC subnets, Transit Gateways, Route 53 rules) qua 3 thành phần: resources, principals và managed permissions
* **Nội bộ Tổ chức vs. Bên ngoài:** Chia sẻ tự động không cần lời mời trong cùng AWS Organizations/OU so với cơ chế xác nhận lời mời khi chia sẻ cho tài khoản ngoài
* **Quản trị CLI & Bảo mật biên:** Thao tác qua `aws ram` CLI và chặn chia sẻ ra ngoài tổ chức bằng điều kiện SCP `ram:RequestedAllowsExternalPrincipals`

AWS RAM giải quyết bài toán trùng lặp hạ tầng trong môi trường đa tài khoản bằng cách cho phép một tài khoản chủ chia sẻ tài nguyên trực tiếp cho các tài khoản khác. Khác với cross-account IAM role (người dùng phải chuyển đổi danh tính sang tài khoản khác), RAM giúp tài nguyên được chia sẻ (như VPC subnet) xuất hiện trực tiếp trong tài khoản nhận để khởi tạo EC2, trong khi quyền sửa/xóa hạ tầng gốc vẫn thuộc về tài khoản sở hữu.

Điểm cốt lõi rút ra:

- **Tái sử dụng hạ tầng:** Chia sẻ tài nguyên trực tiếp giữa các tài khoản mà không cần nhân bản hay tạo thêm IAM user.
- **Giữ nguyên quyền sở hữu:** Tài khoản nhận chỉ được phép sử dụng tài nguyên theo quyền hạn được cấp, không thể tự ý chỉnh sửa hay xóa tài nguyên gốc.
- **Kiểm soát phạm vi chia sẻ:** Tắt tùy chọn chia sẻ ra ngoài (external principals) kết hợp SCP giúp ngăn chặn rủi ro lộ tài nguyên ra ngoài tổ chức.
