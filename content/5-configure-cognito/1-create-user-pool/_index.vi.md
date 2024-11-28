+++
title = "Tạo User Pool"
date = 2024
weight = 1
chapter = false
pre = "<b>5.1 </b>"
+++

#### Tạo User pool

1. Ở giao diện Console:
   Tìm kiếm từ khóa: **Cognito**
   ![Search Cognito](/images/5/5_1/1.png?width=90pc)

2. Chọn User pools ở phía menu phía bên trái
   Nhấn vào **Create user pool**
   ![Click Create user pool](/images/5/5_1/2.png?width=90pc)

3. Chọn User name, Email

- Tích chọn **Allow users to sign in with a preferred user name**
- Ấn **Next**
  ![Chọn User name](/images/5/5_1/3.png?width=90pc)

4. Chọn **Cognito defaults** cho mục Password policy
   ![Chọn Cognito defaults](/images/5/5_1/4.png?width=90pc)

5. Kéo xuống, chọn **No MFA** cho mục Multi-factor authentication

- Chọn **Email only** cho mục Delivery method
- Ấn **Next**
  ![Delivery methodChọn Cognito defaults](/images/5/5_1/5.png?width=90pc)

6. Để **_mặc định_** các tuỳ chọn

- Lướt xuống cùng, phần **Additional required attributes**: Chọn **name**
- Chọn **Next**
  ![Additional required attributes](/images/5/5_1/6.png?width=90pc)

7. Chọn **Send email with Cognito**

- Ấn **Next**
  ![Send email with Cognito](/images/5/5_1/7.png?width=90pc)

8. Tại phần cấu hình **SMS**:

- Chọn **Create a new IAM role**
- IAM role name: `cognito-sms-role`
- Chọn **Next**
  ![Cấu hình sms](/images/5/5_1/8.png?width=90pc)

9. Tạo **User pool**

   - Nhập tên cho user pool, ví dụ: `test-lamda-pool-01`
   - Tích chọn **Use the Cognito Hosted UI**
   - Domain: Chọn **Use a Cognito domain**
   - Nhập vào domain, ví dụ như: **https://test-fcj-cloud**
     ![Tạo User pool](/images/5/5_1/9.png?width=90pc)
     ![Tạo User pool](/images/5/5_1/10.png?width=90pc)

10. Tạo **App Client**

    - Chọn **Public client**
    - Nhập tên cho app client, ví dụ: `test-change-data-rds`
      ![Tạo App Client](/images/5/5_1/11.png?width=90pc)

11. Tại phần mở rộng **Advanced app client settings**

- Chọn **ALLOW_USER_PASSWORD_AUTH**
- Chọn **ALLOW_USER_SRP_AUTHSRP**
- Chọn **ALLOW_CUSTOM_AUTH**
  ![Advanced app client settings](/images/5/5_1/12.png?width=90pc)
  ![Advanced app client settings](/images/5/5_1/13.png?width=90pc)
  Sau đó chọn **Next**, Chọn **Create user pool**
