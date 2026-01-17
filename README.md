# 🇻🇳 HỆ THỐNG QUẢN LÝ SINH HOẠT HÈ - SỐ HÓA & TỰ ĐỘNG HÓA (CONCEPT v8.0)

> **⚠️ TUYÊN BỐ MIỄN TRỪ TRÁCH NHIỆM (DISCLAIMER):**
> Đây là dự án mã nguồn mở mang tính chất **Thử nghiệm Ý tưởng (Proof of Concept)**. Phần mềm được xây dựng nhằm mục đích nghiên cứu giải pháp Chuyển đổi số (Digital Transformation) trong công tác đoàn thể tại địa phương. 
> *Dự án chưa phải là sản phẩm thương mại chính thức.*

---

## 📖 1. Tổng quan Dự án

Trong bối cảnh công tác quản lý sinh hoạt hè tại địa phương thường gặp nhiều khó khăn với hồ sơ giấy tờ, khó kiểm soát số lượng học sinh thực tế và minh bạch tài chính, **Hệ thống Quản lý Sinh hoạt Hè (Summer Activity Management System)** ra đời như một giải pháp toàn diện "All-in-One".

Hệ thống hoạt động trên nền tảng Web (Web-based), không cần cài đặt, tương thích mọi thiết bị (PC, Laptop, Smartphone, Tablet), giúp kết nối liền mạch giữa:
1.  **Ban Chỉ đạo (Admin):** Quản trị hệ thống, cấu hình toàn cục.
2.  **Cấp Quản lý/Giám sát (Supervisor):** Theo dõi tiến độ, báo cáo số liệu.
3.  **Phụ trách nhóm/Chi đoàn (Manager):** Thực hiện nghiệp vụ hàng ngày.

---

## ⚙️ 2. Kiến trúc Kỹ thuật (Technical Architecture)

Hệ thống được xây dựng theo mô hình **Serverless** hiện đại, tận dụng sức mạnh của hệ sinh thái Google:

* **Backend:** Google Apps Script (GAS) - Xử lý logic phía máy chủ, API endpoints.
* **Database:** Google Spreadsheet - Cơ sở dữ liệu thời gian thực (Real-time), dễ dàng truy xuất và sao lưu.
* **Frontend UI/UX:** * **AdminLTE 3.2.0:** Giao diện quản trị chuyên nghiệp, chuẩn Responsive.
    * **Bootstrap 4:** Hệ thống Grid và Components.
    * **jQuery 3.6.0:** Xử lý sự kiện và DOM.
* **Libraries & Modules:**
    * `SheetJS (XLSX)`: Đọc/Ghi file Excel trực tiếp trên trình duyệt.
    * `Chart.js`: Vẽ biểu đồ thống kê động.
    * `SweetAlert2` & `Toastr`: Hệ thống thông báo người dùng thân thiện.
    * `Canvas Confetti`: Hiệu ứng đồ họa tương tác.

---

## 🚀 3. Phân hệ Chức năng Chi tiết

### A. Phân hệ Dành cho Phụ trách Nhóm (Manager Client)
*Giao diện: `index.html` - Nơi diễn ra các hoạt động nghiệp vụ hàng ngày.*

1.  **Điểm danh Thông minh (Smart Attendance):**
    * **Giao diện One-Touch:** Điểm danh nhanh bằng cách chạm (Có mặt / Vắng phép / Không phép).
    * **Import Excel:** Hỗ trợ tải lên file danh sách điểm danh offline nếu mất mạng, hệ thống tự động đồng bộ.
    * **Validation:** Chặn việc điểm danh trùng lặp trong cùng một ngày.

2.  **Quản lý Quỹ Đội/Nhóm (Fund Management):**
    * **Sổ Thu/Chi điện tử:** Ghi lại chi tiết từng giao dịch (Thu tiền áo, chi mua nước, liên hoan...).
    * **Tự động tính toán:** Hệ thống tự động cộng dồn số dư (Balance) dựa trên dòng tiền vào/ra.
    * **Minh bạch hóa:** Mọi thành viên trong nhóm đều có thể xem báo cáo quỹ (nếu được cấp quyền).

3.  **Đánh giá & Xếp loại Thi đua:**
    * Đánh giá học sinh dựa trên 3 tiêu chí cốt lõi: *Ý thức kỷ luật*, *Sự nhiệt tình*, *Tham gia phong trào*.
    * Thuật toán tự động xếp loại (Xuất sắc, Tốt, Khá, TB, Yếu) dựa trên điểm số nhập vào.

4.  **Hệ thống Phản hồi & Tiện ích:**
    * **Gửi kiến nghị:** Cho phép Manager gửi yêu cầu hỗ trợ hoặc báo cáo sự cố kèm **ảnh chụp minh chứng** trực tiếp lên Admin.
    * **Trung tâm tải xuống:** Truy cập kho tài liệu, nhạc sinh hoạt, hướng dẫn do Admin cung cấp.

---

### B. Phân hệ Dành cho Cấp Quản lý (Supervisor Portal)
*Giao diện: `supervisor.html` - Công cụ giám sát dành cho Lãnh đạo.*

1.  **Dashboard Giám sát (Overview):**
    * Xem tổng quan tình hình nhân sự toàn phường/xã.
    * Biểu đồ phân bổ học sinh theo từng nhóm/khu phố.
    * Theo dõi nhật ký hoạt động (Logs): Biết chính xác ai vừa đăng nhập, ai vừa sửa dữ liệu vào thời gian nào.

