# Báo cáo tuần - Tuần 02 (Networking Fundamentals - VPC)

## 1. Thông tin chung
- **Tuần:** 02  
- **Chủ đề:** AWS Networking Fundamentals (VPC)  
- **Thời gian thực hiện:** Từ ngày ... đến ngày ...  
- **Dịch vụ AWS chính:** VPC, Subnet, Route Table, Internet Gateway, Security Group, EC2 (Windows Server)  
- **Region thực hành:** us-east-1  

---

## 2. Mục tiêu tuần
- Hiểu kiến trúc mạng cơ bản trên AWS và cách AWS quản lý hệ thống mạng nội bộ.
- Thực hành tạo VPC custom và chia subnet theo mô hình Public/Private.
- Thiết lập Internet Gateway và Route Table để public subnet truy cập Internet.
- Deploy EC2 Windows Server trong public subnet và kiểm tra truy cập Remote Desktop (RDP).
- Thực hành cấu hình Security Group để mở port phù hợp và đảm bảo bảo mật.

---

## 3. Nội dung đã học

### 3.1 Kiến thức lý thuyết
- **VPC (Virtual Private Cloud)** là một mạng riêng ảo trên AWS cho phép triển khai tài nguyên cloud trong một môi trường mạng riêng biệt.
- **CIDR (Classless Inter-Domain Routing)** dùng để định nghĩa phạm vi IP cho VPC và subnet.
- **Subnet** là một mạng con trong VPC.
- **Public Subnet** là subnet có route ra Internet Gateway, cho phép tài nguyên bên trong truy cập Internet và được truy cập từ bên ngoài.
- **Private Subnet** là subnet không có route trực tiếp ra Internet Gateway, thường dùng cho database hoặc hệ thống nội bộ.
- **Internet Gateway (IGW)** là thành phần cho phép kết nối giữa VPC và Internet.
- **Route Table** quyết định hướng đi của traffic trong VPC.
- **Security Group** hoạt động như firewall cấp instance, kiểm soát inbound/outbound traffic.
- **EC2 Instance** là máy chủ ảo trên AWS, có thể triển khai Windows Server hoặc Linux.

### 3.2 Dịch vụ AWS đã tìm hiểu
- Amazon VPC
- Subnet (Public / Private)
- Internet Gateway
- Route Table
- Security Group
- Amazon EC2 (Windows Server)
- Remote Desktop Protocol (RDP)

---

## 4. Nội dung thực hành (Hands-on)

### 4.1 Các bước triển khai hệ thống mạng
- Tạo VPC custom với CIDR: `10.0.0.0/16`
- Tạo 2 subnet:
  - Public Subnet: `10.0.1.0/24`
  - Private Subnet: `10.0.2.0/24`
- Tạo Internet Gateway và attach vào VPC.
- Thiết lập Route Table cho public subnet:
  - Add route: `0.0.0.0/0 → Internet Gateway`
  - Associate route table vào public subnet.

### 4.2 Deploy EC2 Windows Server
- Launch EC2 Windows Server trong public subnet.
- Enable Auto-assign public IPv4 address.
- Tạo Security Group cho instance và mở các rule:
  - RDP (TCP 3389) cho phép truy cập từ máy cá nhân.
- Truy cập Windows Server bằng Remote Desktop Connection.
- Kiểm tra kết nối Internet trên Windows Server bằng Microsoft Edge.

---

## 5. Kết quả đạt được
- ✅ Tạo thành công VPC custom với CIDR phù hợp.
- ✅ Tạo thành công public subnet và private subnet.
- ✅ Thiết lập Internet Gateway và route table để public subnet có thể truy cập Internet.
- ✅ Deploy thành công EC2 Windows Server trong public subnet.
- ✅ Remote Desktop (RDP) vào instance thành công.
- ✅ Kiểm tra truy cập Internet trong Windows Server thành công.

---

## 6. Khó khăn gặp phải và cách xử lý

| Khó khăn | Nguyên nhân | Cách xử lý |
|---------|------------|-----------|
| Không kết nối được Remote Desktop (Error 0x204) | Instance được triển khai nhầm vào private subnet hoặc chưa mở port 3389 | Kiểm tra subnet/route table và security group, đảm bảo instance nằm trong public subnet và mở port RDP |
| Không truy cập được RDP do IP bị chặn | Security Group chỉ allow một IP cũ trong khi IP mạng thay đổi | Thay đổi inbound rule thành My IP hoặc test tạm 0.0.0.0/0 |
| Chưa hiểu rõ public subnet hoạt động thế nào | Chưa phân biệt rõ route table của subnet | Kiểm tra route `0.0.0.0/0 → IGW` để xác định subnet public |

---

## 7. Kinh nghiệm rút ra
- Việc phân biệt public subnet và private subnet phụ thuộc chủ yếu vào **Route Table** và route ra Internet Gateway.
- Khi triển khai EC2 để truy cập từ Internet, cần đảm bảo:
  - Subnet phải là public subnet
  - Instance có Public IPv4 address
  - Security Group mở đúng port (RDP 3389 hoặc SSH 22)
- AWS Security Group nên giới hạn nguồn truy cập (My IP) để tránh rủi ro bảo mật.
- Khi gặp lỗi kết nối, nên kiểm tra theo thứ tự:
  1. Public IP của instance
  2. Security Group inbound rule
  3. Route table của subnet
  4. Internet Gateway đã attach chưa

---

## 8. Kế hoạch tuần tiếp theo
- Tìm hiểu Compute & Storage trên AWS: EC2, S3, RDS.
- Thực hành tạo EC2 web server và lưu trữ dữ liệu trên S3.
- Làm quen với RDS database và kiểm tra kết nối từ EC2.

---

## 9. Minh chứng (Screenshots)

### 9.1 VPC và Subnet
![VPC Created](/screenshot/vpc-created.png)  
![Subnet List](/screenshot/subnet-created.png)  
![Public Subnet](/screenshot/subnet-created.png)  
![Private Subnet](/screenshot/subnet-created.png)

### 9.2 Internet Gateway và Route Table
![IGW Attached](./screenshots/igw-attached.png)  
![Route Table Public](./screenshots/route-table-public.png)  
![Route Table Association](./screenshots/route-table-association.png)  

### 9.3 Security Group và EC2
![Security Group RDP](/screenshot/security-group.png)  
![EC2 Running](/screenshot/ec2-running.png)  

### 9.4 Remote Desktop và Test Internet
![Windows Desktop](/screenshot/window-desktop.png)  
