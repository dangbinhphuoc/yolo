# Document yolo
How to train yolo: https://blog.roboflow.com/training-yolov4-on-a-custom-dataset/

I. Giới thiệu
- Yolo (You only life one) là thuật toán được dùng để Detetect đối tượng
- Thuật toán Yolo bản chất có cấu tạo từ mạng CNN được biến đổi để xác định và phân loại đối tượng
- Trong đó, phần convolutional layer được dùng để trích xuất đặc trưng và phần fully connected layer được dùng để dự đoán đối tượng và toạ độ của đối tượng đó
II. Cách thức hoạt động
- Đầu vào là ảnh của vật. Tuy nhiên ảnh không nhất thiết phải có cùng kích thước với các ảnh đầu vào khác giống CNN
- Đầu ra của ảnh là 5xN + M trọng số
- Trong đó:
-- 
