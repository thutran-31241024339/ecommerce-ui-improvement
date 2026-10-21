# AI Usage Log

## 1. Công cụ AI
- **Tên công cụ:** Antigravity (Claude Opus 4.6 Thinking) – AI coding assistant của Google DeepMind

## 2. Mục đích sử dụng
- Đọc và trích xuất nội dung file Word khảo sát (`Khao_sat_website_Cocoon_Vietnam.docx`).
- Phân tích giao diện website Cocoon Vietnam dựa trên kết quả khảo sát 5 khu vực chức năng.
- Đề xuất bố cục trang e-commerce áp dụng các cải tiến từ khảo sát.
- Viết mã nguồn HTML5, CSS3 và JavaScript thuần cho trang giao diện.
- Hỗ trợ viết tài liệu dự án (README.md, AI_USAGE.md).

## 3. Prompt đã sử dụng
**Prompt chính:**
> "Đọc file Word khảo sát Cocoon, đọc phần cải tiến chi tiết sản phẩm, sau đó viết source code cho trang giao diện thương mại điện tử bằng HTML5 và CSS3. Yêu cầu: giao diện có tiêu đề và khu vực sản phẩm, tối thiểu 4 sản phẩm mẫu, mỗi sản phẩm có hình ảnh, tên, giá và nút thao tác, bố cục phù hợp màn hình máy tính và điện thoại, CSS tách file riêng, không backend, không thư viện không cần thiết."

**Prompt bổ sung:**
> "Sửa lại file README theo cấu trúc template cho sẵn (7 mục)."

## 4. Kết quả AI đề xuất
- **HTML:** Trang e-commerce hoàn chỉnh gồm header (logo, menu, tìm kiếm, giỏ hàng), hero banner, khu vực chọn theo nhu cầu da, lưới 6 sản phẩm có bộ chọn dung tích, gợi ý combo mua kèm, đánh giá khách hàng, giới thiệu thương hiệu và footer.
- **CSS:** Stylesheet responsive (breakpoint 768px và 480px) sử dụng CSS Grid và Flexbox, tông màu xanh lá theo brand Cocoon.
- **JavaScript:** Menu mobile toggle, dropdown gợi ý tìm kiếm, chọn dung tích cập nhật giá, lọc theo loại da, sắp xếp theo giá/bán chạy, thông báo toast khi thêm giỏ hàng.

## 5. Kiểm tra và điều chỉnh
- **Đã kiểm tra:** Cấu trúc file HTML hợp lệ, CSS liên kết đúng, các data attribute trên thẻ sản phẩm khớp với logic JavaScript.
- **Cần kiểm tra thủ công:** Hiển thị trên các trình duyệt thực tế (Chrome, Firefox, Edge, Safari mobile), responsive ở nhiều kích thước, tương tác người dùng (chọn dung tích, lọc, sắp xếp, thêm giỏ).
- **Chưa sử dụng / cần bổ sung:** Hình ảnh sản phẩm thật (hiện dùng placeholder), dữ liệu sản phẩm thực tế, chức năng tìm kiếm thực sự (hiện chỉ có gợi ý tĩnh).

## 6. Phần tôi hiểu và có thể giải thích
- **Cấu trúc HTML semantic:** Sử dụng `<header>`, `<nav>`, `<section>`, `<article>`, `<footer>` để phân chia rõ ràng các khu vực trang.
- **CSS Grid & Flexbox:** `grid-template-columns: repeat(auto-fill, minmax(280px, 1fr))` tạo lưới sản phẩm tự động điều chỉnh số cột theo chiều rộng màn hình.
- **Media Queries:** `@media (max-width: 768px)` chuyển bố cục sang mobile (ẩn menu, hiện hamburger, thay đổi số cột).
- **Data attributes:** `data-price`, `data-skin`, `data-sold` trên thẻ sản phẩm giúp JavaScript lọc và sắp xếp mà không cần backend.
- **Event handling:** `addEventListener` xử lý sự kiện click (chọn dung tích), change (lọc/sắp xếp), focus/click (tìm kiếm).
- **DOM manipulation:** `classList.toggle()` để mở/đóng menu, `appendChild()` để sắp xếp lại thứ tự thẻ sản phẩm.
