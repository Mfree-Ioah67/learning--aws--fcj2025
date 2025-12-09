---
title: "Week 9 Worklog"
date: 2025-11-03
weight: 9
chapter: false
pre: " <b> 1.9. </b> "
---

### Week 9 Objectives:

- Finalize project proposal and get approval
- Set up development environment
- Initialize project structure for Frontend and Backend
- Configure AWS infrastructure foundation

### Tasks to be carried out this week:

| Day | Task | Start Date | Completion Date | Reference Material |
|-----|------|------------|-----------------|-------------------|
| 1-2 | - Present project proposal to team <br> - Get feedback and approval <br> - Finalize technical requirements | 2025/11/03 | 2025/11/04 | Project proposal document |
| 3-4 | - Set up development environment <br>&emsp; + Install Node.js, Maven, AWS CLI <br>&emsp; + Configure Git repository <br> - Initialize project structure <br>&emsp; + Create React + Vite frontend <br>&emsp; + Create Spring Boot backend | 2025/11/05 | 2025/11/06 | <https://vitejs.dev/> <br> <https://spring.io/> |
| 5-7 | - Configure AWS foundation <br>&emsp; + Create VPC and subnets <br>&emsp; + Set up Security Groups <br>&emsp; + Create RDS MySQL database <br>&emsp; + Configure S3 buckets <br> - Test database connectivity | 2025/11/07 | 2025/11/09 | <https://docs.aws.amazon.com/> |

### Week 9 Achievements:

- **Proposal Approval:**
  - Presented Blood Donation Support System proposal
  - Received approval from mentors and team
  - Finalized technical stack: React+Vite, Spring Boot, MySQL on RDS

- **Development Environment:**
  - Installed and configured development tools
  - Set up Git repository for version control
  - Created project structure with separate FE and BE folders
  - Initialized React frontend with Vite build tool
  - Created Spring Boot backend with Maven

- **AWS Infrastructure Setup:**
  - Created VPC with public and private subnets
  - Configured Security Groups for EC2, RDS, and ALB
  - Provisioned RDS MySQL database instance
  - Created S3 buckets for frontend hosting and backend artifacts
  - Tested database connection from local environment

### Challenges Encountered:

- **VPC Configuration:** Understanding subnet routing → Studied AWS VPC documentation
- **RDS Connectivity:** Connection timeout issues → Configured Security Group inbound rules properly
- **Project Structure:** Organizing monorepo → Separated FE, BE, and AWS folders

### Key Learnings:

- Learned VPC networking basics and subnet design
- Understood RDS security group configuration
- Gained experience with project initialization and structure

### References:

- [React + Vite](https://vitejs.dev/guide/)
- [Spring Boot](https://spring.io/guides/gs/spring-boot/)
- [AWS VPC](https://docs.aws.amazon.com/vpc/)
- [Amazon RDS](https://docs.aws.amazon.com/rds/)
