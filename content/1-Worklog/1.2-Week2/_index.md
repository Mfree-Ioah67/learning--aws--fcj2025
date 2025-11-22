---
title: "Week 2 Worklog"
date: 2025-09-15
weight: 2
chapter: false
pre: " <b> 1.2. </b> "
---

### Week 2 Objectives:

- Deep dive into AWS networking fundamentals and VPC architecture
- Master EC2 instance management and storage configuration
- Understand VPC connectivity patterns: Peering and Transit Gateway

### Tasks to be carried out this week:

| Day | Task                                                                                                                                                                                                                         | Start Date | Completion Date | Reference Material                  |
| --- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------- | --------------- | ----------------------------------- |
| 1   | - Study AWS core services overview <br>&emsp; + Compute (EC2, Lambda) <br>&emsp; + Storage (S3, EBS) <br>&emsp; + Networking (VPC, Route53) <br> - Learn VPC fundamentals: CIDR blocks, Subnets, Route Tables                | 2025/09/15 | 2025/09/15      | <https://000003.awsstudygroup.com/> |
| 2   | - **Hands-on Practice:** <br>&emsp; + Generate IAM Access Keys <br>&emsp; + Install and configure AWS CLI <br>&emsp; + Test CLI with basic commands <br>&emsp; + Verify credentials and default region                       | 2025/09/16 | 2025/09/16      | <https://000003.awsstudygroup.com/> |
| 3   | - Deep dive into EC2: <br>&emsp; + Instance types and use cases <br>&emsp; + AMI selection <br>&emsp; + EBS volume types <br> - Learn network security: Security Groups vs NACLs <br> - Configure VPC Flow Logs              | 2025/09/17 | 2025/09/17      | <https://000019.awsstudygroup.com/> |
| 4   | - **Lab Session:** <br>&emsp; + Launch EC2 instance with custom configuration <br>&emsp; + SSH key pair setup and connection <br>&emsp; + Create and attach EBS volume <br> - Study VPC Peering architecture and limitations | 2025/09/18 | 2025/09/18      | <https://000019.awsstudygroup.com/> |
| 5   | - Learn AWS Transit Gateway architecture <br> - Compare connectivity options: <br>&emsp; + VPC Peering (1-to-1) <br>&emsp; + Transit Gateway (hub-and-spoke) <br> - Configure Transit Gateway with multiple VPC attachments  | 2025/09/19 | 2025/09/19      | <https://000020.awsstudygroup.com/> |
| 6   | - Weekly knowledge review <br> - Practice troubleshooting common VPC issues <br> - Document learnings and best practices                                                                                                     | 2025/09/20 | 2025/09/20      |                                     |
| 7   | - Final testing of all configurations <br> - Complete weekly report <br> - Self-assessment and knowledge gaps identification                                                                                                 | 2025/09/21 | 2025/09/21      |                                     |

### Week 2 Achievements:

- Mastered VPC architecture: CIDR planning, subnets, route tables, Internet Gateway, NAT Gateway
- Configured AWS CLI and executed commands: `aws configure`, `aws ec2 describe-instances`, `aws s3 ls`
- Launched EC2 instance, established SSH connection, attached EBS volume, assigned Elastic IP
- Implemented Security Groups and NACLs for network security
- Enabled VPC Flow Logs for traffic monitoring
- Configured VPC Peering between two VPCs with proper route table updates
- Deployed AWS Transit Gateway as centralized connectivity hub for multiple VPCs
- Completed weekly objectives and documented all configurations

### Challenges Encountered:

- **CIDR Overlap:** VPC Peering failed due to overlapping CIDR blocks → Redesigned with non-overlapping ranges
- **SSH Timeout:** Missing Security Group inbound rule for port 22 → Added SSH rule for specific IP
- **NAT Gateway Costs:** Discovered hourly charges → Documented cost comparison for future reference
- **Route Misconfiguration:** Private subnet couldn't reach internet → Added default route to NAT Gateway
- **Transit Gateway Delays:** Attachments stayed in pending state → Waited 5-10 minutes for propagation
- **Flow Logs Storage:** High CloudWatch costs → Switched to S3 destination for cost optimization

### References:

**AWS Official Documentation:**
- [What is Amazon VPC?](https://docs.aws.amazon.com/vpc/latest/userguide/what-is-amazon-vpc.html) - AWS VPC User Guide
- [Amazon EC2 User Guide](https://docs.aws.amazon.com/ec2/index.html) - Complete EC2 documentation
- [AWS CLI Command Reference](https://docs.aws.amazon.com/cli/latest/reference/) - AWS CLI documentation
- [VPC Peering Guide](https://docs.aws.amazon.com/vpc/latest/peering/what-is-vpc-peering.html) - VPC Peering connections
- [AWS Transit Gateway](https://docs.aws.amazon.com/vpc/latest/tgw/what-is-transit-gateway.html) - Transit Gateway documentation

**AWS Workshops & Tutorials:**
- [AWS VPC Workshop](https://000003.awsstudygroup.com/) - Hands-on VPC configuration
- [EC2 Workshop](https://000019.awsstudygroup.com/) - EC2 instance management
- [Transit Gateway Workshop](https://000020.awsstudygroup.com/) - Transit Gateway setup

**Technical Articles:**
- [VPC Design Best Practices](https://aws.amazon.com/blogs/networking-and-content-delivery/vpc-sharing-a-new-approach-to-multiple-accounts-and-vpc-management/) - AWS Networking Blog
- [Security Groups vs NACLs](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-network-acls.html) - Understanding network security
- [VPC Flow Logs Analysis](https://aws.amazon.com/blogs/aws/vpc-flow-logs-log-and-view-network-traffic-flows/) - Traffic monitoring guide
- [Cost Optimization for NAT Gateway](https://aws.amazon.com/blogs/architecture/reduce-nat-gateway-costs-by-using-vpc-endpoints/) - Cost reduction strategies
