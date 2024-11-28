+++
title = "Khởi chạy RDS Instance"
date = 2024
weight = 2
chapter = false
pre = "<b>3.2 </b>"
+++

#### Khởi chạy RDS Instance

Tạo RDS Instance

- Chọn phần: **Databases**
- Chọn: **Create Database**
  ![Choose DB](/images/3/3_2/1.png?width=90pc)
- Chọn phương thức: **Standard create**
- Chọn loại lưu trữ là: **MySQL**
  ![Template](/images/3/3_2/2.png?width=90pc)

- Chọn template: **Dev/Test**
- Chọn **Multi-AZ DB instance**
  Phần này chúng ta có thể tự điều chỉnh sao cho phù hợp với yêu cầu để tối ưu hóa chi phí của bạn, tuy nhiên cũng sẽ có một số giới hạn vậy nên cần phải tìm hiểu kỹ.
  ![Subnet DB](/images/3/3_2/3.png?width=90pc)

- Nhập tên DB instance: `fcj-database-instance`
- Nhập username: `admin`
- Nhập mật khẩu: `admin2024`
  ![Info DB](/images/3/3_2/4.png?width=90pc)

Ở phần cài đặt:
![Class & Storage](/images/3/3_2/5.png?width=90pc)

- Kết nối tới VPC đã tạo: **FCJ-Lab-vpc**
- chọn Subnet đã tạo từ phần trước: **fcj-lab-subnet-group-db**
- Puclic access: **Yes**
  ![Resource](/images/3/3_2/6.png?width=90pc)

- Chọn Security group đã tạo cho DB: **FCJ-Lab-sg-db**
- Phần sau có thể để mặc định hoặc cấu hình theo mong muốn
  ![Resource](/images/3/3_2/7.png?width=90pc)

- Kiểm tra kĩ lại các cấu hình tránh gây nhầm lẫn ảnh hưởng tới chi phí thực hiện
- Chọn **Create**
  ![Resource](/images/3/3_2/8.png?width=90pc)

- Hoàn tất tạo DB instance và quá trình này phải chờ khoảng 15 phút để hiện Available
  ![Resource](/images/3/3_2/9.png?width=90pc)
