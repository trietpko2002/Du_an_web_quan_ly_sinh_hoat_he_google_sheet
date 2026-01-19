# 🇻🇳 HỆ THỐNG QUẢN LÝ SINH HOẠT HÈ - CHUYỂN ĐỔI SỐ TOÀN DIỆN (CONCEPT v9.0)

> **❝ Không chỉ là quản lý - Đó là trải nghiệm số hóa đầy cảm hứng cho Thanh niên ❞**

![Badge](https://img.shields.io/badge/Status-Stable-success) ![Badge](https://img.shields.io/badge/Platform-Google_Ecosystem-blue) ![Badge](https://img.shields.io/badge/License-OpenSource-orange) ![Badge](https://img.shields.io/badge/Version-9.0.2-purple)

---

## 🌟 1. Tầm nhìn & Sứ mệnh (The Vision)

Công tác Đoàn và sinh hoạt hè tại địa phương đang đứng trước bài toán lớn: **Làm sao để vừa quản lý chặt chẽ, minh bạch, lại vừa tạo được sự hứng thú, hiện đại trong mắt đoàn viên thanh niên?**

Hệ thống này là câu trả lời. Không còn những file Excel rời rạc, không còn báo cáo giấy thủ công. Đây là giải pháp **"All-in-One"** chạy trên nền tảng Serverless, biến công việc quản lý khô khan thành một trải nghiệm công nghệ thú vị, mang đậm hơi thở của Gen Z.

---

## 🎨 2. Điểm Nhấn Đột Phá: "Đa Vũ Trụ" Giao Diện

Khác biệt hoàn toàn với các phần mềm hành chính cứng nhắc, hệ thống sở hữu **Cơ chế Giao diện Thích ứng (Adaptive Theme Engine)** cực kỳ mạnh mẽ ngay từ màn hình Đăng nhập (`login.html`).

### ✨ Cá nhân hóa trải nghiệm (Personalization)
Hệ thống hiểu và ghi nhớ sở thích người dùng thông qua công nghệ **Local Storage**. Một khi bạn chọn giao diện yêu thích, hệ thống sẽ tự động kích hoạt nó ở những lần đăng nhập sau trên cùng thiết bị.

* **Kho giao diện 20+ Themes:**
    * 🌊 **Thiên nhiên:** Đại dương, Nắng vàng, Mưa rơi (Rain effect), Tuyết trắng.
    * 🚀 **Viễn tưởng:** Galaxy (Sao bay), Cyberpunk (Neon), Matrix (Mưa code xanh).
    * 🎉 **Lễ hội:** Tết Nguyên Đán (Pháo hoa), Trung Thu, Noel.
    * 🔥 **Trendy:** Jack J97 (Đom đóm), Meme Mode.
* **Custom Mode (Mới):** Cho phép người dùng **tự tải lên** ảnh nền hoặc Video (tối đa 50MB) để làm giao diện riêng biệt.

### 🎮 Gamification & Tương tác
* **Audio Experience:** Tích hợp trình phát nhạc ZingMP3 mini ngay trong hệ thống, giúp buổi sinh hoạt thêm sôi động.
* **Interactive UI:** Hiệu ứng con trỏ mèo (Cat paw), pháo hoa khi click chuột, dòng chữ chạy... tạo cảm giác thân thiện, xóa bỏ khoảng cách giữa "người dùng" và "phần mềm".

---

## ⚙️ 3. Kiến Trúc Kỹ Thuật (Technical Stack)

Dự án chứng minh rằng **chi phí 0 đồng** vẫn có thể tạo ra sản phẩm chất lượng cao nhờ tận dụng tối đa hệ sinh thái Google.

* **Backend (Core):** Google Apps Script (GAS) - Xử lý logic phía máy chủ, bảo mật API.
* **Database:** Google Spreadsheet - Real-time, dễ dàng trích xuất, sao lưu và phân quyền.
* **Frontend (Visual):**
    * **UI Framework:** AdminLTE 3.2 + Bootstrap 4 (Responsive Mobile-first).
    * **Logic:** jQuery & Vanilla JS.
    * **Effects Library:** Canvas Confetti (Pháo hoa), Toastr (Thông báo), SweetAlert2 (Popup đẹp mắt).
* **Bảo mật:**
    * Mã hóa MD5 (cơ bản) cho các định danh file.
    * Token xác thực phiên làm việc.

---

## 🚀 4. Hệ Sinh Thái Chức Năng (Ecosystem)

Hệ thống được cấu trúc thành 3 phân hệ kết nối chặt chẽ, đáp ứng nhu cầu của mọi đối tượng:

### A. Phân hệ Tác Nghiệp & Cá Nhân (Manager Workspace)
*Dành cho Bí thư chi đoàn/Phụ trách nhóm.*

* **Trung tâm Điều hành (`index.html`):**
    * **Điểm danh 1 chạm (Smart Attendance):** Tối ưu hóa cho mobile. Hỗ trợ import Excel nếu ấn trên nền web không được.
    * **Quỹ nhóm minh bạch:** Tự động tính toán thu/chi, hiển thị số dư tồn quỹ theo thời gian thực.
    * **Xếp loại:** xếp loại học sinh đầy đủ.
    * **Tiện ích:** Trung tâm tải file, gửi kiến nghị kèm ảnh minh chứng.

* **Quản lý Tài khoản Cá nhân (`profile.html`):** **🆕 MỚI**
    * **Thông tin định danh:** Người quản lý xem và cập nhật thông tin liên hệ, đơn vị công tác của chính mình.
    * **Bảo mật:** Tính năng đổi mật khẩu an toàn, xem nhật ký hoạt động cá nhân để phát hiện đăng nhập lạ.

### B. Phân hệ Giám sát (Supervisor Portal)
*Giao diện: `supervisor.html` & `supervisor_profile.html`*
*Dành cho cấp Quản lý*

* **Real-time Analytics:** Biểu đồ phân tích dữ liệu nhân sự, tỷ lệ chuyên cần của từng khu phố.
* **Deep Inspection (Soi chiếu):** Supervisor có thể truy cập sâu vào hồ sơ chi tiết của bất kỳ học sinh nào (`supervisor_profile.html`) để kiểm tra chéo (Cross-check) độ chính xác của báo cáo từ cấp dưới.
* **Xuất báo cáo 1-Click:** Xuất toàn bộ danh sách, bảng chấm công ra file Excel tiêu chuẩn.

### C. Phân hệ Quản trị (Admin Control)
*Giao diện: `admin.html`*
*Trung tâm kỹ thuật cao nhất.*

* **Chế độ Bảo trì (Maintenance Mode):** Chủ động khóa hệ thống khi cập nhật, hiển thị màn hình chờ.
* **Backup & Restore:** Sao lưu toàn bộ Database về máy cá nhân (JSON) và phục hồi khi cần thiết.
* **Quản lý người dùng:** Phân quyền, thêm/sửa/xóa tài khoản, reset mật khẩu cho các Manager.

---

## 📸 5. Hướng Dẫn Triển Khai (Deployment)

Dễ dàng cài đặt chỉ trong 4 bước - Không cần thuê Server, không cần mua tên miền.

1.  **Khởi tạo Database:** Tạo Google Sheet theo mẫu (Sheet: `users`, `students`, `logs`, `attendance`, v.v...).
2.  **Cài đặt Script:** Copy mã nguồn vào Google Apps Script của Sheet đó.
3.  **Cấu hình:** Thay thế `SPREADSHEET_ID` trong `Code.gs` bằng ID file của bạn.
4.  **Deploy:** Chọn "New Deployment" -> "Web App" -> Access: "Anyone" -> **Lấy link và chạy ngay!**

---

## 💡 6. Tầm nhìn & Tiềm năng mở rộng

Đây không chỉ là một phần mềm, đây là **bước đệm cho Chuyển đổi số** tại địa phương.
* **Mở rộng:** Tích hợp quét mã QR Code để điểm danh không chạm.
* **Kết nối:** Tích hợp Zalo API để gửi thông báo điểm danh về cho phụ huynh.
* **Cộng đồng:** Mã nguồn mở cho phép nhân rộng mô hình sang các đơn vị khác.

> **⚠️ TUYÊN BỐ MIỄN TRỪ TRÁCH NHIỆM:**
> Dự án là sản phẩm thử nghiệm (Proof of Concept) phục vụ cộng đồng. Dữ liệu được lưu trữ trên tài khoản Google của người dùng, đảm bảo quyền riêng tư và kiểm soát dữ liệu tuyệt đối.

---
*Phát triển bởi [Triết Võ] - Tổ Công nghệ Đoàn phường Phan Rang © 2026*
*Liên hệ: [phanranggaming@gmail.com/0396385579]*
