# Images with Python Library – PIL & OpenCV

## 1. Mục tiêu bài lab
Bài lab này nhằm giới thiệu cách làm việc với ảnh trong Python thông qua hai thư viện phổ biến là PIL và OpenCV. Nội dung tập trung vào:
- đọc ảnh từ file
- kiểm tra thông tin cơ bản của ảnh
- hiển thị ảnh lên màn hình
- làm quen với cách ảnh được biểu diễn trong Python

---

## 2. Công nghệ sử dụng
- Python 3  
- PIL (Pillow) – thư viện xử lý ảnh cơ bản, cú pháp đơn giản  
- OpenCV (cv2) – thư viện mạnh trong xử lý ảnh và thị giác máy tính  
- NumPy – biểu diễn ảnh dưới dạng mảng  
- Matplotlib – hiển thị ảnh  

---

## 3. Cách hoạt động của chương trình

### 3.1. Làm việc với ảnh bằng PIL (`2.1.1_Images_with_python_library_PIL.ipynb`)
Chương trình thực hiện các bước chính:
1. đọc ảnh từ file bằng PIL  
2. hiển thị ảnh lên màn hình  
3. kiểm tra kích thước ảnh (width, height)  
4. kiểm tra chế độ màu của ảnh (RGB, grayscale, …)  

Qua đó giúp hiểu ảnh trong PIL được quản lý như một đối tượng image.

---

### 3.2. Làm việc với ảnh bằng OpenCV (`2.1.2_Images_with_python_library_CV.ipynb`)
Các bước thực hiện:
1. đọc ảnh bằng OpenCV  
2. quan sát ảnh dưới dạng mảng NumPy  
3. kiểm tra kích thước ảnh và số kênh màu  
4. chuyển ảnh từ BGR sang RGB để hiển thị đúng màu  
5. hiển thị ảnh bằng matplotlib  

Phần này giúp hiểu cách OpenCV lưu trữ ảnh và sự khác biệt về không gian màu.

---

## 4. Kết quả đạt được
- đọc và hiển thị ảnh thành công bằng cả PIL và OpenCV  
- hiểu ảnh thực chất là một mảng số (NumPy array)  
- phân biệt được:
  - RGB (PIL, Matplotlib)  
  - BGR (OpenCV)  
- nắm được thông tin cơ bản của ảnh như kích thước và số kênh màu  

---

## 5. Giao diện hiển thị kết quả
- kết quả hiển thị trực tiếp trên Jupyter Notebook (`.ipynb`)  
- sử dụng matplotlib để hiển thị ảnh  

---

## 6. Kết luận
Bài lab giúp sinh viên làm quen với cách đọc và hiển thị ảnh trong Python, đồng thời hiểu được sự khác nhau giữa PIL và OpenCV. Đây là nền tảng quan trọng cho các bài lab xử lý ảnh ở các phần sau.
