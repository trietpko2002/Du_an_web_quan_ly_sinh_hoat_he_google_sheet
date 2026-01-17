HỆ THỐNG QUẢN LÝ SINH HOẠT HÈ (SUMMER ACTIVITY MANAGEMENT SYSTEM)

Phần mềm nền tảng web (Web-based Application) được xây dựng để hỗ trợ công tác quản lý, điểm danh, đánh giá và báo cáo hoạt động sinh hoạt hè tại địa phương. Hệ thống sử dụng công nghệ Serverless của Google Apps Script kết hợp với giao diện AdminLTE hiện đại.

🚀 TỔNG QUAN CÔNG NGHỆ
Backend:
- Google Apps Script (GAS)
- Dữ liệu lưu trữ và đồng bộ trực tiếp trên Google Sheets

Frontend:
- HTML5, CSS3, JavaScript

Framework / Library:
- UI/UX: Bootstrap 4, AdminLTE 3.2.0
- Xử lý dữ liệu: jQuery 3.6.0, SheetJS (XLSX)
- Biểu đồ & Báo cáo: Chart.js
- Tiện ích: SweetAlert2, Toastr, Canvas Confetti, PDFMake

PWA (Progressive Web App):
- Hỗ trợ Service Worker (sw.js)
- Cache dữ liệu, hoạt động ngoại tuyến cơ bản

🛠 PHÂN HỆ CHỨC NĂNG CHI TIẾT

Hệ thống được chia thành 3 phân hệ chính tương ứng với 3 nhóm quyền hạn:
Admin (Quản trị viên), Supervisor (Giám sát), Manager (Quản lý nhóm)

────────────────────────────────
1. PHÂN HỆ QUẢN TRỊ (ADMIN DASHBOARD)
────────────────────────────────
Tệp nguồn: admin.html, code.gs

Chức năng chính:
- Dashboard thống kê tổng quan:
  + Tổng số học sinh
  + Trạng thái điểm danh (Có mặt / Vắng phép / Không phép)
  + Số lượng quản lý, nhóm sinh hoạt
  + Biểu đồ phân bố học sinh theo nhóm, theo trường
  + Biểu đồ biến động điểm danh theo thời gian thực

- Quản lý dữ liệu học sinh:
  + Thêm / Sửa / Xóa (CRUD)
  + Import Excel danh sách học sinh (tự động kiểm tra trùng)
  + Duyệt đăng ký học sinh tạm thời

- Quản lý tài khoản (Managers):
  + Tạo tài khoản, phân quyền (Admin / Supervisor / Manager)
  + Hệ thống vinh danh VIP (VIP 1 → VIP 10)
  + Reset mật khẩu
  + Theo dõi lần đăng nhập cuối

- Cấu hình hệ thống:
  + Bật/Tắt chế độ bảo trì (Maintenance Mode)
  + Hẹn giờ bảo trì tự động
  + Nhạc nền bảo trì
  + Marquee chữ chạy
  + Hiệu ứng thời tiết (Mưa / Tuyết / Nắng)
  + Dark Mode
  + Giới hạn dung lượng upload
  + Khóa nhập liệu học sinh

- Sao lưu & Phục hồi:
  + Backup toàn bộ dữ liệu Google Sheets ra Excel
  + Restore dữ liệu từ file backup (có Captcha xác thực)

- Thông báo & Bình chọn:
  + Đăng thông báo chung (đính kèm file)
  + Ghim thông báo khẩn cấp (Banner / Troll Mode)
  + Tạo bình chọn (Poll)

────────────────────────────────
2. PHÂN HỆ GIÁM SÁT (SUPERVISOR)
────────────────────────────────
Tệp nguồn: supervisor.html, supervisor_profile.html

Chức năng:
- Theo dõi điểm danh tất cả các nhóm
- Lọc theo ngày, trạng thái
- Xuất báo cáo:
  + Lịch sử hoạt động (.xlsx)
  + Danh sách học sinh toàn phường
- Quản lý file:
  + Xem, tải tài liệu do Admin/Manager upload
- Theo dõi bảng đánh giá, xếp loại học sinh

────────────────────────────────
3. PHÂN HỆ QUẢN LÝ NHÓM (MANAGER CLIENT)
────────────────────────────────
Tệp nguồn: index.html, profile.html

Chức năng:
- Điểm danh thông minh:
  + Điểm danh theo ngày
  + Import điểm danh từ Excel

- Quản lý học sinh nhóm:
  + Danh sách học sinh nhóm phụ trách
  + Chỉnh sửa thông tin
  + Chuyển nhóm

- Quản lý quỹ:
  + Tự động tính tổng quỹ
  + Ghi sổ Thu / Chi (log)
  + Xuất báo cáo tài chính ra Excel

- Đánh giá & xếp loại:
  + Tiêu chí: Kỷ luật, Tích cực, Tình nguyện
  + Tự động xếp loại: Xuất sắc / Tốt / Trung bình / Yếu

- Phản ánh & kiến nghị:
  + Gửi yêu cầu hỗ trợ
  + Đính kèm hình ảnh minh chứng

- Trung tâm tải file:
  + Upload tài liệu, hình ảnh
  + Gửi link Google Drive cho Admin

🔐 BẢO MẬT & TIỆN ÍCH (BACKEND code.gs)
- Xác thực Username / Password
- Phân quyền theo vai trò
- Chống brute-force (khóa tạm sau >10 lần sai)
- Ghi nhận User Agent
- Mã hóa MD5 cho file upload
- Captcha cho hành động nhạy cảm
- Logging toàn bộ hành động hệ thống
- Tự động xóa file tạm sau 7–30 ngày
- Đồng bộ trạng thái “Đã xem” thông báo

✨ HIỆU ỨNG GIAO DIỆN ĐẶC BIỆT
- Easter Eggs (Confetti, Jack97 mode)
- Weather Overlay (Mưa / Tuyết / Nắng)
- VIP Frames (CSS Animation khung avatar)

📂 CẤU TRÚC DỮ LIỆU GOOGLE SHEETS
- users
- students
- attendance
- groups
- logs
- settings
- notifications
- feedback
- evaluations
- fund_logs
- uploads
