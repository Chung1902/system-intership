# Mô hình TCP/IP
## Mô hình TCP/IP là gì?
**TCP/IP (Transmission Control Protocol/Internet Protocol)** là bộ giao thức truyền thông quan trọng và là nền tảng của mạng Internet, chịu trách nhiệm về việc kết nối các thiết bị và truyền tải dữ liệu hiệu quả. Bộ giao thức này hoạt động bằng cách chia nhỏ thông tin thành các gói dữ liệu, định tuyến chúng đến đúng địa chỉ đích, và đảm bảo chúng được tập hợp lại chính xác tại điểm nhận.

![alt text](../images/TCPIPmodel.jpg)

**Vai trò của các giao thức chính**:
- **TCP (Transmission Control Protocol)**: Đảm bảo việc truyền dữ liệu đáng tin cậy và có thứ tự. TCP thiết lập kết nối giữa người gửi và người nhận, chia dữ liệu thành các gói, và đảm bảo chúng đến nơi đầy đủ, chính xác bằng cách phát hiện lỗi và yêu cầu truyền lại.
- **IP (Internet Protocol)**: Chịu trách nhiệm định địa chỉ và định tuyến dữ liệu. Mỗi thiết bị trên mạng có một địa chỉ IP riêng, và IP sẽ xác định con đường hiệu quả nhất để các gói dữ liệu đi qua mạng đến đúng địa chỉ đích.
## Các Layer trong mô hình TCP/IP
**Lớp 1: Lớp vật lý - Physical**
1. **Khái niệm**: là tầng thấp nhất, chịu trách nhiệm truyền tín hiệu số thành các tín hiệu vật lý (như sóng điện, sóng quang) để truyền qua môi trường truyền dẫn (cáp, sóng vô tuyến) giữa các thiết bị trong cùng một mạng.
2. **Đặc điểm**:
- **Truyền tải dữ liệu ở dạng bit**: Đây là tầng thực hiện việc chuyển đổi dữ liệu thành các tín hiệu điện tử (bit) để truyền qua các phương tiện vật lý. 
- **Tập trung vào kết nối vật lý**: Tầng này quy định các tiêu chuẩn vật lý cho mạng, bao gồm loại cáp, đầu nối, và các thông số kỹ thuật khác cần thiết để thiết lập kết nối giữa các thiết bị. 
- **Sử dụng tín hiệu đồng bộ**: Các thiết bị ở hai đầu kết nối vật lý phải đồng ý về một quy ước tín hiệu để phân biệt các bit 0 và 1 một cách chính xác.
- **Chịu trách nhiệm về phương tiện truyền dẫn**: Bao gồm cáp, sóng radio, hoặc quang học, và các công nghệ như Bluetooth, NFC, Ethernet.
3. **Chức năng**:
- **Định nghĩa đặc tính vật lý**: Xác định các tiêu chuẩn cho cáp, đầu nối, hiệu điện thế, tần số, và các thông số khác của kết nối vật lý.
- **Đóng gói dữ liệu**: Chuyển đổi gói tin (packet) từ tầng Internet thành các khung (frame) để truyền đi trên mạng.
- **Xử lý địa chỉ**: Chịu trách nhiệm sử dụng địa chỉ vật lý (MAC Address) để định danh và định tuyến dữ liệu đến các thiết bị cụ thể trong cùng mạng nội bộ.

**Lớp 2: Lớp mạng - Internet**
1. **Khái niệm**: Tầng mạng (Network Layer hay Internet Layer) trong mô hình TCP/IP chịu trách nhiệm định tuyến các gói tin (packet) từ nguồn đến đích bằng cách sử dụng Giao thức Internet (IP).
2. **Đặc điểm**:
- **Đóng gói dữ liệu**: Dữ liệu từ tầng trên được chia thành các gói tin (packet) với kích thước phù hợp với mạng.
- **Định tuyến (Routing)**: Đây là chức năng cốt lõi, quyết định đường đi tốt nhất cho gói tin từ nguồn đến đích qua các mạng khác nhau.
- **Kết nối các mạng**: Tầng mạng có nhiệm vụ liên kết các mạng độc lập, tạo thành một mạng lưới rộng lớn hơn (Internet).
3. **Chức năng**:
- **Đóng gói (Packetizing)**: Nhận dữ liệu từ tầng trên, đóng gói chúng thành các đơn vị dữ liệu gọi là gói tin (packet) và thêm một phần đầu (header) chứa thông tin định tuyến.
- **Định địa chỉ (Addressing)**: Sử dụng địa chỉ IP để xác định duy nhất từng thiết bị trên mạng, giống như địa chỉ nhà.
- **Xử lý lỗi (Error Handling)**: Giao thức ICMP được sử dụng trong tầng này để báo cáo lỗi và gửi thông báo liên quan đến các sự cố mạng.

![alt text](../images/Internet.jpg)

