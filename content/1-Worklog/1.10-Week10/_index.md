---
title: "Week 10 Worklog"
date: 2025-11-10
weight: 10
chapter: false
pre: " <b> 1.10. </b> "
---

### Week 10 Objectives:

- Develop core backend APIs with Spring Boot
- Implement database models and repositories
- Set up JWT authentication
- Deploy backend to EC2

### Tasks to be carried out this week:

| Day | Task | Start Date | Completion Date | Reference Material |
|-----|------|------------|-----------------|-------------------|
| 1-3 | - Design database schema (ERD) <br> - Create JPA entities and repositories <br> - Implement user authentication APIs <br>&emsp; + Register, Login, Logout <br>&emsp; + JWT token generation | 2025/11/10 | 2025/11/12 | Spring Boot JPA docs |
| 4-5 | - Develop blood donation APIs <br>&emsp; + Create donation request <br>&emsp; + Search donors by blood type <br>&emsp; + Update donation status <br> - Test APIs with Postman | 2025/11/13 | 2025/11/14 | REST API best practices |
| 6-7 | - Build JAR file with Maven <br> - Deploy backend to EC2 <br>&emsp; + Upload JAR to S3 <br>&emsp; + Configure EC2 with Java <br>&emsp; + Run Spring Boot application <br> - Test deployed APIs | 2025/11/15 | 2025/11/16 | AWS EC2, S3 docs |

### Week 10 Achievements:

- **Backend Development:**
  - Designed database schema with 5 main tables: Users, BloodDonations, Donors, Hospitals, DonationHistory
  - Created JPA entities with relationships (OneToMany, ManyToOne)
  - Implemented Spring Data JPA repositories
  - Built authentication system with JWT tokens
  - Developed RESTful APIs for user management and blood donations

- **API Implementation:**
  - User APIs: Register, Login, Get Profile, Update Profile
  - Donation APIs: Create Request, Search Donors, Update Status, Get History
  - Implemented proper error handling and validation
  - Tested all endpoints with Postman

- **Backend Deployment:**
  - Built JAR file using Maven: `mvn clean package`
  - Uploaded JAR to S3 bucket for artifact storage
  - Configured EC2 instance with Java 17
  - Deployed Spring Boot application on EC2
  - Configured application.properties with RDS connection
  - Verified APIs working on EC2

### Challenges Encountered:

- **JPA Relationships:** Circular dependency issues → Used `@JsonIgnore` and DTOs
- **JWT Implementation:** Token expiration handling → Implemented refresh token mechanism
- **EC2 Deployment:** Port 8080 not accessible → Configured Security Group inbound rules

### Key Learnings:

- Mastered Spring Boot REST API development
- Understood JPA entity relationships and lazy loading
- Learned EC2 deployment process for Java applications

### References:

- [Spring Boot JPA](https://spring.io/guides/gs/accessing-data-jpa/)
- [JWT Authentication](https://jwt.io/introduction)
- [AWS EC2 Deployment](https://docs.aws.amazon.com/ec2/)
