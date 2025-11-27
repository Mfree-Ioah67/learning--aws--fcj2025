---
title: "Workshop DevOps trên AWS"
date: 2025-11-17
weight: 4
chapter: false
pre: " <b> 4.4. </b> "
---

{{% notice warning %}}
⚠️ **Lưu ý:** Thông tin dưới đây chỉ mang tính chất tham khảo. Vui lòng **không sao chép nguyên văn** vào báo cáo của bạn, bao gồm cả cảnh báo này.
{{% /notice %}}

# Báo Cáo Tóm Tắt: "Workshop DevOps trên AWS"

### Mục Tiêu Sự Kiện

- Hiểu về văn hóa, nguyên tắc và thực hành tốt nhất của DevOps
- Học các dịch vụ AWS DevOps để tự động hóa CI/CD
- Khám phá Infrastructure as Code với CloudFormation và CDK
- Làm chủ các dịch vụ container: ECR, ECS, EKS và App Runner
- Triển khai giám sát và khả năng quan sát với CloudWatch và X-Ray
- Áp dụng các thực hành DevOps vào các tình huống thực tế

### Thông Tin Sự Kiện

- **Địa điểm**: Văn phòng AWS Việt Nam
- **Ngày & Giờ**: 8:30 sáng – 5:00 chiều, Thứ Hai, ngày 17 tháng 11 năm 2025

### Diễn Giả & Điều Phối Viên

**Giảng viên:**

- **Trương Quang Tính** – AWS Community Builder – Văn hóa DevOps và Cơ bản về CI/CD
- **Văn Hoàng Kha** – AWS Community Builder – Infrastructure as Code với CloudFormation
- **Nguyễn Khánh Phúc Thịnh** – AWS Community Builder – Tìm hiểu sâu về AWS CDK
- **Lê Huỳnh Nghiêm** – AWS Community Builder – Các dịch vụ Container trên AWS
- **Huỳnh Hoàng Long** – AWS Community Builder – Giám sát và Khả năng quan sát
- **Phạm Hoàng Quý** – AWS Community Builder – Thực hành tốt nhất DevOps và Nghiên cứu điển hình

**Điều phối viên:**

- **Đội ngũ AWS Việt Nam**
- **AWS Community Builders Việt Nam**

### Chương Trình Sự Kiện

#### 8:30 sáng - 9:00 sáng: Đăng ký và Chào mừng

- Đăng ký và giao lưu
- Phát biểu chào mừng và tổng quan về workshop
- Giới thiệu về các dịch vụ AWS DevOps

#### 9:00 sáng - 10:30 sáng: Văn hóa DevOps và CI/CD Pipeline

**Trình bày bởi Trương Quang Tính**

- **Tư duy DevOps**: Hiểu về sự chuyển đổi văn hóa từ phát triển truyền thống sang DevOps
  - **Cộng tác**: Phá vỡ rào cản giữa đội Development và Operations
  - **Tự động hóa**: Tự động hóa các tác vụ lặp đi lặp lại để tăng hiệu quả
  - **Cải tiến liên tục**: Chấp nhận vòng phản hồi và phát triển lặp đi lặp lại
  - **Trách nhiệm chung**: Mọi người đều sở hữu chất lượng, bảo mật và độ tin cậy
- **Chỉ số DORA**: Đo lường thành công DevOps với các chỉ số tiêu chuẩn ngành
  - **Tần suất Triển khai**: Tần suất mã được triển khai lên production
  - **Thời gian Dẫn đầu cho Thay đổi**: Thời gian từ commit đến triển khai production
  - **Thời gian Trung bình để Phục hồi (MTTR)**: Hệ thống phục hồi nhanh như thế nào sau sự cố
  - **Tỷ lệ Thất bại Thay đổi**: Phần trăm triển khai gây ra vấn đề production
