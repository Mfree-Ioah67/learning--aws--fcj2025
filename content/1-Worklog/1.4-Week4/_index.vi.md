---
title: "Worklog Tuần 4"
date: 2025-09-29
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---

### Mục Tiêu Tuần 4:

- Nắm vững các dịch vụ AWS Storage với trọng tâm là kiến thức cơ bản về S3
- Hiểu các storage classes của S3, lifecycle policies và kiểm soát truy cập
- Học các giải pháp lưu trữ lai: Snow Family và Storage Gateway
- Khám phá khả năng của FSx for Windows File Server
- Thực hành migration VM từ on-premises lên AWS

### Các nhiệm vụ cần thực hiện trong tuần này:

| Ngày | Nhiệm vụ | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
|------|----------|--------------|-----------------|-------------------|
| 1 | - Nghiên cứu tổng quan AWS Storage Services <br>&emsp; + Kiến thức cơ bản và trường hợp sử dụng S3 <br>&emsp; + S3 Access Points và Storage Classes <br>&emsp; + S3 Glacier cho lưu trữ | 2025/09/29 | 2025/09/29 | <https://docs.aws.amazon.com/s3/> |
| 2 | - Tìm hiểu sâu về các tính năng S3: <br>&emsp; + Static website hosting và CORS <br>&emsp; + Kiểm soát truy cập (IAM, Bucket Policies, ACLs) <br>&emsp; + Object keys và tối ưu hiệu suất <br> - Học Snow Family và Storage Gateway | 2025/09/30 | 2025/09/30 | <https://docs.aws.amazon.com/storagegateway/> |
| 3 | - **Lab 13:** Triển khai AWS Backup <br>&emsp; + Tạo S3 bucket và hạ tầng <br>&emsp; + Cấu hình backup plans <br>&emsp; + Thiết lập thông báo <br>&emsp; + Kiểm tra quy trình restore | 2025/10/01 | 2025/10/01 | <https://000013.awsstudygroup.com/> |
| 4 | - **Lab 14:** VM Import/Export <br>&emsp; + Export VM từ VMware Workstation <br>&emsp; + Upload lên S3 và import vào AWS <br>&emsp; + Deploy instance từ AMI <br>&emsp; + Export VM trở lại từ AWS | 2025/10/02 | 2025/10/02 | <https://000014.awsstudygroup.com/> |
| 5 | - **Lab 24:** Thiết lập Storage Gateway <br>&emsp; + Tạo File Gateway <br>&emsp; + Cấu hình file shares <br>&emsp; + Mount shares trên máy on-premises <br> - **Lab 57:** S3 static website (Phần 1) | 2025/10/03 | 2025/10/03 | <https://000024.awsstudygroup.com/> <br> <https://000057.awsstudygroup.com/> |
| 6 | - **Lab 25:** FSx for Windows File Server <br>&emsp; + Tạo Multi-AZ file systems (SSD & HDD) <br>&emsp; + Kiểm tra và giám sát hiệu suất <br>&emsp; + Bật deduplication và shadow copies <br>&emsp; + Cấu hình user quotas | 2025/10/04 | 2025/10/04 | <https://000025.awsstudygroup.com/> |
| 7 | - Hoàn thành Lab 57: Tích hợp CloudFront <br> - Ôn tập tuần và dọn dẹp tất cả tài nguyên <br> - Ghi chép kiến thức | 2025/10/05 | 2025/10/05 | |

### Thành Tựu Tuần 4:

- **Thành Thạo S3:**
  - Hiểu các storage classes của S3: Standard, IA, One Zone-IA, Glacier, Deep Archive
  - Cấu hình bucket policies, ACLs và access points cho truy cập an toàn
  - Triển khai lifecycle policies để tối ưu chi phí
  - Bật versioning và cross-region replication

- **AWS Backup (Lab 13):**
  - Tạo backup plans tự động cho EC2 và RDS
  - Cấu hình backup retention và lifecycle policies
  - Thiết lập SNS notifications cho các sự kiện backup
  - Khôi phục thành công tài nguyên từ backups

- **VM Migration (Lab 14):**
  - Export VMs từ VMware Workstation sang định dạng OVA
  - Upload VM images lên S3 sử dụng AWS CLI
  - Import VMs thành AMIs sử dụng VM Import/Export
  - Deploy EC2 instances từ AMIs đã import
  - Export running instances trở lại định dạng VM

