# HCMUS - 23TNT1
# Lab 1: Dự đoán Giá Xe - Phương pháp Toán cho Trí tuệ Nhân tạo

## Giới thiệu

Đây là project thực hiện Lab 1 môn "Phương pháp Toán cho Trí tuệ Nhân tạo" tại Trường Đại học Khoa học Tự nhiên - ĐHQG HCM[cite: 1, 3]. Mục tiêu là xây dựng và đánh giá các mô hình Hồi quy Tuyến tính (Linear Regression) để dự đoán giá xe ô tô cũ dựa trên tập dữ liệu `train.csv`

## Quy trình thực hiện

1.  **Đánh giá và Tiền xử lý Dữ liệu:**
    * Phân tích tổng quan dữ liệu, xác định và xử lý giá trị thiếu (missing values) bằng cách điền dựa trên nhóm (Make, Model) và giá trị trung vị/mode
    * Trích xuất giá trị số từ các cột dạng văn bản (Engine, Max Power, Max Torque)
    * Kỹ thuật đặc trưng (Feature Engineering): Tạo các đặc trưng mới như Tuổi xe (Car Age), Log Kilometer, Tương tác Tuổi-KM, Thể tích xe, các tỉ lệ công suất/dung tích/mô-men xoắn, đánh dấu xe cao cấp, xếp hạng hệ truyền động
    * Xử lý ngoại lệ (Outlier Handling) bằng phương pháp IQR
    * Mã hóa One-Hot cho các biến phân loại
    * Chuẩn hóa dữ liệu số (Standardization)
    * Tính toán Hệ số lạm phát phương sai (VIF) để đánh giá đa cộng tuyến
    * Lựa chọn đặc trưng (Feature Selection) dựa trên tương quan với biến mục tiêu và VIF, loại bỏ các đặc trưng gây đa cộng tuyến cao

2.  **Xây dựng Mô hình Hồi quy:**
    * Xây dựng lớp `LinearRegression` tùy chỉnh, hỗ trợ L2 Regularization và các hàm biến đổi đặc trưng
    * Triển khai và so sánh 4 loại mô hình hồi quy
        * Hồi quy Tuyến tính Chuẩn (có L2)
        * Hồi quy với Đặc trưng Logarit (Logarithmic Features + L2)
        * Hồi quy Đa thức Bậc 2 (Polynomial Features Degree 2 + L2)
        * Hồi quy Tương tác Đặc trưng (Feature Interaction + L2)
    * Giải thích lý do lựa chọn từng công thức dựa trên giả định về mối quan hệ tuyến tính, phi tuyến, lợi ích giảm dần và tương tác giữa các yếu tố ảnh hưởng đến giá xe.

3.  **Đánh giá Mô hình:**
    * Sử dụng K-Fold Cross-Validation (k=5) để đánh giá độ ổn định và hiệu năng tổng quát của các mô hình
    * Các chỉ số đánh giá bao gồm: Mean Squared Error (MSE), Root Mean Squared Error (RMSE), Mean Absolute Error (MAE), và R-squared (R²)
    * Chọn ra mô hình tốt nhất dựa trên kết quả cross-validation (trong báo cáo là mô hình Hồi quy Tương tác Đặc trưng)
    * Đánh giá performance của mô hình được chọn trên tập kiểm thử (test set) riêng biệt

## Tập dữ liệu

* `train.csv`: Dữ liệu được cung cấp để huấn luyện mô hình

## Yêu cầu Thư viện

* Python 3.x
* Pandas
* Numpy
* Matplotlib
* Seaborn
* **Lưu ý:** *Không* sử dụng các thư viện như `sklearn` cho việc huấn luyện mô hình hồi quy (theo yêu cầu ban đầu của Lab).

## Cách chạy

1.  Clone repository này.
2.  Đặt file `train.csv` vào vị trí phù hợp.
3.  Chạy file mã nguồn chính (Jupyter Notebook hoặc .py) để thực thi toàn bộ quy trình từ tiền xử lý đến huấn luyện và đánh giá mô hình.

## Cấu trúc Thư mục (Đề xuất)
* `/`: Chứa mã nguồn (ví dụ: `main.ipynb`, `linear_regression.py`, ...).
* `Data/`: Chứa file `train.csv`.

## Thực hiện

* Nguyễn Ngọc Khoa - 23122036
