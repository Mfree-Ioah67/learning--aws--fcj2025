---
title: "AWS Cloud Mastery Series #3 - Security Pillar"
date: 2025-11-29
weight: 5
chapter: false
pre: " <b> 4.5. </b> "
---

{{% notice warning %}}
⚠️ **Lưu ý:** Thông tin dưới đây chỉ mang tính chất tham khảo. Vui lòng **không sao chép nguyên văn** vào báo cáo của bạn, bao gồm cả cảnh báo này.
{{% /notice %}}

# Báo Cáo Tóm Tắt: "AWS Cloud Mastery Series #3 - Security Pillar"

### Mục Tiêu Sự Kiện

- Hiểu về các nguyên tắc cơ bản của AWS Well-Architected Security Pillar
- Học các best practices về Identity and Access Management (IAM)
- Khám phá các dịch vụ phát hiện và giám sát liên tục
- Nắm vững các chiến lược bảo vệ hạ tầng và mạng
- Hiểu về bảo vệ dữ liệu với mã hóa và quản lý khóa
- Học các quy trình ứng phó sự cố và tự động hóa

### Thông Tin Sự Kiện

- **Địa điểm**: Bitexco Financial Tower, Quận 1, Thành phố Hồ Chí Minh
- **Ngày & Giờ**: 8:30 sáng – 12:00 trưa, Thứ Bảy, ngày 29 tháng 11 năm 2025

### Diễn Giả & Điều Phối Viên

**Diễn giả:**

- **Lê Vũ Xuân An** – AWS Cloud Club Captain HCMUTE, First Cloud AI Journey
- **Trần Đức Anh** – AWS Cloud Club Captain SGU, First Cloud AI Journey
- **Trần Đoàn Công Lý** – AWS Cloud Club Captain PTIT, First Cloud AI Journey
- **Danh Hoàng Hiếu Nghị** – AWS Cloud Club Captain HUFLIT, First Cloud AI Journey

**Điều phối viên:**

- **AWS Cloud Club Vietnam**
- **First Cloud Journey Program Team**

### Chương Trình Sự Kiện

#### 8:30 – 8:50 sáng: Khai Mạc & Nền Tảng Bảo Mật

- Đăng ký và chào mừng
- Giới thiệu về AWS Well-Architected Framework
- **Tổng quan Security Pillar**:
  - Vai trò của Security Pillar trong Well-Architected Framework
  - Các nguyên tắc cốt lõi: Least Privilege, Zero Trust, Defense in Depth
  - **Shared Responsibility Model**: Hiểu trách nhiệm của AWS và khách hàng
  - Các mối đe dọa bảo mật hàng đầu trong môi trường cloud tại Việt Nam
- Thiết lập kỳ vọng cho buổi sáng

#### 8:50 – 9:30 sáng: Pillar 1 — Identity & Access Management

- **Kiến Thức Cơ Bản về IAM**:
  - **IAM Users**: Danh tính cá nhân cho người truy cập AWS
  - **IAM Groups**: Nhóm người dùng có quyền tương tự
  - **IAM Roles**: Thông tin xác thực tạm thời cho dịch vụ và ứng dụng
  - **IAM Policies**: Tài liệu JSON định nghĩa quyền
  - Tránh sử dụng thông tin xác thực và access keys dài hạn
- **Best Practices về IAM**:
  - **Nguyên tắc Least Privilege**: Chỉ cấp quyền cần thiết
  - **Multi-Factor Authentication (MFA)**: Thêm lớp bảo mật bổ sung
  - **Password Policies**: Thực thi mật khẩu mạnh
  - **Credential Rotation**: Cập nhật access keys thường xuyên
- **IAM Identity Center (AWS SSO)**:
  - Quản lý truy cập tập trung cho nhiều tài khoản AWS
  - Single Sign-On (SSO) để đơn giản hóa trải nghiệm người dùng
  - Permission sets cho kiểm soát truy cập nhất quán
- **Khái Niệm IAM Nâng Cao**:
  - **Service Control Policies (SCP)**: Ranh giới quyền toàn tổ chức
  - **Permission Boundaries**: Quyền tối đa cho các thực thể IAM
  - **IAM Access Analyzer**: Xác định truy cập không mong muốn vào tài nguyên
- **Mini Demo**: Xác thực IAM policies và mô phỏng các kịch bản truy cập

#### 9:30 – 9:55 sáng: Pillar 2 — Detection

