# Bài 2:Hướng dẫn cài đặt cảm biến độ ẩm cho trang trại Lan

1.  ## Tổng quan
    

Cảm biến độ ẩm giúp theo dõi độ ẩm không khí trong nhà lưới, hỗ trợ người quản lý kiểm soát điều kiện môi trường cho cây trồng.

### Thiết bị cần chuẩn bị

-   Cảm biến độ ẩm DHT22 hoặc AM2302

-   Raspberry Pi (BCM)

-   Dây nối Dupont

-   Tuốc nơ vít và băng keo điện

-   Thẻ nhớ đã cài hệ điều hành

2.  ## Các bước cài đặt
    

### Bước 1: Cập nhật hệ thống

Mở Terminal và chạy lệnh sau để cập nhật danh sách gói và nâng cấp hệ thống:

```

```

### Bước 2: Cài đặt thư viện cho cảm biến DHT22

```

```

> Lưu ý: Tùy phiên bản Raspberry Pi OS, lệnh cài thư viện Python có thể cần điều chỉnh theo hướng dẫn chính thức của hệ điều hành.

### Bước 3: Bật giao tiếp 1-Wire (nếu dùng DHT22 phù hợp)

Mở công cụ cấu hình:

```

```

Chọn **Interface Options** và bật giao tiếp cần thiết cho loại cảm biến đang sử dụng. DHT22 dạng GPIO thông thường không yêu cầu 1-Wire; hãy kiểm tra đúng loại module trước khi bật tùy chọn này.

### Bước 4: Kiểm tra thiết bị đã được nhận diện

```

```

Lệnh này kiểm tra thiết bị trên bus 1-Wire. Với cảm biến DHT22 nối GPIO thông thường, kết quả có thể không xuất hiện tại đường dẫn này.

### Bước 5: Chạy chương trình đọc cảm biến

Ví dụ dưới đây minh họa cách đọc DHT22 bằng thư viện Adafruit_DHT và bật/tắt máy bơm theo ngưỡng độ ẩm. Số chân GPIO và mạch điều khiển cần được xác nhận theo phần cứng thực tế.

```

```

Lưu mã trên vào tệp [read_dht22.py](http://read_dht22.py), sau đó chạy:

```

```

3.  ## Sơ đồ kết nối
    

Chân cảm biến DHT22

Chân Raspberry Pi (BCM)

Ghi chú

VCC

3.3V (Pin 1)

Cấp nguồn

GND

GND (Pin 6)

Nối đất

DATA

GPIO4 (Pin 7)

Tín hiệu dữ liệu

NC

Không kết nối

Để trống

> Kiểm tra sơ đồ chân theo đúng model cảm biến và bo mạch. Không nối máy bơm trực tiếp vào GPIO; cần mạch driver hoặc relay phù hợp và nguồn riêng.

4.  ## Vị trí lắp đặt
    

-   Lắp cảm biến ở nơi thông thoáng, đại diện cho khu vực trồng cây.

-   Tránh ánh nắng trực tiếp chiếu vào cảm biến.

-   Che chắn khỏi nước tưới và mưa trực tiếp.

-   Cố định dây nối để tránh bị kéo tuột hoặc chập điện.

5.  ## Kiểm tra kết quả
    

Kết quả minh họa khi chương trình chạy:

```

```

Giá trị thực tế phụ thuộc môi trường và cảm biến. Ngưỡng độ ẩm cần được điều chỉnh theo loại cây trồng và mục tiêu canh tác.

6.  ## Danh sách kiểm tra thiết bị
    

-   [ ] Chuẩn bị Raspberry Pi và thẻ nhớ hệ điều hành

-   [ ] Chuẩn bị cảm biến DHT22/AM2302

-   [ ] Kiểm tra chân VCC, GND và DATA

-   [ ] Cài đặt các thư viện cần thiết

-   [ ] Chạy thử chương trình đọc cảm biến

-   [ ] Kiểm tra máy bơm qua mạch điều khiển phù hợp

-   [ ] Kiểm tra vị trí lắp đặt và bảo vệ cảm biến

7.  ## Minh họa ký tự Escape
    

Dùng dấu gạch chéo ngược để hiển thị ký tự đặc biệt mà không áp dụng định dạng Markdown:

-   \* hiển thị dấu sao *.

-   \# hiển thị dấu thăng #.
