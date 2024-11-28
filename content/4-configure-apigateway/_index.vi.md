+++
title = "Cấu hình API Gateway"
date = 2024
weight = 4
chapter = false
pre = "<b>4. </b>"
+++

### Tổng quan về API Gateway

Một dịch vụ **API Gateway** được cung cấp bởi AWS. Nó cung cấp một cách đơn giản để xây dựng, quản lý và bảo mật các **RESTful API** hoặc **WebSocket**. AWS API Gateway là một dịch vụ quan trọng trong kiến trúc dựa trên các dịch vụ của AWS (AWS-based microservices architecture) và thường được sử dụng cùng với các dịch vụ AWS khác như **_AWS Lambda, EC2, S3, Amazon DynamoDB_**.

#### AWS API Gateway cung cấp các tính năng gì ?

- Cho phép thiết kế và phát triển API RESTful hoặc WebSocket thông qua web GUI.
- Điều phối các yêu cầu API đến các hệ thống hoặc dịch vụ khác nhau.
- Authen/Author request tới các API.
- Quản lý và giám sát các yêu cầu API, vd số lượng request, response time...• AWS API Gateway cũng cung cấp các tính năng bảo mật, bao gồm chứng thực và ủy quyền các yêu cầu API và mã hóa secure communication giữa các hệ thống khác nhau.

#### Đặc trưng của API Gateway

- Là một fully managed service của AWS.
- Khả năng scale và High Availablity không giới hạn.
- Zero idle cost
- Easy to setup
- Dễ dàng kết hợp với các dịch vụ khác như CloudWatch, WAF cho mục đích monitor & security.

#### Khi nào nên sử dụng API Gateway?

- API Gateway phù hợp cho những bài toán sau
  - Kiến trúc Micro-service sử dụng lambda làm backend
  - Backend API cho hầu hết các use case (web API, IoT)
  - Gateway nhận data trực tiếp từ client sau đó lưu vào DynamoDB (DB First)
  - Web Socket cho những hệ thống realtime communication.

#### Chi phí API Gateway ?

API Gateway PricingAPI Gateway là một dịch vụ có idle cost = 0. Người dùng chỉ trả tiền cho chi phí chạy thực tế,

- **Với REST API**
  - Số lượng request (Vd Singapore region:$ 4.25/1M requests)
  - Data transfer out ($/GB)
  - Caching size tính theo GB/hour
- **Với Web socket**
  - Message number (đối với Web socket). Vd $1.15/1M message với block 32KB.
  - Connection minutes: $0.288/1M connection minutes

#### Authentication cho API Gateway ?

API Gateway cung cấp 2 phương thức authen tích hợp trực tiếp (authorizer) thường được sử dụng đó là:

- **Cognito Authorizer**
  Liên kết trực tiếp với một Cognito User Pool sử dụng làm authorizer. Khi access API, client passing trực tiếp token lấy được thông qua login với Cognito, API Gateway sẽ check token và allow access nếu token hợp lệ.
- **Lambda Authorizer** (custom authorizer)
  Khi sử dụng loại authorizer này, bạn sẽ tự implement logic authen trên Lambda. Có 2 hình thức là authen dựa vào TOKEN (JWT) hoặc request parameter based (VD username/password).

- **Mô hình sử dụng Lambda làm authorizer**
  ![Lambda with authorizer](/images/4/4_1/000.png?width=90pc)

### Nội dung

1. [Tạo REST API](1-create-rest-api)
2. [Kiểm tra API với Postman](2-check-api-with-postman)
