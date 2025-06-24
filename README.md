# Bài tập xử lý ảnh với Python

Dự án này là một bộ bài tập thực hành xử lý ảnh sử dụng Python với các thư viện OpenCV, NumPy, SciPy và Matplotlib. Chương trình cung cấp các chức năng biến đổi ảnh từ cơ bản đến nâng cao và menu tương tác cho người dùng.

## 📋 Mục lục

- [Tính năng chính](#-tính-năng-chính)
- [Yêu cầu hệ thống](#-yêu-cầu-hệ-thống)
- [Cài đặt](#-cài-đặt)
- [Cấu trúc dự án](#-cấu-trúc-dự-án)
- [Hướng dẫn sử dụng](#-hướng-dẫn-sử-dụng)
- [Chi tiết các bài tập](#-chi-tiết-các-bài-tập)
- [Ví dụ kết quả](#-ví-dụ-kết-quả)
- [Tính năng nâng cao](#-tính-năng-nâng-cao)

## 🚀 Tính năng chính

### Biến đổi hình học
- **Tịnh tiến (Translation)**: Di chuyển ảnh theo vector (dx, dy)
- **Xoay (Rotation)**: Xoay ảnh với góc tùy chỉnh
- **Phóng to/thu nhỏ (Zoom)**: Thay đổi kích thước với hệ số zoom
- **Uốn cong (Warping)**: Tạo hiệu ứng barrel distortion

### Hiệu ứng đặc biệt
- **Hiệu ứng sóng**: Tạo gợn sóng theo chiều ngang hoặc dọc
- **Gradient màu**: Áp dụng chuyển màu gradient lên đối tượng
- **Phản chiếu dọc**: Tạo hiệu ứng mirror với độ mờ dần
- **Gaussian Blur**: Làm mờ ảnh với sigma tùy chỉnh

### Xử lý ảnh nâng cao
- **Ghép ảnh PNG**: Tạo file PNG với alpha channel trong suốt
- **Canvas trắng**: Ghép nhiều ảnh lên nền trắng
- **Map coordinates**: Sử dụng SciPy để biến đổi tọa độ chính xác

## 🔧 Yêu cầu hệ thống

### Python version
- Python 3.7 trở lên

### Thư viện cần thiết
```
opencv-python>=4.5.0
numpy>=1.19.0
matplotlib>=3.3.0
scipy>=1.6.0
Pillow>=8.0.0
```

## 📦 Cài đặt

1. **Clone hoặc tải xuống dự án:**
```bash
git clone <repository-url>
cd image-processing-exercises
```

2. **Tạo môi trường ảo (khuyến nghị):**
```bash
python -m venv venv
source venv/bin/activate  # Linux/Mac
# hoặc
venv\Scripts\activate     # Windows
```

3. **Cài đặt dependencies:**
```bash
pip install opencv-python numpy matplotlib scipy Pillow
```

4. **Tạo thư mục cần thiết:**
```bash
mkdir output
```

## 📁 Cấu trúc dự án

```
image-processing-exercises/
├── paste.txt                 # File code chính (Jupyter Notebook format)
├── output/                   # Thư mục lưu kết quả
│   ├── kiwi_wave.jpg
│   ├── fruits_gradient.png
│   ├── mountain_boat_mirror.jpg
│   └── pagoda_warped.jpg
├── boat.jpg                  # Ảnh đầu vào (tùy chọn)
├── kiwi.jpg
├── mountain.jpg
├── pagoda.jpg
├── dudu.jpg
├── duahau.jpg
└── README.md
```

## 🎯 Hướng dẫn sử dụng

### Chạy từng bài tập riêng lẻ

1. **Mở file paste.txt trong Jupyter Notebook hoặc IDE Python**
2. **Chạy từng cell theo thứ tự:**
   - Import thư viện
   - Load ảnh
   - Chạy từng bài tập (Bài 1-5)

### Chạy menu tương tác (Bài 5)

```python
processor = ImageProcessor()
processor.select_image()
processor.interactive_menu()
```

### Sử dụng ảnh tùy chỉnh

Đặt các file ảnh vào thư mục gốc với tên:
- `boat.jpg` - Ảnh thuyền
- `kiwi.jpg` - Ảnh kiwi  
- `mountain.jpg` - Ảnh núi
- `pagoda.jpg` - Ảnh chùa
- `dudu.jpg` - Ảnh đu đủ
- `duahau.jpg` - Ảnh dưa hấu

*Lưu ý: Nếu không có ảnh, chương trình sẽ tự động tạo ảnh mẫu.*

## 📚 Chi tiết các bài tập

### Bài 1: Tịnh tiến và hiệu ứng sóng
- **Input**: Ảnh kiwi
- **Xử lý**: 
  1. Tịnh tiến 50px sang phải, 30px xuống
  2. Áp dụng hiệu ứng sóng (amplitude=30, frequency=0.05)
- **Output**: `output/kiwi_wave.jpg`

### Bài 2: Gradient màu và ghép ảnh
- **Input**: Ảnh đu đủ và dưa hấu
- **Xử lý**:
  1. Áp dụng gradient màu (Đỏ→Xanh lá cho đu đủ, Vàng→Tím cho dưa hấu)
  2. Ghép thành file PNG với alpha channel
- **Output**: `output/fruits_gradient.png`

### Bài 3: Xoay và phản chiếu
- **Input**: Ảnh núi và thuyền
- **Xử lý**:
  1. Xoay 45° (giữ kích thước ban đầu)
  2. Tạo hiệu ứng phản chiếu dọc với gradient mờ dần
  3. Ghép lên canvas trắng
- **Output**: `output/mountain_boat_mirror.jpg`

### Bài 4: Phóng to và uốn cong
- **Input**: Ảnh chùa
- **Xử lý**:
  1. Phóng to 2 lần
  2. Áp dụng biến đổi uốn cong (barrel distortion)
- **Output**: `output/pagoda_warped.jpg`

### Bài 5: Menu tương tác
- **Tính năng**: Menu console cho phép người dùng:
  - Chọn ảnh từ thư viện
  - Áp dụng các biến đổi real-time
  - Xem kết quả ngay lập tức
  - Reset về ảnh gốc

## 🖼️ Ví dụ kết quả

### Hiệu ứng sóng
```python
# Tạo sóng ngang
wave_horizontal = wave_effect(image, amplitude=20, frequency=0.1, direction='horizontal')

# Tạo sóng dọc  
wave_vertical = wave_effect(image, amplitude=15, frequency=0.08, direction='vertical')
```

### Gradient màu
```python
# Gradient ngang từ đỏ sang xanh lá
gradient_img = apply_gradient(image, (0, 0, 255), (0, 255, 0), 'horizontal')

# Gradient dọc từ vàng sang tím
gradient_img = apply_gradient(image, (0, 255, 255), (255, 0, 255), 'vertical')
```

### Phản chiếu dọc
```python
# Tạo hiệu ứng phản chiếu với gradient mờ dần
mirrored = vertical_mirror(image)
```

## ⚡ Tính năng nâng cao

### Map Coordinates với SciPy
- Sử dụng `scipy.ndimage.map_coordinates` để biến đổi tọa độ chính xác
- Hỗ trợ interpolation order=1 cho chất lượng tốt
- Xử lý boundary với mode='constant'

### Alpha Channel Processing
- Tạo file PNG với kênh trong suốt
- Tự động phát hiện vùng nền trắng để loại bỏ
- Ghép ảnh với độ trong suốt tự nhiên

### Error Handling
- Tự động tạo ảnh mẫu khi không tìm thấy file
- Kiểm tra kích thước và định dạng ảnh
- Xử lý lỗi I/O và memory

### Performance Optimization
- Clip tọa độ để tránh out-of-bounds
- Sử dụng numpy vectorization
- Tối ưu memory với dtype uint8

## 🛠️ Customization

### Thêm hiệu ứng mới
```python
def custom_effect(img, param1, param2):
    """Template cho hiệu ứng tùy chỉnh"""
    # Xử lý ảnh
    result = your_processing_logic(img, param1, param2)
    return result.astype(np.uint8)
```

### Mở rộng menu
```python
def apply_custom_effect(self):
    param1 = float(input("Nhập tham số 1: "))
    param2 = float(input("Nhập tham số 2: "))
    self.current_image = custom_effect(self.current_image, param1, param2)
    print("✅ Đã áp dụng hiệu ứng tùy chỉnh.")
```

## 🐛 Troubleshooting

### Lỗi thường gặp

1. **ModuleNotFoundError**: Cài đặt thiếu thư viện
```bash
pip install opencv-python numpy matplotlib scipy Pillow
```

2. **File not found**: Đặt đúng tên file ảnh hoặc để chương trình tạo ảnh mẫu

3. **Memory error**: Giảm kích thước ảnh hoặc hệ số zoom

4. **Display issues**: Đảm bảo có GUI backend cho matplotlib
```bash
pip install PyQt5  # hoặc tkinter
```

## 📝 License

Dự án này được phát hành dưới MIT License. Xem file LICENSE để biết thêm chi tiết.

## 👥 Contributing

Mọi đóng góp đều được hoan nghênh! Vui lòng:
1. Fork repository
2. Tạo feature branch
3. Commit changes
4. Push và tạo Pull Request

## 📞 Liên hệ

Nếu có thắc mắc hoặc góp ý, vui lòng tạo Issue trên GitHub repository.

---

*Dự án được phát triển cho mục đích giáo dục và thực hành xử lý ảnh với Python.*
