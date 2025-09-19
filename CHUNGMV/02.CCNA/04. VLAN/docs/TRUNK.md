# Tìm hiểu vè TRUNK
## Trunk là gì?
Trunk (cổng trunk hoặc đường trunk) là một kết nối vật lý giữa hai bộ chuyển mạch (switch) hoặc giữa switch và router cho phép truyền lưu lượng của nhiều VLAN cùng lúc qua một liên kết duy nhất, sử dụng cơ chế gắn thẻ VLAN ID theo chuẩn IEEE 802.1Q để phân biệt các VLAN.

![alt text](../images/TRUNK.jpg)

## Chuẩn IEEE 802.1Q (DOT1Q)
1. Khái niệm
Chuẩn IEEE 802.1Q là một tiêu chuẩn mạng định nghĩa phương pháp gắn thẻ (tagging) VLAN vào các khung dữ liệu Ethernet để cho phép các «mạng cục bộ ảo» (VLAN) trên các mạng Ethernet hoạt động cùng nhau.

![alt text](../images/IEEE802.jpg)

Chức năng chính của IEEE 802.1Q
- **VLAN Tagging:** 802.1Q thêm một thẻ 4-byte vào khung Ethernet, còn được gọi là «thẻ Dot1q». Thẻ này bao gồm 12-bit VLAN ID (từ 0 đến 4095), cho phép phân loại và quản lý tới 4096 VLAN khác nhau.
- **Giao thức Trunking:** Giao thức này cho phép các cổng trung kế (trunk ports) trên thiết bị chuyển mạch truyền lưu lượng của nhiều VLAN qua một kết nối vật lý duy nhất, trong khi vẫn giữ chúng tách biệt.
- **Ưu tiên chất lượng dịch vụ (QoS):** Thẻ 802.1Q cũng bao gồm 3 bit PRI (Priority) để phân loại lưu lượng, cho phép ưu tiên các loại dữ liệu quan trọng hơn.
- **VLAN gốc (Native VLAN):** Giao thức hỗ trợ «VLAN gốc» cho phép truyền một số lưu lượng không gắn thẻ (untagged) qua các cổng trung kế, giúp tương thích với các thiết bị cũ hơn.
