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
```

SSH key được tạo gồm:

- Private key: `~/.ssh/id_ed25519`
- Public key: `~/.ssh/id_ed25519.pub`

Fingerprint của SSH key:

`SHA256:VNh0g5HOl1N4aHp0nU6PAdqJFK88bJIVn8fDNBE5C9k`

Private key không được đưa lên GitHub.

## 3. Cấu hình SSH với GitHub

Public key `id_ed25519.pub` được thêm vào GitHub tại:

`Settings → SSH and GPG keys`

Tên SSH key:

`Ubuntu - IT209`

Sau khi thêm SSH key, kiểm tra kết nối bằng:

```bash
ssh -T git@github.com
```

Kết quả xác thực thành công:

```text
Hi latp1102! You've successfully authenticated, but GitHub does not provide shell access.
```

## 4. Cấu hình Remote Repository

Repository GitHub:

```text
git@github.com:latp1102/CNTT1_IT209_Session04_b3.git
```

Kiểm tra remote bằng:

```bash
git remote -v
```

Kết quả:

```text
origin  git@github.com:latp1102/CNTT1_IT209_Session04_b3.git (fetch)
origin  git@github.com:latp1102/CNTT1_IT209_Session04_b3.git (push)
```

Remote sử dụng giao thức SSH.

## 5. Commit và Push dự án

Thực hiện các lệnh:

```bash
git add .
git commit -m "Configure SSH authentication and GitHub remote"
git branch -M main
git push -u origin main
```

Sau khi push thành công, mã nguồn và lịch sử commit được đẩy lên GitHub.

## 6. Kiểm tra trạng thái

Kiểm tra trạng thái repository bằng:

```bash
git status
```

Kiểm tra lịch sử commit bằng:

```bash
git log --oneline
```

## 7. Repository GitHub

https://github.com/latp1102/CNTT1_IT209_Session04_b3

## 8. Kết luận

Đã tạo SSH key sử dụng thuật toán Ed25519, cấu hình xác thực SSH với GitHub, liên kết repository cục bộ bằng remote SSH và đẩy dự án lên GitHub.

Private key không được đưa lên repository.
