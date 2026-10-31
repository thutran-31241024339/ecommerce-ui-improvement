# Nhật Ký Sử Dụng AI Có Kiểm Soát (AI Usage Log)
> **Môn học:** Phát triển ứng dụng Web / TMĐT – Buổi 2: HTML5 & CSS3 Cơ Bản  
> **Sinh viên:** Trần Thị Kim Thư – **MSSV:** 31241024339  
> **Công cụ AI sử dụng:** Antigravity (Google DeepMind) & Gemini 3.8 Flash (High)

---

## 1. Mục đích sử dụng AI
Trong bài tập cá nhân Buổi 2, AI được sử dụng như một **trợ lý lập trình (AI Coding Assistant)** theo đúng định hướng "Sử dụng AI có kiểm soát":
- Đóng vai trò đối thoại, phản biện và gợi ý giải pháp cải thiện cấu trúc mã nguồn.
- Rà soát tính hợp lệ của mã HTML5 ngữ nghĩa và phát hiện các thẻ đóng/mở chưa hợp lý.
- Đề xuất các đoạn mã CSS mẫu minh họa cho Box Model, Flexbox, CSS Grid và Pseudo-classes.
- Sinh viên giữ vai trò chủ động: kiểm tra, tinh chỉnh, điều chỉnh mã nguồn và tự sửa các vấn đề phát sinh trên trình duyệt thực tế.

---

## 2. Nhật ký chi tiết các Prompt đã sử dụng (Theo đúng các bước trong Đề bài)

### Prompt 1 – Rà soát bài Buổi 1 và xác định nội dung cải thiện (Bước 1)
- **Câu lệnh Prompt:**
  > *"Tôi đang làm bài tập cá nhân môn Phát triển ứng dụng thương mại điện tử. Trong Buổi 1, tôi đã khảo sát website Cocoon Vietnam và tạo một giao diện cải tiến bằng HTML/CSS. Đây là mã nguồn hiện tại của tôi: [Dán mã HTML và CSS từ Buổi 1]. Hãy giúp tôi: 1. Xác định những thành phần HTML đã có. 2. Chỉ ra các thành phần HTML còn thiếu hoặc chưa hợp lý. 3. Nêu ba vấn đề về cấu trúc HTML hoặc trình bày. 4. Đề xuất cách cải thiện bằng kiến thức HTML5 và CSS3 cơ bản. 5. Giải thích thứ tự nên thực hiện các cải tiến. Chưa viết lại toàn bộ mã nguồn. Không tạo website mới. Hãy giúp tôi hiểu mã hiện tại trước khi sửa."*
- **Kết quả AI đề xuất:**
  - AI chỉ ra các thành phần đã có (header, search, danh sách sản phẩm, review, footer).
  - AI phát hiện trang web chưa có thẻ `<main>` bao trọn nội dung chính; hình ảnh sản phẩm đang dùng placeholder; thẻ sản phẩm chưa có nút "Xem chi tiết"; chưa có trạng thái `:focus-visible`.
  - Bảng tổng hợp đề xuất:
    | Vấn đề tồn tại | Hướng cải thiện | Kết quả mong muốn |
    |---|---|---|
    | Thiếu thẻ bao bọc nội dung chính | Bổ sung thẻ `<main id="main-content">` | Cấu trúc cây DOM chuẩn SEO & Accessibility |
    | Ảnh sản phẩm dùng placeholder xám | Bổ sung thư mục `images/` với ảnh thật của Cocoon | Giao diện sinh động, chuyên nghiệp |
    | Thẻ sản phẩm chỉ có 1 nút "Thêm vào giỏ" | Thêm cụm `.product-actions` gồm nút Xem chi tiết và Thêm giỏ | Người dùng có thêm lựa chọn xem thông tin |
    | Chưa có phản hồi bàn phím khi duyệt Tab | Thêm pseudo-class `:focus-visible` | Hỗ trợ chuẩn trợ năng WCAG |
- **Đánh giá và điều chỉnh của sinh viên:**  
  Em đồng ý với phân tích của AI và quyết định chọn khu vực **Danh sách sản phẩm (Product Grid) và Thẻ sản phẩm (Product Card)** làm trọng tâm thực hành, đồng thời cải tiến cả Header/Nav bằng Flexbox.

---

