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
| `log_key` | `string` | Mã lượt truy cập QR nhận được từ VietCheck (`vid`) |

### Kết quả trả về
Kết quả dữ liệu hợp lệ:
 ```http
STATUS: 200 OK
Content-Type: application/json
```
```javascript
{
    "status": "OK",
    "status_code": 200,
    "message": "Lấy dữ liệu thành công",
    "data": {
        "id": "byNMB0LGkK",
        "phone": "+84987000000",
        "name": "Nguyễn Văn A",
        "address": "số 19, đường Nguyễn Trãi, Thanh Xuân, Hà Nội",
        "email": "test1@example.com",
        "add_at": "2024-09-05 08:43:55",
        "edit_at": "2024-09-05 09:14:55",
        "add_from": "abaha"
    }
}
```

- `data.id` ID khách hàng trên hệ thống VietCheck
- `data.phone` Số điện thoại khách hàng
- `data.name` Họ tên khách hàng
- `data.address` Địa chỉ của khách hàng
- `data.email` Địa chỉ email của khách hàng
- `data.add_at` Ngày ghi nhận thông tin khách hàng
- `data.edit` Ngày cập nhật thông tin khách hàng
- `data.add_from` Nguồn ghi nhận thông tin khách hàng

Dữ liệu không tồn tại:
 ```http
STATUS: 200 OK
Content-Type: application/json
```
```javascript
{
    "status": "NOT_FOUND",
    "status_code": 404,
    "message": "Thông tin khách hàng chưa tồn tại",
    "errors": {
        "email": [
            "Email khách hàng chưa tồn tại"
        ]
    }
}
```

Dữ liệu không hợp lệ:
 ```http
STATUS: 200 OK
Content-Type: application/json
```
```javascript
{
    "status": "NOT_FOUND",
    "status_code": 422,
    "message": "Có dữ liệu không hợp l",
    "errors": {
        "email": [
            "Địa chỉ email không hợp lệ"
        ]
    }
}
```
