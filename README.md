# Bài Tập Lớn: Tích Hợp Zoom API

## Thành viên: 
- **Họ tên**: Vũ Anh Quân  
- **Mã sinh viên**: B21DCCN618

## Mô tả ngắn gọn
Dự án này cung cấp một ứng dụng Node.js giúp tích hợp với Zoom API. Dự án bao gồm hai phần chính:
1. **Máy chủ Express.js** (`server.js`) để xử lý xác thực OAuth và nhận token truy cập từ Zoom.
2. **Client API** (`index.js`) để tương tác với Zoom, thực hiện các tác vụ như lấy danh sách các cuộc họp và tạo mới cuộc họp.

## Công nghệ lựa chọn:
- **Node.js** và **Express.js** để xây dựng máy chủ.
- **Axios** để thực hiện các yêu cầu HTTP tới Zoom API.
- **Zoom OAuth 2.0** để xác thực và lấy token truy cập.
- **Ngrok** để phát triển và kiểm thử webhook sự kiện từ Zoom trong môi trường cục bộ.

## Yêu cầu trước khi bắt đầu

- **Node.js** và **npm** (Node Package Manager)
- **Tài khoản Zoom** có quyền nhà phát triển
- Đã đăng ký ứng dụng OAuth trên Zoom với **Client ID** và **Client Secret**

## Cài đặt

1. **Clone hoặc Tải về Dự án**:
   - Clone dự án từ GitHub hoặc tải và giải nén file dự án.

2. **Cài đặt các Thư viện**:
   - Chạy lệnh sau trong thư mục dự án để cài đặt các thư viện cần thiết:
     ```bash
     npm install
     ```

3. **Thiết lập biến môi trường**:
   - Tạo file `.env` trong thư mục gốc của dự án với các biến sau:
     ```env
     ZOOM_API_KEY=your_zoom_client_id
     ZOOM_API_SECRET=your_zoom_client_secret
     REDIRECT_URI=https://d70e-1-55-255-239.ngrok-free.app/callback
     WEBHOOK_URL=https://d70e-1-55-255-239.ngrok-free.app/webhook
     TOKEN=your_zoom_oauth_token
     ```
   - `ZOOM_API_KEY` và `ZOOM_API_SECRET` lấy từ ứng dụng OAuth trên Zoom.
   - `REDIRECT_URI` và `WEBHOOK_URL` sử dụng URL mà ngrok cung cấp.

## Chạy máy chủ

- Khởi chạy máy chủ Express để xử lý OAuth:
  ```bash
  node server.js
