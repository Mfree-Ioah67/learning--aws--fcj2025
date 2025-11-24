---
title: "Tối ưu hóa kết nối RISE with SAP bằng AWS Cloud WAN"
date: 2025-08-21
weight: 2
chapter: false
pre: " <b> 3.2. </b> "
---

**Tác giả:** Pablo Sánchez Carmona, Kenny Rajan, and Rozal Singh | **Ngày:** 21 tháng 8 năm 2025

**Chuyên mục:** [AWS Cloud WAN](https://aws.amazon.com/blogs/networking-and-content-delivery/category/networking-content-delivery/aws-cloud-wan/), [Networking & Content Delivery](https://aws.amazon.com/blogs/networking-and-content-delivery/category/networking-content-delivery/), [SAP on AWS](https://aws.amazon.com/blogs/networking-and-content-delivery/category/sap/), [Technical How-to](https://aws.amazon.com/blogs/networking-and-content-delivery/category/post-types/technical-how-to/)

---

## Giới thiệu

Khi triển khai [RISE with SAP](https://docs.aws.amazon.com/sap/latest/general/rise.html), việc thiết lập kết nối mạng đến RISE trên [Amazon Virtual Private Cloud (Amazon VPC)](https://aws.amazon.com/vpc/) trong **Amazon Web Services (AWS)** là trách nhiệm của bạn. Trước đây, người dùng thường dựa vào [AWS Site-to-Site VPN](https://aws.amazon.com/vpn/), [AWS Direct Connect](https://aws.amazon.com/directconnect/), [Amazon VPC peering](https://docs.aws.amazon.com/vpc/latest/peering/what-is-vpc-peering.html), hoặc [AWS Transit Gateway](https://aws.amazon.com/transit-gateway/) để kết nối hệ thống tại chỗ và các tài khoản AWS hiện có với môi trường được quản lý bởi SAP. Hơn nữa, các tổ chức đã sử dụng [AWS Cloud WAN](https://aws.amazon.com/cloud-wan/) để xây dựng, quản lý và giám sát mạng toàn cầu thống nhất của họ có thể muốn đồng bộ kết nối RISE with SAP với kiến trúc Cloud WAN hiện có. Với Cloud WAN, bạn có thể có một mạng toàn cầu thống nhất với khả năng kiểm soát dựa trên chính sách nhất quán, giúp bạn đơn giản hóa việc quản lý, tăng cường bảo mật thông qua kiểm tra lưu lượng và duy trì chiến lược mạng nhất quán trên toàn tổ chức.

**Cloud WAN** là một trong những lựa chọn kết nối mạng cho RISE with SAP có thể được kích hoạt theo yêu cầu của người dùng với nhóm RISE with SAP. Hơn nữa, các mẫu kết nối được đề cập trong bài viết này cũng có thể được áp dụng cho các tích hợp bên thứ ba khác theo cùng kiến trúc với RISE with SAP.

---

## Tại sao chọn AWS Cloud WAN?

**AWS Cloud WAN** là một dịch vụ **wide area networking (WAN)** được quản lý cho phép bạn xây dựng, quản lý và giám sát mạng toàn cầu kết nối tài nguyên trên môi trường cloud và on-premises. Dịch vụ này cung cấp một mạng được quản lý tập trung, giúp giảm chi phí vận hành và sự phức tạp khi vận hành một mạng toàn cầu.

Mặc dù AWS cung cấp nhiều dịch vụ kết nối mạng mạnh mẽ, **Cloud WAN** nâng cấp khả năng quản lý mạng lên một tầm cao mới bằng cách cung cấp cái nhìn toàn cầu và khả năng kiểm soát dựa trên chính sách nhất quán trên toàn bộ mạng. Bạn có thể tìm hiểu thêm về dịch vụ này trong các bài viết [Introducing AWS Cloud WAN](https://aws.amazon.com/blogs/networking-and-content-delivery/introducing-aws-cloud-wan-preview/) (nơi bạn có thể hiểu rõ hơn về các thành phần chính của dịch vụ) và [Simplify global security inspection with AWS Cloud WAN service insertion](https://aws.amazon.com/blogs/networking-and-content-delivery/simplify-global-security-inspection-with-aws-cloud-wan-service-insertion/) (để hiểu cách Cloud WAN đơn giản hóa cấu hình kiểm tra lưu lượng bảo mật).

Tuy nhiên, câu hỏi chính mà bạn có thể tự đặt ra là: lợi ích của việc sử dụng **Cloud WAN** so với các phương thức kết nối khác là gì?

1. Cloud WAN cung cấp mạng động (multi-Region) toàn cầu trong AWS. Điều này có nghĩa là bất kỳ VPC nào trong các Region của bạn đều có thể tự động truy cập RISE with SAP một cách linh hoạt, bất kể môi trường SAP của bạn được tạo ở Region nào.
2. Việc quản lý và quan sát tập trung giúp đơn giản hóa quá trình hiểu về các mạng phức tạp và cách chúng kết nối với các kết nối bên thứ ba của bạn.
3. Transit Gateway cho phép bạn tự định nghĩa định tuyến, cách lan truyền (propagations) và cách các attachments được ánh xạ tới các route tables. Việc thêm một route table hoặc attachment mới thường dẫn đến hàng chục thay đổi ở các tầng dưới. Cloud WAN cho phép bạn sử dụng attachment tags và các metadata khác để tự động ánh xạ các attachments vào các segments, trong đó bạn xác định mối quan hệ giữa các segments thông qua policy.
4. Khi kết nối với các giải pháp bên thứ ba thông qua VPC attachments, chúng tôi khuyến nghị bạn nên bao gồm việc kiểm tra lưu lượng (traffic inspection) giữa môi trường của bạn và môi trường của bên thứ ba. Tính năng [service insertion của Cloud WAN](https://docs.aws.amazon.com/network-manager/latest/cloudwan/cloudwan-policy-service-insertion.html) giúp đơn giản hóa việc cấu hình định tuyến để thiết lập quá trình kiểm tra này.

---

## Kiến trúc và các bước triển khai RISE with SAP trên AWS Cloud WAN

Bây giờ, sau khi chúng ta đã xác định AWS Cloud WAN và các lợi ích của nó, chúng ta có thể tập trung vào việc tích hợp với RISE with SAP. Hình 1 minh họa kiến trúc kết nối RISE with SAP bằng Cloud WAN trong môi trường có nhiều tài khoản (multi-account environment). Chúng tôi đã bao gồm một lớp kiểm tra lưu lượng (inspection layer) sử dụng [AWS Network Firewall](https://aws.amazon.com/network-firewall/) để kiểm tra lưu lượng giữa RISE with SAP VPC và phần còn lại của môi trường. Mẫu kiến trúc này cũng hoạt động khi sử dụng bất kỳ thiết bị tường lửa của bên thứ ba nào kết hợp với [Gateway Load Balancer (GWLB)](https://aws.amazon.com/elasticloadbalancing/gateway-load-balancer/).

![alt text](<Streamlining RISE with SAP Connectivity using AWS Cloud WAN- Networking & Content Delivery/images/image1.png>)

_Hình 1. Kiến trúc tổng thể Multi-Region và multi-account AWS Cloud WAN kết nối với RISE with SAP_

Các bước sau đây phác thảo quy trình tích hợp cho mạng AWS của bạn (sử dụng Cloud WAN) với RISE with SAP. Trong phần này, chúng ta tập trung vào việc xác định các bước cấu hình của quá trình tích hợp.

- Bạn cần tạo Global Network và Core Network với một policy document xác định cấu trúc mạng của bạn: các AWS Regions, segments, routing actions, và attachment policies. Kiểm tra [AWS documentation](https://docs.aws.amazon.com/network-manager/latest/cloudwan/cloudwan-policies-json.html) để biết thêm thông tin chi tiết về thiết lập này.  
   Chúng tôi khuyến nghị sử dụng một dedicated segment riêng cho các kết nối RISE with SAP VPC. Việc phân tách tối thiểu trong cấu hình Cloud WAN — với các VPC được kết nối vào một segment riêng biệt — cho phép kiểm soát tốt hơn cấu hình định tuyến (thêm lớp kiểm tra, tạo các static routes hoặc blackholes, v.v.).

- Để tuân theo thực hành tốt nhất trong việc bao gồm lớp kiểm tra lưu lượng (inspection layer), bạn nên triển khai một Inspection VPC sử dụng Network Firewall hoặc GWLB cùng với các thiết bị bảo mật của bên thứ ba. Ngoài ra, policy document của bạn cần chèn firewall này giữa khối lượng công việc (workload) của bạn và các RISE with SAP VPCs.

- Chia sẻ Core Network với tài khoản RISE with SAP bằng [AWS Resource Access Manager](https://aws.amazon.com/ram/) (AWS RAM). Kiểm tra documentation để hiểu cách bạn có thể chia sẻ tài nguyên thông qua AWS RAM.  
   Core Network là tài nguyên toàn cầu, do đó việc chia sẻ phải được thực hiện từ Region N. Virginia (us-east-1).

- Làm việc với nhóm RISE with SAP để chấp nhận Core Network invitation đã được chia sẻ. Nhóm RISE with SAP cần thực hiện các hành động sau:

  - Chấp nhận shared Core Network invitation.
  - Cấu hình các VPC attachments để kết nối với shared Core Network.
  - Thêm các private network routes cần thiết trong subnet route table để đảm bảo giao tiếp hai chiều liền mạch.

Thiết lập này cho phép chia sẻ mạng an toàn và đảm bảo kết nối giữa môi trường AWS account của người dùng và môi trường RISE with SAP. Các yếu tố cần xem xét bao gồm việc tránh trùng lặp CIDR blocks, giám sát chi phí truyền dữ liệu, thường xuyên kiểm tra quy tắc tường lửa (firewall rules), và sử dụng [AWS CloudTrail](https://aws.amazon.com/cloudtrail/) cho mục đích kiểm toán.

---

## Các thực tiễn tốt nhất khi triển khai AWS Cloud WAN cho RISE with SAP

Trong phần này, chúng ta tập trung vào các thực tiễn tốt nhất (best practices) khi tích hợp RISE with SAP với mạng của bạn dựa trên AWS Cloud WAN. Nội dung này bao gồm cả việc cấu hình policy document và các quy tắc tường lửa (firewall rules) cần được triển khai.

Chúng ta có thể xem xét một policy document hoàn chỉnh được triển khai phù hợp với kiến trúc được minh họa trong Hình 2. Chúng tôi sử dụng ví dụ này để làm nổi bật các thực tiễn tốt nhất quan trọng và các phần chính của policy document.

![alt text](<Streamlining RISE with SAP Connectivity using AWS Cloud WAN- Networking & Content Delivery/images/image4.png>)

_Hình 2. Ví dụ về kiến trúc AWS Cloud WAN có lớp kiểm tra lưu lượng (inspection layer) nằm giữa các khối lượng công việc (AWS workloads) và RISE with SAP._

```json
{
  "version": "2021.12",
  "core-network-configuration": {
    "vpn-ecmp-support": true,
    "asn-ranges": ["64496-64500"],
    "edge-locations": [
      {
        "location": "us-east-1",
        "asn": 64496
      },
      {
        "location": "eu-central-1",
        "asn": 64497
      }
    ]
  },
  "segments": [
    {
      "name": "vpcs",
      "require-attachment-acceptance": false
    },
    {
      "name": "saprise",
      "require-attachment-acceptance": true,
      "isolate-attachments": true
    }
  ],
  "network-function-groups": [
    {
      "name": "inspectionVpcs",
      "require-attachment-acceptance": true
    }
  ],
  "segment-actions": [
    {
      "action": "send-via",
      "segment": "vpcs",
      "mode": "dual-hop",
      "when-sent-to": {
        "segments": ["saprise"]
      },
      "via": {
        "network-function-groups": ["inspectionVpcs"]
      }
    }
  ],
  "attachment-policies": [
    {
      "rule-number": 100,
      "condition-logic": "and",
      "conditions": [
        {
          "type": "attachment-type",
          "operator": "equals",
          "value": "vpc"
        },
        {
          "type": "tag-exists",
          "key": "domain"
        }
      ],
      "action": {
        "association-method": "tag",
        "tag-value-of-key": "domain"
      }
    },
    {
      "rule-number": 200,
      "condition-logic": "and",
      "conditions": [
        {
          "type": "attachment-type",
          "operator": "equals",
          "value": "vpc"
        },
        {
          "type": "account-id",
          "operator": "equals",
          "value": "XXXXXXXXXXXX"
        }
      ],
      "action": {
        "association-method": "constant",
        "segment": "saprise"
      }
    },
    {
      "rule-number": 300,
      "condition-logic": "and",
      "conditions": [
        {
          "type": "tag-value",
          "operator": "equals",
          "key": "nfg",
          "value": "inspectionVpcs"
        }
      ],
      "action": {
        "add-to-network-function-group": "inspectionVpcs"
      }
    }
  ]
}
```

Trong các bước sau, chúng ta sẽ phân tích các thành phần chính và các thực tiễn tốt nhất:

### Định nghĩa phân đoạn mạng (Network segment definition)

Chúng tôi khuyến nghị sử dụng một segment riêng biệt dành cho các RISE with SAP VPCs. Cách tiếp cận này cho phép bạn duy trì khả năng kiểm soát định tuyến độc lập cho các VPC này và phần còn lại của môi trường. Trong trường hợp của segment "saprise", chúng tôi cấu hình tùy chọn isolate-attachments, để các attachments trong segment đó không thể giao tiếp với nhau theo mặc định.

```json
"segments": [
  {
    "name": "vpcs",
    "require-attachment-acceptance": false
  },
  {
    "name": "saprise",
    "require-attachment-acceptance": true,
    "isolate-attachments": true
  }
],
```

### Kiểm tra lưu lượng (Traffic inspection) và tính năng chèn dịch vụ của Cloud WAN

Sau khi thiết lập các phân đoạn mạng (network segments), hãy xem xét các khuyến nghị sau để tăng cường cấu hình Cloud WAN cho RISE with SAP:

- Triển khai lớp tường lửa (firewall layer) để bảo vệ lưu lượng giữa RISE with SAP VPCs và các workloads khác được kết nối qua Cloud WAN. Để thực hiện điều này, hãy tạo một [Network Function Group (NFG)](https://docs.aws.amazon.com/network-manager/latest/cloudwan/cloudwan-policy-service-insertion.html) để sử dụng chức năng service insertion.

```json
"network-function-groups": [
  {
    "name": "inspectionVpcs",
    "require-attachment-acceptance": true
  }
],
```

- Hành động định tuyến service insertion để kiểm tra lưu lượng giữa các phân đoạn được gọi là send-via. Trong ví dụ của chúng ta, tùy chọn dual-hop cho phép kiểm tra lưu lượng xuyên vùng (cross-Region) tại cả hai vùng AWS mà lưu lượng đi qua. Một tùy chọn khác là sử dụng single-hop, cho phép kiểm tra lưu lượng chỉ trong một vùng (bạn cũng có thể chọn vùng AWS nào sẽ được sử dụng). Bạn có thể truy cập [tài liệu AWS](https://docs.aws.amazon.com/network-manager/latest/cloudwan/cloudwan-policies-json.html#cloudwan-segment-actions-json) để tìm hiểu thêm về cách hoạt động của cơ chế này.

```json
"segment-actions": [
  {
    "action": "send-via",
    "segment": "vpcs",
    "mode": "dual-hop",
    "when-sent-to": {
      "segments": [
        "saprise"
      ]
    },
    "via": {
      "network-function-groups": [
        "inspectionVpcs"
      ]
    }
  }
],
```

### Cấu hình attachment policies

Các attachment mới trong Cloud WAN sẽ tự động được liên kết (associated) với một segment hoặc NFG bằng cách sử dụng [attachment-policies](https://docs.aws.amazon.com/network-manager/latest/cloudwan/cloudwan-policies-json.html#cloudwan-attach-policies-json) trong policy document. Từ các attachments, bạn có thể lấy metadata (chẳng hạn như tags, attachment type, AWS account, hoặc AWS Region) để xác định các policy chi tiết (granular policies) và chỉ định cách một attachment mới sẽ được gán vào segment trong mạng. Chúng ta có thể tập trung vào rule số 200 như một ví dụ để đi sâu vào khả năng này.

- Đối với RISE with SAP VPCs, khuyến nghị là sử dụng SAP Account ID làm metadata để tự động hóa quá trình liên kết attachment. Trong đoạn mã bên dưới, bạn nên thay thế phần giữ chỗ "XXXXXXXXXXXX" bằng Account ID thực tế.
- Ngoài ra, hãy sử dụng cờ require acceptance để thêm một lớp kiểm soát thủ công bổ sung khi tạo liên kết (association).

```json
{
  "rule-number": 200,
  "condition-logic": "and",
  "conditions": [
    {
      "type": "attachment-type",
      "operator": "equals",
      "value": "vpc"
    },
    {
      "type": "account-id",
      "operator": "equals",
      "value": "XXXXXXXXXXXX"
    }
  ],
  "action": {
    "association-method": "constant",
    "segment": "saprise"
  }
}
```

---

## Các lưu ý khác

### Cấu hình Firewall Rules

Khi cấu hình **firewall rules**, hãy xem xét các **port chuyên biệt của RISE with SAP** để cho phép lưu lượng từ các **workloads** của bạn đến **RISE with SAP VPC**. Để biết thêm chi tiết về những **firewall** có thể triển khai, hãy tham khảo bài viết [Securing SAP with AWS Network Firewall part-2 managed rules](https://aws.amazon.com/blogs/awsforsap/securing-sap-with-aws-network-firewall-part-2-managed-rules/).

- **RFC Connections (BAPI and IDoc):** Cổng 33xx (trong đó xx là số instance của bạn)
- **HTTPS cho OData và REST/SOAP:** Cổng 443, 44300
- **ODBC/JDBC cho SAP HANA connections:** Cổng 3xx15 (trong đó xx là số instance của bạn)
- **Một số cổng cần thiết khác:**
  - 44301–44302: Client và SAP AS connections
  - 3201–3202: Client và SAP AS connections
  - 8001–8002: Client và SAP AS connections
  - 3600: Nếu sử dụng load balancing với message server
  - 3299: SAProuter service
  - 3200–3299: SAP Connector
  - 3300–3399: SAPGUI

### Giám sát và Bảo trì

- Sử dụng AWS Network Manager để giám sát (monitor) và quản lý (manage) Core Network của bạn:

  - Thiết lập alerts cho các sự cố mạng và vi phạm policy
  - Cấu hình dashboards để quan sát tình trạng mạng
  - Kích hoạt logging cho việc xử lý sự cố và đảm bảo tuân thủ (compliance)

- Thực hiện các thủ tục bảo trì định kỳ (regular maintenance procedures) cho:
  - Kiểm tra định kỳ các firewall rules
  - Cập nhật cấu hình mạng
  - Thực hiện thay đổi configuration khi cần thiết

---

## Kết luận

**AWS Cloud WAN** cung cấp một phương pháp hợp lý hóa để kết nối môi trường của bạn với RISE with SAP trên AWS. Một mạng toàn cầu thống nhất với khả năng kiểm soát dựa trên chính sách nhất quán giúp bạn đơn giản hóa việc quản lý, tăng cường bảo mật thông qua kiểm tra lưu lượng (traffic inspection), và duy trì chiến lược mạng thống nhất trên toàn tổ chức.

Cấu hình này cho phép chia sẻ mạng an toàn và duy trì kết nối ổn định giữa tài khoản AWS của bạn và môi trường **RISE with SAP**, dù bạn đang sử dụng **Cloud WAN** hiện có hay thiết lập mới.

Để tìm hiểu thêm về **AWS Cloud WAN** và các tùy chọn kết nối **RISE with SAP**, hãy truy cập [AWS Cloud WAN documentation](https://docs.aws.amazon.com/network-manager/latest/cloudwan/what-is-cloudwan.html) và [RISE with SAP on AWS documentation](https://docs.aws.amazon.com/sap/latest/general/welcome.html).

---

## Về tác giả

**Pablo Sánchez Carmona**
![alt text](<Streamlining RISE with SAP Connectivity using AWS Cloud WAN- Networking & Content Delivery/images/image2.png>)
Pablo là Kiến trúc sư Giải pháp Chuyên gia Mạng cấp cao (Senior Network Specialist Solutions Architect) tại AWS, nơi anh hỗ trợ khách hàng thiết kế các hệ thống mạng an toàn, linh hoạt và tiết kiệm chi phí. Khi không nói về mạng (Networking), Pablo thường chơi bóng rổ hoặc trò chơi điện tử. Anh có bằng Thạc sĩ Khoa học ngành Kỹ thuật Điện (MSc in Electrical Engineering) từ Viện Công nghệ Hoàng gia Thụy Điển (KTH) và Thạc sĩ Kỹ thuật Viễn thông (Telecommunications Engineering) từ Đại học Bách khoa Catalonia (UPC).

**Kenny Rajan**
![alt text](<Streamlining RISE with SAP Connectivity using AWS Cloud WAN- Networking & Content Delivery/images/image5.png>)
Kenny là Kiến trúc sư Doanh nghiệp Cấp cao (Principal Enterprise Architect) tại AWS, chuyên về tích hợp Generative AI với các hệ thống doanh nghiệp và tiếp thị như SAP và Adobe. Anh giúp các tổ chức hiện đại hóa nền tảng trải nghiệm số, chuỗi cung ứng và hệ thống backend thông qua các giải pháp điện toán đám mây dựa trên dữ liệu và AI. Ngoài công việc, Kenny còn đóng góp cho giáo dục công nghệ và các hoạt động thiện nguyện.

**Rozal Singh**
![alt text](<Streamlining RISE with SAP Connectivity using AWS Cloud WAN- Networking & Content Delivery/images/image3.png>)
Rozal là Kiến trúc sư Giải pháp Cấp cao (Principal Solutions Architect) chuyên về SAP tại AWS. Với hơn 18 năm kinh nghiệm trong lĩnh vực SAP, anh có chuyên môn trong việc hướng dẫn khách hàng trong hành trình chuyển đổi lên đám mây, đặc biệt là trong quá trình di chuyển và tối ưu hóa hệ thống SAP trên AWS. Trong vai trò hiện tại, Rozal hợp tác với các khách hàng doanh nghiệp để phát triển và triển khai các chiến lược đám mây toàn diện, đảm bảo thành công cho các sáng kiến chuyển đổi số đồng thời tối đa hóa hiệu quả đầu tư vào công nghệ AWS và SAP. Sự cam kết với đổi mới và thành công của khách hàng đã giúp anh trở thành cố vấn đáng tin cậy trong lĩnh vực công nghệ doanh nghiệp.

---

**Nguồn bài viết gốc:** [AWS Networking & Content Delivery Blog](https://aws.amazon.com/blogs/networking-and-content-delivery/streamlining-rise-with-sap-connectivity-using-aws-cloud-wan/)
