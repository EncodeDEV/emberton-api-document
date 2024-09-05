# Kiểm tra mã QR

_API cần gửi các tham số bắt buộc và cần xác thực bằng token [Xem tại đây](README.md)

Gửi request thông qua địa chỉ sau
 ```http
GET https://emberton.mhvn.vn/api/code/check

Accept: application/json
Content-Type: application/json
```

Các tham số gửi lên ngoài tham số bắt buộc:

| Key | Type | Description |
| :--- | :--- | :--- |
| `code` | `string` | **Bắt buộc**. Mã cá thể hóa được cung cấp bởi VietCheck |

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
    "message": "Mã hợp lệ",
    "data": {
        "serial": "1002377",
        "view_count": 6,
        "first_view_at": "2024-04-27 18:15:37",
        "last_viewed_at": "2024-09-05 08:38:48"
    }
}
```

- `data.serial` Mã serial đi kèm mã cá thể hóa
- `data.view_count` Lượt truy cập mã QR
- `data.first_view_at` Thời điểm truy cập mã QR lần đầu tiên
- `data.last_viewed_at` Thời điểm truy cập mã QR lần gần nhất

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
        "code": [
            "Mã không tồn tại"
        ]
    }
}
```
