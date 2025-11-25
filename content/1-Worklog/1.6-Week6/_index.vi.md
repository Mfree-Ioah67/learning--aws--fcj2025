---
title: "Worklog Tuần 6"
date: 2025-10-13
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
---

### Mục Tiêu Tuần 6:

- Hiểu các dịch vụ database của AWS và trường hợp sử dụng
- Nắm vững kiến thức cơ bản về Amazon RDS và các tính năng Aurora
- Học chiến lược migration database với AWS DMS
- Khám phá data warehousing với Redshift và caching với ElastiCache
- Thực hành backup, restore và high availability cho database

### Các nhiệm vụ cần thực hiện trong tuần này:

| Ngày | Nhiệm vụ | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
|------|----------|--------------|-----------------|-------------------|
| 1 | - Ôn tập các khái niệm database: <br>&emsp; + Relational vs NoSQL databases <br>&emsp; + Thuộc tính ACID và transactions <br> - Nghiên cứu Amazon RDS: <br>&emsp; + Các engine được hỗ trợ (MySQL, PostgreSQL, SQL Server, Oracle) <br>&emsp; + Multi-AZ và Read Replicas | 2025/10/13 | 2025/10/13 | <https://docs.aws.amazon.com/rds/> |
| 2 | - Tìm hiểu sâu về Amazon Aurora: <br>&emsp; + Aurora MySQL và PostgreSQL compatibility <br>&emsp; + Aurora Serverless <br> - Học Redshift cho data warehousing <br> - Nghiên cứu ElastiCache (Redis và Memcached) | 2025/10/14 | 2025/10/14 | <https://docs.aws.amazon.com/aurora/> |
| 3 | - **Lab 05:** Triển khai RDS <br>&emsp; + Tạo VPC và security groups <br>&emsp; + Tạo DB subnet group <br>&emsp; + Khởi chạy EC2 và RDS instances <br>&emsp; + Deploy ứng dụng <br>&emsp; + Kiểm tra backup và restore | 2025/10/15 | 2025/10/15 | <https://000005.awsstudygroup.com/> |
| 4 | - **Lab 43:** Database migration (Phần 1) <br>&emsp; + Kết nối EC2 qua RDP và Fleet Manager <br>&emsp; + Cấu hình SQL Server source database <br>&emsp; + Cấu hình Oracle source database <br>&emsp; + Drop constraints cho migration | 2025/10/16 | 2025/10/16 | <https://000043.awsstudygroup.com/> |
| 5 | - **Lab 43:** Database migration (Phần 2) <br>&emsp; + Cấu hình Aurora MySQL target <br>&emsp; + Tạo DMS project <br>&emsp; + Thực hiện schema conversion <br>&emsp; + Convert MSSQL sang MySQL schema <br>&emsp; + Convert Oracle sang MySQL schema | 2025/10/17 | 2025/10/17 | <https://000043.awsstudygroup.com/> |
| 6 | - **Lab 43:** Database migration (Phần 3) <br>&emsp; + Tạo migration tasks và endpoints <br>&emsp; + Kiểm tra S3 cho migration data <br>&emsp; + Tạo serverless migration <br>&emsp; + Cấu hình event notifications <br>&emsp; + Xem xét migration logs | 2025/10/18 | 2025/10/18 | <https://000043.awsstudygroup.com/> |
| 7 | - **Lab 43:** Troubleshooting <br>&emsp; + Kiểm tra memory pressure scenarios <br>&emsp; + Troubleshoot table errors <br> - Ôn tập tuần và dọn dẹp | 2025/10/19 | 2025/10/19 | <https://000043.awsstudygroup.com/> |

### Thành Tựu Tuần 6:

- **Kiến Thức Cơ Bản RDS:**
  - Hiểu kiến trúc RDS và các database engines được hỗ trợ
  - Học Multi-AZ deployment cho high availability
  - Cấu hình Read Replicas cho read scalability
  - Triển khai automated backups và manual snapshots
  - Hiểu mô hình giá RDS và tối ưu chi phí

- **Amazon Aurora:**
  - Học kiến trúc distributed storage của Aurora
  - Hiểu Aurora MySQL và PostgreSQL compatibility
  - Khám phá Aurora Serverless cho workloads biến đổi
  - Cấu hình Aurora Global Database cho disaster recovery
  - Triển khai Aurora Backtrack cho point-in-time recovery

- **Cấu Hình VPC (Lab 05-2.1):**
  - Tạo custom VPC với CIDR block 10.0.0.0/16
  - Cấu hình public subnet (10.0.1.0/24) cho EC2 web server
  - Cấu hình private subnets (10.0.2.0/24, 10.0.3.0/24) cho RDS ở các AZ khác nhau
  - Tạo Internet Gateway và gắn vào VPC
  - Cấu hình route tables cho public và private subnets
  - Bật DNS hostnames và DNS resolution cho VPC
  - Triển khai network isolation cho database tier

- **Cấu Hình Security Groups (Lab 05-2.2 & 2.3):**
  - Tạo EC2 security group cho phép HTTP (80), HTTPS (443), và SSH (22)
  - Tạo RDS security group cho phép MySQL (3306) chỉ từ EC2 security group
  - Triển khai nguyên tắc least privilege cho network access
  - Cấu hình security group rules cho inbound và outbound traffic
  - Sử dụng security group references thay vì IP addresses để bảo mật tốt hơn

