---
title: "Các Thực Tiễn Tốt Nhất để Tối Ưu Thời Gian Failover cho Overlay Tunnels trên AWS Direct Connect"
date: 2025-08-21
weight: 3
chapter: false
pre: " <b> 3.3. </b> "
---

**Tác giả:** Pavlos Kaimakis và Azeem | **Ngày:** 21 tháng 8 năm 2025

**Chuyên mục:** [AWS Direct Connect](https://aws.amazon.com/directconnect/), [AWS Site-to-Site VPN](https://aws.amazon.com/vpn/), [AWS Transit Gateway](https://aws.amazon.com/transit-gateway/)

---

## Giới thiệu

Tối ưu failover times trong hybrid connectivity là rất quan trọng để đáp ứng Key Performance Indicators (KPIs) về khả dụng trong các modern enterprise workloads. Điều này đặc biệt quan trọng khi triển khai overlay tunnels trên Amazon Web Services (AWS) Direct Connect, chẳng hạn như AWS Site-to-Site VPN sử dụng IPSec tunnels, hoặc Connect Attachments sử dụng Generic Routing Encapsulation (GRE) tunnels. Cấu hình đúng có thể giảm failover times từ vài phút xuống còn mili giây, cải thiện đáng kể độ tin cậy mạng.

Theo nguyên tắc thiết kế 'Anticipate Failure' từ Well-Architected Framework Operational Excellence pillar, bài viết này nêu ra các operational best practices để giảm thiểu downtime lên đến 99% trong khi vẫn duy trì các kết nối mạng resilient giữa on-premises và môi trường AWS. Ví dụ, phân tích của chúng tôi cho thấy chỉ cần chọn unpinned thay vì pinned tunnel configurations cũng có thể giảm failover times tới 33%.

Một hạ tầng Direct Connect bền vững tạo nền tảng cho highly available hybrid connectivity. Trước khi đi sâu vào overlay tunnel optimization, người đọc nên làm quen với Direct Connect Resiliency Toolkit và hiểu về Active/Active and Active/Passive configurations. Bài viết này sử dụng Direct Connect High Resiliency: Multi-Site non Redundant Deployment model như một kiến trúc tham chiếu để minh họa các kỹ thuật tối ưu hóa này, như thể hiện trong hình dưới đây.

![alt text](images/image6.png)

_Hình 1: Kết nối trực tiếp với mô hình có khả năng phục hồi cao_

---

## Các yếu tố chính ảnh hưởng đến Failover Times

Khi tối ưu hóa failover times cho overlay tunnels trên Direct Connect, có hai yếu tố chính cần xem xét:

1. **Tốc độ failover của kết nối cơ bản**
2. **Hành vi của overlay tunnel**

Trước tiên, chúng ta sẽ xem cách tối ưu hóa BGP timers và triển khai BFD để cải thiện khả năng phát hiện và hội tụ lỗi Direct Connect failover ở tầng cơ bản. Sau đó, chúng ta tìm hiểu cách các phương pháp cấu hình tunnel khác nhau—pinned và unpinned—có thể ảnh hưởng đáng kể đến hiệu suất failover tổng thể.

Mặc dù việc tối ưu hóa BGP timer giúp phát hiện sự cố nhanh hơn ở tầng Direct Connect, nhưng chiến lược cấu hình tunnel sẽ quyết định mức độ nhanh chóng mà lưu lượng overlay có thể phục hồi thông qua các đường đi thay thế. Hiểu và triển khai cả hai yếu tố này là rất quan trọng để đạt được failover times tối ưu trong kiến trúc mạng hybrid của bạn.

### Virtual Interfaces (VIFs)

Direct Connect cần Virtual Interfaces (VIFs), có thể là Public, Private, hoặc Transit. Tạo một Direct Connect VIF bao gồm hai bước chính: trao đổi VLAN tags và thiết lập Border Gateway Protocol (BGP) sessions. Nếu bạn muốn tìm hiểu thêm về Direct Connect VIFs, bạn có thể tham khảo [our documentation](https://docs.aws.amazon.com/directconnect/).

Trong bài viết này, chúng ta tập trung vào hai tùy chọn sau:

- BGP hold timers
- Tunneling over Direct Connect

---

## Bộ đếm thời gian BGP và tác động của chúng đến thời gian failover

Direct Connect VIF failover times chủ yếu phụ thuộc vào BGP failover timing. Có hai loại bộ đếm chính cần xem xét:

### BGP Hold Timer

Đây là khoảng thời gian tối đa mà một BGP router chờ để nhận keepalive hoặc update message trước khi tuyên bố peer bị chết và chấm dứt BGP session. Trên Direct Connect VIF, default hold timer là 90 giây, có thể giảm xuống tối thiểu 3 giây.

### BGP Keepalive Timer

Bộ đếm này xác định khoảng thời gian mà một BGP router gửi keepalive messages tới các peer để duy trì BGP session và báo hiệu trạng thái hoạt động. Trên Direct Connect VIF, default keepalive timer là 30 giây, có thể giảm xuống tối thiểu 1 giây.

Để cải thiện failover times, người dùng có thể giảm BGP timers trên routers của họ. AWS tự động thương lượng để khớp các giá trị này khi nhận được BGP message. Tuy nhiên, BGP timers không thể cấu hình qua AWS Management Console.

**Lưu ý quan trọng:** Mặc dù giảm giá trị BGP timer giúp cải thiện failover times, nhưng việc đặt quá thấp không được khuyến nghị vì có thể ảnh hưởng đến tính ổn định mạng. Cấu hình quá mạnh mẽ có thể gây ra các lần BGP session resets không cần thiết trong thời gian tắc nghẽn mạng hoặc CPU tăng đột biến.

---

## Bidirectional Forwarding Detection (BFD)

Để phát hiện lỗi và failover nhanh hơn, chúng tôi khuyến nghị bật Bidirectional Forwarding Detection (BFD). Asynchronous BFD được bật tự động cho Direct Connect VIFs ở phía AWS. Tuy nhiên, bạn phải cấu hình router để enable asynchronous BFD cho kết nối Direct Connect của mình.

Sau đây là một lệnh cấu hình CLI minh họa cách bật BFD trên Cisco ASR 1002-HX chạy IOS-XE 16.1:

```
! Interface Configuration
interface TenGigabitEthernet1/0/0.100
description DX-VIF-1
encapsulation dot1q 100
ip address 169.254.100.1 255.255.255.252
bfd interval 300 min_rx 300 multiplier 3
no shutdown

! BGP Configuration
router bgp 65000
neighbor 169.254.100.2 remote-as 64512
neighbor 169.254.100.2 fall-over bfd
```

### Các thành phần chính của BFD

**Minimum liveness detection interval:** Đây là khoảng thời gian tối thiểu giữa các gói điều khiển BFD nhận được mà router của bạn nên mong đợi. Khoảng thời gian ngắn hơn cho phép phát hiện lỗi nhanh hơn nhưng tăng mức sử dụng CPU. Trên Direct Connect, giá trị tối thiểu được supported là 300 msec.

**Minimum BFD multiplier:** Đây là số gói BFD có thể bị bỏ qua trước khi một phiên bị coi là ngừng hoạt động. Tổng thời gian phát hiện lỗi được xác định bằng cách nhân giá trị này với khoảng thời gian phát hiện. Giá trị tối thiểu được supported là 3 (ba).

### So sánh hiệu quả

Việc sử dụng BFD trên Direct Connect VIFs giúp giảm đáng kể failover times:

- **Without BFD:** BGP failover time = 3 giây
- **With BFD:** Failover time = 3 × 300 ms = 0.9 giây

Điều này cho thấy mức **70% reduction** trong thời gian failover, khiến BFD trở thành một giải pháp hiệu quả hơn nhiều cho việc phát hiện và khắc phục lỗi.

---

## Tunneling qua Direct Connect

Direct Connect hoạt động như một kết nối underlay cho những người dùng triển khai overlay tunnels (Site-to-Site VPN hoặc Connect Attachments) đến Transit Gateway. Mặc dù những tùy chọn overlay này cung cấp các tính năng kết nối nâng cao, chúng cũng làm tăng sự phụ thuộc vào giao thức và các yếu tố thời gian ảnh hưởng đến hiệu suất failover tổng thể.

### Các phương pháp cấu hình Tunnel

#### 1. Pinned Tunnels

Trong cấu hình này, các địa chỉ IP outside của tunnel phía người dùng được định tuyến độc quyền qua một Direct Connect VIF cụ thể. Điều này thường xảy ra khi người dùng sử dụng địa chỉ IP interface Direct Connect VIF làm địa chỉ IP outside tunnel.

![alt text](images/image2.png)

_Hình 2: Interface pinned overlay tunnels trên Direct Connect_

**Ví dụ cấu hình:**

```
! DX Interface Configuration
interface TenGigabitEthernet1/0/0.100
description DX-VIF-1
encapsulation dot1q 100
ip address 169.254.100.1 255.255.255.252
no shutdown

! BGP for DX VIF
router bgp 65000
bgp log-neighbor-changes
neighbor 169.254.100.2 remote-as 64512
!
address-family ipv4
! Important: Advertise VIF interface IP for tunnel endpoint reachability
network 169.254.100.1 mask 255.255.255.252
neighbor 169.254.100.2 activate
neighbor 169.254.100.2 route-map SET-LOCAL-PREF in
exit-address-family

! GRE Tunnel Configuration using DX VIF IP
interface Tunnel1
description TGW-Connect-Primary
ip address 172.16.1.1 255.255.255.252
tunnel source 169.254.100.1
tunnel destination 10.0.1.1
tunnel mode gre ip
no shutdown
```

**Tác động của Pinned Tunnels:**

Việc "pinning" (gắn chặt) của tunnel vào một kết nối cụ thể có những tác động quan trọng đến failover:

- Tunnel được gắn với một kết nối Direct Connect cụ thể
- Traffic không thể ngay lập tức sử dụng đường dự phòng trong trường hợp xảy ra sự cố ở lớp underlay
- Failover cần BGP session của tunnel phát hiện sự cố thông qua việc hết hạn BGP timer
- Traffic chỉ failover sau khi tunnel đã ngắt
- Có thể dẫn đến thời gian failover lâu hơn

#### 2. Unpinned Tunnels

Trong cấu hình này, các địa chỉ IP bên ngoài của tunnel bắt nguồn từ các interface logic (chẳng hạn như loopbacks) được cấu hình trên user routers. Cả AWS tunnel endpoint IP (Transit Gateway CIDR) và các địa chỉ IP loopback của user router đều có thể truy cập thông qua tất cả các Direct Connect VIFs có sẵn.

![alt text](images/image4.png)

_Hình 3: Unpinned overlay tunnels trên Direct Connect_

**Traffic Engineering:**

- **Trên Public VIFs:** Sử dụng AS_PATH khi quảng bá các tuyến loopback
- **Trên Private/Transit VIFs:** Sử dụng BGP Local Preference communities khi quảng bá các tuyến loopback

**Ví dụ cấu hình:**

```
! Loopback Interface Configuration
interface Loopback1
description Tunnel-Source-Interface
ip address 192.168.1.1 255.255.255.255
no shutdown

! GRE Tunnel Configuration
interface Tunnel1
description TGW-Connect
ip address 172.16.1.1 255.255.255.252
tunnel source Loopback1
tunnel destination 10.0.1.1
no shutdown

interface TenGigabitEthernet1/0/0.100
description DX-VIF-1
encapsulation dot1q 100
ip address 169.254.100.1 255.255.255.252
no shutdown

! BGP Configuration
router bgp 65000
bgp log-neighbor-changes
! DX VIF BGP
neighbor 169.254.100.2 remote-as 64512
!
address-family ipv4
! Important: Advertise loopback to DX VIF BGP
network 192.168.1.1 mask 255.255.255.255
! DX VIF neighbor - advertise loopback
neighbor 169.254.100.2 activate
neighbor 169.254.100.2 route-map SET-LOCAL-PREF in
neighbor 169.254.100.2 route-map ADVERTISE-LOOPBACK out
exit-address-family
```

---

## Phân tích thời gian Failover

Các dịch vụ tunneling của AWS khác nhau sử dụng các thiết lập mặc định BGP timer khác nhau. Chúng tôi sử dụng Transit Gateway Connect attachments để so sánh thời gian failover giữa các cấu hình pinned và unpinned.

Transit Gateway Connect sử dụng các BGP timer khác với Direct Connect VIFs:

- Keepalive timeout: 10 giây
- Hold timer: 30 giây

### So sánh thời gian Failover

![alt text](images/image3.png)

Như được thể hiện trong bảng so sánh ở trên, mặc dù cả cấu hình pinned và unpinned đều có thể đạt thời gian failover dưới một giây với BFD, nhưng mức độ phức tạp khi triển khai lại khác nhau đáng kể.

---

## Các lưu ý khi triển khai

Khi triển khai các kỹ thuật tối ưu hóa failover này, hãy xem xét các khía cạnh chính sau:

### Hiệu năng và phần cứng

- Thời gian failover thực tế có thể thay đổi tùy theo khả năng phần cứng của router và độ phức tạp của mạng
- Cấu hình BFD yêu cầu phần cứng tương thích và cần có kế hoạch phù hợp cho CPU và bộ nhớ
- Hãy tham khảo tài liệu của nhà cung cấp thiết bị mạng để biết các đặc tính hội tụ cụ thể và giá trị timer được khuyến nghị

### Giới hạn kiến trúc

- Mặc dù BFD giúp tối ưu đáng kể việc phát hiện failover ở lớp underlay, nhưng nó chỉ có thể được cấu hình trên Direct Connect VIF, không áp dụng cho overlay tunnels
- Các sự cố headend tunnel trong overlay vẫn phụ thuộc vào tunnel BGP timers
- Khi áp dụng các giá trị timer quá ngắn, cần lưu ý rằng sự mất ổn định của phiên BGP và định tuyến bất đối xứng có thể xảy ra nếu không được cấu hình đúng

### Triển khai và xác thực

Thành công phụ thuộc vào việc triển khai có phương pháp và xác thực liên tục:

1. Bắt đầu với các giá trị timer bảo thủ và điều chỉnh dần dựa trên hiệu năng thực tế
2. Ghi lại thời gian failover cơ bản trước khi thay đổi
3. Áp dụng tối ưu hóa theo từng bước:
   - Bắt đầu với BGP timers
   - Sau đó kích hoạt BFD (nếu được hỗ trợ)
   - Cuối cùng là triển khai cấu hình tunnel mà bạn đã chọn

Việc kiểm tra định kỳ bằng Direct Connect failover test và giám sát thông qua Amazon CloudWatch metrics, cùng với việc theo dõi trạng thái BFD và BGP ở cấp độ thiết bị, sẽ giúp đảm bảo cấu hình của bạn duy trì hiệu năng tối ưu theo thời gian.

---

## Kết luận

Bài viết này minh họa cách tối ưu hóa thời gian failover cho các overlay tunnels trên AWS Direct Connect. Phân tích của chúng tôi cho thấy:

- Các cấu hình tunnel cố định với giá trị timer mặc định cần nhiều hơn **33%** thời gian để failover so với các tunnel không cố định
- Nguyên nhân chính là do phụ thuộc vào phiên BGP trong overlay
- Việc triển khai BFD với các tunnel không cố định cho phép giảm thời gian failover từ 90 giây xuống chỉ còn khoảng 300 mili-giây
- Đạt được mức cải thiện **99%** về thời gian khôi phục

Đối với người dùng triển khai overlay tunnels trên Direct Connect, chúng tôi khuyến nghị sử dụng các cấu hình tunnel không cố định để giảm thiểu tác động trong quá trình failover. Mặc dù bài viết này tập trung vào lỗi kết nối underlay, nhưng các nguyên tắc và cấu hình được trình bày có thể giúp bạn xây dựng kiến trúc mạng hybrid có độ tin cậy cao hơn.

---

## Về tác giả

**Azeem Ayaz**

![alt text](images/image1.png)

Azeem là Chuyên gia Mạng cấp cao (Sr Network Specialist TAM) tại AWS Enterprise Support, chuyên hỗ trợ các khách hàng doanh nghiệp chiến lược và nhu cầu mạng đám mây phức tạp của họ. Với 13 năm kinh nghiệm trong việc thiết kế và vận hành hạ tầng mạng và bảo mật, anh tập trung vào việc xây dựng kiến trúc có khả năng mở rộng, giúp doanh nghiệp tối ưu hóa đầu tư vào đám mây và đạt được hiệu quả kinh doanh có thể đo lường. Trước khi gia nhập AWS, Azeem đã phát triển chuyên môn của mình tại các tập đoàn hàng đầu như Vodafone, Cisco và Juniper. Khi không bận rộn với việc thiết kế giải pháp đám mây, anh thường chơi các trò chiến thuật và khám phá những điểm đến mới cùng bạn đời của mình.

**Pavlos Kaimakis**

![alt text](images/image5.png)

Pavlos là Kiến trúc sư Giải pháp cấp cao (Senior Solutions Architect) tại AWS, nơi anh hỗ trợ khách hàng thiết kế và triển khai các giải pháp quan trọng cho doanh nghiệp. Với kinh nghiệm sâu rộng trong phát triển sản phẩm và hỗ trợ khách hàng, anh tập trung vào việc xây dựng các kiến trúc có khả năng mở rộng nhằm mang lại giá trị kinh doanh thực tiễn. Ngoài công việc, Pavlos là một người đam mê du lịch, thích khám phá những vùng đất và nền văn hóa mới.

---

**Nguồn bài viết gốc:** [AWS Networking & Content Delivery Blog](https://aws.amazon.com/blogs/networking-and-content-delivery/)
