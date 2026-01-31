# 🏠 Vietnam House Price Prediction

Dự án **dự đoán giá nhà (triệu đồng/m²) tại Việt Nam** sử dụng **Machine Learning (XGBoost)**.  
Hệ thống được thiết kế với **2 pipeline huấn luyện riêng biệt** cho **Hà Nội** và **các tỉnh/thành khác** nhằm giảm bias dữ liệu và tăng độ chính xác mô hình.

---

## 📌 Mục tiêu

- Dự đoán giá nhà theo **triệu đồng/m²**
- Xử lý dữ liệu bất động sản **không đồng nhất, nhiều nhiễu**
- Xây dựng pipeline **ổn định, dễ mở rộng và triển khai thực tế**

---

## 📊 Dữ liệu

- Dữ liệu được **tổng hợp từ nhiều nguồn khác nhau**
- Số bản ghi: **93,049**
- Số thuộc tính: **10**

### Phân bố dữ liệu
- **Hà Nội** chiếm khoảng **82%** tổng dữ liệu
- Các tỉnh/thành khác **phân tán, số mẫu ít và không đồng đều**

👉 Vì sự chênh lệch lớn này, dự án sử dụng **2 mô hình riêng biệt**.

---

## 🧠 Mô hình

### 1️⃣ Hà Nội
- Huấn luyện **riêng dữ liệu Hà Nội**
- Sử dụng **Pipeline + Target Encoding**
- Encoding nằm trong pipeline → **không cần lưu mapping khi deploy**
- Phù hợp cho hệ thống dự đoán realtime

---

### 2️⃣ Các tỉnh/thành khác
- Huấn luyện trên dữ liệu **ngoài Hà Nội**
- Target Encoding **thủ công**
- Lưu mapping để xử lý dữ liệu mới khi dự đoán


---

## ⚙️ Tiền xử lý chính

- Chuẩn hóa tên **Tỉnh/Thành phố**
- Trích xuất **Quận / Huyện từ Địa chỉ** nếu bị thiếu
- Xử lý giá trị thiếu:
  - Số tầng, số phòng ngủ → median
  - Biến phân loại → giá trị mặc định
- Loại bỏ tỉnh/thành có **< 300 bản ghi**
- Lọc **outliers**:
  - Giá
  - Diện tích
  - Số tầng

---

## 📈 Đánh giá mô hình

- **R² Score** – đánh giá mức độ phù hợp của mô hình
- **MAE (Mean Absolute Error)** – sai số tuyệt đối trung bình (triệu đồng/m²)

---

## 👤 Tác giả

**Nhóm 20**  
Machine Learning & AI (Student)
