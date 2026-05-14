# Báo cáo tuần - Tuần 01 (Nền tảng AWS & IAM)

## 1. Thông tin chung
- **Tuần:** 01  
- **Chủ đề:** Nền tảng AWS & IAM  
- **Thời gian thực hiện:** Từ ngày 17/4/2026  đến ngày 26/4/2026
- **Dịch vụ AWS chính:** IAM, MFA, Billing, AWS Budgets  

---

## 2. Mục tiêu tuần
- Làm quen tổng quan AWS Cloud và lộ trình AWS Cloud Journey.
- Thiết lập tài khoản AWS và cấu hình bảo mật cơ bản.
- Tìm hiểu IAM và cách quản lý quyền truy cập.
- Thiết lập kiểm soát chi phí để tránh phát sinh phí ngoài ý muốn.

---

## 3. Nội dung đã học

### 3.1 Kiến thức lý thuyết
- Tổng quan AWS Cloud, AWS Management Console.
- AWS Global Infrastructure: Region, Availability Zone, Edge Location.
- AWS Shared Responsibility Model (mô hình trách nhiệm chia sẻ).
- Tổng quan về IAM và nguyên tắc phân quyền.
- Best practices khi quản lý tài khoản AWS:
  - Không dùng Root account thường xuyên
  - Bật MFA ngay từ đầu
  - Phân quyền theo nhóm (Group) thay vì gán trực tiếp vào User

### 3.2 Dịch vụ AWS đã tìm hiểu
- AWS IAM (Identity and Access Management)
- Billing Dashboard
- AWS Budgets

---

## 4. Nội dung thực hành (Hands-on)

### 4.1 Các bài lab/workshop đã thực hiện
- Tạo AWS account và đăng nhập AWS Console.
- Tạo IAM User và gán quyền truy cập.
- Bật MFA để tăng bảo mật tài khoản.
- Tạo IAM Group (Admin, Developer, ReadOnly).
- Thực hành tạo IAM Policy cơ bản.
- Thiết lập AWS Budgets và Billing Alerts.

### 4.2 Các bước cấu hình / triển khai
- Tạo IAM User riêng để sử dụng thay cho Root account.
- Cấu hình MFA để tăng độ an toàn.
- Tạo group và gán policy theo từng nhóm.
- Thiết lập cảnh báo chi phí để tránh vượt quá Free Tier.

---

## 5. Kết quả đạt được
- ✅ Tạo và cấu hình tài khoản AWS thành công.
- ✅ Thiết lập IAM User và IAM Group hoàn chỉnh.
- ✅ Bật MFA cho tài khoản để tăng bảo mật.
- ✅ Tạo IAM Policy và thử nghiệm quyền truy cập.
- ✅ Thiết lập AWS Budgets và Billing Alerts.

---

## 6. Khó khăn gặp phải và cách xử lý

| Khó khăn | Nguyên nhân | Cách xử lý |
|---------|------------|-----------|
| MFA lỗi hoặc không nhận mã | Lỗi đồng bộ thiết bị hoặc nhập sai mã | Thử lại, kiểm tra thời gian thiết bị, cấu hình lại MFA |
| Chưa hiểu rõ policy JSON | IAM policy có nhiều rule và condition | Đọc thêm AWS docs và thử tạo policy đơn giản trước |

---

## 7. Kinh nghiệm rút ra
- IAM là phần quan trọng nhất trong AWS vì liên quan trực tiếp đến bảo mật hệ thống.
- Việc bật MFA và hạn chế sử dụng Root account giúp giảm nguy cơ bị tấn công.
- Quản lý quyền theo nhóm sẽ dễ kiểm soát và tránh sai sót hơn so với gán trực tiếp cho user.
- Nên thiết lập Budgets và cảnh báo chi phí ngay từ đầu để tránh mất tiền ngoài ý muốn.

---

## 8. Kế hoạch tuần tiếp theo
- Tìm hiểu Networking trên AWS: VPC, Subnet, Route Table, Internet Gateway.
- Thực hành tạo VPC custom và triển khai EC2 trong public subnet.
- Thực hành cấu hình Security Group và Network ACL.
- Vẽ sơ đồ kiến trúc mạng cơ bản.

---

## 9. Minh chứng

### Ảnh cấu hình IAM User
![IAM User](/week-01-foundation/screenshot/)

### Ảnh bật MFA
![MFA](/week-01-foundation/screenshot/MFA.png)

### Ảnh AWS Budgets
![Budgets](/week-01-foundation/screenshot/image.png)