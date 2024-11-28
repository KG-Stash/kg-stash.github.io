+++
title = "Khởi chạy RDS Instance"
date = 2024
weight = 3
chapter = false
pre = "<b>3. </b>"
+++

### Tổng quan Amazon RDS

**Amazon RDS** là cơ sở dữ liệu được quản lý trên AWS, chúng ta chỉ truy cập và quản lý ở mức RDBMS,không thể truy cập và quản lý ở mức hệ điều hành. Bao gồm Aurora, MySQL, PostgreSQL, MSSQL, Oracle, và MariaDB. Amazon RDS cung cấp các tính năng:

- Tự động sao lưu (cả log và database – tối đa 35 ngày).
- Tạo bản sao chỉ đọc (Read Replica) phục vụ cho các workload đọc (reporting).
- Read Replica có thể được tách ra và chuyển thành một Primary node.
- Chạy với cơ chế tự động failover, Primary/Standby, hay còn gọi là cơ chế Multi-AZ.
- RDS thường được sử dụng cho các ứng dụng OLTP.
- RDS cung cấp tính năng mã hóa dữ liệu at rest và in transit.
- RDS cũng được bảo vệ bởi tính năng tường lửa giống như EC2 (Security Group và NACL).
- Thay đổi quy mô (thay đổi instance size).
- Tự động tăng dung lượng lưu trữ (Storage Auto Scale).

### Pricing

- Về cơ bản RDS tính tiền dựa trên các thông số
  - Instance size. Instance size càng lớn cost càng cao. Có hỗ trợ reserve instance tương tự EC2.
  - Lượng data lưu trữ (GB/month)
  - Dung lượng các bản snapshot được tạo ra.
  - Các tính năng khác vd Backtracking đối với Aurora.

### Mô hình triển khai RDS

- RDS Có thể được triển khai theo một số mô hình sau

  - **Single Instance**
  - **Single Instance with Multi-AZ option = yes**
  - **Master – Read Only cluster**
  - **Master – Read Only cluster with Multi-AZ option = yes**
  - **Master – Multi Read cluster**

- **Single Instance** Chỉ có 1 database instance duy nhất được tạo ra trên 1 Availability Zone (AZ). Nếu sự cố xảy ra ở cấp độ AZ, database không thể truy cập.Phù hợp cho môi trường Dev-Test để tiết kiệm chi phí

- **Single Instance with Multi-AZ option enabled**

  - Một bản sao của instance sẽ được tạo ra ở AZ khác và hoạt động dưới mode standby. Nhiệm vụ của instance standby này là sync data từ master, không thể truy cập instance này.
  - Khi có sự cố, instance standby sẽ được chuyển lên thành master (việc này được AWS thực hiện tự động, endpoint url được giữ nguyên).
  - Nếu enable multi AZ, số tiền bỏ ra sẽ x2.
  - Phù hợp cho Database Production.

- **Master – Read Only cluster**

  - Một instance với mode ReadOnly sẽ được tạo ra và liên tục replica data từ master instance. Instance này chỉ có thể đọc data.
  - Phù hợp cho hệ thống có workload read > write, muốn tối ưu performance của Database. Sau khi thiết lập quan hệ, instance được tạo ra sẽ kết hợp thành 1 cluster.
  - Trong trạng thái 2 instance đã hình thành cluster, nếu Master instance gặp sự cố, failover sẽ được tự động thực hiện, _ReadOnly instance được promote lên làm Master_.
  - Nên tạo cluster sau đó mới add node read vào để quản lý connection ở cluster level (số lượng node read có thể tuỳ chọn)

{{% notice note %}}
Lưu ý: Nếu 2 instance được tạo ra riêng biệt sau đó mới thiết lập quan hệ read-replica, endpoint của 2 instance sẽ riêng biệt nên saukhi failover, cần chỉnh lại connection từ App.
{{% /notice %}}

- **Master – Read Only cluster with Multi-AZ option = yes**
  - Tương tự mô hình **Master – Read Only** tuy nhiên các node đều được bật multi-AZ enabled. Chi phí sẽ gấp 4 lần mô hình Single Instance.

#### Nên tạo RDS Cluster hay RDS Instance?

AWS cung cấp cơ chế cho phép tạo ra 1 cluster RDS giúp quản lý node và failover dễ dàng hơn.
Ưu điểm so với việc tạo RDS instance thông thường:

- Quản lý endpoint ở cấp độ cluster, không bị thay đổi khi instance trong cluster gặp sự cố.
- Failover tự động.
- Scale read instance dễ dàng.

### Nội dung

1. [Tạo DB Subnet Group](1-db-subnet-group)
2. [Khởi chạy RDS Instance](2-start-db)
3. [Tạo EC2 Instance](3-launch-ec2)
4. [Tạo hàm lamda](4-create-lambda-function)
5. [Khởi chạy RDS Instance](5-connect-lambda-rds)