- **DB Subnet Group (Lab 05-2.4):**
  - Tạo DB subnet group trải rộng nhiều availability zones
  - Chọn private subnets ở các AZ khác nhau cho high availability
  - Đảm bảo cấu hình subnet phù hợp cho Multi-AZ deployment
  - Xác minh subnet group đáp ứng yêu cầu RDS

- **Triển Khai RDS (Lab 05-3 đến 05-7):**
  - Khởi chạy EC2 instance trong public subnet với vai trò web server
  - Khởi chạy RDS MySQL instance trong private subnets với Multi-AZ enabled
  - Deploy ứng dụng web kết nối với RDS qua private endpoint
  - Kiểm tra automated backup và restore procedures
  - Xác minh hành vi Multi-AZ failover
  - Thực hành dọn dẹp resources để tránh chi phí không cần thiết

- **Thiết Lập Database Migration (Lab 43-01 đến 43-06):**
  - Kết nối Windows EC2 qua RDP Client (Lab 43-01)
  - Kết nối EC2 sử dụng Fleet Manager cho truy cập qua browser (Lab 43-02)
  - Cấu hình SQL Server source database settings (Lab 43-03)
  - Kết nối Oracle source database (Lab 43-04)
  - Cấu hình Oracle source database cho migration (Lab 43-05)
  - Drop foreign key constraints để chuẩn bị cho migration (Lab 43-06)

- **Schema Conversion (Lab 43-07 đến 43-10):**
  - Cấu hình Aurora MySQL làm target database (Lab 43-07)
  - Tạo AWS SCT project cho MSSQL sang Aurora MySQL (Lab 43-08)
  - Thực hiện schema conversion từ MSSQL sang MySQL (Lab 43-09)
  - Thực thi Oracle sang MySQL schema conversion (Lab 43-10)
  - Phân tích conversion assessment reports
  - Điều chỉnh thủ công các database objects không tương thích

- **Thực Thi Data Migration (Lab 43-11 đến 43-15):**
  - Tạo DMS replication instances và endpoints (Lab 43-11)
  - Kiểm tra S3 buckets cho migration artifacts (Lab 43-12)
  - Tạo serverless DMS migration tasks (Lab 43-13)
  - Cấu hình event notifications cho migration status (Lab 43-14)
  - Giám sát CloudWatch logs cho tiến trình migration (Lab 43-15)
  - Xác thực tính toàn vẹn dữ liệu sau migration

- **Troubleshooting Migration (Lab 43-16 đến 43-17):**
  - Kiểm tra memory pressure scenarios trên replication instance (Lab 43-16)
  - Troubleshoot table-level errors trong migration (Lab 43-17)
  - Giải quyết các DMS error codes phổ biến
  - Tối ưu task settings cho hiệu suất tốt hơn
  - Triển khai retry logic cho failed tasks

- **Data Warehousing & Caching:**
  - Hiểu kiến trúc Redshift cho analytics workloads
  - Học ElastiCache cho in-memory caching
  - So sánh Redis vs Memcached use cases
  - Hiểu khi nào dùng RDS vs Redshift vs DynamoDB

### Thách Thức Gặp Phải:

- **Kết Nối RDS:** Ứng dụng không kết nối được RDS → Xác minh security group inbound rules và subnet routing
- **Multi-AZ Failover:** Failover mất nhiều thời gian hơn dự kiến → Học được thời gian failover thông thường là 60-120 giây
- **Schema Conversion:** Một số stored procedures không convert được → Viết lại thủ công SQL syntax không tương thích
- **DMS Replication Lag:** CDC replication bị lag → Tăng kích thước replication instance
- **Foreign Key Constraints:** Migration thất bại do constraints → Drop constraints trước migration, tạo lại sau
- **Character Encoding:** Dữ liệu bị hỏng trong migration → Đảm bảo character sets khớp giữa source và target
- **Memory Pressure:** DMS task thất bại dưới tải → Tăng task memory và tối ưu batch settings

### Tài Liệu Tham Khảo:

**Tài Liệu Chính Thức AWS:**
- [Amazon RDS User Guide](https://docs.aws.amazon.com/rds/) - Tài liệu RDS đầy đủ
- [Amazon Aurora User Guide](https://docs.aws.amazon.com/aurora/) - Tài liệu Aurora
- [AWS Database Migration Service](https://docs.aws.amazon.com/dms/) - Hướng dẫn DMS
- [AWS Schema Conversion Tool](https://docs.aws.amazon.com/SchemaConversionTool/) - Tài liệu SCT
- [Amazon Redshift](https://docs.aws.amazon.com/redshift/) - Hướng dẫn Data warehouse
- [Amazon ElastiCache](https://docs.aws.amazon.com/elasticache/) - Hướng dẫn Caching service

**AWS Workshops & Labs:**
- [RDS Workshop](https://000005.awsstudygroup.com/) - Lab 05: Triển khai và quản lý RDS
- [Database Migration Workshop](https://000043.awsstudygroup.com/) - Lab 43: Hướng dẫn migration đầy đủ

**Bài Viết Kỹ Thuật:**
- [RDS Best Practices](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/CHAP_BestPractices.html) - Hiệu suất và bảo mật
- [Aurora Best Practices](https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/Aurora.BestPractices.html) - Tối ưu Aurora
- [DMS Best Practices](https://docs.aws.amazon.com/dms/latest/userguide/CHAP_BestPractices.html) - Chiến lược Migration
- [Database Migration Strategies](https://aws.amazon.com/blogs/database/category/database-migration-service/) - AWS Database Blog
- [RDS Multi-AZ](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Concepts.MultiAZ.html) - Hướng dẫn High availability
