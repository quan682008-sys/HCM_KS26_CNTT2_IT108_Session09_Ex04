# HCM_KS26_CNTT2_IT108_Session09_Ex04
# Bài 4 : Tối ưu chi phí Token cho hệ thống AI

## Phần 1. Phân tích bài toán

AI không đọc theo ký tự mà đọc theo **token** (các mảnh văn bản nhỏ), và chi phí cũng được tính theo token. Cùng một nội dung:

```markdown
# Giới thiệu

**SmartCampus** là ứng dụng tra cứu lịch học.

- Tra cứu lịch học
- Xem phòng trống
```

```html
<h1>Giới thiệu</h1>

<p><strong>SmartCampus</strong> là ứng dụng tra cứu lịch học.</p>

<ul>
  <li>Tra cứu lịch học</li>
  <li>Xem phòng trống</li>
</ul>
```

Ví dụ trên: Markdown **98 ký tự**, HTML **154 ký tự** (HTML dài hơn khoảng **36%**). Số ký tự ít hơn thường kéo theo số token ít hơn.

**Vì sao Markdown giúp AI xử lý nhanh hơn?**

- Ít ký hiệu thừa: `#`, `**`, `-` thay cho cặp thẻ mở/đóng như `<h1></h1>`, `<li></li>`.
- Ít token hơn nên rẻ hơn và nhanh hơn, đồng thời chứa được nhiều nội dung hơn trong giới hạn ngữ cảnh của AI.

**Vì sao chính xác hơn?**

- Phần lớn token là nội dung thật, ít "nhiễu" từ thẻ HTML, nên AI dễ tập trung vào ý chính.
- Cấu trúc (tiêu đề, danh sách, bảng) vẫn rõ ràng qua ký hiệu đơn giản.
- AI được huấn luyện trên rất nhiều tài liệu Markdown (README, tài liệu kỹ thuật), nên hiểu định dạng này tốt.

## Phần 2. So sánh và đánh giá

| Tiêu chí | Markdown | HTML |
| :--- | :---: | :---: |
| Số ký tự / token | Ít | Nhiều (do thẻ mở/đóng) |
| Human-readable | Rất dễ đọc ngay cả khi chưa render | Khó đọc, rối vì thẻ |
| Tốc độ xử lý của AI | Nhanh hơn | Chậm hơn |
| Chi phí token | Thấp | Cao hơn |
| Khả năng tùy biến giao diện | Hạn chế | Rất mạnh (CSS, JS) |
| Độ khó học | Học trong vài phút | Cần học thẻ và thuộc tính |

### Lựa chọn cuối cùng: **Markdown**

Hệ thống chỉ gửi tài liệu cho AI đọc, không cần dàn trang phức tạp, nên Markdown thắng ở cả 3 tiêu chí của đề: ít ký tự, dễ đọc với mắt người, xử lý nhanh.

### Vì sao lập trình viên luôn chọn Markdown để viết README?

- Viết nhanh bằng bất kỳ trình soạn thảo nào
- Đọc được ngay dưới dạng văn bản thô, kể cả khi chưa render
- GitHub tự render đẹp mắt, không cần thêm công cụ
- Diff và quản lý phiên bản bằng Git gọn gàng, vì file ngắn và ít thẻ
