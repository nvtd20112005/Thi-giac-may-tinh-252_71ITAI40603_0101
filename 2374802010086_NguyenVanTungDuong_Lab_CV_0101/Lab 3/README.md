# Computer Vision & Data Analysis Labs

## 1. Mục tiêu bài lab

Bộ bài lab này bao gồm 3 phần chính nhằm giới thiệu các kỹ thuật xử lý ảnh và phân tích dữ liệu trong Python:

**Lab 1: Làm quen với OpenCV**
- Làm quen với thư viện OpenCV để xử lý ảnh
- Thực hiện các thao tác cơ bản: đọc, hiển thị, chuyển đổi không gian màu
- Thực hiện các phép biến đổi hình học: phóng to, crop, ghép ảnh

**Lab 2: Phân tích dữ liệu Uber**
- Phân tích dữ liệu chuyến đi Uber tháng 7/2014
- Xử lý và trực quan hóa dữ liệu thời gian
- Tìm ra các xu hướng theo giờ và ngày trong tuần
- Làm việc với dữ liệu địa lý (latitude, longitude)

**Lab 3: Histogram và Biến đổi cường độ**
- Tạo và phân tích histogram của ảnh
- Áp dụng các phép biến đổi cường độ để cải thiện độ tương phản và độ sáng
- Sử dụng ngưỡng (thresholding) để phân đoạn đối tượng trong ảnh

---

## 2. Công nghệ sử dụng

### Xử lý ảnh
- **Python 3** – ngôn ngữ lập trình chính
- **OpenCV (cv2)** – thư viện mạnh mẽ cho xử lý ảnh và thị giác máy tính
- **NumPy** – biểu diễn và xử lý ảnh dưới dạng mảng
- **Matplotlib** – hiển thị ảnh và biểu đồ

### Phân tích dữ liệu
- **Pandas** – thư viện xử lý và phân tích dữ liệu
- **Seaborn** – thư viện trực quan hóa dữ liệu nâng cao
- **Geopy** – tính toán khoảng cách địa lý

---

## 3. Cách hoạt động của chương trình

### 3.1. Lab01b - Làm quen với OpenCV

Chương trình thực hiện các bước chính:

1. **Đọc ảnh từ file**
   - Sử dụng `cv.imread()` để đọc 2 file ảnh (hinh1.jpg, hinh2.jpg)
   - Kiểm tra xem ảnh có đọc thành công không

2. **Kiểm tra thông tin ảnh**
   - In ra shape của ảnh (height, width, channels)
   - Hiểu được cấu trúc ảnh: ảnh là mảng 3 chiều

3. **Hiển thị ảnh với matplotlib**
   - Hiển thị ảnh gốc (lưu ý: màu sẽ sai do OpenCV dùng BGR)
   - Chuyển đổi từ BGR sang RGB bằng `cv.cvtColor()`
   - Hiển thị ảnh với màu đúng

4. **Biến đổi hình học**
   - **Phóng to ảnh**: Sử dụng `cv.resize()` với hệ số fx=1.5, fy=1.5
   - **Crop ảnh**: Cắt vùng ảnh bằng slicing mảng `[50:200, 100:300]`

5. **Ghép ảnh**
   - Resize ảnh 2 cho cùng kích thước với ảnh 1
   - Ghép ngang: sử dụng `np.hstack()`
   - Ghép dọc: sử dụng `np.vstack()`

**Lưu ý đặc biệt**: Chương trình sử dụng tên biến `TenHoSV` thay vì `plt` cho matplotlib theo yêu cầu bài tập.

---

### 3.2. Consumption - Phân tích dữ liệu Uber

Chương trình thực hiện phân tích dữ liệu theo các bước:

1. **Đọc và khám phá dữ liệu**
   - Đọc file CSV chứa dữ liệu chuyến đi Uber tháng 7/2014
   - Kiểm tra thông tin cơ bản: số dòng, kiểu dữ liệu, giá trị null

2. **Xử lý dữ liệu thời gian**
   - Chuyển đổi cột Date/Time sang kiểu datetime
   - Làm tròn thời gian về giờ gần nhất bằng `dt.floor('1h')`
   - Tách thành các thành phần: giờ, ngày trong tuần, ngày

3. **Phân tích xu hướng theo thời gian**
   - Đếm số chuyến đi theo từng giờ
   - Sắp xếp dữ liệu theo thứ tự thời gian
   - Vẽ biểu đồ đường để quan sát xu hướng

