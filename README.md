# Bài 3 - Cấu hình xác thực SSH và Đẩy dự án lên GitHub

## 1. Mục tiêu

- Khởi tạo cặp khóa SSH sử dụng thuật toán Ed25519.
- Cấu hình xác thực SSH với GitHub.
- Liên kết repository cục bộ với GitHub bằng giao thức SSH.
- Đẩy mã nguồn và lịch sử commit lên GitHub.

## 2. Tạo SSH Key Ed25519

Sử dụng lệnh:

```bash
ssh-keygen -t ed25519 -C "latp1102@gmail.com"

