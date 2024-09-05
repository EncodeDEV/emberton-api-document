# Thêm mới hoặc cập nhật thông tin khách hàng

_API cần gửi các tham số bắt buộc và cần xác thực bằng token [Xem tại đây](README.md)

Gửi request thông qua địa chỉ sau
 ```http
POST https://emberton.mhvn.vn/api/customer/add-update

Accept: application/json
Content-Type: application/json
```

Các tham số gửi lên ngoài tham số bắt buộc:

| Key | Type | Description |
| :--- | :--- | :--- |
| `cc_phone` | `string` | **Bắt buộc**. Mã điện thoại quốc gia không bao gồm dấu cộng (+) |
| `phone` | `string` | **Bắt buộc**. Số điện thoại khách hàng |
| `name` | `string` | **Bắt buộc**. Tên khách hàng |
| `address` | `string` | **Bắt buộc**. Địa chỉ khách hàng |
| `email` | `string` | Địa chỉ email của khách hàng |
| `log_key` | `string` | Mã lượt truy cập QR nhận được từ VietCheck |

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
    "message": "Cập nhật thành công",
    "data": {
        "action": "edit",
        "id": "byNMB0LGkK"
    }
}
```

- `data.action` Hành động thêm mới hoặc cập nhật, giá trị gồm: `add`, `edit`
- `data.id` ID khách hàng trên hệ thống VietCheck

Dữ liệu không hợp lệ:
 ```http
STATUS: 200 OK
Content-Type: application/json
```
```javascript
{
    "status": "INVALID_FIELD",
    "status_code": 422,
    "message": "Có dữ liệu không hợp lệ",
    "errors": {
         "phone": [
            "Vui lòng nhập số điện thoại"
        ],
        "name": [
            "Vui lòng cung cấp họ tên"
        ]
    }
}
```
