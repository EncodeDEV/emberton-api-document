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
