---
title: "Truy cập an toàn qua internet đến các điểm cuối SaaS PrivateLink bằng AWS Verified Access"
date: 2025-08-21
weight: 1
chapter: false
pre: " <b> 3.1. </b> "
---

**Tác giả:** Salman Ahmed và Ankush Goyal | **Ngày:** 21 tháng 8, 2025

**Danh mục:** [AWS PrivateLink](https://aws.amazon.com/privatelink/), [AWS Verified Access](https://aws.amazon.com/verified-access/), [Mạng & Phân phối Nội dung](https://aws.amazon.com/products/networking/), [SaaS](https://aws.amazon.com/saas/), [Hướng dẫn Kỹ thuật](https://aws.amazon.com/blogs/networking-and-content-delivery/category/post-types/technical-how-to/)

---

## Giới thiệu

Khi việc áp dụng điện toán đám mây tiếp tục phát triển, các nhà cung cấp phần mềm dưới dạng dịch vụ (SaaS) trên AWS ngày càng sử dụng **Amazon Web Services (AWS) PrivateLink** để cung cấp dịch vụ một cách an toàn cho khách hàng.

PrivateLink cho phép kết nối riêng tư, liền mạch giữa các VPC mà không cần phơi bày ứng dụng ra internet công cộng, đảm bảo bảo mật mạnh mẽ và hiệu suất mạng ổn định.

Tuy nhiên, điều gì sẽ xảy ra nếu bạn muốn cung cấp cùng mức độ truy cập an toàn đó cho người dùng bên ngoài AWS — chẳng hạn như nhân viên làm việc từ xa hoặc đối tác kết nối qua internet? **AWS Verified Access** cho phép bạn mở rộng các dịch vụ được hỗ trợ bởi PrivateLink đến người dùng được ủy quyền qua internet trong khi vẫn duy trì các rào cản bảo mật nghiêm ngặt và kiến trúc **zero trust**.

Trong bài viết này, chúng ta sẽ khám phá cách kích hoạt truy cập an toàn, có khả năng mở rộng qua internet đến các điểm cuối PrivateLink bằng cách sử dụng Verified Access. Điều này giúp các tổ chức mở rộng khả năng tích hợp SaaS đến người dùng ở bất kỳ đâu — mà không ảnh hưởng đến bảo mật.

_(Bài viết này giả định rằng bạn đã quen thuộc với các khái niệm cơ bản của AWS Verified Access, vì vậy chúng tôi sẽ không đi sâu vào kiến thức nền tảng.)_

---

## Tổng quan Giải pháp

Chúng ta sẽ bắt đầu với một kịch bản liên quan đến truy cập an toàn vào ứng dụng SaaS. Trong trường hợp này, nhà cung cấp SaaS cung cấp ứng dụng của họ thông qua dịch vụ điểm cuối PrivateLink, trong khi người dùng thiết lập một điểm cuối VPC giao diện trong VPC của họ để kết nối với dịch vụ này. Điều này được minh họa trong sơ đồ kiến trúc ở phần tiếp theo.

Thách thức phát sinh khi người dùng trong tổ chức cần truy cập dịch vụ này từ bên ngoài AWS, ví dụ qua internet. Chúng ta triển khai Verified Access như một giải pháp để thiết lập kết nối này, vì các điểm cuối PrivateLink chỉ có thể được truy cập từ bên trong VPC hoặc thông qua các kết nối mạng riêng tư như **AWS Site-to-Site VPN** hoặc **AWS Direct Connect**. Giải pháp này không yêu cầu kết nối PrivateLink xuyên vùng, vì nó dựa vào kết nối cùng vùng trong AWS.

![alt text](image14.png)

_Hình 1: Sơ đồ kiến trúc cho thấy các yêu cầu của người dùng sử dụng điểm cuối Verified Access để truy cập dịch vụ SaaS được lưu trữ trong tài khoản SaaS._

### Luồng Lưu lượng

Sử dụng Verified Access có nghĩa là luồng lưu lượng diễn ra như sau:

1. Người dùng từ xa với **Verified Access Connectivity Client** được cài đặt gửi yêu cầu đến URL công khai do chủ sở hữu VPC người tiêu dùng cung cấp, URL này trỏ đến các điểm cuối AWS Verified Access. Verified Access Connectivity Client cho phép kết nối an toàn giữa các thiết bị người dùng và các ứng dụng không sử dụng HTTP(s).

2. Trong tài khoản người tiêu dùng, có một **vùng lưu trữ công khai Amazon Route 53** chứa các bản ghi định tuyến có trọng số giúp cân bằng tải lưu lượng giữa hai điểm cuối AWS Verified Access.

3. Mỗi điểm cuối Verified Access được ánh xạ đến một điểm cuối VPC giao diện cụ thể.

4. Người dùng được xác thực bằng **AWS IAM Identity Center**.

5. Các yêu cầu từ điểm cuối VPC giao diện được chuyển tiếp qua PrivateLink đến **Network Load Balancer (NLB)** trong VPC SaaS.

6. NLB định tuyến lưu lượng đến các phiên bản **Amazon Elastic Compute Cloud (Amazon EC2)** phía sau nó — nơi ứng dụng SaaS được lưu trữ.

## Triển khai Giải pháp

Các bước sau đây sẽ hướng dẫn bạn triển khai giải pháp này.

### Bước 1: VPC Nhà cung cấp SaaS — Thiết lập Dịch vụ PrivateLink

Tạo một dịch vụ được hỗ trợ bởi PrivateLink (Create a service powered by PrivateLink), được gọi là **dịch vụ điểm cuối**, như được minh họa trong hình dưới đây. Trong ví dụ này, dịch vụ được lưu trữ trên các phiên bản EC2 phía sau Network Load Balancer (NLB). Làm cho dịch vụ điểm cuối khả dụng (Make the endpoint service) để người dùng (người tiêu dùng dịch vụ) có thể truy cập nó.

![alt text](image11.png)

_Hình 2: Dịch vụ điểm cuối VPC hiển thị các Network Load Balancer (NLB) đã đăng ký trong tab Load balancers._

### Bước 2: VPC Người tiêu dùng — Tạo Điểm cuối VPC Giao diện

Trong **VPC Người tiêu dùng**, tạo một **điểm cuối VPC giao diện** cho **tên dịch vụ** bạn đã tạo ở Bước 1, như được minh họa trong hình dưới đây.

Để đảm bảo **Tính khả dụng cao**, hãy tạo điểm cuối này trong ít nhất hai **Vùng khả dụng (AZ)**.

Ghi chú các **ID Giao diện Mạng Đàn hồi (ENI)** được tạo bởi điểm cuối này, vì chúng sẽ cần thiết trong các bước tiếp theo.

![alt text](image5.png)

_Hình 3: Điểm cuối VPC trong VPC Người tiêu dùng hiển thị tab Subnets với chi tiết subnet và ID Giao diện Mạng trong hai Vùng khả dụng._

### Bước 3: Tài khoản Người tiêu dùng — Tạo AWS Verified Access

#### 3.1. Tạo Trust Provider

Tạo một **nhà cung cấp tin cậy danh tính người dùng** cho Verified Access.

Trong ví dụ này, chúng tôi sử dụng **IAM Identity Center**, như được minh họa trong hình dưới đây.

![alt text](image12.png)

_Hình 4: Loại nhà cung cấp tin cậy Verified Access là IAM Identity Center._

#### 3.2. Tạo Phiên bản Verified Access

Tạo một **phiên bản Verified Access**, như được minh họa trong hình dưới đây.

Khi tạo Phiên bản Verified Access, bạn có thể **liên kết** nó với nhà cung cấp tin cậy bạn đã tạo ở bước trước.

![alt text](image15.png)

_Hình 5: Phiên bản Verified Access sử dụng loại User iam-identity-center._

#### 3.3. Tạo Nhóm Verified Access

Tạo một **nhóm Verified Access**, như được minh họa trong hình dưới đây.

Gán nhóm này cho phiên bản Verified Access được tạo ở bước trước.

Xác định **chính sách nhóm Verified Access** để quản lý quyền truy cập. Trong ví dụ này, chúng tôi cho phép truy cập cho các địa chỉ email đã xác minh với tên miền `@amazon.com`.

![alt text](image7.png)

_Hình 6: Chính sách nhóm Verified Access._

#### 3.4. Tạo Điểm cuối Giao diện Mạng

Tạo một **điểm cuối giao diện mạng** cho Verified Access:

- Chọn nhóm Verified Access bạn đã tạo ở bước trước.
- Trong phần **Protocol**, chọn **TCP**.
- Trong **Port ranges**, nhập **"443-443"**.
- Trong phần **Network interface**, chọn ID ENI của điểm cuối VPC giao diện bạn đã tạo ở Bước 2.
- Bạn cần tạo một điểm cuối Verified Access cho mỗi ENI. Khi hoàn tất, bạn sẽ có hai điểm cuối Verified Access, như được minh họa trong hình dưới đây.

![alt text](image3.png)

_Hình 7: Chi tiết điểm cuối Verified Access._

Khi bạn đã hoàn thành các bước trên, mỗi điểm cuối Verified Access sẽ có một tên miền DNS riêng biệt. Ghi chú các tên miền này, vì chúng sẽ được sử dụng để cấu hình vùng lưu trữ công khai trong Route 53. Hình dưới đây minh họa cách xác định vị trí tên miền điểm cuối đã được tạo.

![alt text](image10.png)

_Hình 8: Tên miền điểm cuối Verified Access._

### Bước 4: Tạo DNS cho Ứng dụng của bạn

Tạo một **bản ghi định tuyến có trọng số** trong **vùng lưu trữ công khai Route 53**.

Mỗi điểm cuối Verified Access sẽ có **bản ghi CNAME** riêng, như được minh họa trong hình dưới đây.

![alt text](image4.png)

_Hình 9: Vùng lưu trữ Route 53 với các bản ghi CNAME._

---

## Truy cập Ứng dụng bằng AWS Verified Access

Khi điểm cuối Verified Access đã sẵn sàng, bạn có thể truy cập ứng dụng bằng Connectivity Client. Người dùng cần tải xuống và cài đặt phiên bản mới nhất của Connectivity Client trên hệ điều hành ưa thích của họ (Windows hoặc macOS). Trước khi tiếp tục, hãy gỡ cài đặt bất kỳ phiên bản cũ nào của client.

Trước khi đăng nhập, người dùng cần xuất tệp cấu hình client, có thể thực hiện thông qua bảng điều khiển **Amazon Virtual Private Cloud (Amazon VPC)** hoặc **AWS Command Line Interface (AWS CLI)**. Sau đó, các tệp cấu hình phải được triển khai đến các vị trí cụ thể như sau:

- **Đối với Windows:** `C:\ProgramData\Connectivity Client`
- **Đối với macOS:** `/Library/Application\ Support/Connectivity\Client`

Sau khi hoàn thành các bước này, người dùng có thể khởi chạy Connectivity Client và xác thực thông qua giao diện được cung cấp, như được minh họa trong hình tiếp theo.

![alt text](image9.png)

_Hình 10: Màn hình Đăng nhập Connectivity Client_

Khi bạn chọn **Sign In**, một cửa sổ trình duyệt sẽ xuất hiện yêu cầu bạn nhập tên người dùng và mật khẩu. Sau đó, bạn sẽ thấy yêu cầu quyền với thông báo "Allow Connectivity Client to access your data?" — bạn cần xác nhận để tiếp tục.

![alt text](image13.png)

_Hình 11: Cho phép Connectivity Client truy cập dữ liệu của bạn_

Sau khi chọn **Allow access**, quá trình xác thực của bạn sẽ hoàn tất, như được minh họa trong hình dưới đây.

![alt text](image8.png)

_Hình 13: Trạng thái Connectivity Client khi đã kết nối_

Quá trình này cho phép truy cập an toàn và đã xác minh vào ứng dụng. Sau khi xác thực thành công, client thiết lập một kênh an toàn đến điểm cuối Verified Access. Tiếp theo, tất cả lưu lượng được định tuyến qua ENI, kết nối với nhà cung cấp SaaS thông qua PrivateLink. Quy trình làm việc được tối ưu hóa này đảm bảo kết nối an toàn và hiệu quả giữa người dùng và ứng dụng, tận dụng các dịch vụ và tính năng bảo mật của AWS.

Để truy cập ứng dụng từ trình duyệt, hãy điều hướng đến URL bản ghi bạn đã tạo trong vùng lưu trữ công khai Route 53. Hình dưới đây minh họa rằng người dùng giờ đây có thể truy cập ứng dụng được lưu trữ trong VPC của nhà cung cấp SaaS, trên các phiên bản EC2 phía sau NLB riêng tư.

![alt text](image1.png)

_Hình 14: Màn hình chào mừng của dịch vụ SaaS được cung cấp thông qua Verified Access qua PrivateLink._

---

## Kết luận

AWS Verified Access cung cấp một cách mới để thiết lập truy cập an toàn, có khả năng mở rộng qua internet đến các tài nguyên AWS nội bộ, chẳng hạn như các điểm cuối SaaS dựa trên PrivateLink. Kết hợp khả năng của PrivateLink và Verified Access cho phép các doanh nghiệp xây dựng quy trình truy cập ứng dụng an toàn từ đầu đến cuối vừa đơn giản vừa tuân thủ.

Nếu bạn là nhà cung cấp hoặc người tiêu dùng SaaS đang tìm cách kích hoạt truy cập bên ngoài an toàn đến các dịch vụ PrivateLink, Verified Access cung cấp một giải pháp mạnh mẽ với chi phí vận hành tối thiểu. Bắt đầu ngay hôm nay với các tính năng Verified Access cho phép truy cập tài nguyên qua các giao thức không phải HTTP(S).

### Tài liệu tham khảo

- [Truy cập dịch vụ AWS thông qua AWS PrivateLink](https://docs.aws.amazon.com/vpc/latest/privatelink/)
- [AWS Verified Access là gì?](https://docs.aws.amazon.com/verified-access/latest/ug/what-is-verified-access.html)

---

## Về các Tác giả

**Salman Ahmed**

![Salman Ahmed](image2.png)

Salman Ahmed là Senior Technical Account Manager tại AWS Enterprise Support. Ông chuyên giúp khách hàng thiết kế, triển khai và vận hành các giải pháp AWS. Kết hợp chuyên môn sâu về mạng với niềm đam mê khám phá các công nghệ mới, Salman giúp các tổ chức thành công trong hành trình chuyển đổi đám mây của họ. Ngoài công việc, ông thích nhiếp ảnh, du lịch và theo dõi các đội thể thao yêu thích của mình.

**Ankush Goyal**

![Ankush Goyal](image6.png)

Ankush Goyal là Senior Technical Account Manager tại AWS Enterprise Support, chuyên giúp khách hàng trong ngành du lịch và khách sạn tối ưu hóa cơ sở hạ tầng đám mây của họ. Với hơn 20 năm kinh nghiệm trong lĩnh vực CNTT, ông tập trung vào việc tận dụng các dịch vụ mạng AWS để nâng cao hiệu quả hoạt động và thúc đẩy việc áp dụng đám mây. Ankush đam mê cung cấp các giải pháp thực tế giúp khách hàng đơn giản hóa và tối ưu hóa hoạt động của họ trên nền tảng đám mây.

---

**Nguồn Bài viết Gốc:** [AWS Networking & Content Delivery Blog](https://aws.amazon.com/blogs/networking-and-content-delivery/)