- **AWS CloudTrail**:
  - **CloudTrail là gì**: Ghi lại các API calls và hoạt động người dùng
  - **Organization-level trails**: Logging tập trung trên các tài khoản
  - **Use cases**: Kiểm toán tuân thủ, phân tích bảo mật, khắc phục sự cố
  - **Log file integrity validation**: Đảm bảo logs không bị giả mạo
- **Amazon GuardDuty**:
  - **Phát hiện mối đe dọa thông minh**: Giám sát bảo mật được hỗ trợ bởi ML
  - **Các loại mối đe dọa**: Truy cập trái phép, instances bị xâm nhập, trinh sát
  - **Findings và severity levels**: Hiểu và ưu tiên cảnh báo
  - **Tích hợp với EventBridge**: Phản ứng tự động với mối đe dọa
- **AWS Security Hub**:
  - **Chế độ xem bảo mật tập trung**: Tổng hợp findings từ nhiều dịch vụ
  - **Security standards**: Kiểm tra tuân thủ CIS AWS Foundations, PCI DSS
  - **Automated compliance checks**: Giám sát liên tục tình trạng bảo mật
- **Logging ở Mọi Tầng**:
  - **VPC Flow Logs**: Giám sát lưu lượng mạng
  - **Application Load Balancer (ALB) logs**: Logging yêu cầu HTTP/HTTPS
  - **S3 access logs**: Theo dõi truy cập bucket
- **Cảnh Báo và Tự Động Hóa**:
  - **Amazon EventBridge**: Tự động hóa theo sự kiện
  - **Detection-as-Code**: Hạ tầng và quy tắc bảo mật dưới dạng code

#### 9:55 – 10:10 sáng: Giải Lao

- Giao lưu và giải khát
- Q&A với diễn giả

#### 10:10 – 10:40 sáng: Pillar 3 — Infrastructure Protection

- **Bảo Mật Mạng VPC**:
  - **VPC Segmentation**: Cô lập tài nguyên với subnets
  - **Public vs Private Subnets**: Khi nào sử dụng từng loại
  - **Internet Gateway và NAT Gateway**: Kiểm soát truy cập internet
  - **VPC Peering và Transit Gateway**: Kết nối VPCs một cách an toàn
- **Security Groups vs Network ACLs**:
  - **Security Groups**: Tường lửa stateful ở cấp instance
  - **Network ACLs**: Tường lửa stateless ở cấp subnet
  - **Best practices**: Khi nào sử dụng từng loại và cách kết hợp chúng
  - **Common patterns**: Phương pháp bảo mật nhiều lớp
- **AWS WAF (Web Application Firewall)**:
  - **Bảo vệ chống lại các lỗ hổng web phổ biến**: SQL injection, XSS
  - **Managed rules**: Bộ quy tắc được cấu hình sẵn
  - **Custom rules**: Bảo vệ tùy chỉnh cho ứng dụng của bạn
  - **Rate limiting**: Ngăn chặn tấn công DDoS
- **AWS Shield**:
  - **Shield Standard**: Bảo vệ DDoS tự động (miễn phí)
  - **Shield Advanced**: Bảo vệ DDoS nâng cao với hỗ trợ 24/7
- **AWS Network Firewall**:
  - **Stateful inspection**: Kiểm tra gói tin sâu
  - **Intrusion prevention**: Chặn lưu lượng độc hại
- **Cơ Bản về Bảo Vệ Workload**:
  - **EC2 security**: Hardening và patching instance
  - **ECS/EKS security**: Best practices bảo mật container

#### 10:40 – 11:10 sáng: Pillar 4 — Data Protection

- **AWS Key Management Service (KMS)**:
  - **KMS là gì**: Dịch vụ quản lý khóa mã hóa
  - **Customer Master Keys (CMKs)**: AWS-managed vs customer-managed
  - **Key policies**: Kiểm soát ai có thể sử dụng khóa
  - **Grants**: Quyền tạm thời để sử dụng khóa
  - **Automatic key rotation**: Tăng cường bảo mật theo thời gian
- **Mã Hóa Khi Lưu Trữ (Encryption at Rest)**:
  - **Amazon S3**: Server-side encryption (SSE-S3, SSE-KMS, SSE-C)
  - **Amazon EBS**: Volumes được mã hóa cho EC2 instances
  - **Amazon RDS**: Mã hóa database với KMS
  - **Amazon DynamoDB**: Mã hóa mặc định