4. **Phân tích theo giờ và ngày trong tuần**
   - Tính trung bình số chuyến đi cho mỗi tổ hợp giờ/ngày trong tuần
   - Chuyển đổi số ngày (0-6) thành tên ngày (Monday-Sunday) bằng thư viện calendar
   - Nhóm dữ liệu và tính trung bình
   - Sử dụng `unstack()` để chuyển đổi dữ liệu thành dạng pivot table

5. **Trực quan hóa bằng Heatmap**
   - Vẽ heatmap bằng Seaborn
   - Hiển thị mối quan hệ giữa giờ trong ngày và ngày trong tuần
   - Dễ dàng nhận ra các khung giờ cao điểm

6. **Phân tích địa lý**
   - Cài đặt và sử dụng thư viện geopy
   - Tính khoảng cách giữa các vị trí (latitude, longitude)

---

### 3.3. Histograms and Intensity Transformations

Chương trình tập trung vào xử lý ảnh ở mức pixel:

1. **Tạo và phân tích Histogram**
   - Hiểu histogram: đếm số lần xuất hiện của các giá trị cường độ pixel
   - Sử dụng `cv2.calcHist()` để tạo histogram
   - Tham số: `[image]`, kênh `[0]`, mask `None`, số bins `[256]`, phạm vi `[0,256]`

2. **Ví dụ đơn giản (Toy Example)**
   - Tạo mảng 3x3 với giá trị từ 0-2
   - Tạo histogram với 3 bins
   - Hiểu cách histogram đếm số lượng mỗi giá trị

3. **Hàm hỗ trợ (Helper Functions)**
   - `plot_image()`: Vẽ 2 ảnh cạnh nhau để so sánh
   - `plot_hist()`: Vẽ 2 histogram cạnh nhau để so sánh
   - Giúp quan sát kết quả trước và sau khi xử lý

4. **Biến đổi cường độ (Intensity Transformations)**
   - Cải thiện độ tương phản và độ sáng của ảnh
   - Làm cho các đối tượng dễ nhìn hơn
   - Áp dụng các phép toán trên từng pixel

5. **Ngưỡng và phân đoạn (Thresholding and Segmentation)**
   - Sử dụng ngưỡng để tách đối tượng khỏi nền
   - Chuyển ảnh xám thành ảnh nhị phân
   - Ứng dụng trong nhận dạng và phân tích đối tượng

6. **Thực hành với ảnh thực tế**
   - Download các ảnh mẫu: lenna.png, baboon.png, goldhill.bmp, cameraman.jpeg, zelda.png, mammogram.png
   - Áp dụng các kỹ thuật đã học lên ảnh thực tế

---

## 4. Kết quả đạt được

### Lab 1: OpenCV
- ✅ Đọc và hiển thị ảnh thành công bằng OpenCV
- ✅ Hiểu được cấu trúc ảnh: mảng NumPy 3 chiều (H×W×C)
- ✅ Phân biệt được không gian màu BGR (OpenCV) và RGB (Matplotlib)
- ✅ Thực hiện các phép biến đổi: resize, crop, ghép ảnh
- ✅ Nắm vững cách sử dụng matplotlib để hiển thị kết quả

### Lab 2: Phân tích dữ liệu
- ✅ Xử lý thành công dữ liệu thời gian phức tạp
- ✅ Tạo được các biểu đồ trực quan: line plot, heatmap
- ✅ Phát hiện được các xu hướng:
  - Giờ cao điểm trong ngày
  - Ngày cao điểm trong tuần
  - Mối quan hệ giữa giờ và ngày
- ✅ Nắm được kỹ thuật pivot table và groupby trong Pandas
- ✅ Biết cách làm việc với dữ liệu địa lý

### Lab 3: Histogram
- ✅ Hiểu được ý nghĩa của histogram trong xử lý ảnh
- ✅ Tạo và phân tích histogram thành công
- ✅ Áp dụng các phép biến đổi cường độ để cải thiện chất lượng ảnh
- ✅ Sử dụng thresholding để phân đoạn ảnh
- ✅ So sánh được ảnh trước và sau khi xử lý
- ✅ Nền tảng cho các kỹ thuật nâng cao: histogram equalization, adaptive thresholding

---

## 5. Giao diện hiển thị kết quả

### Lab 1 & 3: Jupyter Notebook
- Kết quả hiển thị trực tiếp trên Jupyter Notebook (.ipynb)
- Sử dụng matplotlib để hiển thị ảnh
- Các ảnh được sắp xếp rõ ràng với tiêu đề mô tả
- Có thể tắt trục tọa độ bằng `axis('off')` cho giao diện đẹp hơn

