+++
title = "Kiểm tra API với Postman"
date = 2024
weight = 2
chapter = false
pre = "<b>4.2 </b>"
+++

**Postman** hiện là một trong những công cụ phổ biến nhất được sử dụng trong thử nghiệm các API.
Như ta đã biết, API chịu trách nhiệm kết nối các ứng dụng với nhau, có Postman sẽ giúp cho thao tác với API này trở nên dễ dàng hơn. Thông thường, Postman sẽ được dùng cho API kiểu REST. Với Postman, ta có thể gọi Rest API mà không cần viết dòng code nào.
Bạn hãy tải xuống [Postman](https://www.postman.com/downloads/).

#### Kiểm tra API với Postman

Click vào dấu **+** , để thêm 1 tab mới

- Chọn POST method
- Nhập **InvokURL** của POST API đã ghi lại từ bước trước
- Nhập vào **RequestBody** với dạng **raw**:

```
 {
 "method": "GET"
 }
```

- Ấn nút **Send**

Kết quả trả về là toàn bộ dữ liệu của bảng User đã qua xử lý

![Kiểm tra API](/images/4/4_2/1.png?width=90pc)
