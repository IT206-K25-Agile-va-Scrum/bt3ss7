# BÁO CÁO KẾ HOẠCH SPRINT 5 - ĐỘI RIKKEIGO

> 👤 **Học viên:** Đỗ Hoàng Sơn | **Mã SV:** PTIT-HCM-066
> 🏫 **Môn học:** IT206-K25-Agile-va-Scrum

---

## Nhiệm vụ 1: Phân tích Capacity và Velocity

Dựa trên dữ liệu nhân sự hiện tại, tôi đã tính toán lại Planning Capacity cho Sprint 5 (10 ngày làm việc). Lưu ý rằng Hà nghỉ 2 ngày, nên tổng số ngày công của Hà là 8 ngày.

Công thức tính: Planning Capacity = (Ngày khả dụng * Giờ tập trung/ngày) - Việc cố định.

- Tổng Planning Capacity của đội: 212 giờ.
- Velocity trung bình 4 Sprint gần nhất: (18 + 20 + 19 + 15) / 4 = 18 Story Points (SP).
- Khoảng dự báo cho Sprint 5: 15 - 20 SP. Đây là ngưỡng an toàn để đội cam kết hoàn thành công việc mà không bị quá tải.

| Developer | Ngày khả dụng | Giờ/ngày | Việc cố định | Planning Capacity (giờ) |
| --- | --- | --- | --- | --- |
| Tú | 10 | 6 | 6 | 54 |
| Vy | 10 | 6 | 0 | 60 |
| Khoa | 9 | 6 | 4 | 50 |
| Hà | 8 | 6 | 0 | 48 |

## Nhiệm vụ 2: Thiết kế Sprint Goal và Lựa chọn PBI

Sprint Goal: Đảm bảo người dùng có thể thanh toán ổn định bằng ví RikkeiPay và an tâm về số dư khi có sự cố hủy chuyến, đồng thời cải thiện trải nghiệm xem lịch sử giao dịch.

Dưới đây là danh sách PBI được chọn dựa trên thứ tự ưu tiên của Product Owner và khả năng đáp ứng của đội:

- Tổng SP dự kiến: 18 SP (Khớp với Velocity trung bình).
- Lý do không chọn PBI 'Gửi SMS': Nhà cung cấp dịch vụ chưa ký hợp đồng, PBI này bị chặn (blocked).
- Lý do không chọn PBI 'Chat với tài xế': Tổng SP đã đạt ngưỡng 18, việc thêm 5 SP nữa sẽ vượt quá khả năng thực tế của đội trong bối cảnh Hà nghỉ phép.

| PBI | SP | Trạng thái |
| --- | --- | --- |
| Thanh toán chuyến đi bằng ví RikkeiPay | 8 | Chọn |
| Hoàn tiền vào ví khi chuyến bị hủy | 5 | Chọn |
| Xem số dư và lịch sử giao dịch ví | 3 | Chọn |
| Giao diện chủ đề Tết | 2 | Chọn |
| Gửi SMS khi tài xế sắp đến | 3 | Không chọn |
| Chat với tài xế | 5 | Không chọn |

## Nhiệm vụ 3: Phân rã PBI 'Hoàn tiền vào ví khi chuyến bị hủy'

Để đảm bảo PBI này có thể kiểm chứng được, tôi chia thành 3 Task cụ thể như sau:

| Task | Mô tả | Đầu ra kiểm chứng |
| --- | --- | --- |
| Task 1 | Thiết kế logic trigger hoàn tiền khi trạng thái chuyến chuyển sang 'Hủy' | Log hệ thống ghi nhận sự kiện hủy và trạng thái hoàn tiền |
| Task 2 | Cập nhật API ví để cộng số dư dựa trên số tiền chuyến đi | API trả về số dư mới chính xác sau khi gọi hàm hoàn tiền |
| Task 3 | Viết Unit Test cho kịch bản hoàn tiền | Báo cáo test pass 100% các trường hợp biên (số tiền âm, số tiền bằng 0) |

---

## 📁 Danh sách tệp tin nộp bài trong Repository
- 📝 `bt3.docx`: Báo cáo tài liệu phân tích nghiệp vụ hoàn chỉnh.