- **Mã Hóa Khi Truyền Tải (Encryption in Transit)**:
  - **TLS/SSL**: Bảo mật dữ liệu đang di chuyển
  - **VPN connections**: Đường hầm được mã hóa đến AWS
  - **AWS Certificate Manager (ACM)**: Quản lý chứng chỉ SSL/TLS
- **Quản Lý Secrets**:
  - **AWS Secrets Manager**: Lưu trữ và xoay vòng secrets tự động
  - **AWS Systems Manager Parameter Store**: Lưu trữ cấu hình và secrets
  - **Rotation patterns**: Best practices cho xoay vòng thông tin xác thực
- **Phân Loại Dữ Liệu và Kiểm Soát Truy Cập**:
  - **Amazon Macie**: Phát hiện và bảo vệ dữ liệu nhạy cảm
  - **S3 bucket policies**: Kiểm soát truy cập chi tiết
  - **Access guardrails**: Ngăn chặn lộ dữ liệu vô tình

#### 11:10 – 11:40 sáng: Pillar 5 — Incident Response

- **Vòng Đời Ứng Phó Sự Cố**:
  - **Preparation**: Lập kế hoạch và công cụ
  - **Detection**: Xác định sự cố bảo mật
  - **Analysis**: Hiểu phạm vi và tác động
  - **Containment**: Hạn chế thiệt hại
  - **Eradication**: Loại bỏ mối đe dọa
  - **Recovery**: Khôi phục hoạt động bình thường
  - **Post-incident activity**: Học hỏi và cải thiện
- **Playbooks Sự Cố Phổ Biến**:
  - **IAM key bị xâm nhập**:
    - Vô hiệu hóa key ngay lập tức
    - Xem xét CloudTrail logs cho các hành động trái phép
    - Xoay vòng thông tin xác thực và thông báo các bên liên quan
  - **S3 bucket bị public**:
    - Xác định dữ liệu bị lộ
    - Loại bỏ truy cập public
    - Điều tra cách xảy ra lộ dữ liệu
    - Triển khai các biện pháp kiểm soát phòng ngừa
  - **EC2 instance phát hiện malware**:
    - Cô lập instance bị nhiễm
    - Tạo forensic snapshot
    - Phân tích hành vi malware
    - Xây dựng lại instance sạch
- **Thu Thập Bằng Chứng**:
  - **EBS snapshots**: Bảo toàn trạng thái đĩa để phân tích
  - **Memory dumps**: Capture trạng thái runtime
  - **Log preservation**: Đảm bảo logs không bị xóa
- **Ứng Phó Sự Cố Tự Động**:
  - **AWS Lambda**: Các hàm phản ứng serverless
  - **AWS Step Functions**: Điều phối workflows phản ứng phức tạp
  - **EventBridge integration**: Kích hoạt phản ứng tự động
  - **Example automation**: Tự động cô lập instances bị xâm nhập

#### 11:40 – 12:00 trưa: Tổng Kết & Q&A

- **Tóm Tắt 5 Security Pillars**:
  - Identity & Access Management
  - Detection
  - Infrastructure Protection
  - Data Protection
  - Incident Response
- **Các Lỗi Bảo Mật Phổ Biến**:
  - IAM policies quá rộng quyền
  - Thiếu giám sát và cảnh báo
  - Dữ liệu không được mã hóa
  - Không có kế hoạch ứng phó sự cố
- **Kịch Bản Thực Tế tại Doanh Nghiệp Việt Nam**:
  - Chiến lược multi-account cho tổ chức lớn
  - Yêu cầu tuân thủ (GDPR, quy định địa phương)
  - Triển khai bảo mật hiệu quả về chi phí
- **Lộ Trình Học Tập Bảo Mật**:
  - AWS Certified Cloud Practitioner (CLF-C02)
  - AWS Certified Solutions Architect Associate (SAA-C03)
  - AWS Certified Security Specialty
  - AWS Certified Solutions Architect Professional
- **Phiên Q&A Mở**: Thảo luận tương tác với tất cả diễn giả

### Những Điểm Chính Rút Ra

#### Nền Tảng Bảo Mật

