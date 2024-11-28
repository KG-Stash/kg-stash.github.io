+++
title = "Triển khai API Gateway"
date = 2024
weight = 1
chapter = false
pre = "<b>4.1 </b>"
+++

Tiếp theo, chúng ta sẽ thiết lập API Gateway tương tác với các Lambda function đã tạo ở phần trước:

#### Triển khai API Gateway

1. Ở giao diện Console:

- Tìm kiếm từ khóa: **API Gateway**
  ![API Gateway](/images/4/4_1/1.png?width=90pc)

2. Chọn **REST API**
   ![Choose Rest API](/images/4/4_1/2.png?width=90pc)

- Chọn **New API**
- API name: `api-dcj-rds`
- Description – optional: **test**
- API endpoint type: **Regional**
- Chọn **Create API**
  ![Info Create API](/images/4/4_1/3.png?width=90pc)

- Tạo thành công REST API
- Tiếp đến chọn **Create resource**
  ![Create API success](/images/4/4_1/4.png?width=90pc)

Vậy là chúng ta đã tạo xong một REST API mới và resource cho nó. Tiếp theo chúng ta sẽ tạo các method tương tác với Lambda function và cài đặt chúng.

3. Tạo Method API

   - Chọn **Creat Method**
     ![Creat Method](/images/4/4_1/5.png?width=90pc)

   - Method type: **POST**
   - Integration type: **Lambda function**
   - Lambda function: **ChangeDataRDS**
   - Chọn **Create Method**
     ![Info Method](/images/4/4_1/6.png?width=90pc)

4. Sau khi tạo method POST thành công, tiếp đến chọn **Deploy API**
   ![Create Deploy](/images/4/4_1/7.png?width=90pc)

- Chọn Stage: **New stage**
- Stage name: `changdata`
- Chọn **Deploy**
  ![Deploy API](/images/4/4_1/8.png?width=90pc)

5. Copy **Invoke URL** của method **POST** đã tạo
   ![Copy Invoke URL](/images/4/4_1/9.png?width=90pc)
