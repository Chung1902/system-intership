# Tìm hiểu về VLAN
## Mục đích chia VLAN
1. **Tăng cường bảo mật:**
- VLAN tạo ra các "phòng" mạng riêng biệt, nơi các thiết bị trong các VLAN khác nhau không thể giao tiếp trực tiếp với nhau, trừ khi được cấu hình định tuyến rõ ràng.
- Giúp ngăn chặn truy cập trái phép vào dữ liệu nhạy cảm, hạn chế sự lây lan của virus và phần mềm độc hại.
2. **Cải thiện hiệu suất mạng:**
- Mỗi VLAN hoạt động như một miền quảng bá (broadcast domain) riêng biệt.
- Khi lưu lượng broadcast (gói tin được gửi đến tất cả các thiết bị trong mạng) chỉ được giới hạn trong VLAN tương ứng, nó sẽ giảm đáng kể lưu lượng không cần thiết trên toàn mạng.
- Kết quả là giảm tắc nghẽn mạng, cải thiện hiệu suất chung và đảm bảo chất lượng dịch vụ cho các ứng dụng quan trọng như thoại IP.
3. **Tăng tính linh hoạt và quản lý:**
- VLAN cho phép bạn nhóm các thiết bị lại với nhau dựa trên chức năng hoặc phòng ban thay vì vị trí địa lý vật lý.
- Bạn có thể dễ dàng di chuyển một thiết bị sang một VLAN khác mà không cần thay đổi cấu trúc dây cáp vật lý, chỉ bằng cách cấu hình lại cổng switch.
- Điều này đơn giản hóa việc quản lý mạng, đặc biệt là khi cần mở rộng hoặc thay đổi cấu trúc mạng.
4. **Tối ưu hóa việc phân bổ tài nguyên:**
- Mỗi VLAN có thể được quản lý độc lập về tài nguyên, giúp phân chia băng thông và địa chỉ IP hiệu quả hơn.
- Bạn có thể áp dụng các chính sách quản lý lưu lượng riêng cho từng VLAN, như ưu tiên lưu lượng thoại trên một VLAN riêng.

