---
title: "Week 8 Worklog"
date: 2025-10-27
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---

### Week 8 Objectives:

- Complete project proposal for Blood Donation Support System (BDSS)
- Design AWS cloud architecture
- Define technical stack and requirements
- Estimate budget and timeline

### Tasks to be carried out this week:

| Day | Task | Start Date | Completion Date | Reference Material |
|-----|------|------------|-----------------|-------------------|
| 1-2 | - Research blood donation system requirements <br> - Define project scope and objectives <br> - Identify user groups and features | 2025/10/27 | 2025/10/28 | Healthcare system case studies |
| 3-4 | - Design AWS architecture diagram <br>&emsp; + Frontend: Route 53, CloudFront, S3 <br>&emsp; + Backend: API Gateway, EC2, RDS <br>&emsp; + Security: Cognito, IAM <br> - Define tech stack: React+Vite, Spring Boot, MySQL | 2025/10/29 | 2025/10/30 | <https://aws.amazon.com/architecture/> |
| 5-6 | - Estimate AWS service costs <br> - Create implementation timeline <br> - Assess risks and mitigation strategies | 2025/10/31 | 2025/11/01 | <https://calculator.aws/> |
| 7 | - Finalize proposal document <br> - Prepare presentation <br> - Weekly review | 2025/11/02 | 2025/11/02 | Technical writing guidelines |

### Week 8 Achievements:

- **Completed Project Proposal:**
  - Researched blood donation management challenges and defined solution
  - Identified key problems: manual processes, inefficient donor search, lack of synchronization
  - Defined 4 user groups: Guest, Member, Staff, Admin

- **AWS Architecture Design:**
  - Designed 3-tier architecture: Frontend (Route 53, CloudFront, S3), Backend (API Gateway, EC2, RDS), Security (Cognito, IAM)
  - Created architecture diagram showing component interactions
  - Planned VPC with public/private subnets for security

- **Technical Stack:**
  - **Frontend:** React + Vite
  - **Backend:** Spring Boot on EC2
  - **Database:** MySQL on RDS
  - **Auth:** Cognito (4 roles)
  - **CI/CD:** GitLab → CodePipeline → EC2
  - **Monitoring:** CloudWatch, SNS

- **Budget & Timeline:**
  - Estimated ~$8.90/month for AWS services
  - Planned 5-month implementation timeline
  - Identified cost optimization with Free Tier

- **Risk Assessment:**
  - Identified technical, security, and budget risks
  - Defined mitigation strategies (backups, WAF, monitoring)

### Challenges Encountered:

- **Architecture Design:** Balancing simplicity with scalability → Used modular design
- **Cost Control:** Staying within budget → Leveraged Free Tier and right-sized instances
- **Security:** Health data compliance → Implemented encryption and strict IAM policies

### Key Learnings:

- Learned AWS architecture design principles
- Understood project planning and documentation importance
- Gained experience in cost estimation and risk assessment

### References:

**AWS Architecture:**
- [AWS Architecture Center](https://aws.amazon.com/architecture/) - Best practices and reference architectures
- [AWS Well-Architected Framework](https://aws.amazon.com/architecture/well-architected/) - Design principles
- [AWS Solutions Library](https://aws.amazon.com/solutions/) - Pre-built solutions

**AWS Services Documentation:**
- [Amazon EC2](https://docs.aws.amazon.com/ec2/) - Compute instances
- [Amazon RDS](https://docs.aws.amazon.com/rds/) - Managed database
- [Amazon API Gateway](https://docs.aws.amazon.com/apigateway/) - API management
- [Amazon Cognito](https://docs.aws.amazon.com/cognito/) - User authentication
- [AWS CodePipeline](https://docs.aws.amazon.com/codepipeline/) - CI/CD automation
- [Amazon CloudFront](https://docs.aws.amazon.com/cloudfront/) - Content delivery
- [Amazon SNS](https://docs.aws.amazon.com/sns/) - Notification service

**Cost Management:**
- [AWS Pricing Calculator](https://calculator.aws/) - Cost estimation tool
- [AWS Cost Management](https://aws.amazon.com/aws-cost-management/) - Cost optimization
- [AWS Free Tier](https://aws.amazon.com/free/) - Free tier details

**Project Management:**
- [Project Management Best Practices](https://www.pmi.org/) - PMI guidelines
- [Agile Methodology](https://www.agilealliance.org/) - Agile development
- [Risk Management Framework](https://www.nist.gov/cyberframework) - NIST framework

**Healthcare IT:**
- [HIPAA Compliance on AWS](https://aws.amazon.com/compliance/hipaa-compliance/) - Healthcare data security
- [Healthcare Solutions on AWS](https://aws.amazon.com/health/) - Industry solutions