**Lớp 3: Lớp vận chuyển - Transport**
1. **Khái niệm**: là tầng thứ ba, có vai trò xử lý giao tiếp đầu cuối giữa các ứng dụng trên các thiết bị khác nhau, sử dụng hai giao thức chính là TCP (đảm bảo độ tin cậy, thứ tự, sửa lỗi) và UDP (tốc độ cao, không đảm bảo tin cậy).
2. **Đặc điểm**:
- **Phân chia và gom nhóm dữ liệu**: Tầng này nhận dữ liệu từ tầng ứng dụng, chia nhỏ chúng thành các đoạn có kích thước phù hợp, mỗi đoạn có một header chứa thông tin điều khiển và dữ liệu cần truyền.
- **Sử dụng các cổng (Ports)**: Để phân biệt các ứng dụng khác nhau trên cùng một thiết bị, tầng giao vận sử dụng các cổng TCP và UDP, cho phép nhiều ứng dụng cùng lúc sử dụng mạng.
3. **Chức năng**:
- **Kiểm soát luồng (Flow Control)**: Điều chỉnh tốc độ truyền dữ liệu để tránh làm quá tải các thiết bị nhận có kết nối chậm, đảm bảo quá trình truyền dữ liệu diễn ra hiệu quả.
- **Kiểm soát lỗi (Error Control)**: Đảm bảo dữ liệu được nhận đầy đủ và đúng thứ tự. Nếu có lỗi hoặc gói tin bị mất, tầng này sẽ yêu cầu truyền lại để đảm bảo tính toàn vẹn của dữ liệu.

![alt text](../images/Transport.jpg)

**Lớp 4: Lớp ứng dụng - Application**
1. **Khái niệm**: là tầng cao nhất trong mô hình TCP/IP, chịu trách nhiệm giao tiếp trực tiếp với người dùng và các ứng dụng, cho phép các dịch vụ mạng như duyệt web (HTTP), gửi email (SMTP), và truyền tệp (FTP) hoạt động.
2. **Đặc điểm**: cung cấp các dịch vụ mạng cho người dùng và ứng dụng thông qua các giao thức như HTTP, FTP, SMTP, SSH, v.v. Nó nằm ở lớp trên cùng của mô hình, chịu trách nhiệm cho việc trao đổi dữ liệu chuẩn hóa, xử lý các định dạng dữ liệu byte-to-byte và kết hợp thông tin định tuyến để đảm bảo các gói tin được gửi đến đích chính xác.
3. **Chức năng**:
- **Giao tiếp với ứng dụng người dùng**: Tầng ứng dụng cung cấp giao diện cho phép người dùng và các ứng dụng giao tiếp với môi trường mạng.
- **Định dạng và xử lý dữ liệu**: Dữ liệu ở tầng này được định dạng thành các luồng byte và chứa thông tin cần thiết để xác định đường dẫn chính xác của gói tin, đảm bảo giao tiếp thành công.
## So sánh với mô hình OSI
`Giống nhau`
- Đều là mô hình mạng phân tầng
- Nguyên tắc đóng gói dữ liệu giống nhau
- Mỗi lớp hoạt động độc lập, có thể thay đổi công nghệ bên trong mà không ảnh hưởng toàn bộ hệ thống.
- Đều mô tả cách dữ liệu đi từ máy A sang máy B

`Khác nhau`
| |Mô hình OSI|Mô hình TCP/Ip|
|-|-----------|--------------|
|Số tầng|7 tầng|4 tầng|
|Tính chất|Mô hình tham chiếu lý thuyết (chủ yếu dùng trong giảng dạy)|Bộ giao thức thực tế được sử dụng trên Internet|
|Mức độ chi tiết|Chia nhỏ từng chức năng (Session, Presentation riêng)|Gộp nhiều chức năng vào tầng Application|
|Địa chỉ sử dụng|- MAC Address (Data Link)<br>- IP Address (Network)<br>- Port (Transport)|- MAC Address (Link)<br>- IP Address (Internet)<br>- Port (Transport)|
|Đơn vị dữ liệu|- Bits (Physical)<br>- Frame (Data Link)<br>- Packet (Network)<br>- Segment/Datagram (Transport)<br>- Data (các tầng trên)|- Frame (Link)<br>- Packet (Internet)<br>- Segment (TCP) / Datagram (UDP)<br>- Data (Application)<br>|
|Thiết bị hoạt động|- Hub (Physical)<br>- Switch (Data Link)<br>- Router (Network)<br>- Gateway (Application)|- Switch (Link)<br>- Router (Internet)|
|Ứng dụng|Dùng để nghiên cứu, học lý thuyết, chuẩn hoá|Dùng trực tiếp trong thực tế (Internet, LAN, WAN)|
|Đơn vị nghiên cứu|ISO phát triển(1984)|ARPANET phát triển (1970s)|
 

## Workflow với mô hình TCP/IP (các bước khi mà A muốn gửi 1 thông tin đến B)

`Máy gửi`

- **Lớp Ứng dụng**: Chuẩn bị dữ liệu được tạo ra và chuyển xuống các lớp dưới.
- **Lớp Giao vận**: Dữ liệu từ lớp ứng dụng được chia thành các segment (TCP) hoặc datagram (UDP) nhỏ hơn.
- **Lớp Internet**: Mỗi gói tin của lớp giao vận được đóng gói lại thành một datagram, thêm địa chỉ IP nguồn và đích để định tuyến trên mạng. 
- **Lớp vật lý**: Datagram được chuyển thành các frame và truyền qua phương tiện vật lý (như cáp Ethernet, Wi-Fi) đến thiết bị đích.

`Máy nhận`

- **Lớp vật lý**: Gói tin được nhận và chuyển thành dạng phù hợp để xử lý ở lớp trên.
- **Lớp Internet**: Địa chỉ IP được kiểm tra để xác định gói tin đã đến đúng đích hay chưa.
- **Lớp giao vận**: TCP (nếu dùng) kiểm tra số thứ tự để sắp xếp lại các segment, xác nhận dữ liệu có bị mất hay lỗi không, và yêu cầu gửi lại nếu cần.
- **Lớp ứng dụng**: Dữ liệu hoàn chỉnh được ghép lại và chuyển đến ứng dụng tương ứng (ví dụ: trình duyệt web hiển thị nội dung).
