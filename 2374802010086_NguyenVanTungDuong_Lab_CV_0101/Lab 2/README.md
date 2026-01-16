# Basic Image Manipulation – PIL & OpenCV

## 1. Mục tiêu bài lab
Bài lab này giúp làm quen với các thao tác xử lý ảnh cơ bản trong Python như:
- đọc ảnh từ file
- chuyển đổi không gian màu
- lật ảnh theo chiều dọc và chiều ngang
- hiển thị ảnh kết quả

Các thao tác được thực hiện bằng hai thư viện phổ biến là PIL và OpenCV.

---

## 2. Công nghệ sử dụng
- Python 3  
- PIL (Pillow) – đọc và xử lý ảnh cơ bản  
- OpenCV (cv2) – thư viện xử lý ảnh và thị giác máy tính  
- NumPy – hỗ trợ xử lý dữ liệu ảnh dạng mảng  
- Matplotlib – hiển thị ảnh ra màn hình  

---

## 3. Cách hoạt động của chương trình

### 3.1. Xử lý ảnh bằng PIL (`2.2.1_basic_image_manipulation_PIL.ipynb`)
Chương trình thực hiện các bước:
1. đọc ảnh từ file bằng PIL  
2. chuyển ảnh sang không gian màu RGB  
3. lật ảnh theo trục x (flip vertical)  
4. lật ảnh theo trục y (mirror / flip horizontal)  
5. hiển thị ảnh gốc và ảnh sau khi xử lý  

PIL có cú pháp đơn giản, dễ sử dụng cho các thao tác xử lý ảnh cơ bản.

---

### 3.2. Xử lý ảnh bằng OpenCV (`2.2.2_basic_image_manipulation_open_CV.ipynb`)
Các bước chính:
1. đọc ảnh bằng OpenCV (ảnh ở dạng BGR)  
2. chuyển ảnh từ BGR sang RGB  
3. lật ảnh theo chiều dọc bằng `cv2.flip(image, 0)`  
4. lật ảnh theo chiều ngang bằng `cv2.flip(image, 1)`  
5. hiển thị ảnh bằng matplotlib  

OpenCV mạnh hơn và thường được dùng trong các bài toán xử lý ảnh nâng cao.

---

## 4. Kết quả đạt được
- ảnh được đọc và hiển thị đúng  
- ảnh sau khi lật dọc và lật ngang cho kết quả chính xác  
- hiểu được sự khác nhau giữa BGR (OpenCV) và RGB (PIL, Matplotlib)  
- làm quen với hai thư viện xử lý ảnh phổ biến trong Python  

---

## 5. Giao diện hiển thị kết quả
- kết quả được hiển thị trực tiếp trên Jupyter Notebook (`.ipynb`)  
- sử dụng matplotlib để hiển thị ảnh  

---

## 6. Kết luận
Bài lab giúp sinh viên nắm được các thao tác xử lý ảnh cơ bản và tạo nền tảng cho các bài học tiếp theo về xử lý ảnh và thị giác máy tính.