- **Storage Gateway (Lab 24):**
  - Triển khai File Gateway trên EC2
  - Tạo NFS/SMB file shares được hỗ trợ bởi S3
  - Mount shares trên máy Windows/Linux on-premises
  - Kiểm tra đồng bộ file giữa on-premises và S3

- **FSx for Windows (Lab 25):**
  - Tạo Multi-AZ file systems với SSD và HDD storage
  - Kiểm tra sự khác biệt hiệu suất giữa các loại storage
  - Bật data deduplication để giảm chi phí lưu trữ
  - Cấu hình shadow copies cho khôi phục file
  - Thiết lập user storage quotas
  - Mở rộng throughput và storage capacity

- **S3 Static Website (Lab 57):**
  - Host static website trên S3 với custom domain
  - Cấu hình CloudFront cho phân phối nội dung toàn cầu
  - Triển khai bucket versioning cho khả năng rollback
  - Thiết lập cross-region replication cho disaster recovery

### Thách Thức Gặp Phải:

- **Đặt Tên S3 Bucket:** Tên bucket đã được sử dụng toàn cầu → Sử dụng quy ước đặt tên duy nhất với account ID
- **Kích Thước VM Import:** VM lớn mất nhiều giờ để upload → Sử dụng multipart upload và S3 Transfer Acceleration
- **Kích Hoạt Storage Gateway:** Không kích hoạt được gateway → Xác minh security group cho phép ports 80, 443, 1026-1028, 2049
- **Hiệu Suất FSx:** Throughput ban đầu thấp hơn mong đợi → Tăng throughput capacity từ 8 MB/s lên 64 MB/s
- **Cache CloudFront:** Thay đổi website không phản ánh ngay lập tức → Học về cache invalidation và TTL settings
- **Cross-Region Replication:** Objects không replicate → Bật versioning trên cả source và destination buckets
- **Chi Phí Backup:** Chi phí lưu trữ cao cho backups thường xuyên → Điều chỉnh retention policy và chuyển backups cũ sang Glacier

### Tài Liệu Tham Khảo:

**Tài Liệu Chính Thức AWS:**
- [Amazon S3 User Guide](https://docs.aws.amazon.com/s3/) - Tài liệu S3 đầy đủ
- [S3 Storage Classes](https://aws.amazon.com/s3/storage-classes/) - So sánh storage class
- [AWS Backup](https://docs.aws.amazon.com/aws-backup/) - Hướng dẫn dịch vụ Backup
- [VM Import/Export](https://docs.aws.amazon.com/vm-import/) - Hướng dẫn migration VM
- [AWS Storage Gateway](https://docs.aws.amazon.com/storagegateway/) - Tài liệu lưu trữ lai
- [Amazon FSx for Windows](https://docs.aws.amazon.com/fsx/latest/WindowsGuide/) - Tài liệu FSx
- [Amazon CloudFront](https://docs.aws.amazon.com/cloudfront/) - Tài liệu CDN

**AWS Workshops & Labs:**
- [AWS Backup Workshop](https://000013.awsstudygroup.com/) - Lab 13: Triển khai Backup
- [VM Import Workshop](https://000014.awsstudygroup.com/) - Lab 14: Migration VM
- [Storage Gateway Workshop](https://000024.awsstudygroup.com/) - Lab 24: Thiết lập File Gateway
- [FSx Workshop](https://000025.awsstudygroup.com/) - Lab 25: FSx for Windows
- [S3 Static Website Workshop](https://000057.awsstudygroup.com/) - Lab 57: Hosting website

**Bài Viết Kỹ Thuật:**
- [S3 Performance Optimization](https://docs.aws.amazon.com/AmazonS3/latest/userguide/optimizing-performance.html) - Best practices về hiệu suất
- [S3 Security Best Practices](https://docs.aws.amazon.com/AmazonS3/latest/userguide/security-best-practices.html) - Hướng dẫn bảo mật
- [Storage Gateway Best Practices](https://docs.aws.amazon.com/storagegateway/latest/userguide/Performance.html) - Tối ưu hiệu suất
- [FSx Performance](https://docs.aws.amazon.com/fsx/latest/WindowsGuide/performance.html) - Hướng dẫn tối ưu FSx