### Prompt 2 – Củng cố cấu trúc HTML5 có ngữ nghĩa (Bước 2)
- **Câu lệnh Prompt:**
  > *"Tôi đang học HTML5 và muốn cải thiện cấu trúc HTML của bài tập Buổi 1. Hãy hướng dẫn tôi: 1. Xác định các phần tử HTML đang được sử dụng. 2. Kiểm tra cách sử dụng header, nav, main, section, article và footer. 3. Kiểm tra thứ bậc tiêu đề h1, h2, h3. 4. Kiểm tra cách sử dụng img, alt và a. 5. Phát hiện các thẻ chưa đóng hoặc lồng nhau chưa hợp lý. 6. Đề xuất cách sửa phù hợp với nội dung hiện tại. Phân biệt lỗi cần sửa và đề xuất cải thiện. Không thêm phần tử HTML chỉ để làm mã nguồn dài hơn."*
- **Kết quả AI đề xuất:**
  - Bổ sung thẻ `<main>` ngay sau `</header>` và đóng trước `<footer>`.
  - Phân cấp tiêu đề: `<h1>` duy nhất ở Hero Banner, `<h2>` cho tiêu đề mỗi Section, `<h3>` cho tên sản phẩm trong từng `<article>`, `<h4>` cho các thẻ phụ.
  - Thẻ `<img>` cần mô tả `alt` chi tiết công dụng sản phẩm (vd: `alt="Sữa rửa mặt sen Hậu Giang Cocoon làm dịu da nhạy cảm"`).
  - Thêm thẻ `<a href="#product-detail" class="btn-detail">Xem chi tiết</a>` bên trong thẻ sản phẩm.
- **Đánh giá và điều chỉnh của sinh viên:**  
  Em đã áp dụng chính xác cấu trúc này vào tệp `index.html`. Em tự viết thêm một modal JavaScript thuần đơn giản để khi người dùng bấm "Xem chi tiết", một popup hiện lên hiển thị thông tin sản phẩm đầy đủ và có thể đóng bằng phím ESC.

---

### Prompt 3 – Tạo và liên kết tệp CSS cơ bản (Bước 3)
- **Câu lệnh Prompt:**
  > *"Tôi có website HTML5 từ bài tập Buổi 1. Hãy hướng dẫn tôi: 1. Tạo và liên kết file css/style.css. 2. Định dạng font chữ, màu chữ và màu nền. 3. Thiết lập margin và các quy tắc cơ bản cho body. 4. Đảm bảo hình ảnh không vượt quá chiều rộng phần tử chứa. 5. Kiểm tra đường dẫn CSS có chính xác không. Chỉ tạo CSS cần thiết cho bài tập. Không sử dụng Bootstrap hoặc Tailwind CSS."*
- **Kết quả AI đề xuất:**
  - Quy tắc reset: `* { box-sizing: border-box; margin: 0; padding: 0; }`.
  - Định dạng body: `font-family: 'Segoe UI', Tahoma, sans-serif; color: #222222; background-color: #fafaf7; line-height: 1.6;`.
  - Quy tắc ảnh chống tràn: `img { max-width: 100%; height: auto; display: block; }`.
- **Đánh giá và điều chỉnh của sinh viên:**  
  Em đã đưa các quy tắc này vào đầu tệp `css/style.css` và kiểm tra trên trình duyệt qua DevTools để đảm bảo tệp CSS được nạp thành công (mã trạng thái 200).

---

### Prompt 4 – Thực hành CSS Selector và Box Model (Bước 4)
- **Câu lệnh Prompt:**
  > *"Tôi muốn thực hành CSS selector và Box Model trên một thẻ sản phẩm trong website của mình. Hãy hướng dẫn tôi: 1. Sử dụng element selector và class selector. 2. Sử dụng descendant selector khi phù hợp. 3. Điều chỉnh margin, padding và border. 4. Sử dụng border-radius để bo góc. 5. Định dạng tên và giá sản phẩm. 6. Định dạng liên kết thành nút thao tác đơn giản. Hãy giải thích sự khác nhau giữa margin và padding. Giải thích tác dụng của box-sizing: border-box."*
- **Kết quả AI đề xuất:**
  - Thẻ sản phẩm: `.product-card { border: 1px solid #e5e7eb; border-radius: 12px; background-color: #ffffff; overflow: hidden; display: flex; flex-direction: column; }`.
  - Khoảng đệm nội dung: `.product-info { padding: 16px; }`.
  - Descendant selector: `.product-card .product-title { font-size: 1.05rem; margin-bottom: 6px; }`.
  - Nút xem chi tiết: `.btn-detail { display: inline-flex; padding: 8px 14px; border: 1px solid #2e7d32; border-radius: 20px; color: #2e7d32; }`.
