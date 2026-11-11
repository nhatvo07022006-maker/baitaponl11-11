## Bài 6.2 - HRM
- Tab Hồ sơ nhân viên: thêm/sửa/xóa, tìm theo tên, phòng ban, CCCD; chuyển phòng ban ngay trên form sửa.
- Tab Phòng ban: thêm/xóa phòng ban.
- Tab Chấm công: chọn tháng, nạp bản ghi cho toàn bộ nhân viên vào DataTable, chỉnh trực tiếp ngày công/OT, lưu bằng `SqlCommandBuilder` và `SqlDataAdapter.Update()`.
- Tab Tính lương: công thức theo đề, chốt toàn bộ nhân viên của tháng trong một `SqlTransaction`. Khi đã có bảng lương, hệ thống chặn lưu chấm công tháng đó.

## Ghi chú
- Hai bài là hai project độc lập, dùng hai database độc lập: `SalesDB` và `HRMDB`.
- Script SQL có lệnh tạo lại các bảng (DROP/CREATE); chỉ chạy lại khi muốn reset dữ liệu mẫu.
- Bảng `BangChamCong` có thêm ràng buộc UNIQUE(MaNV, ThangNam) để mỗi nhân viên chỉ có một bản ghi chấm công mỗi tháng; đây là ràng buộc hỗ trợ tính đúng dữ liệu.
- Các truy vấn nhận dữ liệu người dùng đều tham số hóa. Tên bảng trong CRUD được giới hạn trong danh sách cho phép.
