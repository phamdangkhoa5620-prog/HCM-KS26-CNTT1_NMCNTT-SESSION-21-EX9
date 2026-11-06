## PHẦN 1: THIẾT KẾ PROMPT 3 THÀNH PHẦN

### 1\. Vì sao câu hỏi ban đầu khiến AI trả lời sai?

* Câu hỏi quá chung chung, thiếu thông tin về thiết bị và hệ điều hành.
* Không cung cấp thông báo lỗi cụ thể.
* Không nêu rõ yêu cầu cần AI hỗ trợ.

**Kết luận:** AI thiếu dữ liệu nên tự suy đoán (Hallucination), dẫn đến hướng dẫn sai lệch.

### 2\. Prompt 3 thành phần hoàn chỉnh

**\[CONTEXT – NGỮ CẢNH]**

Tôi là kỹ thuật viên vận hành trạm sạc VoltCharge số 04 tại Bến xe Miền Đông, sử dụng Windows 11. Trạm sạc đột ngột ngừng hoạt động.

**\[RAW ERROR – LỖI NGUYÊN VĂN]**

```text
System.UnauthorizedAccessException:
Access to the path
'C:\\Program Files\\VoltCharge\\data\\session.log' is denied.
Process terminated with exit code 5.
```

**\[INSTRUCTION – YÊU CẦU]**

Hãy giải thích lỗi bằng tiếng Việt dễ hiểu, xác định nguyên nhân và đưa ra 3 bước khắc phục an toàn trên Windows 11.

## PHẦN 2: GIẢI MÃ LỖI VÀ KHẮC PHỤC

### 3\. Giải thích nguyên nhân lỗi

* `UnauthorizedAccessException`: Lỗi không được cấp quyền truy cập.
* `Access is denied`: Truy cập bị từ chối.
* `Exit code 5`: Lỗi do không đủ quyền.

**Nguyên nhân:** Ứng dụng VoltCharge không có quyền ghi file `session.log` trong thư mục được Windows bảo vệ `Program Files`.

Đây là lỗi phân quyền phần mềm, chưa phải lỗi phần cứng.

### 4\. Ba bước khắc phục trên Windows 11

**Bước 1:** Nhấn chuột phải vào ứng dụng VoltCharge → chọn **Run as administrator** → Yes.

**Bước 2:** Truy cập thư mục:

```text
C:\\Program Files\\VoltCharge\\data
```

* Chuột phải → Properties → Security → Edit.
* Chọn đúng tài khoản dịch vụ VoltCharge.
* Cấp quyền **Modify** → Apply → OK.

**Bước 3:** Khởi động lại ứng dụng, kiểm tra file `session.log` và xác nhận trụ sạc hoạt động bình thường.

**Lưu ý:** Không cấp Full Control cho Everyone hoặc tự ý tháo thiết bị điện.

### 5\. Xử lý API Key bí mật

* Không gửi API Key thật lên ChatGPT/Gemini.
* Thay giá trị bí mật bằng `\[REDACTED]`.

Ví dụ:

```text
API\_KEY: \[REDACTED]
```

**Lý do:** Tránh lộ thông tin xác thực, bị đánh cắp tài khoản hoặc truy cập trái phép hệ thống. Nếu khóa thật đã bị lộ, cần thu hồi và tạo khóa mới.

## 3 NGUYÊN TẮC AN TOÀN KHI DÙNG AI

1. Không chạy mù quáng các câu lệnh AI đề xuất.
2. Cung cấp đủ thông tin để tránh AI suy đoán sai.
3. Tuyệt đối không chia sẻ mật khẩu, API Key và mã OTP.

