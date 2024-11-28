+++
title = "Tạo DB Subnet Group"
date = 2020
weight = 1
chapter = false
pre = "<b>3.1 </b>"
+++

#### Tạo DB Subnet Group

Ở giao diện AWS console thực hiện

1. Tìm kiếm từ khóa: **RDS**

- Chọn phần: **Subnet groups**
- Chọn: **Create DB subnet group**
  ![Subnet DB](/images/3/3_1/1.png?width=90pc)

- Nhập tên: `fcj-lab-subnet-group-db`
- Nhập mô tả: `Subnet Group for FCJ Management`
- Chọn VPC đã được tạo từ trước là **FCJ-Lab-vpc**
  ![Info Subnet DB](/images/3/3_1/2.png?width=90pc)

2. Chọn Availability Zones đã được tạo chung với VPC từ trước đó

- Chọn **2 Subnet private**
- Kiểm tra lại và chọn **Create**
  ![Create Subnet DB](/images/3/3_1/3.png?width=90pc)

- Hoành thành tạo một Subnet groups
  ![Create Success](/images/3/3_1/4.png?width=90pc)
