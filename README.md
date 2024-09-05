# Hướng dẫn sử dụng API hệ thống quản lý QR Emberton


> [!IMPORTANT]
> Tất cả các API cần gửi kèm Header các key sau:

| Key | Value | Description |
| :--- | :--- | :--- |
| `Content-Type` | `application/json` | **Bắt buộc**. Cần có trong nội dung để có thể nhận về kết quả chính xác |
| `Accept` | `application/json` | **Bắt buộc**. Cần có trong nội dung để có thể nhận về kết quả chính xác |

Ngoài ra cần gửi kèm tham số URL sau để xác thực quyền truy cập:
| Key | Value | Description |
| :--- | :--- | :--- |
| `key` | `eZMkqJXucFAt2.....` | **Bắt buộc**. Token để xác thực quyền truy cập thông tin được VietCheck cấp từ trước |

### Danh sách các API:

- [Kiểm tra thông tin mã QR](check_code.md)
- [Lấy thông tin khách hàng bằng số điện thoại](customer_detail_phone.md)
- [Lấy thông tin khách hàng bằng địa chỉ email](customer_detail_email.md)
- [Thêm mới hoặc cập nhật thông tin khách hàng](customer_add_update.md)
- [Lấy danh sách dữ liệu khách hàng có phân trang](customer_list.md)

## Response Status, Status Code
Kết quả trả về với https status 200 nếu thông số gửi lên là hợp lệ có thể xử lý dữ liệu, một số trường hợp khác lỗi hệ thống không xác định https status là 500, do gửi sai phương thức https status là 405, sai địa chỉ https status là 404, không xác thực https status là 401, không có quyền https status là 403 (Xem danh sách HTTP status ở dưới)
API trả về một số status, status code trong kết quả như sau:

| status_code | status | description
| :--- | :--- | :--- | 
| 200 | `OK` | Xử lý yêu cầu thành công |
| 401 | `UNAUTHORIZED` | Yêu cầu chưa được xác thực |
| 400 | `BAD_REQUEST` | Yêu cầu không thể xử lý |
| 403 | `REQUEST_DENIED` | Không có quyền truy cập |
| 404 | `NOT_FOUND` | Không tìm thấy dữ liệu |
| 405 | `METHOD_NOT_ALLOW` | Phương thức yêu cầu không hợp lệ |
| 422 | `INVALID_FIELD` | Có dữ liệu gửi lên không cho phép |
| 500 | `INTERNAL_SERVER ERROR` | Lỗi hệ thống |
| 900 | `AUTHORIZED` | Đang đăng nhập tài khoản |

## HTTP Status có thể trả về

API trả về một số https status code sau:

| Status Code | Status | Description
| :--- | :--- | :--- | 
| 200 | `OK` | Xử lý yêu cầu thành công |
| 401 | `UNAUTHORIZED` | Yêu cầu chưa được xác thực |
| 400 | `BAD REQUEST` | Yêu cầu không thể xử lý |
| 403 | `REQUEST DENIED` | Không có quyền truy cập |
| 404 | `NOT FOUND` | Không tìm thấy dữ liệu |
| 405 | `Method Not Allowed` | Phương thức yêu cầu không hợp lệ |
| 422 | `INVALID FIELD` | Có dữ liệu gửi lên không cho phép |
| 429 | `LIMITED REQUEST` | Vượt quá số lượng gửi request cho phép |
| 500 | `INTERNAL SERVER ERROR` | Lỗi hệ thống hoặc máy chủ |