- **Đánh giá và điều chỉnh của sinh viên:**  
  Em đã kiểm tra box-sizing trong DevTools. Nhờ có `box-sizing: border-box`, khi em tăng `padding: 16px` cho `.product-info`, chiều rộng của thẻ sản phẩm không bị nở to làm vỡ hàng Grid.

---

### Prompt 5 – Thực hành Flexbox căn chỉnh thành phần (Bước 5)
- **Câu lệnh Prompt:**
  > *"Tôi đang học CSS3 và muốn thực hành Flexbox trên một khu vực của website thương mại điện tử. Hãy hướng dẫn tôi: 1. Xác định phần tử cha cần sử dụng display: flex. 2. Căn chỉnh các phần tử bằng justify-content. 3. Căn chỉnh theo trục còn lại bằng align-items. 4. Tạo khoảng cách bằng gap. 5. So sánh kết quả khi thay đổi các giá trị của justify-content. Không sử dụng framework CSS."*
- **Kết quả AI đề xuất:**
  - Áp dụng trên `.site-header .header-inner`: `display: flex; justify-content: space-between; align-items: center; gap: 16px;`.
  - Áp dụng trên `.product-actions`: `display: flex; gap: 8px; align-items: center; margin-top: 8px;`.
  - Áp dụng trên `.price-sold`: `display: flex; justify-content: space-between; align-items: baseline;`.
- **Đánh giá và điều chỉnh của sinh viên:**  
  Em đã thử nghiệm đổi `justify-content` giữa `space-between`, `center` và `flex-start` trong DevTools để quan sát sự dịch chuyển của logo và giỏ hàng, sau đó giữ `space-between` cho header để giao diện cân đối nhất.

---

### Prompt 6 – Hoàn thiện danh sách sản phẩm bằng CSS Grid (Bước 6)
- **Câu lệnh Prompt:**
  > *"Tôi đã có một danh sách sản phẩm bằng HTML. Hãy hướng dẫn tôi sử dụng CSS Grid để: 1. Bố trí danh sách thành hai hoặc ba cột. 2. Điều chỉnh khoảng cách giữa các sản phẩm. 3. Giữ hình ảnh hiển thị đúng tỷ lệ, không bị méo. 4. Thay đổi số cột và quan sát kết quả. 5. Giải thích grid-template-columns, repeat và gap. 6. Giải thích tác dụng của object-fit: cover."*
- **Kết quả AI đề xuất:**
  - Lưới sản phẩm: `.products-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(280px, 1fr)); gap: 24px; }`.
  - Khung ảnh sản phẩm: `.product-img { aspect-ratio: 1 / 1; overflow: hidden; }`.
  - Ảnh bên trong: `.product-card .product-img img { width: 100%; height: 100%; object-fit: cover; }`.
- **Đánh giá và điều chỉnh của sinh viên:**  
  AI ban đầu gợi ý `height: 220px` cho ảnh, nhưng em đã tự phát hiện ảnh sẽ bị co méo nếu người dùng đổi kích thước cửa sổ. Em đã thay bằng `aspect-ratio: 1 / 1;` kết hợp `object-fit: cover;` để ảnh luôn giữ chuẩn hình vuông 100%.

---

### Prompt 7 – Bổ sung hiệu ứng hover và focus-visible (Bước 7)
- **Câu lệnh Prompt:**
  > *"Tôi muốn bổ sung hiệu ứng hover và focus cho một nút bấm hoặc liên kết trong website. Hãy hướng dẫn tôi: 1. Tạo hiệu ứng hover nhẹ. 2. Sử dụng transition để tạo chuyển đổi mượt. 3. Bổ sung focus-visible để hỗ trợ điều hướng bằng bàn phím. 4. Đảm bảo màu chữ và màu nền dễ nhìn. 5. Không làm thay đổi bố cục quá nhiều. Giải thích từng thuộc tính và cách kiểm tra."*
- **Kết quả AI đề xuất:**
  - Hiệu ứng hover nổi thẻ: `.product-card:hover { transform: translateY(-4px); box-shadow: 0 8px 24px rgba(0, 0, 0, 0.12); }`.
  - Hiệu ứng hover nút: `.btn:hover { transform: translateY(-2px); box-shadow: 0 4px 12px rgba(0, 0, 0, 0.15); }`.
  - Chuẩn Accessibility: `:focus-visible { outline: 3px solid #2e7d32; outline-offset: 3px; }`.