2.  **Báo cáo & Xuất dữ liệu (Reporting):**
    * **Xuất Lịch sử Điểm danh:** Tạo file Excel (`.xlsx`) chi tiết từng ngày, từng buổi của tất cả các nhóm chỉ với 1 cú click.
    * **Danh sách trích ngang:** Xuất danh sách toàn bộ học sinh kèm thông tin phụ huynh, số điện thoại để liên hệ khẩn cấp.

3.  **Kiểm tra chéo:**
    * Xem chi tiết bảng đánh giá thi đua của từng nhóm để đảm bảo công bằng trong xét duyệt khen thưởng cuối hè.

---

### C. Phân hệ Quản trị Hệ thống (Admin Control Panel)
*Giao diện: `admin.html` - Trung tâm điều hành cao nhất.*

1.  **Quản lý Vòng đời Dữ liệu (CRUD):**
    * Thêm/Sửa/Xóa tài khoản người dùng và hồ sơ học sinh.
    * **Smart Import:** Nhập danh sách học sinh từ Excel với cơ chế **chống trùng lặp thông minh** (so sánh Họ tên + Năm sinh).

2.  **Cấu hình Hệ thống Nâng cao (System Config):**
    * **Chế độ Bảo trì (Maintenance Mode):** Khóa truy cập toàn hệ thống khi cần nâng cấp, hiển thị màn hình chờ với nhạc nền tùy chỉnh.
    * **Hiệu ứng Giao diện (Visual Effects):** Tùy chỉnh hiệu ứng rơi (Tuyết, Mưa, Lá, Pháo hoa) hoặc chế độ đặc biệt (Jack97 Mode - Dark theme + Fireflies) để tạo hứng thú cho người dùng trẻ.
    * **Hệ thống Vinh danh (VIP System):** Cấp khung Avatar động (CSS Animations) cho các Manager tích cực (VIP 1 -> VIP 10).

3.  **An toàn & Bảo mật (Security):**
    * **Backup & Restore:** Sao lưu toàn bộ Database về máy cá nhân và phục hồi khi cần thiết (Yêu cầu mã Captcha xác thực).
    * **Anti-Brute Force:** Tự động khóa tài khoản tạm thời nếu nhập sai mật khẩu quá 5 lần liên tiếp.
    * **Mã hóa:** Tên file upload được mã hóa MD5 để bảo mật đường dẫn.

---

## 📸 4. Hướng dẫn Cài đặt & Triển khai (Deployment Guide)

Do hệ thống chạy trên Google Apps Script, quy trình cài đặt hoàn toàn miễn phí:

### Bước 1: Chuẩn bị Cơ sở dữ liệu
1.  Tạo một file **Google Sheet** mới.
2.  Đổi tên file tùy ý (Ví dụ: `DB_QuanLyHe_2026`).
3.  Tạo các Sheet con (Tab) với tên chính xác như sau:
    * `users`, `students`, `attendance`, `groups`
    * `logs`, `settings`, `notifications`, `feedback`
    * `evaluations`, `fund_logs`, `uploads`

### Bước 2: Thiết lập Backend (Script)
1.  Từ Google Sheet, chọn menu **Extensions (Tiện ích mở rộng)** > **Apps Script**.
2.  Copy nội dung file `code.gs` vào trình soạn thảo `Code.gs`.
3.  **QUAN TRỌNG:** Tại dòng đầu tiên của `code.gs`, thay đổi biến `SPREADSHEET_ID` thành ID của file Google Sheet bạn vừa tạo.

### Bước 3: Thiết lập Frontend (Giao diện)
1.  Tạo các file HTML trong Apps Script với tên tương ứng: `index`, `admin`, `supervisor`, `dashboard`, `profile`, `login`.
2.  Copy mã nguồn từ các file `.html` đã cung cấp vào các file tương ứng trong Apps Script.

### Bước 4: Triển khai (Deploy)
1.  Nhấn nút **Deploy** (màu xanh) > **New deployment**.
2.  Chọn loại: **Web App**.
    * *Description:* Phiên bản 1.0
    * *Execute as:* **Me** (Email của bạn).
    * *Who has access:* **Anyone** (Bất kỳ ai cũng có thể truy cập - Hệ thống sẽ bảo mật bằng trang Đăng nhập).
3.  Copy đường link `Web App URL` được cấp và gửi cho các quản lý nhóm.

---

## 🔒 5. Chính sách Bảo mật & Quyền riêng tư
* Dữ liệu học sinh chỉ được lưu trữ trên Google Sheet của chính người tạo (Admin), không gửi về máy chủ thứ 3.
* Mật khẩu người dùng (nếu có lưu) cần được Admin quản lý chặt chẽ.
* Khuyến cáo không chia sẻ quyền chỉnh sửa (Editor) file Google Sheet cho người lạ.

---

## 🤝 6. Đóng góp & Phát triển
Dự án được phát triển với tinh thần vì cộng đồng. Nếu bạn là lập trình viên (Developer), bạn có thể đóng góp bằng cách:
1.  Tối ưu hóa thuật toán load dữ liệu (`doGet`).
2.  Nâng cấp giao diện Mobile-first tốt hơn.
3.  Thêm tính năng thông báo qua Email/Zalo.

**Credit:**
* Template: AdminLTE.io
* Icons: FontAwesome 5
* Excel Engine: SheetJS

---
*Generated by [Tên Bạn] - Phiên bản Tài liệu 2.0 (Detailed Edition)*
