+++
title = "Giới thiệu"
date = 2024
weight = 1
chapter = false
pre = "1. "
+++

#### Giới thiệu

Bạn sẽ học cách tích hợp các dịch vụ như **Amazon RDS**, **AWS Lambda**, **Amazon Cognito**, **Amazon API Gateway** để xây dựng một hệ thống web hoặc ứng dụng serverless (không cần quản lý máy chủ).

- **Amazon RDS**: Bạn sẽ hiểu cách tạo và quản lý cơ sở dữ liệu quan hệ (MySQL, PostgreSQL, v.v.) trên AWS để lưu trữ dữ liệu.
- **AWS Lambda**: Bạn sẽ học cách tạo các hàm Lambda để xử lý logic ứng dụng mà không cần phải quản lý máy chủ. Lambda có thể kết nối với RDS và S3 để thao tác dữ liệu.
- **Amazon Cognito**: Bạn sẽ hiểu cách sử dụng Amazon Cognito để xác thực và quản lý người dùng, bảo vệ các API của bạn và xác thực các yêu cầu từ người dùng.
- **API Gateway**: Bạn sẽ biết cách cấu hình **API Gateway** để cung cấp các endpoint HTTP cho phép người dùng hoặc ứng dụng giao tiếp với Lambda, đồng thời bảo vệ API bằng cách sử dụng Cognito cho việc xác thực.

#### Những dịch vụ được sử dụng trong workshop bao gồm:

- **Amazon Relational Database Service (Amazon RDS)**

  - Amazon Relational Database Service là một dịch vụ quản lý cho phép bạn triển khai và quản lý các cơ sở dữ liệu quan hệ trên AWS.
  - Amazon RDS là loại cơ sở dữ liệu xử lý giao dịch trực tuyến (OLTP).
  - Trường hợp sử dụng chính là cơ sở dữ liệu giao dịch (thay vì cơ sở dữ liệu phân tích).
  - Nó phù hợp nhất với các yêu cầu lưu trữ dữ liệu có cấu trúc và quan hệ.
  - Nó nhằm mục tiêu là một tùy chọn thay thế dễ dàng cho các instance trên nơi làm việc truyền thống của cùng loại cơ sở dữ liệu.
  - Các bản sao lưu tự động và việc vá lỗ được thực hiện trong các khung giờ bảo trì được xác định bởi khách hàng.
  - Việc mở rộng, sao chép và tính sẵn có chỉ cần một nút nhấn.

- **AWS Lambda**

  - Chức năng: Cho phép bạn chạy mã mà không cần quản lý máy chủ. Lambda tự động mở rộng để xử lý hàng nghìn yêu cầu mỗi giây.
  - Mục đích sử dụng: Chạy các chức năng serverless (không cần server), ví dụ như xử lý yêu cầu API, tương tác với cơ sở dữ liệu RDS mà không cần duy trì một máy chủ.

- **Amazon API Gateway**

  - Chức năng: Cung cấp API để kết nối các ứng dụng với các dịch vụ phía sau như Lambda.
  - Mục đích sử dụng: Tạo và quản lý các API RESTful hoặc WebSocket cho phép người dùng hoặc ứng dụng gọi hàm Lambda qua HTTP/HTTPS. API Gateway cung cấp tính năng bảo mật, giám sát và kiểm soát truy cập.

- **Amazon Cognito**

  - Chức năng: Cung cấp dịch vụ xác thực người dùng, quản lý đăng nhập và quyền truy cập cho các ứng dụng di động và web.
  - Mục đích sử dụng: Quản lý người dùng và xác thực người dùng trong ứng dụng, bảo vệ các API bằng cách tích hợp xác thực với API Gateway, đảm bảo chỉ những người dùng đã đăng nhập mới có thể truy cập tài nguyên.

#### Các bước triển khai và cấu hình dịch vụ AWS:

Bạn sẽ thực hành tạo các dịch vụ AWS và kết nối chúng lại với nhau, từ đó tạo ra một hệ thống hoàn chỉnh. Bạn sẽ hiểu được quy trình triển khai, từ khi tạo các dịch vụ AWS cho đến khi tích hợp chúng thành một hệ thống hoạt động liền mạch.

- Tạo VPC và security group
- Tạo và cấu hình Amazon RDS cho cơ sở dữ liệu.
- Tạo EC2 để kết nối và thêm dữ liệu vào RDS instance
- Xây dựng các hàm Lambda và kết nối với RDS.
- Tạo API Gateway và tích hợp với Lambda để xử lý các yêu cầu từ người dùng.
- Tạo pool người dùng và xác thực với Amazon Cognito.
- Cấu hình bảo mật API Gateway thông qua Cognito, đảm bảo chỉ người dùng xác thực mới có thể gọi API.
