---
title: "Week 3 Worklog"
date: 2025-09-22
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---

### Week 3 Objectives:

- Master AWS Compute services with focus on EC2 fundamentals
- Understand EC2 instance types, storage options, and lifecycle management
- Learn AWS Backup strategies and disaster recovery concepts
- Explore Storage Gateway for hybrid cloud storage solutions
- Deploy static websites using S3 and CloudFront

### Tasks to be carried out this week:

| Day | Task | Start Date | Completion Date | Reference Material |
|-----|------|------------|-----------------|-------------------|
| 1 | - Study Compute VM on AWS <br>&emsp; + EC2 Instance Types and use cases <br>&emsp; + Amazon Lightsail overview <br>&emsp; + EFS/FSx file systems <br>&emsp; + AWS MGN for migrations | 2025/09/22 | 2025/09/22 | <https://aws.amazon.com/ec2/instance-types/> |
| 2 | - Deep dive into EC2 components: <br>&emsp; + AMI creation and management <br>&emsp; + Backup strategies <br>&emsp; + Key Pair authentication <br>&emsp; + Elastic Block Store (EBS) types <br>&emsp; + Instance Store characteristics | 2025/09/23 | 2025/09/23 | <https://docs.aws.amazon.com/ec2/> |
| 3 | - Learn EC2 advanced features: <br>&emsp; + User Data for bootstrapping <br>&emsp; + Instance Metadata service <br>&emsp; + EC2 Auto Scaling configuration <br> - **Lab 13:** Deploy AWS Backup <br>&emsp; + Create backup plans <br>&emsp; + Test restore procedures | 2025/09/24 | 2025/09/24 | <https://000013.awsstudygroup.com/> |
| 4 | - **Lab 24:** Storage Gateway implementation <br>&emsp; + Create S3 bucket <br>&emsp; + Deploy EC2 for Storage Gateway <br>&emsp; + Configure File Gateway <br>&emsp; + Create File Shares | 2025/09/25 | 2025/09/25 | <https://000024.awsstudygroup.com/> |
| 5 | - **Lab 57:** Static Website Hosting <br>&emsp; + Create S3 bucket and load data <br>&emsp; + Enable static website feature <br>&emsp; + Configure public access <br>&emsp; + Test website functionality | 2025/09/26 | 2025/09/26 | <https://000057.awsstudygroup.com/> |
| 6 | - Continue Lab 57: <br>&emsp; + Block public access <br>&emsp; + Configure CloudFront distribution <br>&emsp; + Enable bucket versioning <br>&emsp; + Configure cross-region replication | 2025/09/27 | 2025/09/27 | <https://000057.awsstudygroup.com/> |
| 7 | - Weekly review and cleanup <br> - Complete all lab resource cleanup <br> - Document learnings and best practices | 2025/09/28 | 2025/09/28 | |

### Week 3 Achievements:

- **EC2 Mastery:**
  - Understood different instance types: General Purpose (T3, M5), Compute Optimized (C5), Memory Optimized (R5)
  - Learned instance lifecycle: Launch, Stop, Terminate, Hibernate
  - Configured User Data scripts for automated instance setup
  - Accessed Instance Metadata for dynamic configuration

- **Storage Solutions:**
  - Compared EBS volume types: gp3, io2, st1, sc1
  - Understood Instance Store vs EBS trade-offs
  - Created and managed AMIs for backup and replication
  - Implemented EBS snapshots and lifecycle policies

- **AWS Backup Implementation (Lab 13):**
  - Deployed infrastructure with EC2 and RDS instances
  - Created backup plans with retention policies
  - Successfully tested restore procedures
  - Verified backup compliance and recovery time objectives

- **Storage Gateway Configuration (Lab 24):**
  - Deployed File Gateway on EC2 instance
  - Connected on-premises applications to S3 via NFS/SMB
  - Configured file shares with appropriate permissions
  - Tested hybrid cloud storage workflows

- **Static Website Hosting (Lab 57):**
  - Configured S3 bucket for static website hosting
  - Implemented CloudFront for global content delivery
  - Enabled versioning for content rollback capability
  - Set up cross-region replication for disaster recovery
  - Optimized costs by blocking direct S3 public access

- **Auto Scaling:**
  - Configured Launch Templates with proper AMI and instance settings
  - Created Auto Scaling Groups with min/max/desired capacity
  - Set up scaling policies based on CloudWatch metrics
  - Tested scale-out and scale-in behaviors

### Challenges Encountered:

- **Instance Type Selection:** Confused between T3 and T3a instances → Learned T3a uses AMD processors at lower cost
- **User Data Execution:** Script didn't run on first boot → Added proper shebang (`#!/bin/bash`) and verified logs in `/var/log/cloud-init-output.log`
- **Backup Restore Time:** RDS restore took longer than expected → Understood that larger databases require more time for restoration
- **Storage Gateway Activation:** Gateway failed to activate → Ensured proper security group rules for ports 80, 443, 1026-1028, 2049
- **CloudFront Propagation:** Distribution took 15-20 minutes to deploy → Learned this is normal for global edge location updates
- **S3 Versioning Costs:** Noticed increased storage costs → Implemented lifecycle policies to delete old versions after 30 days
- **Auto Scaling Delays:** Instances took time to become healthy → Adjusted health check grace period to 300 seconds

### References:

**AWS Official Documentation:**
- [Amazon EC2 Instance Types](https://aws.amazon.com/ec2/instance-types/) - Complete instance type comparison
- [Amazon EC2 User Guide](https://docs.aws.amazon.com/ec2/) - Comprehensive EC2 documentation
- [Amazon EBS Volume Types](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-volume-types.html) - Storage performance guide
- [AWS Backup Documentation](https://docs.aws.amazon.com/aws-backup/) - Backup and restore guide
- [AWS Storage Gateway](https://docs.aws.amazon.com/storagegateway/) - Hybrid storage solutions
- [Amazon S3 Static Website Hosting](https://docs.aws.amazon.com/AmazonS3/latest/userguide/WebsiteHosting.html) - Website hosting guide
- [Amazon CloudFront](https://docs.aws.amazon.com/cloudfront/) - CDN documentation
- [EC2 Auto Scaling](https://docs.aws.amazon.com/autoscaling/ec2/) - Auto Scaling guide

**AWS Workshops & Labs:**
- [AWS Backup Workshop](https://000013.awsstudygroup.com/) - Lab 13: Deploy AWS Backup
- [Storage Gateway Workshop](https://000024.awsstudygroup.com/) - Lab 24: File Gateway implementation
- [S3 Static Website Workshop](https://000057.awsstudygroup.com/) - Lab 57: Static website with CloudFront

**Technical Articles:**
- [EC2 Instance Metadata](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-instance-metadata.html) - Metadata service guide
- [User Data and Shell Scripts](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/user-data.html) - Bootstrap automation
- [EBS vs Instance Store](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/Storage.html) - Storage comparison
- [S3 Versioning Best Practices](https://docs.aws.amazon.com/AmazonS3/latest/userguide/Versioning.html) - Version control guide
- [CloudFront Best Practices](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/best-practices.html) - CDN optimization
- [Auto Scaling Best Practices](https://docs.aws.amazon.com/autoscaling/ec2/userguide/as-best-practices.html) - Scaling strategies
