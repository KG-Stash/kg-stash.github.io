+++
title = "Kiểm tra Kết quả"
date = 2024
weight = 6
chapter = false
pre = "<b>6. </b>"
+++

### Kiểm tra hoạt động

**//Syntax**

```
https://<your user pool domain>/authorize?client_id=<your app client ID>&response_type=<code/token>&scope=<scopes to request>&redirect_uri=<your callback URL>
```

**Hoặc syntax sau:**

```
https://<your app client ID>/authorize?client_id==<your app client ID>&response_type=token&scope=openid&redirect_uri=https://google.com
```

1. Copy **Cognito domain**
   ![Copy Cognito domain](/images/6/1.png?width=90pc)

2. Copy **Client ID**
   ![Copy Client ID](/images/6/2.png?width=90pc)

3. Chỉnh sửa ghép vào syntax ở trên để truy cập vào cognito qua đường dẫn.
   Dùng **username và password** của user đã tạo trong cognito để đăng nhập vào.
   ![Truy cập Cognito](/images/6/3.png?width=90pc)

4. Nhập thông tin để thay đổi mật khẩu:
   ![Truy cập Cognito](/images/6/4.png?width=90pc)

   Sau đó bạn rollback về url **https://google.com kèm với thông tin token**.
   ![Truy cập Cognito](/images/6/5.png?width=90pc)

5. Ta copy ra trình soạn thảo để lấy token
   ![Copy token](/images/6/6.png?width=90pc)

6. Tìm hiểu nội dung Token
   ![data token](/images/6/7.png?width=90pc)

7. Trở lại API Gateway

- Vào API Gateway đã tạo ở phần **Triển khai API Gateway**
- Chọn **Create an authorizer**
  ![Create an authorizer](/images/6/8.png?width=90pc)

8. Thiết lập các thông tin cho xác thực cognito
   - Authorizer name: `coginito-authorizer`
   - Authorizer type: **Cognito**
   - Cognito user pool: **test-lamda-pool-01**
     ![coginito-authorizer](/images/6/9.png?width=90pc)

- **Create authorizer**
  ![Create authorizer success](/images/6/10.png?width=90pc)

9. Trở lại resource
   Chọn method **POST**. Hiện tại Authorization: **NONE**
   Chọn **Edit**
   ![Choose Edit Method POST](/images/6/11.png?width=90pc)

10. Chỉnh sửa thông tin method

- Chọn Authorization đã tạo: **cognito-authorizer**
- Chọn Save
  ![Edit Method POST](/images/6/12.png?width=90pc)

11. **Deploy** để hoạt động method với authorizer vừa gán vào method
    ![Deploy API](/images/6/13.png?width=90pc)

12. Khi này ta copy **Invoke URL**
    ![Copy Invoke URL](/images/6/14.png?width=90pc)

13. Vào công cụ **postman**.

Ấn vào dấu **+** , để thêm 1 tab mới

- Chọn method **POST**
- Nhập **InvokURL** của POST API đã ghi lại từ bước trước
- Nhập vào RequestBody với dạng raw:

```
  {
  "method": "GET"
  }
```

- Ấn nút **Send**

Kết quả: **Ta gặp lỗi xác thực (401 - Unauthorzierd)**
![Request API](/images/6/15.png?width=90pc)

14. Ta bôi đen và copy **id_token** đã lấy từ **_Bước 6_**
    ![Request API](/images/6/16.png?width=90pc)

15. Vào **Postman**

- Chọn **Authorization**
- Loại: **Bearer Token**
- **Dán id_token** đã copy vào khung token bên phải. Sau đó Gửi lại request
- Kết quả trả về thông tin user
  ![Request API](/images/6/17.png?width=90pc)

16. **Thêm mới** người dùng vào cơ sở dữ liệu

- Kèm với Authorization: token đã dán vào
- Kết quả: Thêm mới thành công
  ![Create New User](/images/6/18.png?width=90pc)

17. Kiểm tra bảng User qua EC2 kết nối với RDS
    ![Check New User with EC2](/images/6/19.png?width=90pc)

18. Kiểm tra log trong **Cloud Watch**
    ![Cloud Watch](/images/6/20.png?width=90pc)

    ! [Cloud Watch log](/images/6/21.png?width=90pc)
