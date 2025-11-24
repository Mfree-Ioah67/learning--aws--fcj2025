---
title: "Week 4 Worklog"
date: 2025-09-29
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---

### Week 4 Objectives:

- Master AWS Storage services with focus on S3 fundamentals
- Understand S3 storage classes, lifecycle policies, and access control
- Learn hybrid storage solutions: Snow Family and Storage Gateway
- Explore FSx for Windows File Server capabilities
- Practice VM migration from on-premises to AWS

### Tasks to be carried out this week:

| Day | Task                                                                                                                                                                                                                                   | Start Date | Completion Date | Reference Material                                                           |
| --- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------- | --------------- | ---------------------------------------------------------------------------- |
| 1   | - Study AWS Storage Services overview <br>&emsp; + S3 fundamentals and use cases <br>&emsp; + S3 Access Points and Storage Classes <br>&emsp; + S3 Glacier for archival                                                                | 2025/09/29 | 2025/09/29      | <https://docs.aws.amazon.com/s3/>                                            |
| 2   | - Deep dive into S3 features: <br>&emsp; + Static website hosting and CORS <br>&emsp; + Access control (IAM, Bucket Policies, ACLs) <br>&emsp; + Object keys and performance optimization <br> - Learn Snow Family and Storage Gateway | 2025/09/30 | 2025/09/30      | <https://docs.aws.amazon.com/storagegateway/>                                |
| 3   | - **Lab 13:** AWS Backup implementation <br>&emsp; + Create S3 bucket and infrastructure <br>&emsp; + Configure backup plans <br>&emsp; + Set up notifications <br>&emsp; + Test restore procedures                                    | 2025/10/01 | 2025/10/01      | <https://000013.awsstudygroup.com/>                                          |
| 4   | - **Lab 14:** VM Import/Export <br>&emsp; + Export VM from VMware Workstation <br>&emsp; + Upload to S3 and import to AWS <br>&emsp; + Deploy instance from AMI <br>&emsp; + Export VM back from AWS                                   | 2025/10/02 | 2025/10/02      | <https://000014.awsstudygroup.com/>                                          |
| 5   | - **Lab 24:** Storage Gateway setup <br>&emsp; + Create File Gateway <br>&emsp; + Configure file shares <br>&emsp; + Mount shares on on-premises machine <br> - **Lab 57:** S3 static website (Part 1)                                 | 2025/10/03 | 2025/10/03      | <https://000024.awsstudygroup.com/> <br> <https://000057.awsstudygroup.com/> |
| 6   | - **Lab 25:** FSx for Windows File Server <br>&emsp; + Create Multi-AZ file systems (SSD & HDD) <br>&emsp; + Test and monitor performance <br>&emsp; + Enable deduplication and shadow copies <br>&emsp; + Configure user quotas       | 2025/10/04 | 2025/10/04      | <https://000025.awsstudygroup.com/>                                          |
| 7   | - Complete Lab 57: CloudFront integration <br> - Weekly review and cleanup all resources <br> - Document learnings                                                                                                                     | 2025/10/05 | 2025/10/05      |                                                                              |

### Week 4 Achievements:

- **S3 Mastery:**

  - Understood S3 storage classes: Standard, IA, One Zone-IA, Glacier, Deep Archive
  - Configured bucket policies, ACLs, and access points for secure access
  - Implemented lifecycle policies for cost optimization
  - Enabled versioning and cross-region replication

- **AWS Backup (Lab 13):**

  - Created automated backup plans for EC2 and RDS
  - Configured backup retention and lifecycle policies
  - Set up SNS notifications for backup events
  - Successfully restored resources from backups

- **VM Migration (Lab 14):**

  - Exported VMs from VMware Workstation to OVA format
  - Uploaded VM images to S3 using AWS CLI
  - Imported VMs as AMIs using VM Import/Export
  - Deployed EC2 instances from imported AMIs
  - Exported running instances back to VM format

- **Storage Gateway (Lab 24):**

  - Deployed File Gateway on EC2
  - Created NFS/SMB file shares backed by S3
  - Mounted shares on on-premises Windows/Linux machines
  - Tested file synchronization between on-premises and S3

- **FSx for Windows (Lab 25):**

  - Created Multi-AZ file systems with SSD and HDD storage
  - Tested performance differences between storage types
  - Enabled data deduplication to reduce storage costs
  - Configured shadow copies for file recovery
  - Set up user storage quotas
  - Scaled throughput and storage capacity

- **S3 Static Website (Lab 57):**
  - Hosted static website on S3 with custom domain
  - Configured CloudFront for global content delivery
  - Implemented bucket versioning for rollback capability
  - Set up cross-region replication for disaster recovery

### Challenges Encountered:

- **S3 Bucket Naming:** Bucket name already taken globally → Used unique naming convention with account ID
- **VM Import Size:** Large VM took hours to upload → Used multipart upload and S3 Transfer Acceleration
- **Storage Gateway Activation:** Failed to activate gateway → Verified security group allowed ports 80, 443, 1026-1028, 2049
- **FSx Performance:** Initial throughput lower than expected → Increased throughput capacity from 8 MB/s to 64 MB/s
- **CloudFront Cache:** Website changes not reflecting immediately → Learned about cache invalidation and TTL settings
- **Cross-Region Replication:** Objects not replicating → Enabled versioning on both source and destination buckets
- **Backup Costs:** High storage costs for frequent backups → Adjusted retention policy and moved old backups to Glacier

### References:

**AWS Official Documentation:**

- [Amazon S3 User Guide](https://docs.aws.amazon.com/s3/) - Complete S3 documentation
- [S3 Storage Classes](https://aws.amazon.com/s3/storage-classes/) - Storage class comparison
- [AWS Backup](https://docs.aws.amazon.com/aws-backup/) - Backup service guide
- [VM Import/Export](https://docs.aws.amazon.com/vm-import/) - VM migration guide
- [AWS Storage Gateway](https://docs.aws.amazon.com/storagegateway/) - Hybrid storage documentation
- [Amazon FSx for Windows](https://docs.aws.amazon.com/fsx/latest/WindowsGuide/) - FSx documentation
- [Amazon CloudFront](https://docs.aws.amazon.com/cloudfront/) - CDN documentation

**AWS Workshops & Labs:**

- [AWS Backup Workshop](https://000013.awsstudygroup.com/) - Lab 13: Backup implementation
- [VM Import Workshop](https://000014.awsstudygroup.com/) - Lab 14: VM migration
- [Storage Gateway Workshop](https://000024.awsstudygroup.com/) - Lab 24: File Gateway setup
- [FSx Workshop](https://000025.awsstudygroup.com/) - Lab 25: FSx for Windows
- [S3 Static Website Workshop](https://000057.awsstudygroup.com/) - Lab 57: Website hosting

**Technical Articles:**

- [S3 Performance Optimization](https://docs.aws.amazon.com/AmazonS3/latest/userguide/optimizing-performance.html) - Performance best practices
- [S3 Security Best Practices](https://docs.aws.amazon.com/AmazonS3/latest/userguide/security-best-practices.html) - Security guide
- [Storage Gateway Best Practices](https://docs.aws.amazon.com/storagegateway/latest/userguide/Performance.html) - Performance tuning
- [FSx Performance](https://docs.aws.amazon.com/fsx/latest/WindowsGuide/performance.html) - FSx optimization guide
