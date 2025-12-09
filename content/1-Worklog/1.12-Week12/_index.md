---
title: "Week 12 Worklog"
date: 2025-11-24
weight: 12
chapter: false
pre: " <b> 1.12. </b> "
---

### Week 12 Objectives:

- Set up CI/CD pipeline with AWS CodePipeline
- Implement monitoring and logging
- Perform testing and bug fixes
- Complete project documentation

### Tasks to be carried out this week:

| Day | Task | Start Date | Completion Date | Reference Material |
|-----|------|------------|-----------------|-------------------|
| 1-2 | - Set up CI/CD pipeline <br>&emsp; + Configure AWS CodePipeline <br>&emsp; + Connect to Git repository <br>&emsp; + Automate build and deploy <br> - Test automated deployment | 2025/11/24 | 2025/11/25 | AWS CodePipeline docs |
| 3-4 | - Implement monitoring <br>&emsp; + CloudWatch logs for backend <br>&emsp; + CloudWatch metrics <br>&emsp; + Set up alarms <br> - Configure API Gateway logging | 2025/11/26 | 2025/11/27 | AWS CloudWatch docs |
| 5-6 | - Comprehensive testing <br>&emsp; + Unit tests for backend <br>&emsp; + Integration tests <br>&emsp; + Frontend E2E tests <br> - Bug fixes and optimization | 2025/11/28 | 2025/11/29 | Testing best practices |
| 7 | - Complete documentation <br>&emsp; + README files <br>&emsp; + API documentation <br>&emsp; + Deployment guide <br> - Project presentation preparation | 2025/11/30 | 2025/11/30 | Documentation standards |

### Week 12 Achievements:

- **CI/CD Pipeline:**
  - Configured AWS CodePipeline for automated deployment
  - Connected pipeline to Git repository
  - Set up build stage with CodeBuild
  - Automated backend deployment to EC2
  - Automated frontend deployment to S3 with CloudFront invalidation
  - Tested complete CI/CD flow: Git push → Build → Deploy

- **Monitoring & Logging:**
  - Configured CloudWatch Logs for Spring Boot application
  - Set up CloudWatch metrics for EC2 and RDS
  - Created CloudWatch alarms for high CPU and memory usage
  - Enabled API Gateway access logs
  - Implemented application-level logging with proper log levels

- **Testing & Quality:**
  - Wrote unit tests for backend services (JUnit)
  - Created integration tests for API endpoints
  - Performed manual E2E testing for all user flows
  - Fixed bugs discovered during testing
  - Optimized database queries for better performance

- **Documentation:**
  - Created comprehensive README with setup instructions
  - Documented all API endpoints with request/response examples
  - Wrote deployment guide for team members
  - Prepared project presentation slides
  - Documented architecture decisions and trade-offs

### Challenges Encountered:

- **CodePipeline Configuration:** Build failures → Fixed Maven dependencies and build script
- **CloudWatch Logs:** Logs not appearing → Configured IAM role for EC2 CloudWatch access
- **Performance Issues:** Slow API responses → Added database indexes and query optimization

### Key Learnings:

- Mastered AWS CI/CD pipeline setup
- Understood importance of monitoring and logging in production
- Learned testing strategies for full-stack applications
- Improved documentation and communication skills

### Project Summary:

Successfully completed Blood Donation Support System with:
- **Frontend:** React + Vite deployed on S3/CloudFront
- **Backend:** Spring Boot deployed on EC2
- **Database:** MySQL on RDS
- **CI/CD:** Automated pipeline with CodePipeline
- **Monitoring:** CloudWatch logs and metrics
- **Security:** JWT authentication, HTTPS, Security Groups

### References:

- [AWS CodePipeline](https://docs.aws.amazon.com/codepipeline/)
- [CloudWatch Monitoring](https://docs.aws.amazon.com/cloudwatch/)
- [JUnit Testing](https://junit.org/junit5/)
- [API Documentation](https://swagger.io/)