- **Well-Architected Security Pillar**: Framework để xây dựng kiến trúc cloud an toàn
- **Shared Responsibility Model**: AWS bảo mật cloud, khách hàng bảo mật trong cloud
- **Các Nguyên Tắc Cốt Lõi**: Least Privilege, Zero Trust, Defense in Depth
- **Bảo mật là trách nhiệm của mọi người**: Không chỉ là công việc của team bảo mật

#### Identity & Access Management

- **IAM là nền tảng**: Cấu hình IAM đúng cách là quan trọng cho bảo mật
- **Tránh thông tin xác thực dài hạn**: Sử dụng roles và thông tin xác thực tạm thời khi có thể
- **MFA ở mọi nơi**: Bật MFA cho tất cả người dùng, đặc biệt là tài khoản có đặc quyền
- **Least Privilege**: Chỉ cấp quyền cần thiết để thực hiện công việc
- **IAM Identity Center**: Đơn giản hóa quản lý truy cập multi-account
- **Kiểm toán thường xuyên**: Sử dụng IAM Access Analyzer để xác định truy cập không mong muốn

#### Phát Hiện và Giám Sát

- **CloudTrail**: Thiết yếu cho audit trails và tuân thủ
- **GuardDuty**: Phát hiện mối đe dọa thông minh mà không cần quản lý hạ tầng
- **Security Hub**: Chế độ xem tập trung về tình trạng bảo mật trên các tài khoản
- **Logging là quan trọng**: Bật logging ở mọi tầng (VPC, ALB, S3, v.v.)
- **Tự động hóa phản ứng**: Sử dụng EventBridge để kích hoạt remediation tự động
- **Detection-as-Code**: Xử lý quy tắc bảo mật như infrastructure code

#### Bảo Vệ Hạ Tầng

- **Phân đoạn mạng**: Sử dụng VPCs và subnets để cô lập tài nguyên
- **Security Groups và NACLs**: Phương pháp bảo mật nhiều lớp
- **WAF cho web applications**: Bảo vệ chống lại các lỗ hổng phổ biến
- **Shield cho DDoS**: Bảo vệ tự động với Shield Standard
- **Private theo mặc định**: Đặt tài nguyên trong private subnets trừ khi cần truy cập internet
- **Workload hardening**: Giữ instances được patch và tuân theo best practices bảo mật

#### Bảo Vệ Dữ Liệu

- **Mã hóa ở mọi nơi**: Khi lưu trữ và khi truyền tải
- **KMS cho quản lý khóa**: Kiểm soát tập trung các khóa mã hóa
- **Secrets Manager**: Không bao giờ hardcode thông tin xác thực trong code
- **Xoay vòng tự động**: Xoay vòng khóa và secrets thường xuyên
- **Phân loại dữ liệu**: Biết bạn có dữ liệu gì và ở đâu
- **Kiểm soát truy cập**: Sử dụng bucket policies và IAM để kiểm soát truy cập dữ liệu

#### Ứng Phó Sự Cố

- **Có kế hoạch**: Chuẩn bị playbooks ứng phó sự cố trước khi sự cố xảy ra
- **Tự động hóa phản ứng**: Sử dụng Lambda và Step Functions cho các kịch bản phổ biến
- **Bảo toàn bằng chứng**: Chụp snapshots và bảo toàn logs để phân tích forensic
- **Cô lập nhanh chóng**: Ngăn chặn mối đe dọa để ngăn lan rộng
- **Học hỏi và cải thiện**: Tiến hành đánh giá sau sự cố để tăng cường phòng thủ
- **Thực hành thường xuyên**: Chạy các bài tập tabletop và mô phỏng

### Áp Dụng Vào Công Việc

- **Kiểm toán IAM policies**: Xem xét và thắt chặt quyền theo nguyên tắc least privilege
- **Bật CloudTrail**: Đảm bảo logging toàn tổ chức được bật
- **Bật GuardDuty**: Bắt đầu giám sát mối đe dọa ngay lập tức
- **Mã hóa dữ liệu**: Bật mã hóa cho S3, EBS, RDS và các dịch vụ khác
- **Sử dụng Secrets Manager**: Di chuyển thông tin xác thực hardcoded sang Secrets Manager
- **Tạo incident playbooks**: Tài liệu hóa quy trình phản ứng cho các kịch bản phổ biến
- **Triển khai MFA**: Yêu cầu MFA cho tất cả người dùng, đặc biệt là administrators
- **Đánh giá bảo mật thường xuyên**: Lên lịch đánh giá bảo mật định kỳ
- **Học cho chứng chỉ**: Hướng tới chứng chỉ AWS Security Specialty

