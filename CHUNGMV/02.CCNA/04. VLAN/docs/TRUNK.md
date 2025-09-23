# Tìm hiểu vè TRUNK
## Trunk là gì?
Trunk (cổng trunk hoặc đường trunk) là một kết nối vật lý giữa hai bộ chuyển mạch (switch) hoặc giữa switch và router cho phép truyền lưu lượng của nhiều VLAN cùng lúc qua một liên kết duy nhất, sử dụng cơ chế gắn thẻ VLAN ID theo chuẩn IEEE 802.1Q để phân biệt các VLAN.

![alt text](../images/TRUNK.jpg)

## Chuẩn IEEE 802.1Q (DOT1Q)
1. Khái niệm
Chuẩn IEEE 802.1Q là một tiêu chuẩn mạng định nghĩa phương pháp gắn thẻ (tagging) VLAN vào các khung dữ liệu Ethernet để cho phép các «mạng cục bộ ảo» (VLAN) trên các mạng Ethernet hoạt động cùng nhau.

![alt text](../images/IEEE802.jpg)

**Chức năng chính của IEEE 802.1Q**
- **VLAN Tagging:** 802.1Q thêm một thẻ 4-byte vào khung Ethernet, còn được gọi là «thẻ Dot1q». Thẻ này bao gồm 12-bit VLAN ID (từ 0 đến 4095), cho phép phân loại và quản lý tới 4096 VLAN khác nhau.
- **Giao thức Trunking:** Giao thức này cho phép các cổng trung kế (trunk ports) trên thiết bị chuyển mạch truyền lưu lượng của nhiều VLAN qua một kết nối vật lý duy nhất, trong khi vẫn giữ chúng tách biệt.
- **Ưu tiên chất lượng dịch vụ (QoS):** Thẻ 802.1Q cũng bao gồm 3 bit PRI (Priority) để phân loại lưu lượng, cho phép ưu tiên các loại dữ liệu quan trọng hơn.
- **VLAN gốc (Native VLAN):** Giao thức hỗ trợ «VLAN gốc» cho phép truyền một số lưu lượng không gắn thẻ (untagged) qua các cổng trung kế, giúp tương thích với các thiết bị cũ hơn.

**Cách hoạt động**
- Switch thêm VLAN tag (802.1Q header) vào frame để đánh dấu VLAN. Gói tin sau khi gắn tag sẽ đi qua đường trunk.
- Switch đọc VLAN ID trong tag → xác định gói tin thuộc VLAN nào. Sau đó quyết định có forward đến port nào (dựa trên VLAN table).
- Switch sẽ loại bỏ VLAN tag (untag) trước khi gửi ra cho thiết bị đầu cuối (PC, laptop…), vì thiết bị thường không hiểu VLAN tag.

**Cấu trúc thẻ VLAN (802.1Q VLAN Tag - 4 byte)**

Một Ethernet frame bình thường có cấu trúc:
```
[Dest MAC][Src MAC][EtherType][Payload][FCS]
```
Khi dùng 802.1Q, sẽ chèn thêm VLAN Tag (4 byte) ngay sau địa chỉ MAC nguồn:
```
[Dest MAC][Src MAC][802.1Q Tag][EtherType][Payload][FCS]
```
Trong đó, 802.1Q Tag (4 byte) gồm:
- TPID (Tag Protocol Identifier – 16 bit): Luôn có giá trị 0x8100 → báo hiệu đây là frame có VLAN tag.
- TCI (Tag Control Information – 16 bit): gồm 3 trường nhỏ:
  - Priority (3 bit): QoS – ưu tiên gói tin.
  - CFI/DEI (1 bit): chỉ ra định dạng khung (Canonical Format Indicator).
  - VLAN ID (12 bit): chỉ VLAN mà frame thuộc về (giá trị 0–4095, dùng được 1–4094).

Ví dụ:

PC1 thuộc VLAN 10 muốn gửi dữ liệu đến PC2 (cũng VLAN 10) qua 2 switch nối bằng trunk:
- Switch1 gắn VLAN tag 10 → gửi qua trunk.
- Switch2 đọc VLAN tag 10 → chuyển frame vào các port thuộc VLAN 10.
- Khi frame ra cổng nối PC2 (access port VLAN 10) → tag bị bỏ đi.

## CHUẨN ISL (Inter Switch Link) của Cisco
### Khái niệm
**Chuẩn ISL** là giao thức đóng gói VLAN của Cisco và chỉ được hỗ trợ trên một số thiết bị Cisco qua các liên kết Fast và Gigabit Ethernet.
