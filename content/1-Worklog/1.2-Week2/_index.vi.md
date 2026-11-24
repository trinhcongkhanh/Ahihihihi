---
title: "Worklog Tuần 2"
date: 2024-01-01
weight: 2
chapter: false
pre: " <b> 1.2. </b> "
---

### Mục tiêu tuần 2:

* **Chủ đề:** AWS Firewall Manager
* **Mục tiêu chính:** Quản lý chính sách tường lửa tập trung, thực thi quy tắc và các giới hạn phổ biến

### Các công việc cần triển khai trong tuần này:
| Ngày | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| Ngày 1 | - **Kế hoạch:** Tổng quan về Firewall Manager <br> - **Tác vụ chính:** Cơ bản về Firewall Manager <br> - **Hoạt động chi tiết:** Tìm hiểu AWS Firewall Manager là gì và tại sao nó được sử dụng trong môi trường đa tài khoản. Hiểu được mục đích chính của quản lý tường lửa tập trung | 17/09/2026 | 17/09/2026 | [AWS Firewall Manager Console](https://console.aws.amazon.com/wafv2/fms) <br> [Tài liệu hướng dẫn AWS Firewall Manager](https://docs.aws.amazon.com/waf/latest/developerguide/fms-chapter.html) |
| Ngày 2 | - **Kế hoạch:** Chính sách tập trung <br> - **Tác vụ chính:** Chính sách & Quy tắc <br> - **Hoạt động chi tiết:** Nghiên cứu cách chính sách Firewall Manager áp dụng quy tắc bảo mật cho tài nguyên và tài khoản AWS. Hiểu được sự khác biệt giữa chính sách trung tâm và quy tắc tường lửa thực tế | 18/09/2026 | 18/09/2026 | [AWS Firewall Manager Console](https://console.aws.amazon.com/wafv2/fms) <br> [Tài liệu hướng dẫn AWS Firewall Manager](https://docs.aws.amazon.com/waf/latest/developerguide/fms-chapter.html) |
| Ngày 3 | - **Kế hoạch:** Xem xét rủi ro <br> - **Tác vụ chính:** Giới hạn & Rủi ro <br> - **Hoạt động chi tiết:** Xem xét các vấn đề phổ biến như xung đột chính sách, cấu hình sai và các vấn đề tự động hóa. Hiểu rằng Firewall Manager có thể thực thi chính sách nhưng không thể tự động sửa các quyết định bảo mật sai lầm | 21/09/2026 | 21/09/2026 | [AWS Firewall Manager Console](https://console.aws.amazon.com/wafv2/fms) <br> [Tài liệu hướng dẫn AWS Firewall Manager](https://docs.aws.amazon.com/waf/latest/developerguide/fms-chapter.html) |

### Kết quả đạt được tuần 2:

* **AWS Firewall Manager:** Quản lý tập trung việc triển khai và giám sát chính sách tường lửa trên môi trường đa tài khoản AWS Organizations
* **Chính sách vs. Quy tắc:** Phân biệt rõ giữa chính sách quản trị trung tâm (áp dụng cho tài khoản/tài nguyên nào) và bộ quy tắc lọc lưu lượng thực tế
* **Kiểm soát rủi ro vận hành:** Nhận diện rủi ro khi cấu hình sai chính sách trung tâm hoặc xung đột quy tắc gây ảnh hưởng đồng loạt tới nhiều tài khoản

AWS Firewall Manager bản chất không phải là một tường lửa độc lập, mà là lớp điều phối trung tâm giúp áp đặt và duy trì các chính sách bảo mật đồng nhất trên nhiều tài khoản. Tự động hóa giúp tài nguyên mới tạo luôn tuân thủ chuẩn bảo mật, nhưng cũng làm tăng phạm vi ảnh hưởng nếu cấu hình sai: một chính sách lỗi ở cấp trung tâm có thể làm gián đoạn hàng loạt hệ thống cùng lúc.

Điểm cốt lõi rút ra:

- **Điều phối tập trung:** Dịch vụ giúp đồng bộ hóa việc áp dụng quy tắc, nhưng quản trị viên vẫn phải tự thiết kế nội dung quy tắc phù hợp với từng hệ thống.
- **Tự động hóa không thay thế tư duy:** Công cụ đảm bảo chính sách được thực thi đúng đối tượng, nhưng không thể tự sửa một quy tắc bảo mật thiết kế kém.
- **Kiểm soát phạm vi ảnh hưởng:** Mọi chính sách trung tâm cần được kiểm thử kỹ trước khi áp dụng rộng rãi để tránh xung đột quy tắc.
