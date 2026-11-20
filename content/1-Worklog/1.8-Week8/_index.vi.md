---
title: "Worklog Tuần 8"
date: 2024-01-01
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---

### Mục tiêu tuần 8:

* **Chủ đề:** Infrastructure as Code (IaC)
* **Mục tiêu chính:** Hiểu IaC là gì và cách tạo các tài nguyên AWS bằng code thay vì bấm thủ công trên console, chủ yếu với AWS CloudFormation

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| Ngày 1 | - **Kế hoạch:** Cơ bản về IaC <br> - **Tác vụ chính:** Giới thiệu về IaC <br> - **Hoạt động chi tiết:** Tìm hiểu ý nghĩa của IaC và lý do các đội ngũ sử dụng nó thay vì tạo tài nguyên bằng tay. Đọc về các công cụ phổ biến: AWS CloudFormation, AWS CDK và Terraform | 29/10/2026 | 29/10/2026 | [Tài liệu hướng dẫn AWS CloudFormation](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/Welcome.html) <br> [Tài liệu hướng dẫn AWS CDK](https://docs.aws.amazon.com/cdk/v2/guide/home.html) |
| Ngày 2 | - **Kế hoạch:** CloudFormation <br> - **Tác vụ chính:** Viết Template đầu tiên <br> - **Hoạt động chi tiết:** Tìm hiểu các phần cơ bản của một CloudFormation template bằng YAML: `Parameters`, `Resources` và `Outputs`. Viết một template nhỏ để tạo một S3 bucket | 31/10/2026 | 31/10/2026 | [Tài liệu hướng dẫn AWS CloudFormation](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/Welcome.html) <br> [Tài liệu hướng dẫn AWS CDK](https://docs.aws.amazon.com/cdk/v2/guide/home.html) |
| Ngày 3 | - **Kế hoạch:** Stacks <br> - **Tác vụ chính:** Tạo, Cập nhật & Xóa một Stack <br> - **Hoạt động chi tiết:** Triển khai template dưới dạng một stack trên console. Thay đổi template và cập nhật lại stack, sau đó xóa stack và thấy toàn bộ tài nguyên được gỡ bỏ cùng lúc | 01/11/2026 | 01/11/2026 | [Tài liệu hướng dẫn AWS CloudFormation](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/Welcome.html) <br> [Tài liệu hướng dẫn AWS CDK](https://docs.aws.amazon.com/cdk/v2/guide/home.html) |
| Ngày 4 | - **Kế hoạch:** Thực hành <br> - **Tác vụ chính:** Viết Template lớn hơn <br> - **Hoạt động chi tiết:** Viết một template tạo máy chủ EC2 kèm theo một security group. Sử dụng một parameter cho instance type để cùng một template có thể tái sử dụng được | 02/11/2026 | 02/11/2026 | [Tài liệu hướng dẫn AWS CloudFormation](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/Welcome.html) <br> [Tài liệu hướng dẫn AWS CDK](https://docs.aws.amazon.com/cdk/v2/guide/home.html) |
| Ngày 5 | - **Kế hoạch:** Ôn tập <br> - **Tác vụ chính:** Các công cụ khác & Thói quen tốt <br> - **Hoạt động chi tiết:** Xem qua các ví dụ ngắn của AWS CDK và Terraform để so sánh với CloudFormation. Đưa các templates vào kho lưu trữ Git để theo dõi lịch sử thay đổi | 04/11/2026 | 04/11/2026 | [Tài liệu hướng dẫn AWS CloudFormation](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/Welcome.html) <br> [Tài liệu hướng dẫn AWS CDK](https://docs.aws.amazon.com/cdk/v2/guide/home.html) |

### Kết quả đạt được tuần 8:

* **AWS CloudFormation:** Định nghĩa hạ tầng bằng YAML template (`Parameters`, `Resources`, `Outputs`) và quản lý vòng đời tài nguyên theo từng Stack
* **Hệ sinh thái công cụ IaC:** Phân biệt công cụ chuyên biệt cho AWS (CloudFormation, AWS CDK) với công cụ đa đám mây (Terraform)
* **Thực hành chuẩn IaC:** Quản lý phiên bản template trên Git, tham số hóa cấu hình, không gán cứng mật khẩu và tránh sửa tay trên console

Chuyển từ việc bấm tạo thủ công trên console sang **Infrastructure as Code (IaC)** đã thay đổi hoàn toàn cách tôi dựng và dọn dẹp môi trường AWS. Thay vì phải cố nhớ từng bước cấu hình mỗi khi cần dựng lại hệ thống, một file YAML trên CloudFormation vừa là bản thiết kế tự động vừa là hồ sơ ghi nhận chính xác những gì đang chạy—và khi xóa stack, toàn bộ tài nguyên liên quan đều được gỡ bỏ sạch sẽ cùng lúc mà không lo sót lại máy chủ hay bucket gây tốn chi phí.

Điểm cốt lõi rút ra:

- **Nhất quán & Tái sử dụng:** Sử dụng `Parameters` trong CloudFormation giúp triển khai lại cùng một kiến trúc nhanh chóng và chính xác ở nhiều lần chạy.
- **Quản lý vòng đời theo cụm (Stack):** Mọi thao tác tạo, cập nhật hay xóa đều thực hiện đồng bộ trên cả nhóm tài nguyên, loại bỏ rủi ro bỏ quên tài nguyên thừa.
- **Kỷ luật quản lý mã hạ tầng:** Lưu trữ template trên Git, tuyệt đối không viết khóa bí mật vào file YAML và không chỉnh sửa thủ công các tài nguyên đã tạo bằng IaC.
