+++
title = "Khởi tạo hàm lambda"
date = 2024
weight = 4
chapter = false
pre = "<b>3.4 </b>"
+++

#### Khởi tạo hàm lambda

1. Ở giao diện AWS Console.

- Tìm kiếm và chọn Lambda
  ![Lambda](/images/3/3_4/1.png?width=90pc)
- Tạo lambda function
  ![Tạo lambd](/images/3/3_4/2.png?width=90pc)

2. Ở phần Create function

- Chọn **Author from scratch**
- Ở phần Basic information - Function name: `ChangeDataRDS` - Runtime: **Node.js 20.x**
  ![Basic information](/images/3/3_4/3.png?width=90pc)

- Chọn Role: **RoleLambdatochangedataRDS**
  ![Chọn Role](/images/3/3_4/4.png?width=90pc)

3. Tích chọn **Enble VPC**
   - Chọn các thông tin đã khởi tạo từ trước:
     - VPC **FCJ-Lab-vpc**
     - Chọn subnet public: **FCJ-Lab-subnet-private2-ap-southeast-1b** & **FCJ-Lab-subnet-private1-ap-southeast-1a**
   - Chọn **Select existing security group**
   - Chọn **FCJ-Lab-sg-public** & **FCJ-Lab-sg-db**
     ![Enble VPC](/images/3/3_4/5.png?width=90pc)

- Sau khi thiết lập, cuối cùng chọn **Create**
  ![Create](/images/3/3_4/6.png?width=90pc)

4. Download file Lambda function với chức năng:
   - Thêm mới user & Xóa user trong database.

- Tải xuống file .zip chứa lambda function.

{{%attachments style="orange" title="Lambda Function" pattern=".*(zip)"/%}}

5. Chọn **Upload form**
   ![Upload Zip](/images/3/3_4/7.png?width=90pc)

- Chọn **Upload**
- Chọn file Zip tại đây
  ![Choose Zip](/images/3/3_4/8.png?width=90pc)

Upload file .zip thành công
![Upload Zip success](/images/3/3_4/9.png?width=90pc)

6. Tại tab **Configuration** trong lambda
   - Chọn **Environment variables**
   - Nhấn **Edit**
     ![Edit Environment variables](/images/3/3_4/10.png?width=90pc)

- Chọn **Add environment variable**:

```
RDS_LAMBDA_HOSTNAME: endpoint_your_rds_instance
RDS_LAMBDA_USERNAME: admin
RDS_LAMBDA_PASSWORD: admin2024
RDS_LAMBDA_PORT: 3306
JWT_SECRET: 0bac010eca699c25c8f62ba86e319c2305beb94641b859c32518cb854addb5f4
```

- Chọn **Save** để lưu biến môi trường.
  ![Edit Environment variables](/images/3/3_4/11.png?width=90pc)
  ![Edit Environment variables](/images/3/3_4/12.png?width=90pc)
