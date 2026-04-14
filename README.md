# Fullstack Java Travel Blog

Fullstack Java Travel Blog là một dự án website du lịch toàn diện, gồm:
- front-end tĩnh với giao diện HTML/CSS/JavaScript cho blog, danh mục, trang chi tiết, quản trị và tìm kiếm;
- back-end Spring Boot xử lý API, xác thực người dùng, quản lý bài viết, hình ảnh và bình luận.

## Tổng quan

Dự án mô phỏng hệ thống blog du lịch, cho phép người dùng:
- tạo và quản lý bài viết du lịch;
- tải ảnh lên và gán ảnh cho bài viết;
- bình luận trên bài viết;
- duyệt blog công khai, tìm kiếm theo từ khóa và hiển thị bài viết mới nhất.

## Kiến trúc dự án

- `client/` - giao diện front-end tĩnh, gồm các trang HTML, CSS, SCSS, JS và tài nguyên media.
- `server/` - back-end Java Spring Boot, kết nối MongoDB và cung cấp REST API.

## Công nghệ sử dụng

- Front-end: HTML5, CSS3, SCSS, JavaScript, Bootstrap
- Back-end: Java, Spring Boot, Spring MVC, Spring Data MongoDB, Spring WebSocket
- Cơ sở dữ liệu: MongoDB
- Lưu trữ ảnh: Cloudinary
- Xác thực JWT và mã hóa mật khẩu
- API documentation: SpringDoc OpenAPI
- Build: Maven (sử dụng Maven Wrapper)

## Điểm nổi bật

- Kiến trúc fullstack rõ ràng: front-end tách biệt với back-end.
- RESTful API cho blog, người dùng, ảnh và bình luận.
- Upload ảnh với Cloudinary.
- Hỗ trợ WebSocket để mở rộng tính năng realtime.
- Sử dụng MapStruct và Lombok để giảm boilerplate trong layer dịch vụ.

## Thiết lập và chạy dự án

### Backend

1. Truy cập thư mục `server`:
    ```bash
    cd server
    ```

2. Cài đặt và chạy bằng Maven Wrapper:
    - Trên Windows:
      ```powershell
      ./mvnw.cmd spring-boot:run
      ```
    - Trên macOS / Linux:
      ```bash
      ./mvnw spring-boot:run
      ```

3. Hoặc build package và chạy file JAR:
    ```bash
    ./mvnw package -DskipTests
    java -jar target/blogdulich-0.0.1-SNAPSHOT.jar
    ```

### Frontend

- Mở trực tiếp `client/index.html` trong trình duyệt.
- Hoặc dùng một static server nếu cần phục vụ nhiều page cùng lúc.

## Biến môi trường đề xuất

Backend cần cấu hình thông tin kết nối và dịch vụ bên thứ ba. Tạo file `.env` trong `server/` với các biến tương tự:

```text
MONGODB_URI=<your_mongodb_connection_string>
CLOUD_NAME=<your_cloudinary_cloud_name>
CLOUD_API_KEY=<your_cloudinary_api_key>
CLOUD_API_SECRET=<your_cloudinary_api_secret>
```

> Nếu dự án sử dụng thêm JWT hoặc cấu hình bảo mật khác, hãy bổ sung biến môi trường phù hợp.

## Các endpoint chính

- `POST /api/user` - tạo người dùng mới
- `POST /api/user/signin` - đăng nhập
- `GET /api/user/me` - lấy thông tin người dùng hiện tại
- `GET /api/user/all` - lấy danh sách người dùng
- `POST /api/blog` - tạo bài viết mới
- `PUT /api/blog/{id}` - chỉnh sửa bài viết
- `DELETE /api/blog/{id}` - xóa bài viết
- `GET /api/blog/all` - lấy tất cả bài viết
- `GET /api/blog/public` - lấy bài viết công khai
- `GET /api/blog/newest` - lấy bài viết mới nhất
- `GET /api/blog/home` - lấy nội dung trang chủ
- `POST /api/image` - upload ảnh
- `DELETE /api/image/{id}` - xóa ảnh
- `POST /api/comment` - thêm bình luận
- `GET /api/comment/{blogId}` - lấy bình luận của bài viết

## Cấu trúc thư mục chính

- `client/` - front-end trang đích, blog, liên hệ, quản trị, HTML/CSS/JS
- `server/src/main/java` - mã nguồn Spring Boot
- `server/src/main/resources` - cấu hình ứng dụng và tài nguyên Spring Boot
- `server/src/test/java` - bài test đơn vị cơ bản

## Mở rộng và phát triển

- Kết nối front-end với API bằng AJAX/Fetch hoặc framework SPA.
- Thêm hệ thống phân quyền người dùng `admin` và `user`.
- Hoàn thiện chức năng WebSocket cho chat hoặc thông báo realtime.
- Triển khai trên cloud với Docker hoặc nền tảng PaaS.

## Ghi chú

- Front-end hiện tại là tĩnh và có thể nâng cấp thành SPA.
- Backend sử dụng MongoDB, nên cần kết nối tới cluster hoặc database cục bộ.
- Cấu trúc này phù hợp để phát triển thành nền tảng du lịch/blog đa người dùng.
