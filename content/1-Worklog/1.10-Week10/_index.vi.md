---
title: "Worklog Tuần 10"
date: 2024-01-01
weight: 10
chapter: false
pre: " <b> 1.10. </b> "
---

### Mục tiêu tuần 10:

* **Chủ đề:** CI/CD Pipelines
* **Mục tiêu chính:** Hiểu CI/CD là gì và xây dựng một đường ống (pipeline) đơn giản trên AWS để tự động biên dịch (build) và triển khai (deploy) code mỗi khi tôi push lên GitHub

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| Ngày 1 | - **Kế hoạch:** Cơ bản về CI/CD <br> - **Tác vụ chính:** Giới thiệu về CI/CD <br> - **Hoạt động chi tiết:** Tìm hiểu sự khác biệt giữa Continuous Integration, Continuous Delivery và Continuous Deployment. Đọc về các giai đoạn (stages) thường gặp của pipeline: source, build, test và deploy | 11/11/2026 | 11/11/2026 | [Tài liệu hướng dẫn AWS CodePipeline](https://docs.aws.amazon.com/codepipeline/latest/userguide/welcome.html) <br> [Tài liệu hướng dẫn AWS CodeBuild](https://docs.aws.amazon.com/codebuild/latest/userguide/welcome.html) |
| Ngày 2 | - **Kế hoạch:** Các công cụ AWS <br> - **Tác vụ chính:** CodePipeline, CodeBuild & CodeDeploy <br> - **Hoạt động chi tiết:** Tìm hiểu nhiệm vụ của từng dịch vụ AWS trong một pipeline. Kết nối kho lưu trữ GitHub của tôi với AWS để pipeline có thể lấy code về | 12/11/2026 | 12/11/2026 | [Tài liệu hướng dẫn AWS CodePipeline](https://docs.aws.amazon.com/codepipeline/latest/userguide/welcome.html) <br> [Tài liệu hướng dẫn AWS CodeBuild](https://docs.aws.amazon.com/codebuild/latest/userguide/welcome.html) |
| Ngày 3 | - **Kế hoạch:** Giai đoạn Build <br> - **Tác vụ chính:** Viết tập tin `buildspec.yml` <br> - **Hoạt động chi tiết:** Viết một tập tin `buildspec.yml` đơn giản cho CodeBuild để cài đặt các gói thư viện, chạy kiểm thử (tests) và đóng gói ứng dụng. Sửa một vài lỗi build bằng cách đọc nhật ký (build logs) | 13/11/2026 | 13/11/2026 | [Tài liệu hướng dẫn AWS CodePipeline](https://docs.aws.amazon.com/codepipeline/latest/userguide/welcome.html) <br> [Tài liệu hướng dẫn AWS CodeBuild](https://docs.aws.amazon.com/codebuild/latest/userguide/welcome.html) |
| Ngày 4 | - **Kế hoạch:** Toàn bộ Pipeline <br> - **Tác vụ chính:** Xây dựng Pipeline <br> - **Hoạt động chi tiết:** Tạo một pipeline trong CodePipeline với các giai đoạn source, build và deploy. Đẩy (push) một thay đổi nhỏ lên GitHub và quan sát nó tự động đi qua từng giai đoạn | 15/11/2026 | 15/11/2026 | [Tài liệu hướng dẫn AWS CodePipeline](https://docs.aws.amazon.com/codepipeline/latest/userguide/welcome.html) <br> [Tài liệu hướng dẫn AWS CodeBuild](https://docs.aws.amazon.com/codebuild/latest/userguide/welcome.html) |
| Ngày 5 | - **Kế hoạch:** Ôn tập <br> - **Tác vụ chính:** Bước phê duyệt & Thói quen tốt <br> - **Hoạt động chi tiết:** Thêm một bước phê duyệt thủ công (manual approval) trước khi triển khai. Tìm hiểu thêm về GitHub Actions như một lựa chọn khác và ôn lại cách giữ cho pipeline luôn an toàn | 16/11/2026 | 16/11/2026 | [Tài liệu hướng dẫn AWS CodePipeline](https://docs.aws.amazon.com/codepipeline/latest/userguide/welcome.html) <br> [Tài liệu hướng dẫn AWS CodeBuild](https://docs.aws.amazon.com/codebuild/latest/userguide/welcome.html) |

### Kết quả đạt được tuần 10:

* **Luồng quy trình CI/CD:** Tự động hóa các chặng Source, Build, Test và Deploy; phân biệt rõ Continuous Integration, Continuous Delivery và Continuous Deployment
* **Bộ công cụ AWS & GitHub:** Điều phối luồng phát hành bằng CodePipeline, chạy kiểm thử/đóng gói theo `buildspec.yml` trên CodeBuild, triển khai với CodeDeploy và đối chiếu với GitHub Actions
* **Bảo mật & Kiểm soát Pipeline:** Không lưu khóa bí mật trong repo hay `buildspec.yml`, cấp quyền IAM tối thiểu cho pipeline và đặt bước phê duyệt thủ công trước khi lên production

Thay thế việc sao chép file và gõ lệnh triển khai thủ công bằng một **CI/CD pipeline** giúp quy trình phát hành phần mềm không chỉ nhanh hơn mà còn chuẩn xác hơn rất nhiều. Khi đẩy một thay đổi lên GitHub và nhìn **CodePipeline** tự động kéo mã nguồn, chạy các bước kiểm thử định nghĩa trong `buildspec.yml` trên **CodeBuild** rồi triển khai ra ứng dụng thực tế, tôi nhận ra giá trị lớn nhất của tự động hóa là tính nhất quán: mọi thay đổi đều phải vượt qua cùng một bộ kiểm thử và bước phê duyệt (approval gate) trước khi đến tay người dùng.

Điểm cốt lõi rút ra:

- **Chuẩn hóa quy trình Build & Test:** Mọi lần push code đều tự động chạy qua các bước trong `buildspec.yml`, giúp phát hiện lỗi sớm ngay trên nhật ký của CodeBuild.
- **Kiểm soát phát hành an toàn:** Bổ sung bước phê duyệt thủ công (manual approval) giúp đội ngũ kiểm tra lần cuối trước khi đẩy bản cập nhật lên môi trường thực tế.
- **Nguyên tắc bảo mật Pipeline:** Tuyệt đối không đặt mật khẩu hoặc khóa bí mật trong kho mã nguồn và chỉ cấp cho pipeline đúng những quyền IAM tối thiểu.
