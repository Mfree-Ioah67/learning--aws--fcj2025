---
title: "Worklog Tuần 7"
date: 2025-10-20
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---

### Mục Tiêu Tuần 7:

- Nắm vững các dịch vụ AWS Analytics: Kinesis, Glue, Athena, QuickSight
- Hiểu kiến thức cơ bản về DynamoDB và design patterns
- Học xử lý dữ liệu với AWS Glue, DataBrew và EMR
- Xây dựng data pipelines và analytics solutions end-to-end
- Thực hành data visualization với QuickSight dashboards

### Các nhiệm vụ cần thực hiện trong tuần này:

| Ngày | Nhiệm vụ | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
|------|----------|--------------|-----------------|-------------------|
| 1 | - Nghiên cứu tổng quan AWS Analytics services <br>&emsp; + Kinesis cho streaming data <br>&emsp; + Glue cho ETL <br>&emsp; + Athena cho querying <br>&emsp; + QuickSight cho visualization <br> - Học kiến thức cơ bản DynamoDB | 2025/10/20 | 2025/10/20 | <https://docs.aws.amazon.com/kinesis/> |
| 2 | - **Lab 35:** Data streaming pipeline <br>&emsp; + Tạo S3 bucket và Kinesis Firehose <br>&emsp; + Tạo sample data <br>&emsp; + Tạo Glue Crawler <br>&emsp; + Query với Athena <br>&emsp; + Visualize với QuickSight | 2025/10/21 | 2025/10/21 | <https://000035.awsstudygroup.com/> |
| 3 | - **Lab 39:** DynamoDB hands-on <br>&emsp; + Khám phá DynamoDB console <br>&emsp; + Tạo tables và items <br>&emsp; + Cấu hình backups <br>&emsp; + Advanced design patterns <br>&emsp; + Xây dựng serverless applications | 2025/10/22 | 2025/10/22 | <https://000039.awsstudygroup.com/> |
| 4 | - **Lab 40:** Tối ưu chi phí DynamoDB <br>&emsp; + Chuẩn bị và xây dựng database <br>&emsp; + Phân tích data và costs <br>&emsp; + Cấu hình tagging cho cost allocation <br>&emsp; + Giám sát usage patterns | 2025/10/23 | 2025/10/23 | <https://000040.awsstudygroup.com/> |
| 5 | - **Lab 60:** AWS CLI và SDK <br>&emsp; + Sử dụng CloudShell <br>&emsp; + Thực hành AWS Console operations <br>&emsp; + Làm việc với AWS SDK <br> - **Lab 70:** AWS Glue DataBrew <br>&emsp; + Tạo Cloud9 instance <br>&emsp; + Upload dataset lên S3 <br>&emsp; + Profile và transform data | 2025/10/24 | 2025/10/24 | <https://000060.awsstudygroup.com/> <br> <https://000070.awsstudygroup.com/> |
| 6 | - **Lab 72:** Complete data pipeline <br>&emsp; + Ingest và store data <br>&emsp; + Catalog với Glue <br>&emsp; + Transform với Glue, DataBrew, EMR <br>&emsp; + Analyze với Athena và Kinesis Analytics <br>&emsp; + Serve với Lambda <br>&emsp; + Warehouse với Redshift | 2025/10/25 | 2025/10/25 | <https://000072.awsstudygroup.com/> |
| 7 | - **Lab 73:** QuickSight dashboards <br>&emsp; + Xây dựng basic dashboard <br>&emsp; + Thêm improvements <br>&emsp; + Tạo interactive visualizations <br> - Ôn tập tuần và dọn dẹp | 2025/10/26 | 2025/10/26 | <https://000073.awsstudygroup.com/> |

### Thành Tựu Tuần 7:

- **AWS Analytics Services:**
  - Hiểu Kinesis Data Streams, Firehose và Analytics
  - Học AWS Glue cho serverless ETL
  - Thành thạo Athena cho SQL queries trên S3
  - Khám phá QuickSight cho business intelligence

- **Data Streaming Pipeline (Lab 35):**
  - Tạo Kinesis Firehose delivery stream
  - Tạo và ingest sample streaming data
  - Cấu hình Glue Crawler để catalog data
  - Query data với Athena SQL
  - Xây dựng QuickSight visualizations và dashboards
  - Triển khai data transformation trong Firehose

