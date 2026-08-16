# NhiemVuApp-GitHub-FULL

Đây là bản chuyển đổi **đúng theo 1.gs bạn cung cấp**: GitHub Pages là giao diện, Google Apps Script Web App là API, Google Sheets hiện tại là nơi lưu dữ liệu.

## 1. Google Apps Script
Mở chính Google Sheet đang dùng → Extensions → Apps Script. Có thể thay nội dung `Code.gs` bằng `gas/Code.gs` trong ZIP.

Không cần tạo Google Sheet mới. Code sử dụng `SpreadsheetApp.getActiveSpreadsheet()` giống file gốc.

Deploy → New deployment → Web app:
- Execute as: Me
- Who has access: Anyone
- Copy URL `/exec`

## 2. GitHub Pages
Mở `js/config.js`, thay:
`const API_URL = "DAN_URL_WEB_APP_CUA_BAN";`
bằng URL `/exec`.

Đưa toàn bộ thư mục lên repository GitHub. Settings → Pages → Deploy from branch → `main` → `/ (root)`.

## 3. Google Sheet được giữ nguyên
Theo 1.gs gốc:
- CBPT: phân công cho HKCCH, MaTuy, ĐCTTP
- Bang_Phan_Cong_2: phân công đất đai
- HKCCH
- MaTuy
- ĐCTTP
- TongHop

Các cột và vị trí đọc/ghi vẫn theo 1.gs gốc: HKCCH/MaTuy ghi trạng thái cột 11; ĐCTTP ghi cột 3; TongHop ghi cột 13,14,15.

## 4. Lưu ý bảo mật
Web App đặt `Anyone` nghĩa là URL API có thể được gọi bởi người biết URL. Nếu dữ liệu nhạy cảm, nên thêm lớp đăng nhập/kiểm tra người dùng trước khi triển khai thực tế.
