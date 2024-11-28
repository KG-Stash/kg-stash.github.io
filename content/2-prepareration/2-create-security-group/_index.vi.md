+++
title = "Create Security Group"
date = 2024
weight = 2
chapter = false
pre = "<b>2.2 </b>"
+++

### Cấu hình Security Group

**Cấu hình Security Group cho EC2 Instance**

1. Trong giao diện quản lý VPC, hãy chọn tùy chọn bên trái.
   - Chọn **Security Group**
   - Chọn **Create Security Group**

![Security Group](/images/2/2_2/1.png?width=90pc)

- Cấu hình cho Security Group
- Trong phần **Basic details**
  - Đặt tên cho Security group: `FCJ-Lab-sg-public`
  - Mô tả Security group: `Security group for FCJ Lab`
  - VPC: **FCJ-Lab-vpc**

![Basic details](/images/2/2_2/2.png?width=90pc)

2. Trong phần Inbound rules
   Chúng ta sẽ thêm các quy tắc sau:
   - Nhập **SSH** source **Anywhere-IPv4**
   - Nhập **HTTP** source **Anywhere-IPv4**
   - Nhập **HTTPS** source **Anywhere-IPv4**
   - Nhập **Custom TCP**, port range **3000**, source **Anywhere-IPv4**

![Inbound rules](/images/2/2_2/3.png?width=90pc)

- Trong phần Outbound Rule, chúng ta sẽ để mặc định
- Nhấp vào **Create security group**

**Cấu hình Security Group cho database instance**

3. Tương tự như bước tạo security group cho EC2 ở trên. Cấu hình cho Security Group DB
   - Trong phần Basic details
     - Tên security group: `FCJ-Lab-sg-db`
     - Mô tả **Security group for RDS database instance**
     - VPC **FCJ-Lab-vpc**
   - Trong phần Inbound
     - Chọn Type **MYSQL/Aurora**
     - Source chọn **FCJ-Lab-sg**
     - Trong phần **Outbound**. Chúng ta để nguyên mặc định

![Inbound rules](/images/2/2_2/4.png?width=90pc)

- Chọn **Create security group**

![Inbound rules](/images/2/2_2/5.png?width=90pc)
