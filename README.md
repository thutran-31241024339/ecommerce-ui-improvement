# E-commerce UI Improvement

## 1. Giới thiệu
Trang giao diện thương mại điện tử cho thương hiệu **Cocoon Vietnam** – mỹ phẩm 100% thuần chay từ thực vật Việt Nam. Giao diện được xây dựng dựa trên kết quả khảo sát UX website gốc, tập trung cải tiến các khu vực: **trang chủ** (sắp xếp lại thứ tự nội dung), **danh mục sản phẩm** (gộp dung tích, thêm lọc/sắp xếp), **chi tiết sản phẩm** (gợi ý mua kèm, đánh giá), **tìm kiếm** (gợi ý từ khóa) và **giỏ hàng** (thông báo sau khi thêm).

## 2. Website tham khảo
- **Tên website:** Cocoon Vietnam
- **URL:** https://cocoonvietnam.com
- **Khu vực đã khảo sát:**
  - Trang chủ
  - Danh mục sản phẩm (Chăm Sóc Da → Sữa Rửa Mặt)
  - Chi tiết sản phẩm (Sữa rửa mặt sen Hậu Giang 500ml)
  - Tìm kiếm
  - Giỏ hàng & Hướng dẫn mua hàng

## 3. Chức năng
- Hiển thị danh sách sản phẩm (6 sản phẩm mẫu).
- Hiển thị tên, giá, mô tả, tag loại da và số lượng đã bán cho mỗi sản phẩm.
- Bộ chọn dung tích trên mỗi thẻ sản phẩm, tự động cập nhật giá.
- Lọc sản phẩm theo loại da và sắp xếp theo giá / bán chạy.
- Thông báo toast khi thêm sản phẩm vào giỏ hàng.
- Gợi ý từ khóa tìm kiếm khi nhấp vào ô tìm kiếm.
- Bố cục hỗ trợ nhiều kích thước màn hình (desktop, tablet, mobile).

## 4. Công nghệ
- HTML5
- CSS3
- JavaScript thuần (không dùng thư viện bên ngoài)

## 5. Cách chạy
Mở file `index.html` bằng trình duyệt (nhấp đúp vào file hoặc kéo thả vào cửa sổ trình duyệt).

## 6. Cải tiến đã thực hiện

| Khu vực | Vấn đề ban đầu | Thay đổi đã thực hiện |
|---|---|---|
| Trang chủ | Sản phẩm bán chạy nằm sau nhiều khối nội dung thương hiệu, khách phải cuộn lâu mới thấy sản phẩm | Đưa lối vào theo nhu cầu da/tóc và sản phẩm bán chạy lên đầu; chuyển nội dung thương hiệu xuống cuối trang |
| Danh mục | Mỗi dung tích tách thành 1 thẻ riêng (gây lặp), không có bộ lọc hay sắp xếp | Gộp các dung tích vào 1 thẻ có bộ chọn; thêm lọc theo loại da và sắp xếp theo giá/bán chạy |
| Chi tiết SP | Số lượt bán lớn nhưng rất ít đánh giá, thiếu gợi ý mua kèm | Thêm khu vực đánh giá khách hàng (kèm nút viết đánh giá), thêm gợi ý combo/sản phẩm dùng kèm |
| Tìm kiếm | Chưa có gợi ý khi gõ, chưa hỗ trợ không dấu | Thêm dropdown gợi ý từ khóa phổ biến khi focus vào ô tìm kiếm |
| Giỏ hàng | Không rõ phản hồi sau khi bấm "Thêm vào giỏ" | Hiện toast thông báo "Đã thêm vào giỏ hàng" trong 2 giây, cập nhật số lượng trên icon giỏ |

## 7. Hỗ trợ từ AI
AI (Antigravity – Claude Opus 4.6) đã hỗ trợ:
- Đọc và trích xuất nội dung file Word khảo sát Cocoon Vietnam.
- Phân tích 5 đề xuất cải tiến từ Bảng 1 trong khảo sát.
- Viết toàn bộ mã nguồn HTML, CSS và JavaScript dựa trên yêu cầu và kết quả khảo sát.
- Viết tài liệu README.md và AI_USAGE.md.

Phần tôi cần kiểm tra, điều chỉnh hoặc bổ sung:
- Kiểm tra giao diện trên các trình duyệt và kích thước màn hình khác nhau.
- Thêm hình ảnh sản phẩm thật vào thư mục `image/`.
- Điều chỉnh thông tin sản phẩm (tên, giá, mô tả) cho phù hợp thực tế.
- Kiểm tra tương tác: chọn dung tích, lọc, sắp xếp, thêm giỏ hàng.
