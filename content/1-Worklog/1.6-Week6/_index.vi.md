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

- **Triển Khai RDS (Lab 05):**
  - Tạo VPC với public và private subnets
  - Cấu hình security groups cho EC2 và RDS
  - Tạo DB subnet group cho Multi-AZ deployment
  - Khởi chạy RDS MySQL instance với cấu hình phù hợp
  - Deploy ứng dụng web kết nối với RDS
  - Kiểm tra automated backup và restore procedures
  - Xác minh hành vi Multi-AZ failover

- **Database Migration (Lab 43):**
  - Kết nối Windows EC2 qua RDP và Fleet Manager
  - Cấu hình SQL Server và Oracle source databases
  - Chuẩn bị databases cho migration (dropped constraints)
  - Sử dụng AWS Schema Conversion Tool (SCT) cho schema migration
  - Convert MSSQL schemas sang Aurora MySQL format
  - Convert Oracle schemas sang MySQL format
  - Tạo DMS replication instances và endpoints
  - Cấu hình migration tasks cho full load và CDC
  - Giám sát tiến trình migration và logs
  - Troubleshoot các vấn đề migration phổ biến

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
