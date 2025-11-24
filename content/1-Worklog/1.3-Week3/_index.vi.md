---
title: "Worklog Tuần 3"
date: 2025-09-22
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---

### Mục Tiêu Tuần 3:

- Nắm vững các dịch vụ AWS Compute với trọng tâm là kiến thức cơ bản về EC2
- Hiểu các loại instance EC2, tùy chọn lưu trữ và quản lý vòng đời
- Học các chiến lược AWS Backup và khái niệm khôi phục thảm họa
- Khám phá Storage Gateway cho giải pháp lưu trữ đám mây lai
- Triển khai website tĩnh sử dụng S3 và CloudFront

### Các nhiệm vụ cần thực hiện trong tuần này:

| Ngày | Nhiệm vụ | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
|------|----------|--------------|-----------------|-------------------|
| 1 | - Nghiên cứu Compute VM trên AWS <br>&emsp; + Các loại EC2 Instance và trường hợp sử dụng <br>&emsp; + Tổng quan Amazon Lightsail <br>&emsp; + Hệ thống file EFS/FSx <br>&emsp; + AWS MGN cho migration | 2025/09/22 | 2025/09/22 | <https://aws.amazon.com/ec2/instance-types/> |
| 2 | - Tìm hiểu sâu về các thành phần EC2: <br>&emsp; + Tạo và quản lý AMI <br>&emsp; + Chiến lược Backup <br>&emsp; + Xác thực Key Pair <br>&emsp; + Các loại Elastic Block Store (EBS) <br>&emsp; + Đặc điểm Instance Store | 2025/09/23 | 2025/09/23 | <https://docs.aws.amazon.com/ec2/> |
| 3 | - Học các tính năng nâng cao của EC2: <br>&emsp; + User Data cho bootstrapping <br>&emsp; + Dịch vụ Instance Metadata <br>&emsp; + Cấu hình EC2 Auto Scaling <br> - **Lab 13:** Triển khai AWS Backup <br>&emsp; + Tạo backup plans <br>&emsp; + Kiểm tra quy trình restore | 2025/09/24 | 2025/09/24 | <https://000013.awsstudygroup.com/> |
| 4 | - **Lab 24:** Triển khai Storage Gateway <br>&emsp; + Tạo S3 bucket <br>&emsp; + Triển khai EC2 cho Storage Gateway <br>&emsp; + Cấu hình File Gateway <br>&emsp; + Tạo File Shares | 2025/09/25 | 2025/09/25 | <https://000024.awsstudygroup.com/> |
| 5 | - **Lab 57:** Static Website Hosting <br>&emsp; + Tạo S3 bucket và load dữ liệu <br>&emsp; + Bật tính năng static website <br>&emsp; + Cấu hình public access <br>&emsp; + Kiểm tra chức năng website | 2025/09/26 | 2025/09/26 | <https://000057.awsstudygroup.com/> |
| 6 | - Tiếp tục Lab 57: <br>&emsp; + Chặn public access <br>&emsp; + Cấu hình CloudFront distribution <br>&emsp; + Bật bucket versioning <br>&emsp; + Cấu hình cross-region replication | 2025/09/27 | 2025/09/27 | <https://000057.awsstudygroup.com/> |
| 7 | - Ôn tập tuần và dọn dẹp <br> - Hoàn thành cleanup tất cả tài nguyên lab <br> - Ghi chép kiến thức và best practices | 2025/09/28 | 2025/09/28 | |

### Thành Tựu Tuần 3:

- **Thành Thạo EC2:**
  - Hiểu các loại instance khác nhau: General Purpose (T3, M5), Compute Optimized (C5), Memory Optimized (R5)
  - Học vòng đời instance: Launch, Stop, Terminate, Hibernate
  - Cấu hình User Data scripts cho thiết lập instance tự động
  - Truy cập Instance Metadata cho cấu hình động

- **Giải Pháp Lưu Trữ:**
  - So sánh các loại EBS volume: gp3, io2, st1, sc1
  - Hiểu sự đánh đổi giữa Instance Store và EBS
  - Tạo và quản lý AMIs cho backup và replication
  - Triển khai EBS snapshots và lifecycle policies

- **Triển Khai AWS Backup (Lab 13):**
  - Triển khai hạ tầng với EC2 và RDS instances
  - Tạo backup plans với retention policies
  - Kiểm tra thành công quy trình restore
  - Xác minh backup compliance và recovery time objectives

- **Cấu Hình Storage Gateway (Lab 24):**
  - Triển khai File Gateway trên EC2 instance
  - Kết nối ứng dụng on-premises với S3 qua NFS/SMB
  - Cấu hình file shares với quyền phù hợp
  - Kiểm tra quy trình lưu trữ đám mây lai

