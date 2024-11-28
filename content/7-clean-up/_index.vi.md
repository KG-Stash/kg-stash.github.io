+++
title = "Dọn dẹp tài nguyên"
date = 2021-06-08T18:57:03+07:00
weight = 7
chapter = false
pre = "<b>7. </b>"
+++

Chúng ta sẽ dọn dẹp tài nguyên theo thứ tự như sau:

1. Vào **API Gateway** xóa tài nguyên đã tạo

2. Vào **Cognito** xóa tài nguyên đã tạo

   - Chọn Delete Cognito domain
   - Chọn Deactivate deletion protection

3. Vào **Lambda** xóa hàm đã tạo.

   - Tự động các **Network interfaces** phát sinh cũng sẽ xóa theo. Kiểm tra lại, nếu còn liên quan đến resource thì xóa, tránh phát sinh chi phí.

4. Vào dịch vụ **Amazon RDS**

   - Mở bảng điều khiển Amazon RDS.
   - Trong ngăn dẫn hướng, chọn Subnet groups.
   - Chọn DB subnet group liên quan bài lab.
   - Chọn Delete, sau đó chọn Delete trong cửa sổ xác nhận.

   - Chọn RDS instance đã khởi tạo
   - Vào Modify. Lướt xuống cùng bỏ tích Enable deletion protection
   - Chọn Action chọn delete
   - Bỏ tích Create final snapshot
   - Bỏ tích Retain automated backups
   - Đợi vài phút để xóa
   - Sau khi xóa db instance, kiểm tra các bản **Snapshot**, **Automated Backup** (nếu có hãy xóa nếu không cần thiết để tránh phát sinh chi phí)
   - Trong phần subnet group. Xóa subnet group liên quan đến VPC đã tạo.

5. Terminate **EC2 instance**

   - Truy cập EC2 Management Console.
   - Trên thanh điều hướng bên trái, chọn Instances.
   - Chọn tất cả EC2 Instance liên quan tới bài lab.
   - Click Actions.
   - Click Manage Instance State.
   - Chọn Terminate.

   - Mở bảng điều khiển Amazon EC2.
   - Chọn Amazon EC2 Dashboard, sau đó chọn Elastic IPs.
   - Chọn Elastic IP address liên quan bài lab.
   - Từ Actions, chọn Release Elastic IP addresses.
   - Trên trang xác nhận, hãy chọn Release.

   - Vào phần Network interfaces
   - Kiểm tra còn xót Network interfaces còn liên quan đến bài

6. Để xóa **VPC** và các tài nguyên liên quan:

   - Truy cập endpoint, xóa tài nguyên đã phát sinh trong quá trình thực hành, endpoint chứa VPC đã tạo.

   - Mở bảng điều khiển Amazon VPC.
   - Xóa VPC.
   - Chọn Bảng điều khiển VPC, sau đó chọn VPC.
   - Chọn VPC bạn muốn xóa.
   - Từ Actions, chọn Delete VPC.
   - Trên trang xác nhận, hãy nhập delete, rồi chọn Delete.

   - Mở bảng điều khiển Amazon VPC.
   - Chọn VPC Dashboard, sau đó chọn Security Groups.
   - Kiểm tra các security group còn xót sau khi đã xóa VPC
   - Chọn security group liên quan bài lab.
   - Chọn Actions, chọn Delete security groups và sau đó chọn Delete để xác nhận.
