---
title: "Week 6 Worklog"
date: 2025-10-13
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
---

### Week 6 Objectives:

- Understand AWS database services and use cases
- Master Amazon RDS fundamentals and Aurora features
- Learn database migration strategies with AWS DMS
- Explore data warehousing with Redshift and caching with ElastiCache
- Practice database backup, restore, and high availability

### Tasks to be carried out this week:

| Day | Task | Start Date | Completion Date | Reference Material |
|-----|------|------------|-----------------|-------------------|
| 1 | - Review database concepts: <br>&emsp; + Relational vs NoSQL databases <br>&emsp; + ACID properties and transactions <br> - Study Amazon RDS: <br>&emsp; + Supported engines (MySQL, PostgreSQL, SQL Server, Oracle) <br>&emsp; + Multi-AZ and Read Replicas | 2025/10/13 | 2025/10/13 | <https://docs.aws.amazon.com/rds/> |
| 2 | - Deep dive into Amazon Aurora: <br>&emsp; + Aurora MySQL and PostgreSQL compatibility <br>&emsp; + Aurora Serverless <br> - Learn Redshift for data warehousing <br> - Study ElastiCache (Redis and Memcached) | 2025/10/14 | 2025/10/14 | <https://docs.aws.amazon.com/aurora/> |
| 3 | - **Lab 05:** RDS deployment <br>&emsp; + Create VPC and security groups <br>&emsp; + Create DB subnet group <br>&emsp; + Launch EC2 and RDS instances <br>&emsp; + Deploy application <br>&emsp; + Test backup and restore | 2025/10/15 | 2025/10/15 | <https://000005.awsstudygroup.com/> |
| 4 | - **Lab 43:** Database migration (Part 1) <br>&emsp; + Connect to EC2 via RDP and Fleet Manager <br>&emsp; + Configure SQL Server source database <br>&emsp; + Configure Oracle source database <br>&emsp; + Drop constraints for migration | 2025/10/16 | 2025/10/16 | <https://000043.awsstudygroup.com/> |
| 5 | - **Lab 43:** Database migration (Part 2) <br>&emsp; + Configure Aurora MySQL target <br>&emsp; + Create DMS project <br>&emsp; + Perform schema conversion <br>&emsp; + Convert MSSQL to MySQL schema <br>&emsp; + Convert Oracle to MySQL schema | 2025/10/17 | 2025/10/17 | <https://000043.awsstudygroup.com/> |
| 6 | - **Lab 43:** Database migration (Part 3) <br>&emsp; + Create migration tasks and endpoints <br>&emsp; + Inspect S3 for migration data <br>&emsp; + Create serverless migration <br>&emsp; + Configure event notifications <br>&emsp; + Review migration logs | 2025/10/18 | 2025/10/18 | <https://000043.awsstudygroup.com/> |
| 7 | - **Lab 43:** Troubleshooting <br>&emsp; + Test memory pressure scenarios <br>&emsp; + Troubleshoot table errors <br> - Weekly review and cleanup | 2025/10/19 | 2025/10/19 | <https://000043.awsstudygroup.com/> |

### Week 6 Achievements:

- **RDS Fundamentals:**
  - Understood RDS architecture and supported database engines
  - Learned Multi-AZ deployment for high availability
  - Configured Read Replicas for read scalability
  - Implemented automated backups and manual snapshots
  - Understood RDS pricing model and cost optimization

- **Amazon Aurora:**
  - Learned Aurora's distributed storage architecture
  - Understood Aurora MySQL and PostgreSQL compatibility
  - Explored Aurora Serverless for variable workloads
  - Configured Aurora Global Database for disaster recovery
  - Implemented Aurora Backtrack for point-in-time recovery

- **RDS Deployment (Lab 05):**
  - Created VPC with public and private subnets
  - Configured security groups for EC2 and RDS
  - Created DB subnet group for Multi-AZ deployment
  - Launched RDS MySQL instance with proper configuration
  - Deployed web application connecting to RDS
  - Tested automated backup and restore procedures
  - Verified Multi-AZ failover behavior

- **Database Migration (Lab 43):**
  - Connected to Windows EC2 via RDP and Fleet Manager
  - Configured SQL Server and Oracle source databases
  - Prepared databases for migration (dropped constraints)
  - Used AWS Schema Conversion Tool (SCT) for schema migration
  - Converted MSSQL schemas to Aurora MySQL format
  - Converted Oracle schemas to MySQL format
  - Created DMS replication instances and endpoints
  - Configured migration tasks for full load and CDC
  - Monitored migration progress and logs
  - Troubleshot common migration issues

- **Data Warehousing & Caching:**
  - Understood Redshift architecture for analytics workloads
  - Learned ElastiCache for in-memory caching
  - Compared Redis vs Memcached use cases
  - Understood when to use RDS vs Redshift vs DynamoDB

### Challenges Encountered:

- **RDS Connection:** Application couldn't connect to RDS → Verified security group inbound rules and subnet routing
- **Multi-AZ Failover:** Failover took longer than expected → Learned typical failover time is 60-120 seconds
- **Schema Conversion:** Some stored procedures didn't convert → Manually rewrote incompatible SQL syntax
- **DMS Replication Lag:** CDC replication lagging behind → Increased replication instance size
- **Foreign Key Constraints:** Migration failed due to constraints → Dropped constraints before migration, recreated after
- **Character Encoding:** Data corruption during migration → Ensured matching character sets between source and target
- **Memory Pressure:** DMS task failed under load → Increased task memory and optimized batch settings

### References:

**AWS Official Documentation:**
- [Amazon RDS User Guide](https://docs.aws.amazon.com/rds/) - Complete RDS documentation
- [Amazon Aurora User Guide](https://docs.aws.amazon.com/aurora/) - Aurora documentation
- [AWS Database Migration Service](https://docs.aws.amazon.com/dms/) - DMS guide
- [AWS Schema Conversion Tool](https://docs.aws.amazon.com/SchemaConversionTool/) - SCT documentation
- [Amazon Redshift](https://docs.aws.amazon.com/redshift/) - Data warehouse guide
- [Amazon ElastiCache](https://docs.aws.amazon.com/elasticache/) - Caching service guide

**AWS Workshops & Labs:**
- [RDS Workshop](https://000005.awsstudygroup.com/) - Lab 05: RDS deployment and management
- [Database Migration Workshop](https://000043.awsstudygroup.com/) - Lab 43: Complete migration guide

**Technical Articles:**
- [RDS Best Practices](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/CHAP_BestPractices.html) - Performance and security
- [Aurora Best Practices](https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/Aurora.BestPractices.html) - Aurora optimization
- [DMS Best Practices](https://docs.aws.amazon.com/dms/latest/userguide/CHAP_BestPractices.html) - Migration strategies
- [Database Migration Strategies](https://aws.amazon.com/blogs/database/category/database-migration-service/) - AWS Database Blog
- [RDS Multi-AZ](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Concepts.MultiAZ.html) - High availability guide
