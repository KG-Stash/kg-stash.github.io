+++
title = "Cấu hình VPC"
date = 2024
weight = 1
chapter = false
pre = "<b>2.1 </b>"
+++

### Cấu hình VPC

1. Ở giao diện AWS console thực hiện
   - Tìm kiếm và chọn VPC

![VPC Search](/images/2/2_1/1.png?width=90pc)

2. Ở giao diện quản lý VPC
   - Chọn **Your VPC**
   - Chọn **Create VPC**

![VPC Search](/images/2/2_1/2.png?width=90pc)

3. Xuất hiện bảng cấu hình cho VPC
   - Chọn **VPC and more**
   - Đặt tên `FCJ-Lab`

![VPC Search](/images/2/2_1/3.png?width=90pc)

- Chọn **Availability Zones (AZs)**: **2**
- Chọn **public subnets**: **2**
- Chọn **private subnets**: **2**

- Ở phần **VPC endpoint**
  - Chọn **None**
  - Chọn **Create VPC**

![VPC Search](/images/2/2_1/4.png?width=90pc)

4. Sau khi tạo xong VPC, chúng ta tiến hành kiểm tra thông tin VPC vừa tạo.
   - Chọn **FCJ-Lab-vpc** vừa tạo để xem tổng quan

![VPC Search](/images/2/2_1/5.png?width=90pc)

5. Cấu hình Public Subnet
   Ở giao diện quản lý VPC, ở mục chọn ở bên trái kéo xuống dưới
   - Chọn **Subnets**
   - Tìm kiếm **_FCJ-Lab_**

![VPC Search](/images/2/2_1/6.png?width=90pc)

Chúng ta sẽ thấy có **2 subnet public**: **FCJ-Lab-subnet-public1-ap-southeast-1a, FCJ-Lab-subnet-public2-ap-southeast-1b**
Đầu tiên chúng ta sẽ setting cho **FCJ-Lab-subnet-public1-ap-southeast-1b**

- Chọn **FCJ-Lab-subnet-public1-ap-southeast-1a**
- Chọn Action
- Chọn Edit subnet settings

![VPC Search](/images/2/2_1/7.png?width=90pc)

- Xuất hiện bảng cấu hình cho public subnet
  - Click chọn **Enable auto-assign public IPv4 address**
  - Chọn **Save**

![VPC Search](/images/2/2_1/8.png?width=90pc)

Tương tự, chúng ta sẽ setting cho **FCJ-Lab-subnet-public2-ap-southeast-1b**
![VPC Search](/images/2/2_1/9.png?width=90pc)

Như vậy, chúng ta vừa cấu hình xong VPC và enable public IPv4 cho subnet public.
