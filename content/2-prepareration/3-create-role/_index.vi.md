+++
title = "Tạo Role cho Lambda"
date = 2024
weight = 3
chapter = false
pre = "<b>2.3 </b>"
+++

### Tạo Role cho Lambda

Ở giao diện Console:

- Tìm kiếm từ khóa: **IAM**

![IAM](/images/2/2_3/1.png?width=90pc)

- Chọn Create Role

![IAM](/images/2/2_3/2.png?width=90pc)

Thông tin điền vào:

- Chọn loại sử dụng: **AWS service**
- Dịch vụ: **Lambda**
- Chọn **Next**

![IAM](/images/2/2_3/3.png?width=90pc)

- Tìm kiếm từ khóa tương ứng chọn các permission sau:
- Chọn `AmazonRDSFullAccess`
- Chọn `AmazonEC2FullAccess`
- Chọn `AWSLambdaVPCAccessExecutionRole`
- Chọn `AmazonVPCFullAccess`

![IAM](/images/2/2_3/4.png?width=90pc)

- Nhập tên role: `RoleLambdatochangedataRDS`

![IAM](/images/2/2_3/5.png?width=90pc)

- Kiểm tra kỹ lại và chọn **Create role**

![IAM](/images/2/2_3/6.png?width=90pc)
