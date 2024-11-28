+++
title = "Kết nối Lambda với RDS Instance"
date = 2024
weight = 5
chapter = false
pre = "<b>3.5 </b>"
+++

#### Kết nối Lambda với RDS Instance

1. Tại tab **Configuration**

- Chọn **RDS databases**
- Chọn **Connect to RDS database**
  ![RDS databases](/images/3/3_5/1.png?width=90pc)

2. Bên trong **RDS database**

- Chọn **Use an exiting database**
- Chọn RDS instance: **fcj-database-instance**
  ![RDS instance](/images/3/3_5/2.png?width=90pc)
- Sau đó chọn **Create**
  ![Create connect](/images/3/3_5/3.png?width=90pc)

3. Test event action: Create new event
   Event name: `CREATE_USER`
   Event JSON:

   ```
   {
   "method": "POST",
   "name": "John Doe",
   "email": "johndoe@example.com",
   "password": "hashedpassword123",
   "image": "/avatar.png",
   "isAdmin": 1,
   "createdAt": "2024-06-05 05:50",
   "updatedAt": "2024-10-05 05:50"
   }

   ```

   ![Create new event](/images/3/3_5/4.png?width=90pc)

Sau khi test CREATE_USERS
![success](/images/3/3_5/5.png?width=90pc)

4. Kiểm tra lại bằng EC2
   ![Check Ec2](/images/3/3_5/6.png?width=90pc)