### Trải Nghiệm Sự Kiện

Tham dự **"AWS Cloud Mastery Series #3 - Security Pillar"** là một buổi sáng học tập bổ ích cung cấp kiến thức nền tảng về các best practices bảo mật AWS phù hợp với Well-Architected Framework. Là người đang học các kiến thức cơ bản về AWS (cấp độ C01, C02, C03), sự kiện này được thiết kế hoàn hảo để xây dựng nền tảng bảo mật vững chắc. Các trải nghiệm chính bao gồm:

#### Học Hỏi từ AWS Cloud Club Captains

- **Các leader sinh viên** từ các trường đại học hàng đầu chia sẻ kiến thức bảo mật thực tế một cách dễ tiếp cận
- **Ví dụ thực tế** từ các doanh nghiệp Việt Nam giúp các khái niệm dễ hiểu và áp dụng được
- **Giải thích thân thiện với người mới bắt đầu** giúp làm sáng tỏ các chủ đề bảo mật phức tạp
- **Q&A tương tác** cho phép làm rõ các khái niệm cơ bản
- Diễn giả nhấn mạnh các best practices bảo mật liên quan đến các kỳ thi chứng chỉ

#### Hiểu Về Các Nguyên Tắc Bảo Mật Cơ Bản

- Hiểu rõ về **Shared Responsibility Model** và những gì khách hàng phải bảo mật
- Học được tầm quan trọng của nguyên tắc **Least Privilege** trong thiết kế IAM policy
- Hiểu cách **Defense in Depth** tạo ra nhiều lớp bảo mật
- Khám phá các mối đe dọa bảo mật phổ biến đối với các tổ chức tại Việt Nam
- Nhận ra rằng bảo mật không chỉ là kỹ thuật mà còn về quy trình và văn hóa

#### Best Practices về IAM

- Học được tại sao **access keys dài hạn có rủi ro** và cách tránh chúng
- Hiểu sự khác biệt giữa **IAM users, groups, roles và policies**
- Khám phá cách **MFA thêm bảo vệ quan trọng** cho tài khoản
- Tìm hiểu **IAM Identity Center** để quản lý truy cập multi-account
- Xem các ví dụ thực tế về **xác thực policy** và mô phỏng truy cập
- Hiểu **Service Control Policies** cho quản trị toàn tổ chức

#### Các Dịch Vụ Phát Hiện và Giám Sát

- Học cách **CloudTrail** ghi lại tất cả hoạt động API để kiểm toán và tuân thủ
- Khám phá khả năng phát hiện mối đe dọa thông minh của **GuardDuty**
- Hiểu **Security Hub** như một dashboard bảo mật tập trung
- Khám phá tầm quan trọng của **VPC Flow Logs** để giám sát mạng
- Học về **EventBridge** cho phản ứng bảo mật tự động
- Nhận ra rằng logging phải được bật ở mọi tầng của kiến trúc

#### Bảo Mật Mạng và Hạ Tầng

- Hiểu **VPC segmentation** và sự khác biệt giữa public và private subnets
- Học khi nào sử dụng **Security Groups vs Network ACLs**
- Khám phá **AWS WAF** để bảo vệ web applications khỏi các tấn công phổ biến
- Tìm hiểu **AWS Shield** cho bảo vệ DDoS
- Hiểu khái niệm **defense in depth** với các biện pháp kiểm soát bảo mật nhiều lớp
- Học các best practices bảo mật cơ bản cho **EC2 và container**

#### Các Yếu Tố Cơ Bản về Bảo Vệ Dữ Liệu

- Hiểu về **AWS KMS** và quản lý khóa mã hóa
- Học về **encryption at rest** cho S3, EBS, RDS và DynamoDB
- Hiểu **encryption in transit** với TLS/SSL
- Khám phá **Secrets Manager** để lưu trữ và xoay vòng thông tin xác thực an toàn
- Tìm hiểu **AWS Certificate Manager** để quản lý chứng chỉ SSL/TLS
- Học về **Amazon Macie** để phát hiện dữ liệu nhạy cảm

#### Chuẩn Bị Ứng Phó Sự Cố

- Hiểu **vòng đời ứng phó sự cố** từ phát hiện đến khôi phục
- Học các **playbooks** thực tế cho các sự cố bảo mật phổ biến:
  - Phản ứng với thông tin xác thực IAM bị xâm nhập
  - Xử lý S3 buckets bị lộ vô tình
  - Đối phó với EC2 instances bị nhiễm malware
