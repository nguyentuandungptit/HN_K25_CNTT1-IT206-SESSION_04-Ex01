# Bài làm: Rà soát User Story và sắp xếp Product Backlog (FoodNow)

## Bước 1: Tìm lỗi theo tiêu chí INVEST

| Mã | Kết quả và lý do |
| :--- | :--- |
| **US1** | **Đạt:** Vai trò rõ ràng, tập trung vào một việc cụ thể, có lợi ích thiết thực, kiểm thử được bằng cách chọn loại món và kiểm tra danh sách nhà hàng trả về. |
| **US2** | **Sai chữ T (Testable) và chữ E (Estimable):** Khái niệm "đẹp" và "dễ dùng" mang tính cảm tính, không có tiêu chí đo lường cụ thể nên Tester không thể viết tiêu chí nghiệm thu và Dev không thể ước lượng khi nào hoàn thành. |
| **US3** | **Sai chữ V (Valuable):** Mục này thuần túy là giải pháp kỹ thuật nội bộ của lập trình viên, không mang lại giá trị nghiệp vụ trực tiếp cho người dùng cuối hoặc mô hình kinh doanh của ứng dụng. |
| **US4** | **Sai chữ S (Small) và chữ E (Estimable):** Mục này gom quá nhiều nghiệp vụ phức tạp (lọc đa chiều theo thời gian, khu vực, nhà hàng; xuất Excel; tự động gửi email), kích thước quá lớn nên nhóm không thể hoàn thành trong một Sprint. |

## Bước 2: Sửa lỗi

### a) Viết lại US2 với tiêu chí đo lường được
Để tiêu chí "dễ dùng" có thể kiểm thử và nghiệm thu rõ ràng, câu chuyện người dùng được lượng hóa qua số bước thao tác:

- **User Story US2 viết lại:**  
  Là một khách hàng,  
  Tôi muốn hoàn tất các bước chọn món và xác nhận giỏ hàng trong tối đa 3 bước chạm,  
  Để tiết kiệm thời gian đặt bữa ăn nhanh chóng.

- **Tiêu chí nghiệm thu (Acceptance Criteria) tham khảo:**  
  Given khách hàng đang ở trang thực đơn của nhà hàng, When chọn món và chuyển sang giỏ hàng, Then toàn bộ quá trình chỉ mất tối đa 3 lần bấm để đến màn hình thanh toán.

### b) Tách US4 và đặt vào cây 3 cấp (Epic -> Feature -> User Story)

- **Cấp 1: Epic**  
  Quản lý và theo dõi báo cáo doanh thu hệ thống

- **Cấp 2: Feature**  
  Báo cáo doanh thu bán hàng của các nhà hàng đối tác theo thời gian

- **Cấp 3: User Story (tách thành 2 story nhỏ độc lập)**
  1. **US4.1 (Xem báo cáo trên giao diện quản trị):**  
     Là một admin,  
     Tôi muốn xem bảng tổng hợp doanh thu theo ngày, tuần, tháng của từng nhà hàng trên màn hình quản trị,  
     Để theo dõi tình hình kinh doanh kịp thời.
  2. **US4.2 (Xuất dữ liệu báo cáo ra file Excel):**  
     Là một admin,  
     Tôi muốn xuất dữ liệu báo cáo doanh thu ra file Excel,  
     Để gửi số liệu đối soát cho ban giám đốc và bộ phận kế toán.

## Bước 3: Sắp xếp lại Product Backlog

### a) Thứ tự ưu tiên cho 4 story
Dựa trên giá trị cốt lõi của ứng dụng đặt món nhanh (giao trong 30 phút), luồng trải nghiệm khách hàng được ưu tiên trước, tiếp theo mới đến công cụ quản trị nội bộ:

1. **Ưu tiên 1: US1 (Lọc nhà hàng theo loại món):** Khách hàng cần tìm thấy đúng món ăn trước tiên; nếu không tìm được quán thì không thể phát sinh đơn hàng.
2. **Ưu tiên 2: US2 đã sửa (Tối ưu đặt món trong 3 bước):** Sau khi tìm được món, khách hàng cần thao tác đặt hàng nhanh gọn để giữ chân người dùng và đảm bảo cam kết giao nhanh.
3. **Ưu tiên 3: US4.1 (Admin xem báo cáo doanh thu trên web):** Phục vụ quản lý theo dõi số liệu kinh doanh hàng ngày, hỗ trợ vận hành cơ bản của hệ thống.
4. **Ưu tiên 4: US4.2 (Admin xuất báo cáo Excel):** Tiện ích hỗ trợ bổ sung cho việc lưu trữ và đối soát định kỳ, thực hiện sau khi giao diện xem báo cáo đã hoạt động ổn định.

### b) Mức độ chi tiết theo DEEP và công việc trong buổi Refinement

#### Mức độ chi tiết của story đứng đầu (theo chữ D trong DEEP)
Theo nguyên tắc Detailed appropriately, story nằm ở vị trí cao nhất (US1) sắp đưa vào Sprint tới nên cần đạt mức độ chi tiết cao nhất:
- Viết đủ 3 vế User Story với câu từ rõ ràng, không còn từ ngữ mơ hồ.
- Có danh sách tiêu chí nghiệm thu (Acceptance Criteria) cụ thể theo mẫu Given - When - Then.
- Có thiết kế giao diện (UI mockup/wireframe) của bộ lọc và danh sách kết quả đi kèm.
- Kích thước vừa vặn (đạt tiêu chí Small) để hoàn thành trọn vẹn trong một Sprint.

#### Các việc nhóm cần làm trong buổi Backlog Refinement trước khi đưa vào Sprint
- Làm rõ nghiệp vụ: Nhóm phát triển thảo luận với Product Owner về các trường hợp biên (nhà hàng bán nhiều loại món, không tìm thấy kết quả nào, phân trang kết quả).
- Kiểm tra tính sẵn sàng (Definition of Ready): Xác nhận story đã có đầy đủ tiêu chí nghiệm thu và thiết kế cần thiết.
- Ước lượng độ phức tạp: Cả nhóm cùng thảo luận kỹ thuật và chấm điểm nỗ lực (Story Points), ví dụ bằng phương pháp Planning Poker.
- Xác định phụ thuộc: Rà soát API danh mục món ăn đã có sẵn chưa để tránh bị tắc nghẽn khi bước vào Sprint.
