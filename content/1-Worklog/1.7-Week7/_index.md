---
title: "Week 7 Worklog"
date: 2025-10-20
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---

### Week 7 Objectives:

- Master AWS Analytics services: Kinesis, Glue, Athena, QuickSight
- Understand DynamoDB fundamentals and design patterns
- Learn data processing with AWS Glue, DataBrew, and EMR
- Build end-to-end data pipelines and analytics solutions
- Practice data visualization with QuickSight dashboards

### Tasks to be carried out this week:

| Day | Task | Start Date | Completion Date | Reference Material |
|-----|------|------------|-----------------|-------------------|
| 1 | - Study AWS Analytics services overview <br>&emsp; + Kinesis for streaming data <br>&emsp; + Glue for ETL <br>&emsp; + Athena for querying <br>&emsp; + QuickSight for visualization <br> - Learn DynamoDB basics | 2025/10/20 | 2025/10/20 | <https://docs.aws.amazon.com/kinesis/> |
| 2 | - **Lab 35:** Data streaming pipeline <br>&emsp; + Create S3 bucket and Kinesis Firehose <br>&emsp; + Generate sample data <br>&emsp; + Create Glue Crawler <br>&emsp; + Query with Athena <br>&emsp; + Visualize with QuickSight | 2025/10/21 | 2025/10/21 | <https://000035.awsstudygroup.com/> |
| 3 | - **Lab 39:** DynamoDB hands-on <br>&emsp; + Explore DynamoDB console <br>&emsp; + Create tables and items <br>&emsp; + Configure backups <br>&emsp; + Advanced design patterns <br>&emsp; + Build serverless applications | 2025/10/22 | 2025/10/22 | <https://000039.awsstudygroup.com/> |
| 4 | - **Lab 40:** DynamoDB cost optimization <br>&emsp; + Prepare and build database <br>&emsp; + Analyze data and costs <br>&emsp; + Configure tagging for cost allocation <br>&emsp; + Monitor usage patterns | 2025/10/23 | 2025/10/23 | <https://000040.awsstudygroup.com/> |
| 5 | - **Lab 60:** AWS CLI and SDK <br>&emsp; + Use CloudShell <br>&emsp; + Practice AWS Console operations <br>&emsp; + Work with AWS SDK <br> - **Lab 70:** AWS Glue DataBrew <br>&emsp; + Create Cloud9 instance <br>&emsp; + Upload dataset to S3 <br>&emsp; + Profile and transform data | 2025/10/24 | 2025/10/24 | <https://000060.awsstudygroup.com/> <br> <https://000070.awsstudygroup.com/> |
| 6 | - **Lab 72:** Complete data pipeline <br>&emsp; + Ingest and store data <br>&emsp; + Catalog with Glue <br>&emsp; + Transform with Glue, DataBrew, EMR <br>&emsp; + Analyze with Athena and Kinesis Analytics <br>&emsp; + Serve with Lambda <br>&emsp; + Warehouse with Redshift | 2025/10/25 | 2025/10/25 | <https://000072.awsstudygroup.com/> |
| 7 | - **Lab 73:** QuickSight dashboards <br>&emsp; + Build basic dashboard <br>&emsp; + Add improvements <br>&emsp; + Create interactive visualizations <br> - Weekly review and cleanup | 2025/10/26 | 2025/10/26 | <https://000073.awsstudygroup.com/> |

### Week 7 Achievements:

- **AWS Analytics Services:**
  - Understood Kinesis Data Streams, Firehose, and Analytics
  - Learned AWS Glue for serverless ETL
  - Mastered Athena for SQL queries on S3
  - Explored QuickSight for business intelligence

- **Data Streaming Pipeline (Lab 35):**
  - Created Kinesis Firehose delivery stream
  - Generated and ingested sample streaming data
  - Configured Glue Crawler to catalog data
  - Queried data with Athena SQL
  - Built QuickSight visualizations and dashboards
  - Implemented data transformation in Firehose

