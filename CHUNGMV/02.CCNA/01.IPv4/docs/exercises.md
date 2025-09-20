# Bài tập
1. Cho biết địa chỉ nào sau đây có thể dùng cho host
- 150.100.255.255-> địa chỉ broadcast-> Không dùng được cho host
- 175.100.255.18-> nằm trong dải lớp B-> có dùng được cho host
- 195.234.253.0-> địa chỉ Network-> Không dùng được cho host
- 100.0.0.23-> nằm trong dải lớp A-> có dùng được cho host
- 188.258.221.176-> Octet thứ 2 = 258 (>255)-> Không dùng được cho host
- 127.34.25.189-> là địa chỉ loopback (127.x.x.x)-> Không dùng được cho host
- 224.156.217.73-> thuộc dải multicast-> Không dùng được cho host
2. Cho mạng và số bit mượn. Giả sử có hỗ trợ subnet zero. Hãy xác định :
a, 192.168.2.0/24 mượn 5 bit.
- Số subnet = 2^5 = 32
- Số host mỗi subnet = 2^3−2=6 host/subnet

|subnet|Host hợp lệ|Broadcast|
|------|-----------|---------|
|192.168.2.0/29|192.168.2.1-192.168.2.6|192.168.2.7|
|192.168.2.8/29|192.168.2.9-192.168.2.14|192.168.2.15|
|192.168.2.16/29|192.168.2.17-192.168.2.22|192.168.2.23|
|---------------|-------------------------|------------|
|192.168.2.248/29|192.168.2.249-192.168.2.254|192.168.2.255|

b, 192.168.12.0/24 mượn 3 bit.
- Số subnet = 2^3 = 8
- Số host mỗi subnet = 2^5−2= 30 host/subnet

|subnet|Host hợp lệ|Broadcast|
|------|-----------|---------|
|192.168.12.0/27|192.168.12.1-192.168.12.30|192.168.12.31|
|192.168.12.32/27|192.168.12.33-192.168.12.62|192.168.12.63|
|---------------|-------------------------|------------|
|192.168.12.224/27|192.168.12.225-192.168.12.254|192.168.12.255|

C, 172.16.2.0/24 mượn 2 bit
- Số subnet = 2^2 = 4
- Số host mỗi subnet = 2^6−2= 62 host/subnet

|subnet|Host hợp lệ|Broadcast|
|------|-----------|---------|
|172.16.2.0/26|172.16.2.1/26-172.16.2.62|172.16.2.63|
|172.16.2.64/26|172.16.2.65-172.16.2.126|172.16.2.127|
|---------------|-------------------------|------------|
|172.16.2.192/26|172.16.2.193-172.16.2.254|172.16.2.255|
d, 10.0.0.0/8 mượn 18 bit.
- Số subnet = 2^18 = 262,144
- Số host mỗi subnet = 2^6−2= 62 host/subnet

|subnet|Host hợp lệ|Broadcast|
|------|-----------|---------|
|10.0.0.0/26|10.0.0.1-10.0.0.62|10.0.0.63|
|10.0.0.64/26|10.0.0.65-10.0.0.126|10.0.0.127|
|---------------|-------------------------|------------|
|10.255.255.192/26|10.255.255.193-10.255.255.254|10.255.255.255|

3. Cho mạng 172.16.5.0/24. Hãy chia nhỏ sao cho phù hợp với sơ đồ sau:
![alt text](image.png)

- Cho mạng 78 host
  - Công thức: 2^m - 2 >= 79 => m = 7 (7 bit phần host)
  - Subnet: 172.16.5.0/25
  - Subnet Mask: 255.255.255.128
  - Số host mỗi subnet = 2^7-2=126 host usable/subnet.
  - Dải host usable: 172.16.5.1 → 172.16.5.126 (126 usable)
  - Broadcast: 172.16.5.127
- Mạng cho 50 host
  - Công thức: 2^m - 2 >= 51 => m = 6 (6 bit phần host)
  - Subnet: 172.16.5.128/26
  - Subnet Mask: 255.255.255.192
  - Số host mỗi subnet = 2^6-2=62 host usable/subnet.
  - Dải host usable: 172.16.5.129 → 172.16.5.190 (62 usable)
  - Broadcast: 172.16.5.191
- Mạng cho 20 host
  - Công thức: 2^m - 2 >= 21 => m = 5 (5 bit phần host)
  - Subnet: 172.16.5.192/27
  - Subnet Mask: 255.255.255.224
  - Số host mỗi subnet = 2^5-2=30 host usable/subnet.
  - Dải host usable: 172.16.5.193 → 172.16.5.222 (30 usable)
  - Broadcast: 172.16.5.223
- Mạng cho 10 host
  - Công thức: 2^m - 2 >= 11 => m = 4 (4 bit phần host)
  - Subnet: 172.16.5.224/28
  - Subnet Mask: 255.255.255.240
  - Số host mỗi subnet = 2^4-2= 14 host usable/subnet.
  - Dải host usable: 172.16.5.225→ 172.16.5.239 (14 usable)
  - Broadcast: 172.16.5.240
- Mạng cho 5 host
  - Công thức: 2^m - 2 >= 6 => m = 3 (3 bit phần host)
  - Subnet: 172.16.5.240/29
  - Subnet Mask: 255.255.255.248
  - Số host mỗi subnet = 2^3-2= 6 host usable/subnet.
  - Dải host usable: 172.16.5.241→ 172.16.5.247 (6 usable)
  - Broadcast: 172.16.5.248
- Liên kết point-to-point
  - Công thức: 2^m - 2 >= 2 => m = 1 (1 bit phần host)
  - Subnet: 172.16.5.248/30
  - Subnet Mask: 255.255.255.252
  - Số host mỗi subnet = 2^2-2= 2 host usable/subnet.
  - Địa chỉ mạng:
     - Liên kết 1: 172.16.5.248/30 => Dải 172.16.5.248->172.16.5.251. Địa chỉ có thể sử dụng: 172.16.5.249 – 172.16.5.250
     - Liên kết 2: 172.16.5.252/30 => Dải 172.16.5.252->172.16.5.255. Địa chỉ có thể sử dụng: 172.16.5.253 – 172.16.5.254
