+++
title = "Tạo người dùng và nhóm trong cognito"
date = 2024
weight = 2
chapter = false
pre = "<b>5.2 </b>"
+++

#### Tạo users và group cho Cognito

1. Sau khi tạo **user pool** thành công, vào thông tin của user pool: **test-lambda-pool-01**

- Ở tab **Users**. Chọn **Create Users**
  ![Users](/images/5/5_2/1.png?width=90pc)

2. Tại phần thông tin người dùng

- Tạo tài khoản bao gồm **username, email và mật khẩu**
  ![Info Users](/images/5/5_2/2.png?width=90pc)

3. Chọn **Create User**
   Sau đó **cognito** sẽ gửi username và password khi đã đăng ký user.
   ![Mail info](/images/5/5_2/3.png?width=90pc)

4. Quay trở lại pool để tạo group

-     Chọn Create group
  ![Back user pool](/images/5/5_2/4.png?width=90pc)

5. Tại phần thông tin group
   - Nhập group name, chẳng hạn như: `admin`
   - Kéo xuống dưới chọn **Create Group**
     ![Create Group](/images/5/5_2/5.png?width=90pc)

- Sau khi tạo user và group thành công
- Vào Group: **admin**
- Chọn **Add user to group**
  ![Add user to group](/images/5/5_2/6.png?width=90pc)

6. Chọn user vừa tạo
   Nhấn **Add**
   ![Add user to group](/images/5/5_2/7.png?width=90pc)
   ![Add user success](/images/5/5_2/8.png?width=90pc)