- **Static Website Hosting (Lab 57):**
  - Cấu hình S3 bucket cho static website hosting
  - Triển khai CloudFront cho phân phối nội dung toàn cầu
  - Bật versioning cho khả năng rollback nội dung
  - Thiết lập cross-region replication cho disaster recovery
  - Tối ưu chi phí bằng cách chặn S3 public access trực tiếp

- **Auto Scaling:**
  - Cấu hình Launch Templates với AMI và instance settings phù hợp
  - Tạo Auto Scaling Groups với min/max/desired capacity
  - Thiết lập scaling policies dựa trên CloudWatch metrics
  - Kiểm tra hành vi scale-out và scale-in

### Thách Thức Gặp Phải:

- **Lựa Chọn Loại Instance:** Nhầm lẫn giữa T3 và T3a instances → Học được T3a sử dụng bộ xử lý AMD với chi phí thấp hơn
- **Thực Thi User Data:** Script không chạy khi khởi động lần đầu → Thêm shebang đúng (`#!/bin/bash`) và kiểm tra logs trong `/var/log/cloud-init-output.log`
- **Thời Gian Restore Backup:** RDS restore mất nhiều thời gian hơn dự kiến → Hiểu rằng database lớn hơn cần nhiều thời gian hơn để khôi phục
- **Kích Hoạt Storage Gateway:** Gateway không kích hoạt được → Đảm bảo security group rules đúng cho ports 80, 443, 1026-1028, 2049
- **Propagation CloudFront:** Distribution mất 15-20 phút để deploy → Học được đây là bình thường cho cập nhật edge location toàn cầu
- **Chi Phí S3 Versioning:** Nhận thấy chi phí lưu trữ tăng → Triển khai lifecycle policies để xóa phiên bản cũ sau 30 ngày
- **Độ Trễ Auto Scaling:** Instances mất thời gian để trở nên healthy → Điều chỉnh health check grace period lên 300 giây

### Tài Liệu Tham Khảo:

**Tài Liệu Chính Thức AWS:**
- [Amazon EC2 Instance Types](https://aws.amazon.com/ec2/instance-types/) - So sánh đầy đủ các loại instance
- [Amazon EC2 User Guide](https://docs.aws.amazon.com/ec2/) - Tài liệu EC2 toàn diện
- [Amazon EBS Volume Types](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-volume-types.html) - Hướng dẫn hiệu suất lưu trữ
- [AWS Backup Documentation](https://docs.aws.amazon.com/aws-backup/) - Hướng dẫn backup và restore
- [AWS Storage Gateway](https://docs.aws.amazon.com/storagegateway/) - Giải pháp lưu trữ lai
- [Amazon S3 Static Website Hosting](https://docs.aws.amazon.com/AmazonS3/latest/userguide/WebsiteHosting.html) - Hướng dẫn hosting website
- [Amazon CloudFront](https://docs.aws.amazon.com/cloudfront/) - Tài liệu CDN
- [EC2 Auto Scaling](https://docs.aws.amazon.com/autoscaling/ec2/) - Hướng dẫn Auto Scaling

**AWS Workshops & Labs:**
- [AWS Backup Workshop](https://000013.awsstudygroup.com/) - Lab 13: Triển khai AWS Backup
- [Storage Gateway Workshop](https://000024.awsstudygroup.com/) - Lab 24: Triển khai File Gateway
- [S3 Static Website Workshop](https://000057.awsstudygroup.com/) - Lab 57: Static website với CloudFront

**Bài Viết Kỹ Thuật:**
- [EC2 Instance Metadata](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-instance-metadata.html) - Hướng dẫn dịch vụ Metadata
- [User Data and Shell Scripts](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/user-data.html) - Tự động hóa Bootstrap
- [EBS vs Instance Store](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/Storage.html) - So sánh lưu trữ
- [S3 Versioning Best Practices](https://docs.aws.amazon.com/AmazonS3/latest/userguide/Versioning.html) - Hướng dẫn kiểm soát phiên bản
- [CloudFront Best Practices](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/best-practices.html) - Tối ưu CDN
- [Auto Scaling Best Practices](https://docs.aws.amazon.com/autoscaling/ec2/userguide/as-best-practices.html) - Chiến lược Scaling

**Tài Nguyên Chứng Chỉ AWS:**
- [AWS Certified Cloud Practitioner (CLF-C01)](https://aws.amazon.com/certification/certified-cloud-practitioner/) - Chứng chỉ nền tảng
- [AWS Certified Solutions Architect Associate (SAA-C03)](https://aws.amazon.com/certification/certified-solutions-architect-associate/) - Chứng chỉ cấp Associate
- [EC2 for SAA-C03](https://explore.skillbuilder.aws/learn/course/external/view/elearning/125/exam-readiness-aws-certified-solutions-architect-associate) - Khóa học chuẩn bị thi
