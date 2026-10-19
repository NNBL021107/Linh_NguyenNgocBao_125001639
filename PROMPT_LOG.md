# Linh_NguyenNgocBao_125001639
# NHẬT KÝ PROMPT ENGINEERING (VIBE CODING LOG)

- **Họ và tên:** Nguyễn Ngọc Bảo Linh
- **MSSV:** 125001639
- **Lớp / Khóa:** 25CT113
- **Tên đề tài Website:** Thiết kế Website Portfolio cá nhân chuẩn Responsive & Semantic HTML5
- **Công cụ AI đã sử dụng:** Antigravity IDE (Mô hình Gemini 3.8 Flash High)

---

## 1. Yêu cầu ban đầu (System/Initial Prompt)
> *"Bạn là một lập trình viên Front-End chuyên nghiệp. Hãy giúp tôi viết mã nguồn hoàn chỉnh cho một trang Website Portfolio cá nhân để nộp bài tập giữa kỳ môn Thiết kế Web.*
>
> *Yêu cầu kỹ thuật bắt buộc:*
> 1. *Cấu trúc HTML5 chuẩn Semantic: Phải sử dụng đúng và tối thiểu các thẻ ngữ nghĩa: `<header>`, `<nav>`, `<main>`, `<section>` (hoặc `<article>`), và `<footer>`. Tuyệt đối không lạm dụng thẻ div vô nghĩa.*
> 2. *CSS & CSS Variables: Sử dụng `:root` để định nghĩa hệ thống biến CSS (`--primary-color`, `--secondary-color`, `--bg-color`, `--text-color`, `--font-main`, `--spacing-unit`). Giao diện hiện đại, tối ưu UI/UX thẩm mỹ cao.*
> 3. *Layout: Sử dụng thành thạo CSS Flexbox và CSS Grid để dàn trang responsive cho cả Desktop và Mobile.*
> 4. *Thư viện hiệu ứng: Tích hợp sẵn CDN của Animate.css và thư viện AOS (Animate On Scroll) vào file HTML.*
> 5. *Nội dung Portfolio gồm các phần: Header/Nav (Giới thiệu, Kỹ năng, Dự án, Liên hệ), Hero Section, About Section, Skills Section, Projects Section, Contact Section / Footer.*
>
> *Hãy trả về toàn bộ mã nguồn gồm file index.html và file style.css riêng biệt."*

---

## 2. Quá trình tinh chỉnh & Giải quyết sự cố (Iteration Iterations)

### Lần 1: Dựng khung Semantic HTML & CSS Variables
- **Prompt đã dùng:** *"Hãy khởi tạo cấu trúc khung HTML5 chuẩn ngữ nghĩa tối thiểu 5 thành phần `<header>`, `<nav>`, `<main>`, `<section>`/`<article>`, `<footer>` cùng file style.css khai báo hệ thống biến `:root` theo đúng đề bài."*
- **Kết quả AI tạo ra:**
  - File `index.html` đầy đủ các thẻ ngữ nghĩa, chia tách rành mạch các khu vực Hero, Giới thiệu, Kỹ năng, Dự án và Liên hệ.
  - File `style.css` khai báo hệ thống Design Tokens trong `:root` với đầy đủ các biến màu, font chữ và đơn vị khoảng cách `--spacing-unit`.
- **Nhận xét & Tinh chỉnh của SV:** 
  - Khung HTML phân tách rất rõ ràng, tuy nhiên ở lần tạo đầu tiên AI vẫn còn dùng một số thẻ `<div>` bọc bao quanh bên trong các section.
  - Sinh viên đã yêu cầu AI thay thế các khối thẻ kỹ năng và dự án bằng thẻ ngữ nghĩa `<article>`, đồng thời đưa phần liên hệ vào thẻ `<address>` để đạt điểm tối đa tiêu chí Semantic HTML5 (2.0 điểm).

---

### Lần 2: Tích hợp thư viện Animate.css & AOS (Animate On Scroll)
- **Prompt đã dùng:** *"Tích hợp CDN của Animate.css và AOS vào index.html. Áp dụng hiệu ứng động Animate.css cho tiêu đề chính, Hero section và nút CTA. Kích hoạt hiệu ứng cuộn trang AOS cho các section nội dung và card dự án."*
- **Thách thức gặp phải:** 
  - Ban đầu hiệu ứng cuộn trang AOS không hoạt động khi cuộn chuột xuống các section dưới, do file script chưa khởi tạo `AOS.init()` đúng thời điểm sau khi cây DOM được tải xong (`DOMContentLoaded`).
  - Thẻ bài viết và nút bấm thiếu trạng thái `:focus` (mới chỉ có `:hover`), chưa đạt yêu cầu tiếp cận người dùng (Accessibility).
- **Cách sửa prompt (Debug prompt):** 
  - Prompt sửa lỗi: *"Kiểm tra lại script khởi tạo AOS với sự kiện DOMContentLoaded, cấu hình `once: true` để animation mượt mà. Đồng thời viết bổ sung hiệu ứng `:focus` và `:focus-visible` bằng CSS cho toàn bộ nút bấm `.btn` và các thẻ `.skill-card`, `.project-card`."*
  - Kết quả sau sửa: AOS hoạt động ổn định, khi cuộn trang các thẻ bay lên mượt mà; các nút bấm và card có viền focus rõ ràng khi dùng phím Tab.