- **Các thành phần CI/CD Pipeline**:
  - **AWS CodeCommit**: Lưu trữ kho Git an toàn, có khả năng mở rộng
  - **AWS CodeBuild**: Dịch vụ build được quản lý hoàn toàn, biên dịch mã và chạy test
  - **AWS CodeDeploy**: Triển khai tự động lên EC2, Lambda, ECS và máy chủ on-premises
  - **AWS CodePipeline**: Dịch vụ điều phối tự động hóa toàn bộ quy trình phát hành
- **Chiến lược Triển khai**:
  - **Blue/Green Deployment**: Giảm thiểu thời gian ngừng hoạt động bằng cách chuyển đổi lưu lượng giữa các môi trường
  - **Canary Deployment**: Dần dần triển khai thay đổi cho một tập hợp con người dùng
  - **Rolling Deployment**: Cập nhật các instance dần dần để duy trì tính khả dụng
- **Demo Trực tiếp**: Xây dựng một CI/CD pipeline hoàn chỉnh từ đầu

#### 10:30 sáng - 10:45 sáng: Giải lao

- Giao lưu và giải khát

#### 10:45 sáng - 12:00 trưa: Infrastructure as Code với CloudFormation

**Trình bày bởi Văn Hoàng Kha**

- **Nguyên tắc Infrastructure as Code (IaC)**:
  - **Kiểm soát Phiên bản**: Theo dõi thay đổi cơ sở hạ tầng như mã ứng dụng
  - **Khả năng Lặp lại**: Triển khai các môi trường giống hệt nhau một cách nhất quán
  - **Tài liệu**: Mã cơ sở hạ tầng phục vụ như tài liệu sống
  - **Kiểm thử**: Xác thực cơ sở hạ tầng trước khi triển khai
- **Cơ bản về AWS CloudFormation**:
  - **Templates**: Các file JSON hoặc YAML định nghĩa tài nguyên AWS
  - **Stacks**: Tập hợp các tài nguyên AWS được quản lý như một đơn vị duy nhất
  - **Change Sets**: Xem trước thay đổi trước khi áp dụng
  - **Drift Detection**: Xác định thay đổi thủ công đối với tài nguyên stack
- **Thực hành tốt nhất CloudFormation**:
  - **Templates Mô-đun**: Sử dụng nested stacks để tái sử dụng
  - **Parameters**: Làm cho templates linh hoạt với các tham số đầu vào
  - **Outputs**: Xuất giá trị để sử dụng trong các stacks khác
  - **Cross-Stack References**: Chia sẻ tài nguyên giữa các stacks
- **Tính năng Nâng cao**:
  - **Stack Policies**: Bảo vệ tài nguyên quan trọng khỏi cập nhật
  - **Rollback Triggers**: Tự động rollback khi có CloudWatch alarms
  - **StackSets**: Triển khai stacks trên nhiều tài khoản và vùng
- **Demo Trực tiếp**: Triển khai ứng dụng đa tầng với CloudFormation

#### 12:00 trưa - 1:00 chiều: Giải lao trưa

- Ăn trưa và giao lưu

#### 1:00 chiều - 2:15 chiều: Tìm hiểu sâu về AWS CDK

**Trình bày bởi Nguyễn Khánh Phúc Thịnh**

