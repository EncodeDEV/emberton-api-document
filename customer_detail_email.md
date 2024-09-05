# Kiểm tra thông tin khách hàng bằng địa chỉ Email

_API cần gửi các tham số bắt buộc và cần xác thực bằng token [Xem tại đây](README.md)

Gửi request thông qua địa chỉ sau
 ```http
GET https://emberton.mhvn.vn/api/customer/detail-by-email

Accept: application/json
Content-Type: application/json
```

Các tham số gửi lên ngoài tham số bắt buộc:

| Key | Type | Description |
| :--- | :--- | :--- |
| `email` | `string` | **Bắt buộc**. Địa chỉ email của khách hàng |
| `log_key` | `string` | Mã lượt truy cập QR nhận được từ VietCheck (vid) |
