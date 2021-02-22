# Document yolo
How to train yolo: https://blog.roboflow.com/training-yolov4-on-a-custom-dataset/<br>
Real time: https://www.youtube.com/watch?v=xKK2mkJ-pHU <br>
Source: https://pysource.com/2019/07/08/yolo-real-time-detection-on-cpu/ <br>


<h1>I. Giới thiệu</h1>

<p>Yolo (You only life one) là thuật toán được dùng để Detetect đối tượng</p>
<p>Thuật toán Yolo bản chất có cấu tạo từ mạng CNN được biến đổi để xác định và phân loại đối tượng</p>
<p>Trong đó, phần convolutional layer được dùng để trích xuất đặc trưng và phần fully connected layer được dùng để dự đoán đối tượng và toạ độ của đối tượng đó</p>

<h1>II. Cách thức hoạt động</h1>
<h2>1. Đầu vào và ra của vật thể</h2>
<p>Đầu vào là ảnh của vật. Tuy nhiên ảnh không nhất thiết phải có cùng kích thước với các ảnh đầu vào khác giống CNN. Ảnh chia thành SxS ô, mà thường là 3x3, 5x5, 7x7, ...</p>
<p>Đầu ra của ảnh là ma trận 3 chiều với kích thước là SxSx(5xN+M)</p>
<p>Ví dụ: ảnh được chia thành 7x7, số box dự đoán trên mỗi ô là 2, số class là 3 thì ma trận đầu ra sẽ là 7x7x(5x2+3)</p>

<h2>2. Giải thích về các trọng số</h2>
<p>SxS là số lượng ô được chia trên 1 tấm ảnh</p>
<p>5 lần lướt là x, y, w, h, prediction</p>
<ul>
<li>(x, y) là tâm toạ độ vật thể</li>
<li>(w, h) lần lượt là chiều rộng và chiều cao vật thể</li>
<li>prediction dự đoán có vật thể hay không</li>
</ul>
<p>N là số lượng box dự đoán trên mỗi ô</p>
<p>M là số lượng class dự đoán tỉ lệ phần trăm dự đoán vật thể đó. M này tương tự như đầu ra của mạng CNN</p>

<h2>3. Công thức prediction</h2>
<p>prediction = pr(object)*IoU(pred, truth)</p>
<p>Trong đó:</p>
<ul>
  <li>pr(object): dự đoán có vật thể hay không</li>
  <li>IoU(pred, truth) được tính bằng:</li>
</ul>
<img src="https://github.com/dangbinhphuoc/yolo/blob/main/IoU.png"/>
