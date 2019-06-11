### CNN cơ bản

- Sự khác biệt cơ bản giữa **Dense layer** và **Convolution layer** đó chính là **Dense layer** khi train image sẽ học **global pattern** (toàn bộ pixel của ảnh) trong khi **Convolution layer** chỉ học **local pattern** (trong TH của ảnh sẽ là cửa sổ 2D có kích thước nhỏ)

- Dense layer thường sẽ được dùng ở cuối của CNN

- Như ví dụ trong file **CNN_basic.py** tầng Dense cuối cùng sẽ có kích cỡ 10, vì lí do đó nó có khả năng phân loại cho 10 loại đầu ra. Mạng CNN xây dựng được sẽ có kiến trúc như sau:

<img src="images/pic1.png" />

### Cơ chế hoạt động

- Khác với mạng neural thông thường, chỉ học các global pattern thì CNN sẽ học các local pattern của một bức ảnh (1 window của CNN có kích cỡ khá nhỏ: 2x2, 3x3)

- Có 2 tính chất quan trọng của CNN mà ta cần nắm rõ:
  - Việc CNN học các pattern là di chuyển bất biến. Nói 1 cách đơn giản đó là CNN sẽ học các pattern của 1 bức ảnh từ góc dưới bên phải cho đến góc trên bên trái. Mạng neural thông thường sẽ phải học các pattern xuất hiện ở chỗ mới thêm 1 lần nữa. Ở CNN, mạng này học được các thể hiện có tính tổng quát hoá cao nên số lượng các ví dụ đi kèm sẽ ít đi
  - Tầng thứ nhất của CNN sẽ học những chi tiết nhỏ (ở viền - edge), tầng thứ 2 sẽ học những chi tiết lớn hơn dựa theo những đặc trưng bóc tách được từ tầng thứ nhất, nên CNN sẽ có khả năng trừu tượng hoá hoá khái niệm thị giác của bức ảnh khá cao