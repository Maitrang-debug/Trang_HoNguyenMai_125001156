# NHẬT KÝ PROMPT ENGINEERING (VIBE CODING LOG)

- **Họ và tên:** Hồ Nguyễn Mai Trang
- **MSSV:** 125001156
- **Tên đề tài Website:** MAI TRANG PATISSERIE - Website Tiệm Bánh Ngọt & Trà Chiều Pháp Cao Cấp
- **Công cụ AI đã sử dụng:** Antigravity (Powered by DeepMind Gemini 3.8 Flash)

---

## 1. Yêu cầu ban đầu (System/Initial Prompt)

> *"Hãy đóng vai trò là một chuyên gia Lập trình Front-End và Chuyên viên Thiết kế UI/UX Ẩm thực Bánh ngọt Pháp (French Patisserie Designer). Tôi cần tạo một website cho tiệm bánh ngọt nghệ thuật & trà chiều mang tên tôi là **'MAI TRANG PATISSERIE'**, với tone màu chủ đạo là **Burgundy (Đỏ rượu vang / Đỏ mận quý tộc)** kết hợp **Beige (Màu be / Kem ấm áp cổ điển)**.*
>
> *Website phải kế thừa cấu trúc kỹ thuật từ Buổi 5 và tuân thủ nghiêm ngặt các tiêu chí sau:*
> 1. *Chuẩn Semantic HTML5: Bắt buộc dùng đúng ngữ nghĩa các thẻ `<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<footer>`, `<address>`, tuyệt đối không lạm dụng thẻ `<div>` vô nghĩa.*
> 2. *CSS Variables & Thiết kế thẩm mỹ: Khai báo hệ thống biến `:root` quản lý màu sắc tone Burgundy & Beige chuẩn tiệm bánh Paris (`--burgundy-primary: #721c24`, `--burgundy-dark: #501319`, `--beige-bg: #f8f4ee`, `--beige-border: #e8dfd6`, `--gold-accent: #c5a059`), font chữ cổ điển ('Playfair Display', 'Plus Jakarta Sans'), spacing và bo góc radius mềm mại.*
> 3. *Tối ưu hóa Responsive: Căn chỉnh hoàn hảo trên cả máy tính (Desktop) và điện thoại di động (Mobile) bằng CSS Flexbox và CSS Grid.*
> 4. *Thư viện & Hiệu ứng: Tích hợp Animate.css cho tiêu đề/nút CTA, hiệu ứng `:hover`, `:focus` tự viết bằng CSS, thẻ 3D Flip Card lật mặt trước/sau giới thiệu nguyên liệu bơ Pháp, socola Valrhona & bột Uji Matcha (Bài 2), Banner Parallax (Bài 4), Nút Floating Action Button đặt bánh nhanh (Bài 1).*
> 5. *TUYỆT ĐỐI KHÔNG DÙNG JAVASCRIPT: Toàn bộ tương tác bao gồm thanh Hamburger Menu Mobile phải hoạt động 100% bằng kỹ thuật CSS Checkbox Hack của Bài 5."*

---

## 2. Quá trình tinh chỉnh & Giải quyết sự cố (Iteration Iterations)

### Lần 1: Dựng khung Semantic HTML5 & Bảng màu CSS Variables Tone Burgundy & Beige
- **Prompt đã dùng:**
  > *"Khởi tạo cấu trúc HTML5 chuẩn ngữ nghĩa cho tiệm bánh ngọt 'MAI TRANG PATISSERIE'. Phân chia rõ ràng các phân khu: `<header>` chứa logo monogram MT và menu điều hướng; `<main>` chứa Hero Section, giá trị cốt lõi tiệm bánh, danh mục bánh Pháp, danh sách sản phẩm bằng thẻ `<article>`, khu vực nguyên liệu 3D Flip Card, quy trình làm bánh 5 bước, trích dẫn Parallax, đánh giá khách hàng và form đặt bánh hẹn trước; cuối cùng là `<footer>` chứa thông tin xưởng bánh và bản quyền mang tên Hồ Nguyễn Mai Trang (MSSV: 125001156). Xây dựng hệ thống biến `:root` tone màu Burgundy kết hợp Beige ấm cúng, sang trọng."*
- **Kết quả AI tạo ra:**
  - AI đã tạo ra khung HTML phân tầng rõ ràng, bảng màu phối giữa màu đỏ rượu vang đậm đà và nền màu be ấm áp đem lại cảm giác ngon miệng và ấm cúng như các tiệm bánh Paris.
  - Tuy nhiên, một số khối thẻ bánh ngọt ban đầu vẫn bị bọc bởi các thẻ `<div>` lồng nhau.
- **Nhận xét & Tinh chỉnh của SV:**
  - Nhắc AI chuẩn hóa toàn bộ thẻ bao quanh sản phẩm thành `<article class="product-card">`.
  - Thay đổi phần chân trang liên hệ sử dụng thẻ `<address>` chuẩn W3C thay vì danh sách `<ul>` thông thường.

---

