# Document yolo
How to train yolo: https://blog.roboflow.com/training-yolov4-on-a-custom-dataset/

#I. Giới thiệu
Yolo (You only life one) là thuật toán được dùng để Detetect đối tượng
Thuật toán Yolo bản chất có cấu tạo từ mạng CNN được biến đổi để xác định và phân loại đối tượng
Trong đó, phần convolutional layer được dùng để trích xuất đặc trưng và phần fully connected layer được dùng để dự đoán đối tượng và toạ độ của đối tượng đó
#II. Cách thức hoạt động
##1. Đầu vào và ra của vật thể
Đầu vào là ảnh của vật. Tuy nhiên ảnh không nhất thiết phải có cùng kích thước với các ảnh đầu vào khác giống CNN. Ảnh chia thành SxS ô, mà thường là 3x3, 5x5, 7x7, ...
Đầu ra của ảnh là ma trận 3 chiều với kích thước là SxSx(5xN+M)
Ví dụ: ảnh được chia thành 7x7, số box dự đoán trên mỗi ô là 2, số class là 3 thì ma trận đầu ra sẽ là 7x7x(5x2+3)
##2. Giải thích về cách trọng số
SxS là số lượng ô được chia trên 1 tấm ảnh
5 lần lướt là x, y, w, h, prediction
Trong đó: (x, y) là tâm toạ độ vật thể, (w, h) lần lượt là chiều rộng và chiều cao vật thể, prediction dự đoán có vật thể hay không
N là số lượng box trên mỗi ô được dự đoán
Ví dụ: N = 2 thì mỗi ô sẽ dự đoán 2 lần
M là số lượng class dự đoán tỉ lệ phần trăm dự đoán vật thể đó. M này tương tự như đầu ra của mạng CNN
