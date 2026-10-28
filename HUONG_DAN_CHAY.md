# HƯỚNG DẪN CÀI ĐẶT VÀ CHẠY DỰ ÁN TRÊN MÁY TÍNH CỦA BẠN

Chào bạn! Đây là toàn bộ mã nguồn của dự án OpenClaw Playground & API Key Studio.

## 1. Yêu cầu hệ thống:
- Đã cài đặt Node.js (phiên bản 18 trở lên): https://nodejs.org
- Trình soạn thảo mã nguồn: Visual Studio Code (hoặc bất kỳ IDE nào bạn thích).

## 2. Các bước khởi chạy dự án:
1. Giải nén file zip này vào thư mục trên máy tính của bạn (VD: `C:\openclaw-project` hoặc `~/openclaw-project`).
2. Mở thư mục này bằng VS Code hoặc mở Terminal (PowerShell / Command Prompt) tại thư mục này.
3. Cài đặt các gói thư viện cần thiết:
   ```bash
   npm install
   ```
4. Cấu hình biến môi trường:
   - Tạo file `.env` (hoặc sao chép từ `.env.example`):
     ```env
     GEMINI_API_KEY="Điền_khóa_Gemini_của_bạn_ở_đây"
     PORT=3000
     ```
5. Khởi động ứng dụng:
   ```bash
   npm run dev
   ```
6. Mở trình duyệt web và truy cập:
   ```
   http://localhost:3000
   ```

Chúc bạn có trải nghiệm tuyệt vời khi tự mình khám phá và chạy OpenClaw trên máy tính cá nhân!