### Lần 2: Tích hợp thư viện Animate.css & Typography Tiếng Việt chuẩn
- **Prompt đã dùng:**
  > *"Nhúng thư viện Animate.css từ cdnjs vào dự án. Hãy gắn các class animation của Animate.css (`animate__animated`, `animate__fadeInDown`, `animate__fadeInUp`, `animate__pulse`) vào phần Text tiêu đề, Huy hiệu bánh tươi, và Nút CTA Đặt Bánh Ngay trên Hero Section. Đồng thời, cấu hình font chữ Playfair Display và Plus Jakarta Sans hỗ trợ 100% Tiếng Việt có dấu, không bị lỗi font khi hiển thị tên 'Hồ Nguyễn Mai Trang'."*
- **Thách thức gặp phải:**
  - Font chữ Serif tiêu đề cần mang nét cổ điển quý phái kiểu Pháp nhưng phải có dấu tiếng Việt đầy đủ cho tên sinh viên và các món bánh (Red Velvet, Trà xanh, Bánh mì bơ).
- **Cách sửa prompt (Debug prompt):**
  - Chỉ định rõ ràng bộ đôi font Google Fonts: `Playfair Display` (font chữ có chân thanh lịch của ẩm thực và thời trang Pháp) và `Plus Jakarta Sans` (font không chân hiện đại dễ đọc), cả hai đều hỗ trợ đầy đủ bộ ký tự Tiếng Việt UTF-8.

---

### Lần 3: Xây dựng Menu Mobile bằng CSS Checkbox Hack (Không Dùng JavaScript)
- **Prompt đã dùng:**
  > *"Quy chế bài thi yêu cầu tuyệt đối KHÔNG được sử dụng JavaScript. Hãy hiện thực hóa thanh Menu Hamburger trên điện thoại hoàn toàn bằng kỹ thuật CSS Checkbox Hack của Bài 5: sử dụng `<input type="checkbox" id="menu-toggle" class="menu-checkbox">` và `<label for="menu-toggle" class="hamburger-btn">`. Khi bấm vào nút 3 gạch, menu trượt xuống êm ái và 3 thanh biến hình thành dấu X mà không cần bất kỳ một dòng code JS nào."*
- **Kết quả AI tạo ra & Tinh chỉnh của SV:**
  - Menu mobile hoạt động trơn tru:
    * Trên desktop: Nút 3 gạch ẩn đi (`display: none`), menu dàn ngang bằng Flexbox.
    * Trên mobile: Nút 3 gạch màu Burgundy xuất hiện ở góc phải. Khi chạm vào `<label>`, trạng thái `:checked` của checkbox kích hoạt `transform: translateY(0)`, menu trượt xuống từ thanh header, 3 thanh xoay 45° thành dấu `X`. Chạm lại lần nữa để thu gọn.
  - Toàn bộ website đạt chuẩn 100% HTML5 & CSS3 thuần khiết, 0 lỗi W3C, mở tốt trên mọi thiết bị.

---

## 3. Đánh giá cá nhân về quá trình Vibe Coding

### AI đã giúp bạn tiết kiệm thời gian ở phần nào nhất?
1. **Khởi tạo nội dung mẫu chuyên ngành ẩm thực bánh ngọt Pháp:** Thay vì mất hàng giờ tự tìm kiếm và nghĩ ra tên các dòng bánh ngọt danh tiếng (Viennoiserie Croissant, Red Velvet Cake, Macaron Paris, Valrhona Chocolate Mousse), các nguyên liệu làm bánh chuẩn mực (Bơ Elle & Vire Normandy 82%, Socola Valrhona 70%, Bột Uji Matcha Nhật), AI đã tự động điền sẵn hệ thống dữ liệu ẩm thực chân thực và vô cùng hấp dẫn.
2. **Thiết lập bảng màu CSS Variables Burgundy & Beige hài hòa:** AI hỗ trợ tính toán các sắc độ màu chuyển tiếp từ nền be kem sáng `#f8f4ee` đến các khối màu đỏ mận `#721c24` và viền vàng kim `#c5a059`, tạo nên phong cách nhận diện thương hiệu tiệm bánh sang trọng chuẩn Âu.
3. **Hiện thực hóa tương tác phức tạp bằng CSS thuần:** Giúp viết chuẩn xác các bộ chọn nâng cao như `#menu-toggle:checked ~ .nav-menu-wrapper` và hiệu ứng lật thẻ 3D `.flip-card-wrapper:hover .flip-card-inner` đúng chuẩn đề thi mà không cần dùng đến JavaScript.

### Bài học rút ra khi đặt câu hỏi (Prompt) cho AI trong thiết kế web?
1. **Rõ ràng về mặt ràng buộc kỹ thuật (Constraints):** Việc quy định rõ ngay từ đầu *"Không dùng JavaScript", "Tone màu Burgundy kết hợp Beige", "Tên sinh viên Hồ Nguyễn Mai Trang"* giúp AI không tự ý thêm các thư viện hay mã script ngoài yêu cầu của giáo viên.
2. **Kỹ năng kiểm tra và tinh chỉnh liên tục (Iteration):** Trong quá trình Vibe Coding, sinh viên cần kiểm tra kỹ từng chi tiết trên màn hình điện thoại (F12 Responsive Mode) để kịp thời chỉ đạo AI tối ưu kích thước nút bấm, khoảng cách dòng và đảm bảo menu đóng mở ổn định trên mọi kích thước màn hình.
