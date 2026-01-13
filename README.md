# ☀️ SUMMER MANAGEMENT SYSTEM (HỆ THỐNG QUẢN LÝ SINH HOẠT HÈ)

Hệ thống quản lý sinh hoạt hè xây dựng trên nền tảng **Web nhẹ (HTML/JavaScript)**, sử dụng **Google Sheets** làm cơ sở dữ liệu và **Google Apps Script (GAS)** làm Backend API.

Mục tiêu của dự án là:
- Dễ triển khai – không cần server riêng
- Phù hợp cho cán bộ Đoàn – quản lý học sinh hè
- An toàn, có phân quyền, nhật ký truy vết
- Tối ưu cho thiết bị di động

---

## 🚀 TÍNH NĂNG CHÍNH

### 🛡️ 1. Đăng nhập & Bảo mật đa lớp
- **Cloudflare Turnstile**: Xác thực người dùng (Human Verification), chống spam & brute-force
- **RBAC – Phân quyền người dùng**
  - **Admin**: Toàn quyền hệ thống, yêu cầu xác thực **2FA (Google Authenticator – TOTP)**
  - **Manager (Quản lý)**: Chỉ truy cập dữ liệu nhóm được phân công
- **Session Management**
  - Kiểm tra quyền truy cập ở mọi trang
  - Chặn truy cập trái phép qua URL

---

### 📊 2. Trang quản trị Admin (`admin.html`)
Giao diện sử dụng **AdminLTE 3**

**Các Tab chức năng:**

1. **Dashboard**
   - Thống kê tổng số học sinh, quản lý, thông báo
   - Biểu đồ điểm danh theo ngày (Chart.js)

2. **Quản lý tài khoản**
   - Thêm / Sửa / Xóa tài khoản Quản lý
   - Reset mật khẩu nhanh về mặc định: `Abc@123`

3. **Quản lý nhóm**
   - Tạo & chỉnh sửa các nhóm sinh hoạt hè
   - Dữ liệu nền cho toàn hệ thống

4. **Cơ sở dữ liệu học sinh**
   - Danh sách tổng học sinh
   - Bộ lọc nâng cao: năm sinh, nhóm, quản lý
   - Xuất báo cáo Excel theo ngày

5. **Nhật ký hệ thống (Audit Logs)**
   - Ghi lại mọi hành động: đăng nhập, thêm/sửa/xóa, điểm danh
   - Phục vụ truy vết & kiểm tra

6. **Quản lý thông báo**
   - Soạn nội dung sinh hoạt hè
   - Thiết lập thời gian mở điểm danh
   - Gửi thông báo đẩy cho Quản lý

---

### 📱 3. Cổng thông tin Quản lý (`index.html`)
Thiết kế **Mobile-first**, thân thiện điện thoại

**Chức năng:**

1. **Điểm danh thông minh**
   - Danh sách học sinh theo nhóm
   - 3 trạng thái nhanh:
     - Có mặt
     - Vắng có lý do
     - Vắng không lý do

2. **Quản lý học sinh nội bộ**
   - Thêm nhanh học sinh mới vào nhóm
   - Cập nhật thông tin cá nhân

3. **Hoạt động & Phản hồi**
   - Nhận thông báo từ Admin
   - Gửi phản ánh qua Google Form (Iframe)
   - Đánh giá – xếp loại học sinh cuối kỳ

---

### 🔔 4. Thông báo & Tương tác
- Chuông thông báo hiển thị số lượng tin chưa đọc
- **Web Push Notification** trên trình duyệt
- Cá nhân hóa giao diện:
  - Lời chào theo tên
  - Avatar người dùng

---

## 🛠️ CÔNG NGHỆ SỬ DỤNG

### Frontend
- HTML5, CSS3
- AdminLTE 3
- JavaScript (ES6+)

### Backend
- Google Apps Script (GAS)

### Database
- Google Sheets API

### Hosting
- **Vercel** (Production)
- **GitHub Pages** (Backup)

### Security
- Cloudflare Turnstile
- TOTP – Google Authenticator (2FA)

### Thư viện hỗ trợ
- DataTables.js – Quản lý bảng
- Chart.js – Biểu đồ
- SheetJS – Xuất Excel
- Toastr.js – Thông báo nhanh

---

## 🗂️ CẤU TRÚC GOOGLE SHEETS

Tạo Google Sheets với các Sheet sau:

| Sheet name | Mô tả |
|-----------|------|
| `users` | Tài khoản Admin / Manager |
| `groups` | Danh sách nhóm sinh hoạt hè |
| `students` | Thông tin học sinh |
| `attendance` | Dữ liệu điểm danh |
| `notifications` | Thông báo hệ thống |
| `logs` | Nhật ký hành động |

---

## ⚙️ HƯỚNG DẪN CÀI ĐẶT NHANH (QUICK START)

### 1️⃣ Google Sheets
- Sao chép file mẫu dữ liệu
- Đặt đúng tên các Sheet như trên

### 2️⃣ Google Apps Script
- Vào **Extensions → Apps Script**
- Dán toàn bộ code vào `Code.gs`
- Deploy:
  - Type: **Web App**
  - Execute as: **Me**
  - Access: **Anyone**
- Sao chép URL Web App

### 3️⃣ Frontend
- Cập nhật biến sau trong `script.js`:
```js
const APPS_SCRIPT_URL = "YOUR_WEB_APP_URL";
```

### 4️⃣ Deploy
- Push source code lên GitHub
- Kết nối repo với **Vercel** và Deploy

---

## 🔐 TÀI KHOẢN MẪU

| Role | Username | Password |
|----|---------|----------|
| Admin | admin | Abc@123 |
| Manager | manager01 | Abc@123 |

> ⚠️ **Khuyến nghị:** Đổi mật khẩu ngay sau khi đăng nhập lần đầu

---

## 📌 LƯU Ý BẢO MẬT
- Không chia sẻ URL Web App GAS công khai
- Bật 2FA cho tài khoản Admin
- Phân quyền đúng nhóm cho Manager
- Sao lưu Google Sheets định kỳ

---


## ❤️ ĐÓNG GÓP

Mọi ý kiến đóng góp, cải tiến vui lòng phản hồi qua GitHub hoặc qua Email: phanranggaming@gmail.com
---

🌻 **Chúc hệ thống sinh hoạt hè của Đoàn Phường vận hành hiệu quả – minh bạch – hiện đại!**

