# 🦋 Phân Tích Nguy Cơ Ung Thư Tuyến Giáp (Thyroid Cancer Risk Intelligence)

[![Python](https://img.shields.io/badge/Python-3.9+-blue.svg)](https://www.python.org/)
[![Scikit-Learn](https://img.shields.io/badge/scikit--learn-0.24+-orange.svg)](https://scikit-learn.org/)
[![Course](https://img.shields.io/badge/Course-INT3425_Data_Science-green.svg)]()

Dự án cuối kỳ môn **Khoa học Dữ liệu (INT3425)**. Áp dụng các phương pháp thống kê suy luận (Inferential Statistics) và Học máy (Machine Learning) để phân tích các chỉ số sinh hóa và dự đoán nguy cơ mắc ung thư tuyến giáp.

Mức độ đóng góp: Bùi Đình Cảnh - 60%
Trần Đức Anh: 40%

## 📖 Bối cảnh dự án
Tuyến giáp đóng vai trò quan trọng trong việc điều hòa trao đổi chất thông qua các hormone (TSH, T3, T4). Dự án này hướng tới việc khai phá mối tương quan giữa các chỉ số này với nguy cơ ung thư tuyến giáp. 

Khác với các phương pháp Black-box Machine Learning truyền thống, dự án sử dụng sức mạnh tính toán (Computational Thinking) thông qua các kỹ thuật mô phỏng như **Permutation Test** và **Bootstrapping** để chứng minh sự khác biệt sinh học, đảm bảo tính diễn giải cao cho y tế.

## 📊 Bộ dữ liệu (Dataset)
- **Nguồn:** Thyroid Cancer Risk Dataset (đã qua xử lý chuẩn hóa).
- **Quy mô:** 150,500 quan sát y tế.
- **Đặc trưng:**
  - 6 biến số thực: `Age`, `TSH_Level`, `T3_Level`, `T4_Level`, `Nodule_Size`.
  - 10 biến phân loại: `Gender`, `Country`, `Family_History`, v.v.
- **Phân phối nhãn (Class Imbalance):** `Benign` (Lành tính) chiếm 75%, `Malignant` (Ác tính) chiếm 25%.

## 🔬 Khám phá chính (Key Findings)
1. **Tín hiệu chẩn đoán:** `TSH_Level` có tương quan tuyến tính mạnh nhất với nhãn chẩn đoán ($r = 0.52$), trong khi Tuổi tác (`Age`) gần như không có tác động ($r = -0.05$).
2. **Kiểm định giả thuyết (A/B Testing):** Sử dụng Permutation Test (1,000 vòng lặp) cho TSH, kết quả $p-value = 0.0000 \rightarrow$ Sự khác biệt về nồng độ hormone giữa nhóm bệnh và khỏe mạnh là thực tế sinh học, không do ngẫu nhiên.
3. **Ước lượng khoảng (Bootstrapping):** Khoảng tin cậy 95% của nồng độ TSH giữa 2 nhóm không hề có điểm giao cắt, được hỗ trợ bởi Định lý Giới hạn Trung tâm (CLT) nhờ quy mô $n > 150,000$.

## 🤖 Kiến trúc Mô hình
- **Baseline Model:** Hồi quy tuyến tính (Linear Regression) đơn biến đạt $R^2 = 0.27$, biểu đồ phần dư (Residuals) phân tán ngẫu nhiên hợp lý.
- **Classification Model:** K-Nearest Neighbors (k-NN).
  - Tối ưu siêu tham số: $k = 7$
  - Accuracy: **82%**
  - Recall (Malignant): **68%**

## 💻 Tech Stack & Công cụ sử dụng
- **Ngôn ngữ:** Python
- **Thư viện chính:** `pandas`, `numpy`, `matplotlib`, `seaborn`, `scikit-learn`
- **Môi trường phát triển:** Chạy mượt mà trên môi trường **Jupyter Notebook** tích hợp sẵn trong **VSCode**, hoặc thông qua container **Docker** / máy ảo **Ubuntu**. CSDL (nếu cần truy xuất) có thể quản lý qua **MySQL Workbench**.

Link báo cáo dự án: https://www.canva.com/design/DAHJmyS-JW0/n42GMWVC4mTmzqA73sdJMg/edit