- **Thành Thạo DynamoDB (Labs 39, 40):**
  - Tạo DynamoDB tables với partition và sort keys
  - Triển khai GSI và LSI cho flexible queries
  - Cấu hình on-demand và provisioned capacity modes
  - Thiết lập point-in-time recovery và backups
  - Học DynamoDB design patterns (single-table design)
  - Xây dựng serverless applications với DynamoDB
  - Triển khai DynamoDB Streams cho event-driven architecture
  - Tối ưu chi phí với tagging và capacity planning

- **Xử Lý Dữ Liệu (Labs 60, 70, 72):**
  - Sử dụng AWS CloudShell cho CLI operations
  - Làm việc với AWS SDK cho programmatic access
  - Tạo Cloud9 development environment
  - Upload và quản lý datasets trong S3
  - Profile data với AWS Glue DataBrew
  - Clean và transform data với DataBrew recipes
  - Xử lý data với AWS Glue interactive sessions
  - Sử dụng Glue Studio GUI cho visual ETL
  - Chạy big data processing với EMR
  - Phân tích streaming data với Kinesis Data Analytics
  - Serve data qua Lambda functions
  - Load data vào Redshift cho warehousing

- **Data Visualization (Lab 73):**
  - Kết nối QuickSight với nhiều data sources
  - Xây dựng interactive dashboards với filters và parameters
  - Tạo các loại chart khác nhau (bar, line, pie, heat maps)
  - Triển khai drill-down capabilities
  - Chia sẻ dashboards với stakeholders
  - Lên lịch dashboard refreshes

### Thách Thức Gặp Phải:

- **Kinesis Firehose Buffer:** Data không xuất hiện ngay lập tức → Hiểu buffer size và interval settings
- **Glue Crawler Scheduling:** Crawler không phát hiện data mới → Cấu hình schedule đúng và S3 event triggers
- **DynamoDB Hot Partition:** Throttling trên partition key có traffic cao → Thiết kế lại partition key cho phân phối tốt hơn
- **Athena Query Performance:** Queries chậm trên datasets lớn → Triển khai partitioning và columnar formats (Parquet)
- **QuickSight Permissions:** Không thể truy cập S3 data → Cấp IAM permissions phù hợp cho QuickSight
- **DataBrew Recipe:** Transformation không hoạt động như mong đợi → Test recipe trên sample data trước khi chạy full
- **EMR Cluster Costs:** Chi phí cao cho idle cluster → Sử dụng transient clusters và spot instances

### Tài Liệu Tham Khảo:

**Tài Liệu Chính Thức AWS:**
- [Amazon Kinesis](https://docs.aws.amazon.com/kinesis/) - Dịch vụ streaming data
- [AWS Glue](https://docs.aws.amazon.com/glue/) - Hướng dẫn ETL service
- [Amazon Athena](https://docs.aws.amazon.com/athena/) - Tài liệu Query service
- [Amazon QuickSight](https://docs.aws.amazon.com/quicksight/) - Hướng dẫn BI service
- [Amazon DynamoDB](https://docs.aws.amazon.com/dynamodb/) - Hướng dẫn NoSQL database
- [AWS Glue DataBrew](https://docs.aws.amazon.com/databrew/) - Data preparation service
- [Amazon EMR](https://docs.aws.amazon.com/emr/) - Big data processing
- [Amazon Redshift](https://docs.aws.amazon.com/redshift/) - Data warehouse

**AWS Workshops & Labs:**
- [Streaming Analytics Workshop](https://000035.awsstudygroup.com/) - Lab 35: Kinesis và analytics
- [DynamoDB Workshop](https://000039.awsstudygroup.com/) - Lab 39: DynamoDB hands-on
- [DynamoDB Cost Workshop](https://000040.awsstudygroup.com/) - Lab 40: Tối ưu chi phí
- [CLI/SDK Workshop](https://000060.awsstudygroup.com/) - Lab 60: CloudShell và SDK
- [DataBrew Workshop](https://000070.awsstudygroup.com/) - Lab 70: Data preparation
- [Data Pipeline Workshop](https://000072.awsstudygroup.com/) - Lab 72: End-to-end pipeline
- [QuickSight Workshop](https://000073.awsstudygroup.com/) - Lab 73: Dashboards

**Bài Viết Kỹ Thuật:**
- [DynamoDB Best Practices](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/best-practices.html) - Design patterns
- [Athena Performance Tuning](https://docs.aws.amazon.com/athena/latest/ug/performance-tuning.html) - Tối ưu Query
- [Glue Best Practices](https://docs.aws.amazon.com/glue/latest/dg/best-practices.html) - Tối ưu ETL
- [QuickSight Best Practices](https://docs.aws.amazon.com/quicksight/latest/user/best-practices.html) - Thiết kế Dashboard