- **DynamoDB Mastery (Labs 39, 40):**
  - Created DynamoDB tables with partition and sort keys
  - Implemented GSI and LSI for flexible queries
  - Configured on-demand and provisioned capacity modes
  - Set up point-in-time recovery and backups
  - Learned DynamoDB design patterns (single-table design)
  - Built serverless applications with DynamoDB
  - Implemented DynamoDB Streams for event-driven architecture
  - Optimized costs with tagging and capacity planning

- **Data Processing (Labs 60, 70, 72):**
  - Used AWS CloudShell for CLI operations
  - Worked with AWS SDK for programmatic access
  - Created Cloud9 development environment
  - Uploaded and managed datasets in S3
  - Profiled data with AWS Glue DataBrew
  - Cleaned and transformed data with DataBrew recipes
  - Processed data with AWS Glue interactive sessions
  - Used Glue Studio GUI for visual ETL
  - Ran big data processing with EMR
  - Analyzed streaming data with Kinesis Data Analytics
  - Served data via Lambda functions
  - Loaded data into Redshift for warehousing

- **Data Visualization (Lab 73):**
  - Connected QuickSight to multiple data sources
  - Built interactive dashboards with filters and parameters
  - Created various chart types (bar, line, pie, heat maps)
  - Implemented drill-down capabilities
  - Shared dashboards with stakeholders
  - Scheduled dashboard refreshes

### Challenges Encountered:

- **Kinesis Firehose Buffer:** Data not appearing immediately → Understood buffer size and interval settings
- **Glue Crawler Scheduling:** Crawler not detecting new data → Configured proper schedule and S3 event triggers
- **DynamoDB Hot Partition:** Throttling on high-traffic partition key → Redesigned partition key for better distribution
- **Athena Query Performance:** Slow queries on large datasets → Implemented partitioning and columnar formats (Parquet)
- **QuickSight Permissions:** Cannot access S3 data → Granted QuickSight proper IAM permissions
- **DataBrew Recipe:** Transformation not working as expected → Tested recipe on sample data before full run
- **EMR Cluster Costs:** High costs for idle cluster → Used transient clusters and spot instances

### References:

**AWS Official Documentation:**
- [Amazon Kinesis](https://docs.aws.amazon.com/kinesis/) - Streaming data services
- [AWS Glue](https://docs.aws.amazon.com/glue/) - ETL service guide
- [Amazon Athena](https://docs.aws.amazon.com/athena/) - Query service documentation
- [Amazon QuickSight](https://docs.aws.amazon.com/quicksight/) - BI service guide
- [Amazon DynamoDB](https://docs.aws.amazon.com/dynamodb/) - NoSQL database guide
- [AWS Glue DataBrew](https://docs.aws.amazon.com/databrew/) - Data preparation service
- [Amazon EMR](https://docs.aws.amazon.com/emr/) - Big data processing
- [Amazon Redshift](https://docs.aws.amazon.com/redshift/) - Data warehouse

**AWS Workshops & Labs:**
- [Streaming Analytics Workshop](https://000035.awsstudygroup.com/) - Lab 35: Kinesis and analytics
- [DynamoDB Workshop](https://000039.awsstudygroup.com/) - Lab 39: DynamoDB hands-on
- [DynamoDB Cost Workshop](https://000040.awsstudygroup.com/) - Lab 40: Cost optimization
- [CLI/SDK Workshop](https://000060.awsstudygroup.com/) - Lab 60: CloudShell and SDK
- [DataBrew Workshop](https://000070.awsstudygroup.com/) - Lab 70: Data preparation
- [Data Pipeline Workshop](https://000072.awsstudygroup.com/) - Lab 72: End-to-end pipeline
- [QuickSight Workshop](https://000073.awsstudygroup.com/) - Lab 73: Dashboards

**Technical Articles:**
- [DynamoDB Best Practices](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/best-practices.html) - Design patterns
- [Athena Performance Tuning](https://docs.aws.amazon.com/athena/latest/ug/performance-tuning.html) - Query optimization
- [Glue Best Practices](https://docs.aws.amazon.com/glue/latest/dg/best-practices.html) - ETL optimization
- [QuickSight Best Practices](https://docs.aws.amazon.com/quicksight/latest/user/best-practices.html) - Dashboard design
