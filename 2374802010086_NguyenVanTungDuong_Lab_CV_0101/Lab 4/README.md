# Lab 04 – Geometric Transformations (PIL & OpenCV)

## 1. Nội dung bài lab
Lab 04 tập trung vào việc thực hiện các **phép biến đổi hình học (Geometric Transformations)** trên ảnh.  
Các phép biến đổi được triển khai và so sánh thông qua hai thư viện xử lý ảnh là **PIL** và **OpenCV**, đồng thời tổng hợp kết quả trong notebook bài lab.

---

## 2. Công nghệ sử dụng
- Python  
- PIL (Pillow)  
- OpenCV (cv2)  
- NumPy  
- Matplotlib  

---

## 3. Mô tả chi tiết các notebook

### 3.1. Geometric Transformations với PIL  
**(2.4.1_Gemetric_trasfroms_PIL.ipynb)**

Notebook này thực hiện các phép biến đổi hình học cơ bản trên ảnh bằng thư viện PIL:

- đọc ảnh từ file  
- thay đổi kích thước ảnh (resize)  
- xoay ảnh với các góc khác nhau (rotate)  
- cắt ảnh theo vùng quan tâm (crop)  
- hiển thị ảnh trước và sau biến đổi  

Các thao tác giúp quan sát trực tiếp sự thay đổi của ảnh khi áp dụng các phép biến đổi hình học.

---

### 3.2. Geometric Transformations với OpenCV  
**(2.4.2_Gemetric_trasfroms_OpenCV.ipynb)**

Notebook này thực hiện các phép biến đổi hình học tương tự nhưng sử dụng OpenCV:

- đọc ảnh bằng `cv.imread()`  
- thay đổi kích thước ảnh bằng `cv.resize()`  
- tịnh tiến ảnh (translation)  
- xoay ảnh bằng ma trận biến đổi affine  
- áp dụng nội suy khi biến đổi ảnh  
- hiển thị kết quả bằng matplotlib  

Notebook cho thấy cách OpenCV thao tác trực tiếp trên ảnh dưới dạng mảng NumPy.

---

### 3.3. Lab 04 – Bài thực hành tổng hợp  
**(2374802010086_NguyenVanTungDuong_Lab_CV_0101_Lab02.ipynb)**

Notebook này tổng hợp lại toàn bộ nội dung của Lab 04:

- đọc và hiển thị ảnh  
- kiểm tra kích thước ảnh  
- áp dụng các phép biến đổi hình học đã học  
- so sánh ảnh trước và sau khi biến đổi  
- trình bày kết quả trực tiếp trên Jupyter Notebook  

Notebook đóng vai trò là bài thực hành hoàn chỉnh cho Lab 04.

---

## 4. Kết quả đạt được
Sau khi hoàn thành Lab 04, có thể:

- đọc và hiển thị ảnh bằng PIL và OpenCV  
- thực hiện các phép biến đổi hình học cơ bản trên ảnh  
- quan sát và so sánh kết quả biến đổi ảnh  
- hiểu sự khác nhau trong cách xử lý ảnh của PIL và OpenCV  
