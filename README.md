# Portfolio cá nhân - Lê Hữu Hoạt

Trang portfolio giới thiệu Lê Hữu Hoạt, các kỹ năng, những nội dung liên quan đến công việc và thông tin liên hệ. Dự án được xây dựng dưới dạng trang web tĩnh, phù hợp để xem trực tiếp trong trình duyệt hoặc phục vụ bằng máy chủ web.

## Chức năng

- Hiển thị phần giới thiệu và ảnh đại diện.
- Điều hướng đến các mục Giới thiệu, Kỹ năng, Dự án và Liên hệ.
- Trình bày danh sách kỹ năng và các thẻ nội dung có hình ảnh, mô tả, liên kết.
- Cung cấp email, Facebook và số điện thoại liên hệ.
- Bố cục responsive cho điện thoại, máy tính bảng và máy tính để bàn.

## Công nghệ

- HTML5: cấu trúc và nội dung trang.
- CSS3: giao diện, Flexbox, CSS Grid và responsive mobile-first.
- Docker với Nginx: tùy chọn để phục vụ trang trong container.

> Trang hiện là website tĩnh, không sử dụng framework JavaScript, backend, cơ sở dữ liệu, trình quản lý gói hay bước biên dịch.

## Cấu trúc dự án

```text
.
├── index.html
├── README.md
└── assets/
	 ├── css/
	 │   └── styles.css
	 └── img/
		  ├── avt.jpg
		  ├── laptop.jpg
		  ├── grn.jpg
		  ├── anh.jpg
		  └── DwcMinh.jpg
```

Đảm bảo các ảnh có mặt đúng tên và đúng đường dẫn trong `assets/img/`; nếu thiếu ảnh, phần tương ứng có thể không hiển thị.

## Yêu cầu môi trường

Để mở trực tiếp trang, chỉ cần một trình duyệt hiện đại như Chrome, Firefox, Edge hoặc Safari. Không cần cài Node.js hay các thư viện dự án.

Để chạy bằng máy chủ cục bộ, cần Python 3. Để chạy bằng Docker, cần Docker Engine hoặc Docker Desktop đang hoạt động và kết nối Internet lần đầu để tải image `nginx:alpine`.

## Cài đặt và chạy thử

### Cách nhanh: mở trực tiếp

Mở file `index.html` bằng trình duyệt. Cách này không yêu cầu cài thêm phần mềm; tuy nhiên, chạy qua máy chủ HTTP bên dưới phản ánh môi trường triển khai web sát hơn.

### Windows

1. Cài Python 3 nếu máy chưa có. Có thể kiểm tra bằng PowerShell:

	```powershell
	py --version
	```

2. Mở PowerShell hoặc Command Prompt tại thư mục chứa `index.html`.
3. Khởi chạy máy chủ:

	```powershell
	py -m http.server 8000
	```

	Nếu lệnh `py` không có, thử `python -m http.server 8000`.
4. Mở [http://localhost:8000](http://localhost:8000) trên trình duyệt.
5. Nhấn `Ctrl+C` trong cửa sổ terminal để dừng máy chủ.

### macOS

1. Mở Terminal và chuyển đến thư mục dự án, ví dụ:

	```bash
	cd "/duong-dan/toi/KT A2.1"
	```

2. Kiểm tra Python 3 và chạy máy chủ:

	```bash
	python3 --version
	python3 -m http.server 8000
	```

3. Mở [http://localhost:8000](http://localhost:8000) trên trình duyệt.
4. Nhấn `Control+C` trong Terminal để dừng máy chủ.

### Linux

1. Mở terminal, chuyển đến thư mục dự án và kiểm tra Python 3:

	```bash
	cd /duong-dan/toi/KT-A2.1
	python3 --version
	```

2. Khởi chạy máy chủ:

	```bash
	python3 -m http.server 8000
	```

3. Mở [http://localhost:8000](http://localhost:8000) trên trình duyệt.
4. Nhấn `Ctrl+C` trong terminal để dừng máy chủ.

### Docker

Không cần Dockerfile: dùng Nginx để phục vụ thư mục dự án trực tiếp. Chạy các lệnh tại thư mục chứa `index.html`.

**macOS / Linux / PowerShell:**

```bash
docker run --rm -d --name portfolio-hoat -p 8080:80 -v "${PWD}:/usr/share/nginx/html:ro" nginx:alpine
```

**Windows Command Prompt (CMD):**

```bat
docker run --rm -d --name portfolio-hoat -p 8080:80 -v "%cd%:/usr/share/nginx/html:ro" nginx:alpine
```

Sau khi container khởi động, mở [http://localhost:8080](http://localhost:8080). Dừng container bằng:

```bash
docker stop portfolio-hoat
```

Lệnh chạy gắn thư mục dự án ở chế độ chỉ đọc; container sẽ tự được xóa sau khi dừng nhờ tùy chọn `--rm`.

## Cấu hình và tùy chỉnh

- Nội dung, tiêu đề, mô tả và liên kết nằm trong `index.html`.
- Màu sắc, bố cục và điểm responsive nằm trong `assets/css/styles.css`.
- Thay ảnh trong `assets/img/` hoặc cập nhật đường dẫn `src` tương ứng trong HTML.
- Có thể thay email, Facebook, số điện thoại và các liên kết dự án trong `index.html`.
- Không cần file `.env` hay cấu hình build. Cổng chạy mặc định trong hướng dẫn là `8000` (Python) hoặc `8080` (Docker); đổi số cổng nếu cổng đó đang được sử dụng.

## Thông tin liên hệ

- **Tác giả:** Lê Hữu Hoạt
- **Email:** [lhhoat2008@gmail.com](mailto:lhhoat2008@gmail.com)
- **Facebook:** [Hữu Hoạt](https://www.facebook.com/lhhoat)
- **Số điện thoại:** 0915644394