- **Đánh giá và điều chỉnh của sinh viên:**  
  Em đã dùng phím **Tab** trên bàn phím để duyệt qua từng liên kết và nút bấm. Khi ấn Tab, viền màu xanh lá đậm nổi bật quanh phần tử đang chọn giúp định vị cực kỳ rõ ràng, đạt chuẩn trợ năng WCAG.

---

### Prompt 8 – Nhờ AI hỗ trợ kiểm tra lỗi giao diện (Bước 8)
- **Câu lệnh Prompt:**
  > *"Tôi đã hoàn thành một phần giao diện website TMĐT bằng HTML5 và CSS3. Tôi nhận thấy vấn đề: Khi xem trên màn hình nhỏ 390px, hai nút trong cụm product-actions bị chen chúc nhau, chữ trên nút bị tràn thành 2 dòng trông xấu mắt. Hãy giúp tôi: 1. Xác định nguyên nhân. 2. Đề xuất cách sửa ít thay đổi nhất. 3. Giải thích vì sao cách sửa giải quyết được vấn đề."*
- **Kết quả AI đề xuất:**
  - Nguyên nhân: Trên màn hình có độ rộng hẹp (390px), thẻ card bị thu nhỏ lại, hai nút đặt cạnh nhau trong flex-row không đủ không gian chứa văn bản.
  - Cách khắc phục: Trong `@media (max-width: 480px)`, chuyển `.product-actions` sang `flex-direction: column;` và gán `width: 100%;` cho cả `.btn-detail` lẫn `.btn-add-cart`.
- **Đánh giá và điều chỉnh của sinh viên:**  
  Em đã áp dụng giải pháp này vào media query mobile trong `css/style.css` và kiểm tra lại qua DevTools ở kích thước 390px. Kết quả hai nút xếp chồng lên nhau gọn gàng, nút bấm to rõ, ngón tay dễ bấm chạm trên điện thoại.

---

### Prompt 9 – Soạn thảo README.md hoàn chỉnh (Bước 14)
- **Câu lệnh Prompt:**
  > *"Tôi đang hoàn thiện README.md cho bài tập cá nhân Buổi 2 của môn Phát triển ứng dụng TMĐT. Hãy đề xuất cấu trúc README chuẩn mực gồm 7 mục theo đề bài: Giới thiệu bài tập, Website tham khảo và khu vực cải tiến, Kỹ thuật HTML5/CSS3, Hướng dẫn chạy website, Những thay đổi đã thực hiện, Công cụ AI và cách kiểm tra kết quả, Câu hỏi kiến thức và đường dẫn repository."*
- **Kết quả AI đề xuất:**
  - AI cung cấp khung tài liệu chi tiết với bảng so sánh trước/sau, bảng kiểm thử và cấu trúc thư mục.
- **Đánh giá và điều chỉnh của sinh viên:**  
  Em đã điền đầy đủ các thông tin cá nhân (MSSV 31241024339, Họ tên Trần Thị Kim Thư, Trường UEH), chèn các đường dẫn ảnh chụp màn hình minh chứng thật (`docs/screenshots/`), và trả lời chi tiết toàn bộ 7 câu hỏi kiểm tra kiến thức dựa trên đúng mã nguồn của dự án.

---

## 3. Tổng kết phần sinh viên tự thực hiện và kiểm soát (Human-in-the-Loop)
1. **Kiểm tra và xác thực mã nguồn:** Đảm bảo toàn bộ HTML5 và CSS3 không sử dụng bất kỳ thư viện bên ngoài nào (không dùng Bootstrap, Tailwind, jQuery hay React), đúng theo yêu cầu bài học cơ bản.
2. **Tự tay tải và xử lý hình ảnh:** Thu thập 8 ảnh sản phẩm và combo thực tế từ Cocoon Vietnam, tối ưu dung lượng và đặt trong thư mục `images/`.
3. **Tự sửa lỗi hiển thị:** Thay đổi giải pháp chiều cao cố định của AI thành `aspect-ratio: 1 / 1` kết hợp `object-fit: cover` để ảnh luôn giữ chuẩn hình vuông.
4. **Kiểm thử trên trình duyệt:** Sử dụng DevTools giả lập 3 kích thước (1366px, 768px, 390px) và kiểm tra chức năng tiếp cận bằng phím Tab.
5. **Chụp ảnh minh chứng:** Tạo các ảnh chụp màn hình Before & After, Desktop, Tablet, Mobile lưu trong thư mục `docs/screenshots/`.