---

### Lần 3: Rà soát bám sát yêu cầu đề bài & Chuẩn hóa thông tin cá nhân
- **Prompt đã dùng:** *"Theo sát đề bài gốc, không thêm không bớt các mục ngoài lề (chỉ giữ đúng 4 mục điều hướng: Giới thiệu, Kỹ năng, Dự án, Liên hệ). Cập nhật tên tác giả thành Nguyễn Ngọc Bảo Linh, sinh viên năm 2 khoa CNTT Đại học Lạc Hồng (LHU)."*
- **Kết quả AI tạo ra:**
  - Loại bỏ các phần thừa không có trong đề bài, tinh gọn đúng cấu trúc chuẩn.
  - Cập nhật toàn bộ thông tin cá nhân của sinh viên Nguyễn Ngọc Bảo Linh ở Header, Logo `<BL.Dev/>`, Hero, About, Email (`baolinh.lhu@gmail.com`) và Footer bản quyền.
- **Nhận xét & Tinh chỉnh của SV:** Bố cục cô đọng, đúng trọng tâm đề thi môn Thiết kế Web, thông tin cá nhân đồng bộ 100% giữa file HTML và CSS.

---

### Lần 4: Đổi mới giao diện sang phong cách Nữ tính (Feminine Aesthetic)
- **Prompt đã dùng:** *"Thiết kế màu sắc nữ tính hơn cho website của nữ sinh viên CNTT: Chuyển từ tone tối (dark slate) sang tone hồng pastel/rose peony trang nhã, nhẹ nhàng, hiện đại nhưng vẫn đảm bảo độ tương phản cao chuẩn WCAG."*
- **Kết quả AI tạo ra:**
  - Hệ thống `:root` được thay đổi:
    - `--primary-color: #d85d7b;` (Hồng Peony ngọt ngào, tinh tế)
    - `--secondary-color: #f497aa;` (Hồng Sakura pastel dịu nhẹ)
    - `--bg-color: #fdf8f9;` (Nền trắng ánh hồng phấn thanh lịch)
    - `--text-color: #3d292e;` (Nâu than ấm tương phản cao, dễ đọc)
  - Thẻ card chuyển sang màu trắng tinh khôi với viền hồng phấn và bóng đổ mềm (`box-shadow: 0 12px 30px rgba(216, 93, 123, 0.14)`).
  - Các icon kỹ năng và banner dự án mang dải màu Gradient hoàng hôn pastel lãng mạn.
- **Nhận xét & Tinh chỉnh của SV:** Giao diện lột xác hoàn toàn, mang nét nữ tính đặc trưng của sinh viên nữ ngành IT, tính thẩm mỹ cao và tạo ấn tượng thị giác rất tốt.

---

## 3. Đánh giá cá nhân về quá trình Vibe Coding

### AI đã giúp bạn tiết kiệm thời gian ở phần nào nhất?
1. **Viết boilerplate và CSS Variables:** Giúp tạo nhanh bảng mã màu, reset CSS, cấu hình biến `:root` và hệ thống Flexbox/Grid chuẩn chỉ trong vài giây thay vì phải gõ thủ công từng dòng.
2. **Tích hợp CDN & Cấu hình hiệu ứng:** Việc nạp chính xác các link CDN Font Awesome, Animate.css, AOS và viết cú pháp `data-aos`, `animate__animated` được tự động hóa hoàn toàn, hạn chế tối đa lỗi gõ sai đường dẫn.
3. **Responsive Media Queries:** Tạo sẵn các điểm ngắt (breakpoints 768px, 480px) và menu Hamburger di động mượt mà, giúp tiết kiệm ít nhất 70% thời gian dàn trang đa thiết bị.

### Bài học rút ra khi đặt câu hỏi (Prompt) cho AI trong thiết kế web?
1. **Prompt cần rõ ràng và phân tách theo ngữ cảnh (Contextual Prompting):** Khi yêu cầu AI, nên cung cấp các từ khóa kỹ thuật chuẩn (Semantic HTML5, CSS Variables, Flexbox, Grid, Animate.css, AOS) thay vì chỉ mô tả chung chung "làm cho tôi một website đẹp".
2. **Kỹ năng phản biện và kiểm soát mã nguồn của lập trình viên:** AI có xu hướng tự ý thêm các tính năng mở rộng hoặc dùng nhiều thẻ `<div>`. Lập trình viên phải hiểu sâu tiêu chí chấm điểm để kịp thời nhắc nhở AI: *"theo sát đề, không thêm không bớt, dùng đúng thẻ ngữ nghĩa"*.
3. **Tư duy tinh chỉnh lặp (Iterative Refinement):** Không nên kỳ vọng một prompt duy nhất ra kết quả hoàn hảo. Quá trình chia nhỏ thành từng lần (Tạo khung -> Tích hợp thư viện -> Rà soát đề -> Tinh chỉnh màu sắc UX/UI) sẽ mang lại sản phẩm chỉn chu và đạt điểm tối đa.