- **Giới thiệu về AWS CDK**:
  - **CDK là gì**: Cloud Development Kit để định nghĩa cơ sở hạ tầng bằng mã
  - **Lợi ích**: Sử dụng các ngôn ngữ lập trình quen thuộc (TypeScript, Python, Java, C#, Go)
  - **Mức độ Trừu tượng**: L1 (tài nguyên CloudFormation), L2 (constructs được tuyển chọn), L3 (patterns)
- **Khái niệm Cốt lõi CDK**:
  - **Constructs**: Các thành phần cloud có thể tái sử dụng
  - **Stacks**: Đơn vị triển khai chứa constructs
  - **Apps**: Tập hợp các stacks
  - **Synthesis**: Chuyển đổi mã CDK thành templates CloudFormation
- **CDK vs CloudFormation**:
  - **Lập trình**: Sử dụng vòng lặp, điều kiện và hàm
  - **Type Safety**: Phát hiện lỗi tại thời điểm biên dịch
  - **Hỗ trợ IDE**: Tự động hoàn thành và tài liệu inline
  - **Testing**: Unit test mã cơ sở hạ tầng
- **Thực hành tốt nhất CDK**:
  - **Construct Libraries**: Tận dụng các patterns được xây dựng sẵn
  - **Environment Agnostic**: Viết mã hoạt động trên các môi trường
  - **Logical IDs**: Định danh ổn định cho tài nguyên
  - **Context Values**: Cấu hình cụ thể cho môi trường
- **Demo Trực tiếp**: Xây dựng ứng dụng serverless với CDK

#### 2:15 chiều - 2:30 chiều: Giải lao

- Giao lưu và giải khát

#### 2:30 chiều - 3:45 chiều: Các dịch vụ Container trên AWS

**Trình bày bởi Lê Huỳnh Nghiêm**

- **Cơ bản về Container**:
  - **Container là gì**: Các gói ứng dụng nhẹ, di động
  - **Lợi ích**: Tính nhất quán, tính di động, hiệu quả, khả năng mở rộng
  - **Cơ bản về Docker**: Images, containers, registries
- **Amazon Elastic Container Registry (ECR)**:
  - **Private Registry**: Lưu trữ an toàn cho container images
  - **Image Scanning**: Phát hiện lỗ hổng tự động
  - **Lifecycle Policies**: Tự động dọn dẹp images cũ
  - **Cross-Region Replication**: Phân phối images toàn cầu
- **Amazon Elastic Container Service (ECS)**:
  - **Điều phối AWS-Native**: Quản lý container đơn giản, tích hợp
  - **Task Definitions**: Bản thiết kế để chạy containers
  - **Services**: Duy trì số lượng tasks mong muốn
  - **Fargate**: Serverless compute cho containers
  - **EC2 Launch Type**: Kiểm soát nhiều hơn đối với cơ sở hạ tầng
- **Amazon Elastic Kubernetes Service (EKS)**:
  - **Managed Kubernetes**: Chạy Kubernetes mà không cần quản lý control plane
  - **Tương thích**: APIs và công cụ Kubernetes tiêu chuẩn
  - **Linh hoạt**: Hỗ trợ nhu cầu điều phối phức tạp
  - **Add-ons**: Các dịch vụ AWS tích hợp (ALB, EBS, EFS)
- **AWS App Runner**:
  - **Tùy chọn Đơn giản nhất**: Từ mã nguồn đến dịch vụ đang chạy
  - **Automatic Scaling**: Mở rộng dựa trên lưu lượng
  - **Built-in CI/CD**: Triển khai từ kho mã nguồn
  - **Use Cases**: Ứng dụng web, APIs, microservices
- **Chọn Dịch vụ Phù hợp**:
  - **ECS**: AWS-native, đơn giản, tích hợp
  - **EKS**: Chuyên môn Kubernetes, điều phối phức tạp
  - **App Runner**: Thời gian triển khai nhanh nhất, cấu hình tối thiểu
- **Demo Trực tiếp**: Triển khai ứng dụng container hóa lên ECS và EKS

#### 3:45 chiều - 4:45 chiều: Giám sát và Khả năng quan sát

**Trình bày bởi Huỳnh Hoàng Long**

- **Khả năng quan sát vs Giám sát**:
  - **Monitoring**: Thu thập và hiển thị metrics
  - **Observability**: Hiểu hành vi hệ thống từ đầu ra
  - **Ba Trụ cột**: Logs, metrics, traces
- **Amazon CloudWatch**:
  - **Metrics**: Thu thập và theo dõi các chỉ số hiệu suất chính
  - **Logs**: Quản lý và phân tích log tập trung
  - **Alarms**: Thông báo và hành động tự động
  - **Dashboards**: Trực quan hóa metrics và logs
  - **Insights**: Truy vấn và phân tích dữ liệu log
  - **Events**: Phản ứng với thay đổi trong tài nguyên AWS
- **AWS X-Ray**:
  - **Distributed Tracing**: Theo dõi yêu cầu qua microservices
  - **Service Map**: Trực quan hóa kiến trúc ứng dụng
  - **Trace Analysis**: Xác định điểm nghẽn hiệu suất
  - **Error Analysis**: Debug và khắc phục sự cố
  - **Integration**: Hoạt động với Lambda, ECS, EKS, API Gateway
- **Thực hành tốt nhất**:
  - **Structured Logging**: Sử dụng định dạng log nhất quán
  - **Custom Metrics**: Theo dõi KPIs cụ thể cho doanh nghiệp
  - **Proactive Monitoring**: Đặt alarms trước khi vấn đề ảnh hưởng người dùng
  - **Correlation**: Liên kết logs, metrics và traces
  - **Retention Policies**: Cân bằng chi phí và tuân thủ
- **Demo Trực tiếp**: Thiết lập giám sát toàn diện cho ứng dụng microservices

#### 4:45 chiều - 5:00 chiều: Thực hành tốt nhất DevOps và Hỏi đáp

**Trình bày bởi Phạm Hoàng Quý**

- **Thực hành tốt nhất DevOps**:
  - **Tự động hóa Mọi thứ**: Từ testing đến deployment đến monitoring
  - **Thất bại Nhanh, Học Nhanh hơn**: Chấp nhận thất bại như cơ hội học hỏi
  - **Blameless Postmortems**: Tập trung vào hệ thống, không phải cá nhân
  - **Progressive Delivery**: Sử dụng feature flags và canary deployments
  - **Continuous Learning**: DevOps là một hành trình liên tục
- **Nghiên cứu Điển hình Thực tế**:
  - **Startup**: Lặp lại nhanh với CI/CD và serverless
  - **Enterprise**: Chiến lược đa tài khoản với StackSets
  - **E-commerce**: Tính khả dụng cao với blue/green deployments
- **Phiên Hỏi đáp**: Thảo luận tương tác với người tham dự

### Điểm Chính Rút Ra

#### Văn hóa và Tư duy DevOps

- **Cộng tác**: DevOps phá vỡ rào cản giữa các đội
- **Tự động hóa**: Tự động hóa các tác vụ lặp đi lặp lại để tập trung vào giá trị
- **Đo lường**: Sử dụng chỉ số DORA để theo dõi tiến độ
- **Cải tiến Liên tục**: Luôn lặp lại và tối ưu hóa
- **Trách nhiệm Chung**: Mọi người đều sở hữu chất lượng và độ tin cậy

#### Tự động hóa CI/CD Pipeline

- **CodeCommit**: Kho Git an toàn cho kiểm soát mã nguồn
- **CodeBuild**: Thực thi build và test tự động
- **CodeDeploy**: Triển khai đáng tin cậy với nhiều chiến lược
- **CodePipeline**: Điều phối toàn bộ quy trình CI/CD
- **Integration**: Hoạt động liền mạch với các dịch vụ AWS và công cụ bên thứ ba

#### Infrastructure as Code

- **CloudFormation**: IaC khai báo với templates JSON/YAML
- **CDK**: IaC lập trình với các ngôn ngữ lập trình quen thuộc
- **Lợi ích**: Kiểm soát phiên bản, khả năng lặp lại và tính nhất quán
- **Drift detection**: Xác định và khắc phục thay đổi thủ công
- **Chọn khôn ngoan**: Chọn công cụ IaC dựa trên kỹ năng đội và yêu cầu

#### Các dịch vụ Container

- **ECR**: Lưu trữ container image an toàn với scanning
- **ECS**: Điều phối container AWS-native, đơn giản và tích hợp
- **EKS**: Kubernetes trên AWS cho nhu cầu điều phối phức tạp
- **App Runner**: Tùy chọn đơn giản nhất cho ứng dụng web container hóa
- **Công cụ phù hợp cho công việc**: Chọn dựa trên độ phức tạp và yêu cầu

#### Giám sát và Khả năng quan sát

- **CloudWatch**: Giám sát toàn diện cho tài nguyên AWS
- **X-Ray**: Distributed tracing để debug microservices
- **Observability**: Hiểu hành vi hệ thống từ đầu ra
- **Proactive monitoring**: Phát hiện vấn đề trước khi ảnh hưởng người dùng
- **Data-driven decisions**: Sử dụng metrics và traces để tối ưu hóa hiệu suất

#### Thực hành tốt nhất DevOps

- **Tự động hóa mọi thứ**: Từ testing đến deployment đến monitoring
- **Thất bại nhanh, học nhanh hơn**: Chấp nhận thất bại như cơ hội học hỏi
- **Blameless postmortems**: Tập trung vào hệ thống, không phải cá nhân
- **Progressive delivery**: Sử dụng feature flags và canary deployments
- **Continuous learning**: DevOps là một hành trình liên tục

### Áp Dụng Vào Công Việc

- **Triển khai CI/CD**: Bắt đầu với CodePipeline cho triển khai tự động
- **Áp dụng IaC**: Sử dụng CloudFormation hoặc CDK để quản lý cơ sở hạ tầng
- **Container hóa ứng dụng**: Di chuyển sang ECS hoặc EKS để mở rộng
- **Nâng cao giám sát**: Thiết lập CloudWatch dashboards và X-Ray tracing
- **Thực hành văn hóa DevOps**: Thúc đẩy cộng tác giữa các đội
- **Đo lường và cải thiện**: Theo dõi chỉ số DORA và tối ưu hóa quy trình
- **Theo đuổi chứng chỉ**: Chứng chỉ AWS DevOps Engineer xác thực kỹ năng

### Trải Nghiệm Sự Kiện

Tham dự **"Workshop DevOps trên AWS"** là một trải nghiệm học tập chuyên sâu cả ngày cung cấp phạm vi bao quát toàn diện về các thực hành DevOps và dịch vụ AWS. Các trải nghiệm chính bao gồm:

#### Học Hỏi Từ Các Chuyên Gia AWS

- **Các Chuyên gia DevOps AWS** cung cấp những hiểu biết sâu sắc về các thực hành tốt nhất CI/CD và chiến lược tự động hóa
- **Các Kiến trúc sư Giải pháp AWS** trình diễn triển khai container thực tế và thiết lập giám sát
- Các ví dụ thực tế minh họa cách các công ty triển khai thành công DevOps trên AWS
- Hướng dẫn chuyên gia về việc chọn công cụ và dịch vụ phù hợp cho các trường hợp sử dụng cụ thể

#### Trình Diễn Thực Hành

- Chứng kiến tạo **CI/CD pipeline** hoàn chỉnh từ đầu
- Thấy **Infrastructure as Code** hoạt động với cả CloudFormation và CDK
- Khám phá **triển khai container** trên ECS, EKS và App Runner
- Học thiết lập **giám sát và tracing** cho hệ thống production
- Hiểu sự khác biệt giữa các chiến lược triển khai khác nhau

#### Hiểu Biết Về Thực Hành DevOps

- Có được hiểu biết về **văn hóa DevOps** vượt ra ngoài công cụ và tự động hóa
- Học về **chỉ số DORA** và cách đo lường thành công DevOps
- Hiểu tầm quan trọng của **khả năng quan sát** trong các hệ thống hiện đại
- Khám phá **thực hành tốt nhất** từ các nghiên cứu điển hình thực tế
- Khám phá **quản lý sự cố** và quy trình blameless postmortem

#### Giao Lưu và Xây Dựng Cộng Đồng

- Kết nối với các nhà phát triển đồng nghiệp và kỹ sư DevOps
- Trao đổi ý tưởng về các thách thức chuyển đổi DevOps
- Xây dựng mối quan hệ với các chuyên gia AWS để được hỗ trợ liên tục
- Tham gia cộng đồng AWS DevOps để học hỏi liên tục

#### Hiểu Biết Thực Tế Thu Được

- **Tự động hóa CI/CD** giảm đáng kể thời gian triển khai và lỗi
- **Infrastructure as Code** đảm bảo tính nhất quán và khả năng lặp lại
- **Containers** cung cấp tính linh hoạt và tính di động cho ứng dụng
- **Giám sát và khả năng quan sát** rất quan trọng cho hệ thống production
- **Văn hóa DevOps** quan trọng như các công cụ và công nghệ

#### Các Bước Tiếp Theo

- Bắt đầu triển khai **CI/CD pipelines** sử dụng AWS CodePipeline
- Áp dụng **Infrastructure as Code** với CloudFormation hoặc CDK
- Container hóa ứng dụng và triển khai lên **ECS hoặc EKS**
- Thiết lập **giám sát** toàn diện với CloudWatch và X-Ray
- Hướng tới **chứng chỉ AWS DevOps Engineer**
- Tiếp tục tham gia với **cộng đồng AWS DevOps**

> Nhìn chung, workshop cả ngày này cung cấp một giới thiệu toàn diện về DevOps trên AWS, bao gồm mọi thứ từ CI/CD pipelines đến các dịch vụ container đến giám sát và khả năng quan sát. Các trình diễn thực hành và nghiên cứu điển hình thực tế làm cho các khái niệm phức tạp trở nên dễ tiếp cận và có thể áp dụng ngay lập tức. Điểm chính rút ra là DevOps không chỉ là về công cụ, mà là về văn hóa, cộng tác và cải tiến liên tục. AWS cung cấp một hệ sinh thái hoàn chỉnh để triển khai các thực hành DevOps, làm cho việc xây dựng, triển khai và vận hành ứng dụng ở quy mô lớn trở nên dễ dàng hơn bao giờ hết.

### Một Số Hình Ảnh Sự Kiện

![Workshop DevOps](images/1.jpg)

---

![Workshop DevOps](images/2.jpg)

---

![Workshop DevOps](images/3.jpg)

---

![Workshop DevOps](images/4.jpg)

---

![Workshop DevOps](images/5.jpg)

---

![Workshop DevOps](images/6.jpg)

---

![Workshop DevOps](images/7.jpg)

---

![Workshop DevOps](images/8.jpg)

---

![Workshop DevOps](images/9.jpg)

---

![Workshop DevOps](images/10.jpg)

---

![Workshop DevOps](images/11.jpg)

---

![Workshop DevOps](images/12.jpg)

---

![Workshop DevOps](images/13.jpg)

---

![Workshop DevOps](images/14.jpg)

---

![Workshop DevOps](images/15.jpg)

---

![Workshop DevOps](images/16.jpg)

---

![Workshop DevOps](images/17.jpg)

---

![Workshop DevOps](images/18.jpg)

---

![Workshop DevOps](images/19.jpg)

---

![Workshop DevOps](images/20.jpg)

---

![Workshop DevOps](images/21.jpg)

---

![Workshop DevOps](images/22.jpg)

---

![Workshop DevOps](images/23.jpg)

---

![Workshop DevOps](images/24.jpg)

---

![Workshop DevOps](images/25.jpg)

---

![Workshop DevOps](images/26.jpg)

---

![Workshop DevOps](images/27.jpg)

---

![Workshop DevOps](images/28.jpg)

---

![Workshop DevOps](images/30.jpg)

---

![Workshop DevOps](images/31.jpg)

---

![Workshop DevOps](images/32.jpg)

---

![Workshop DevOps](images/33.jpg)

---

![Workshop DevOps](images/34.jpg)