### Lab 2: Biểu đồ và Heatmap
- **Line plot**: Hiển thị xu hướng số chuyến đi theo thời gian
- **Heatmap**: Ma trận màu thể hiện mức độ hoạt động theo giờ và ngày
  - Màu đậm: số chuyến đi nhiều
  - Màu nhạt: số chuyến đi ít
  - Dễ dàng nhận diện pattern một cách trực quan

### Đặc điểm chung
- Giao diện thân thiện, dễ đọc
- Có thể chạy từng cell một để quan sát từng bước
- Kết hợp code và giải thích văn bản
- Phù hợp cho mục đích học tập và thử nghiệm

---

## 6. Cấu trúc file

```
├── Lab01b_Làm quen CV.ipynb
│   └── 1 code cell: Thao tác cơ bản với OpenCV
│
├── Consumption.ipynb
│   ├── 4 markdown cells: Giải thích và hướng dẫn
│   └── 47 code cells: Phân tích dữ liệu từng bước
│
└── 2.3.2_ Histograms and Intensity Transformations.ipynb
    ├── 67 markdown cells: Lý thuyết chi tiết
    └── 45 code cells: Thực hành với ví dụ cụ thể
```

---

## 7. Hướng dẫn sử dụng

### Yêu cầu cài đặt

```bash
pip install opencv-python
pip install matplotlib
pip install numpy
pip install pandas
pip install seaborn
pip install geopy
```

### Chạy Lab 1 (OpenCV)

1. Chuẩn bị 2 file ảnh: `hinh1.jpg` và `hinh2.jpg`
2. Đặt file ảnh cùng thư mục với notebook
3. Mở `Lab01b_Làm quen CV.ipynb` bằng Jupyter
4. Chạy cell code và quan sát kết quả

### Chạy Lab 2 (Uber Data)

1. Cần file dữ liệu: `uber-raw-data-jul14.csv`
2. Mở `Consumption.ipynb`
3. Chạy từng cell theo thứ tự
4. Quan sát các biểu đồ và phân tích

### Chạy Lab 3 (Histogram)

1. Notebook sẽ tự động download ảnh mẫu
2. Mở `2.3.2_ Histograms and Intensity Transformations.ipynb`
3. Chạy từng cell và đọc giải thích
4. Thử nghiệm với ảnh của riêng bạn

---

## 8. Kiến thức trọng tâm

### Xử lý ảnh
- Ảnh là mảng NumPy 3 chiều: `(height, width, channels)`
- OpenCV sử dụng BGR, Matplotlib sử dụng RGB → cần chuyển đổi
- Các phép toán trên ảnh thực chất là phép toán trên mảng
- Histogram giúp hiểu phân bố cường độ sáng của ảnh

### Phân tích dữ liệu
- Xử lý datetime là kỹ năng quan trọng trong data science
- Groupby và pivot table là công cụ mạnh mẽ để tổng hợp dữ liệu
- Heatmap giúp trực quan hóa dữ liệu 2 chiều hiệu quả
- Luôn explore dữ liệu trước khi phân tích

### Lập trình
- Viết hàm helper để tái sử dụng code
- Kiểm tra điều kiện trước khi xử lý (ví dụ: kiểm tra ảnh có đọc được không)
- Đặt tên biến có ý nghĩa để code dễ đọc
- Comment code bằng tiếng Việt giúp dễ hiểu hơn

---

## 9. Kết luận

Bộ 3 bài lab này cung cấp nền tảng vững chắc cho:

**Xử lý ảnh**:
- Làm quen với OpenCV và các thao tác cơ bản
- Hiểu bản chất của ảnh số và histogram
- Nắm được các kỹ thuật cải thiện chất lượng ảnh

**Phân tích dữ liệu**:
- Xử lý và trực quan hóa dữ liệu thời gian
- Tìm kiếm xu hướng và pattern trong dữ liệu
- Sử dụng thành thạo Pandas, Matplotlib, Seaborn

**Kỹ năng lập trình**:
- Làm việc với Jupyter Notebook
- Viết code rõ ràng, có cấu trúc
- Debug và xử lý lỗi

Đây là kiến thức nền tảng quan trọng cho các bài lab nâng cao về Computer Vision, Machine Learning và Data Science trong các phần tiếp theo.

---

## 10. Tài liệu tham khảo

- [OpenCV Documentation](https://docs.opencv.org/)
- [Matplotlib Documentation](https://matplotlib.org/stable/contents.html)
- [Pandas Documentation](https://pandas.pydata.org/docs/)
- [Seaborn Documentation](https://seaborn.pydata.org/)
- [NumPy Documentation](https://numpy.org/doc/)

---

**Người thực hiện**: Sinh viên môn Xử lý ảnh và Phân tích dữ liệu  
**Thời gian**: 2026  
**Công cụ**: Python 3, Jupyter Notebook