- Khám phá cách **bảo toàn bằng chứng** với snapshots và logs
- Tìm hiểu **phản ứng tự động** sử dụng Lambda và Step Functions
- Nhận ra tầm quan trọng của **chuẩn bị và thực hành** trước khi sự cố xảy ra

#### Xây Dựng Mạng Lưới và Cộng Đồng

- Kết nối với những người học AWS và đam mê cloud khác
- Trao đổi kinh nghiệm về chuẩn bị chứng chỉ AWS
- Xây dựng mối quan hệ với các thành viên AWS Cloud Club để hỗ trợ liên tục
- Tham gia cộng đồng First Cloud Journey để học tập liên tục
- Khám phá tài nguyên học tập và tài liệu thực hành cho chứng chỉ AWS

#### Những Hiểu Biết Thực Tế cho Người Mới Bắt Đầu

- **Bảo mật là nền tảng**: Phải được xem xét từ ngày đầu tiên, không phải thêm vào sau
- **Bắt đầu với IAM**: Quản lý danh tính và truy cập đúng cách là tuyến phòng thủ đầu tiên
- **Bật logging sớm**: CloudTrail và GuardDuty nên được bật ngay lập tức
- **Mã hóa theo mặc định**: Các dịch vụ AWS hiện đại giúp việc bật mã hóa dễ dàng
- **Tự động hóa khi có thể**: Sử dụng managed services để giảm gánh nặng bảo mật
- **Tiếp tục học hỏi**: Bảo mật liên tục phát triển, giáo dục liên tục là cần thiết

#### Những Hiểu Biết về Chuẩn Bị Chứng Chỉ

- Nhiều chủ đề được đề cập phù hợp trực tiếp với **AWS Certified Cloud Practitioner (CLF-C02)**
- Các khái niệm bảo mật được kiểm tra nhiều trong **AWS Certified Solutions Architect Associate (SAA-C03)**
- Hiểu các kiến thức cơ bản này chuẩn bị cho **AWS Certified Security Specialty**
- Diễn giả chia sẻ mẹo để ghi nhớ các khái niệm chính cho kỳ thi
- Các kịch bản thực tế giúp củng cố kiến thức lý thuyết

#### Các Bước Tiếp Theo

- Xem xét **IAM best practices** và triển khai MFA trên tài khoản AWS cá nhân
- Bật **CloudTrail và GuardDuty** trong tài khoản thực hành
- Thực hành tạo **Security Groups và NACLs** với các quy tắc phù hợp
- Thử nghiệm với **mã hóa KMS** cho S3 và EBS
- Nghiên cứu **incident response playbooks** cho các kịch bản phổ biến
- Tiếp tục chuẩn bị cho **chứng chỉ AWS** với trọng tâm về bảo mật
- Tham gia các nhóm học tập **AWS Cloud Club** để học tập cộng tác
- Thực hành với **AWS Free Tier** để có kinh nghiệm thực tế

> Nhìn chung, buổi sáng này cung cấp một giới thiệu xuất sắc về các nguyên tắc cơ bản bảo mật AWS thông qua góc nhìn của Well-Architected Security Pillar. Nội dung hoàn toàn phù hợp với người mới bắt đầu học các kiến thức cơ bản về AWS, với các giải thích rõ ràng và ví dụ thực tế. Năm pillars—Identity & Access Management, Detection, Infrastructure Protection, Data Protection và Incident Response—cung cấp một framework toàn diện để suy nghĩ về bảo mật cloud. Điểm chính rút ra là bảo mật phải được xây dựng vào mọi tầng của kiến trúc cloud ngay từ đầu, và AWS cung cấp các công cụ và dịch vụ để làm điều này có thể đạt được ngay cả đối với những người mới bắt đầu hành trình cloud của họ.

### Hình Ảnh Sự Kiện

![AWS Cloud Mastery Series #3](images/1.jpg)

---

![AWS Cloud Mastery Series #3](images/2.jpg)

---

![AWS Cloud Mastery Series #3](images/3.jpg)

---

![AWS Cloud Mastery Series #3](images/4.jpg)

---

![AWS Cloud Mastery Series #3](images/5.jpg)

---

![AWS Cloud Mastery Series #3](images/6.jpg)
