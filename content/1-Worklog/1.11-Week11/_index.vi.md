---
title: "Worklog Tuần 11"
date: 2024-01-01
weight: 11
chapter: false
pre: " <b> 1.11. </b> "
---

### Mục tiêu tuần 11:

* **Chủ đề:** AWS Marketplace & AWS Billing Conductor
* **Mục tiêu chính:** Tìm hiểu cách tìm kiếm và mua phần mềm của bên thứ ba thông qua AWS Marketplace, và cách AWS Billing Conductor giúp hiển thị chi phí tùy chỉnh cho các đội ngũ hoặc khách hàng khác nhau

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| Ngày 1 | - **Kế hoạch:** Cơ bản về Marketplace <br> - **Tác vụ chính:** Giới thiệu về AWS Marketplace <br> - **Hoạt động chi tiết:** Tìm hiểu AWS Marketplace là gì và những loại sản phẩm được bán trên đó: AMIs, SaaS, containers và các sản phẩm dữ liệu. Xem thử một vài công cụ bảo mật và giám sát | 17/11/2026 | 17/11/2026 | [Tài liệu hướng dẫn AWS Marketplace](https://docs.aws.amazon.com/marketplace/latest/buyerguide/what-is-marketplace.html) <br> [Tài liệu hướng dẫn AWS Billing Conductor](https://docs.aws.amazon.com/billingconductor/latest/userguide/what-is-billingconductor.html) |
| Ngày 2 | - **Kế hoạch:** Chi phí (Pricing) <br> - **Tác vụ chính:** Các mô hình tính phí trên Marketplace <br> - **Hoạt động chi tiết:** So sánh các hình thức tính phí như miễn phí, theo giờ, theo năm và BYOL (Bring Your Own License - Mang theo bản quyền sẵn có). Khởi chạy một AMI miễn phí từ Marketplace, sau đó hủy đăng ký (unsubscribe) và xóa máy chủ sau khi kiểm thử | 19/11/2026 | 19/11/2026 | [Tài liệu hướng dẫn AWS Marketplace](https://docs.aws.amazon.com/marketplace/latest/buyerguide/what-is-marketplace.html) <br> [Tài liệu hướng dẫn AWS Billing Conductor](https://docs.aws.amazon.com/billingconductor/latest/userguide/what-is-billingconductor.html) |
| Ngày 3 | - **Kế hoạch:** Cơ bản về Billing Conductor <br> - **Tác vụ chính:** Giới thiệu về AWS Billing Conductor <br> - **Hoạt động chi tiết:** Tìm hiểu lý do Billing Conductor ra đời: hiển thị cho từng đội ngũ hoặc khách hàng phiên bản hóa đơn riêng của họ mà không làm thay đổi số tiền thực tế AWS tính phí | 20/11/2026 | 20/11/2026 | [Tài liệu hướng dẫn AWS Marketplace](https://docs.aws.amazon.com/marketplace/latest/buyerguide/what-is-marketplace.html) <br> [Tài liệu hướng dẫn AWS Billing Conductor](https://docs.aws.amazon.com/billingconductor/latest/userguide/what-is-billingconductor.html) |
| Ngày 4 | - **Kế hoạch:** Thiết lập Billing <br> - **Tác vụ chính:** Billing Groups & Pricing Plans <br> - **Hoạt động chi tiết:** Học cách gom các tài khoản vào từng nhóm thanh toán (billing groups), cách các gói giá (pricing plans) cộng thêm biên lợi nhuận (markup) hoặc chiết khấu (discount), và cách các mục chi phí tùy chỉnh (custom line items) thêm phí phụ thu hoặc khoản tín dụng (credits) | 21/11/2026 | 21/11/2026 | [Tài liệu hướng dẫn AWS Marketplace](https://docs.aws.amazon.com/marketplace/latest/buyerguide/what-is-marketplace.html) <br> [Tài liệu hướng dẫn AWS Billing Conductor](https://docs.aws.amazon.com/billingconductor/latest/userguide/what-is-billingconductor.html) |
| Ngày 5 | - **Kế hoạch:** Ôn tập <br> - **Tác vụ chính:** So sánh và Tổng kết <br> - **Hoạt động chi tiết:** So sánh Billing Conductor với Cost Explorer và hóa đơn AWS thông thường. Ghi chép lại khi nào thì mỗi công cụ phát huy tác dụng | 23/11/2026 | 23/11/2026 | [Tài liệu hướng dẫn AWS Marketplace](https://docs.aws.amazon.com/marketplace/latest/buyerguide/what-is-marketplace.html) <br> [Tài liệu hướng dẫn AWS Billing Conductor](https://docs.aws.amazon.com/billingconductor/latest/userguide/what-is-billingconductor.html) |

### Kết quả đạt được tuần 11:

* **AWS Marketplace:** Tìm kiếm và triển khai phần mềm bên thứ ba (AMIs, SaaS, containers) thanh toán gộp trên hóa đơn AWS theo giờ, theo năm, miễn phí hoặc BYOL
* **Quản trị gói đăng ký:** Đánh giá nhà cung cấp, giới hạn quyền mua qua IAM và chủ động hủy đăng ký (unsubscribe) kèm xóa tài nguyên sau khi thử nghiệm
* **AWS Billing Conductor:** Gom tài khoản vào Billing Groups, áp dụng Pricing Plans (markup/discount) và Custom Line Items để phân bổ chi phí cho các phòng ban hoặc khách hàng
* **Hóa đơn Pro Forma:** Hiểu rõ Billing Conductor tạo góc nhìn chi phí tùy chỉnh (pro forma) cho từng nhóm mà không làm thay đổi hóa đơn gốc AWS thu từ tài khoản thanh toán chính

Tuần này mở rộng góc nhìn của tôi sang khía cạnh thương mại và quản trị tài chính đám mây: mua sắm phần mềm qua **AWS Marketplace** và phân bổ chi phí đa tài khoản bằng **AWS Billing Conductor**. Marketplace vận hành như một kho ứng dụng tích hợp sẵn giúp gộp chi phí phần mềm bên thứ ba vào chung hóa đơn AWS—nhưng đòi hỏi phải nhớ hủy đăng ký và xóa máy chủ ngay sau khi dùng thử để tránh phát sinh phí ngầm. Trong khi đó, Billing Conductor giúp các đối tác bán lại (resellers) hoặc doanh nghiệp lớn tạo bảng chi phí *pro forma* riêng cho từng nhóm tài khoản mà không làm thay đổi số tiền thực tế AWS thu từ tài khoản chủ.

Điểm cốt lõi rút ra:

- **Triển khai phần mềm nhanh & Kiểm soát chi phí:** AWS Marketplace hỗ trợ linh hoạt từ bản dùng thử đến BYOL, nhưng cần kiểm soát quyền đăng ký qua IAM và dọn dẹp kỹ sau khi test.
- **Minh bạch hóa phân bổ chi phí:** Kết hợp Billing Groups, Pricing Plans và Custom Line Items giúp tính toán chính xác mức chi phí, phụ phí hoặc chiết khấu riêng cho từng đội ngũ.
- **Phân biệt Pro Forma và Hóa đơn thực:** Billing Conductor chỉ thay đổi bảng chi phí hiển thị cho từng nhóm thanh toán, không làm giảm hay thay đổi hóa đơn gốc của AWS.
