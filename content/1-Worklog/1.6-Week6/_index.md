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

| Day | Task                                                                                                                                                                                                                                                          | Start Date | Completion Date | Reference Material                    |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------- | --------------- | ------------------------------------- |
| 1   | - Review database concepts: <br>&emsp; + Relational vs NoSQL databases <br>&emsp; + ACID properties and transactions <br> - Study Amazon RDS: <br>&emsp; + Supported engines (MySQL, PostgreSQL, SQL Server, Oracle) <br>&emsp; + Multi-AZ and Read Replicas  | 2025/10/13 | 2025/10/13      | <https://docs.aws.amazon.com/rds/>    |
| 2   | - Deep dive into Amazon Aurora: <br>&emsp; + Aurora MySQL and PostgreSQL compatibility <br>&emsp; + Aurora Serverless <br> - Learn Redshift for data warehousing <br> - Study ElastiCache (Redis and Memcached)                                               | 2025/10/14 | 2025/10/14      | <https://docs.aws.amazon.com/aurora/> |
| 3   | - **Lab 05:** RDS deployment <br>&emsp; + Create VPC and security groups <br>&emsp; + Create DB subnet group <br>&emsp; + Launch EC2 and RDS instances <br>&emsp; + Deploy application <br>&emsp; + Test backup and restore                                   | 2025/10/15 | 2025/10/15      | <https://000005.awsstudygroup.com/>   |
| 4   | - **Lab 43:** Database migration (Part 1) <br>&emsp; + Connect to EC2 via RDP and Fleet Manager <br>&emsp; + Configure SQL Server source database <br>&emsp; + Configure Oracle source database <br>&emsp; + Drop constraints for migration                   | 2025/10/16 | 2025/10/16      | <https://000043.awsstudygroup.com/>   |
| 5   | - **Lab 43:** Database migration (Part 2) <br>&emsp; + Configure Aurora MySQL target <br>&emsp; + Create DMS project <br>&emsp; + Perform schema conversion <br>&emsp; + Convert MSSQL to MySQL schema <br>&emsp; + Convert Oracle to MySQL schema            | 2025/10/17 | 2025/10/17      | <https://000043.awsstudygroup.com/>   |
| 6   | - **Lab 43:** Database migration (Part 3) <br>&emsp; + Create migration tasks and endpoints <br>&emsp; + Inspect S3 for migration data <br>&emsp; + Create serverless migration <br>&emsp; + Configure event notifications <br>&emsp; + Review migration logs | 2025/10/18 | 2025/10/18      | <https://000043.awsstudygroup.com/>   |
| 7   | - **Lab 43:** Troubleshooting <br>&emsp; + Test memory pressure scenarios <br>&emsp; + Troubleshoot table errors <br> - Weekly review and cleanup                                                                                                             | 2025/10/19 | 2025/10/19      | <https://000043.awsstudygroup.com/>   |

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

- **VPC Configuration (Lab 05-2.1):**

  - Created custom VPC with CIDR block 10.0.0.0/16
  - Configured public subnet (10.0.1.0/24) for EC2 web server
  - Configured private subnets (10.0.2.0/24, 10.0.3.0/24) for RDS in different AZs
  - Created Internet Gateway and attached to VPC
  - Configured route tables for public and private subnets
  - Enabled DNS hostnames and DNS resolution for VPC
  - Implemented network isolation for database tier

- **Security Groups Configuration (Lab 05-2.2 & 2.3):**

  - Created EC2 security group allowing HTTP (80), HTTPS (443), and SSH (22)
  - Created RDS security group allowing MySQL (3306) only from EC2 security group
  - Implemented principle of least privilege for network access
  - Configured security group rules for inbound and outbound traffic
  - Used security group references instead of IP addresses for better security

- **DB Subnet Group (Lab 05-2.4):**

  - Created DB subnet group spanning multiple availability zones
  - Selected private subnets in different AZs for high availability
  - Ensured proper subnet configuration for Multi-AZ deployment
  - Verified subnet group meets RDS requirements

- **RDS Deployment (Lab 05-3 to 05-7):**

  - Launched EC2 instance in public subnet with web server role
  - Launched RDS MySQL instance in private subnets with Multi-AZ enabled
  - Deployed web application connecting to RDS via private endpoint
  - Tested automated backup and restore procedures
  - Verified Multi-AZ failover behavior
  - Practiced clean up of resources to avoid unnecessary costs

- **Database Migration Setup (Lab 43-01 to 43-06):**

  - Connected to Windows EC2 via RDP Client (Lab 43-01)
  - Connected to EC2 using Fleet Manager for browser-based access (Lab 43-02)
  - Configured SQL Server source database settings (Lab 43-03)
  - Connected to Oracle source database (Lab 43-04)
  - Configured Oracle source database for migration (Lab 43-05)
  - Dropped foreign key constraints to prepare for migration (Lab 43-06)

- **Schema Conversion (Lab 43-07 to 43-10):**

  - Configured Aurora MySQL as target database (Lab 43-07)
  - Created AWS SCT project for MSSQL to Aurora MySQL (Lab 43-08)
  - Performed schema conversion from MSSQL to MySQL (Lab 43-09)
  - Executed Oracle to MySQL schema conversion (Lab 43-10)
  - Analyzed conversion assessment reports
  - Manually adjusted incompatible database objects

- **Data Migration Execution (Lab 43-11 to 43-15):**

  - Created DMS replication instances and endpoints (Lab 43-11)
  - Inspected S3 buckets for migration artifacts (Lab 43-12)
  - Created serverless DMS migration tasks (Lab 43-13)
  - Configured event notifications for migration status (Lab 43-14)
  - Monitored CloudWatch logs for migration progress (Lab 43-15)
  - Validated data integrity after migration

- **Migration Troubleshooting (Lab 43-16 to 43-17):**

  - Tested memory pressure scenarios on replication instance (Lab 43-16)
  - Troubleshot table-level errors during migration (Lab 43-17)
  - Resolved common DMS error codes
  - Optimized task settings for better performance
  - Implemented retry logic for failed tasks

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
