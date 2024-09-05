# Lấy danh sách dữ liệu khách hàng có phân trang

_API cần gửi các tham số bắt buộc và cần xác thực bằng token [Xem tại đây](README.md)

Gửi request thông qua địa chỉ sau
 ```http
GET https://emberton.mhvn.vn/api/customer/list

Accept: application/json
Content-Type: application/json
```

Các tham số gửi lên ngoài tham số bắt buộc:

| Key | Type | Description |
| :--- | :--- | :--- |
| `page` | `integer` | Số trang cần lấy dữ liệu |

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
    "per_page": 20,
    "current_page": 1,
    "has_next_page": true,
    "items_count": 20,
    "items": [
        {
            "id": "byNMB0LGkK",
            "phone": "+84987000000",
            "name": "Nguyễn Văn A",
            "address": "số 19, đường Nguyễn Trãi, Thanh Xuân, Hà Nội",
            "email": "test1@example.com",
            "add_at": "2024-09-05 08:43:55",
            "edit_at": "2024-09-05 09:14:55",
            "add_from": "abaha"
        },
        ...
    ]
}
```

- `per_page` Số bản ghi yêu cầu lấy trong một trang (cố định 20)
- `current_page` Số trang hiện tại
- `has_next_page` Xác định có trang tiếp theo hay không
- `items_count` Số bản ghi của trang hiện tại
- `items.*.id` ID khách hàng trên hệ thống VietCheck
- `items.*.phone` Số điện thoại khách hàng
- `items.*.name` Họ tên khách hàng
- `items.*.address` Địa chỉ của khách hàng
- `items.*.email` Địa chỉ email của khách hàng
- `items.*.add_at` Ngày ghi nhận thông tin khách hàng
- `items.*.edit` Ngày cập nhật thông tin khách hàng
- `items.*.add_from` Nguồn ghi nhận thông tin khách hàng

Dữ liệu trống:
 ```http
STATUS: 200 OK
Content-Type: application/json
```
```javascript
{
    "status": "OK",
    "status_code": 200,
    "message": "Lấy dữ liệu thành công",
    "per_page": 20,
    "current_page": 1,
    "has_next_page": false,
    "items_count": 0,
    "items": []
}
```
