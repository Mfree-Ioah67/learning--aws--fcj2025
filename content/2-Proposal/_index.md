---
title: "Project Proposal"
date: 2025-09-10
weight: 2
chapter: false
pre: " <b> 2. </b> "
---

# Blood Donation Support System (BDSS)

<div class="download-section">
  <div class="download-card">
    <div class="download-icon">
      <svg width="48" height="48" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path d="M14 2H6C4.9 2 4 2.9 4 4V20C4 21.1 4.89 22 5.99 22H18C19.1 22 20 21.1 20 20V8L14 2Z" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
        <polyline points="14,2 14,8 20,8" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
        <line x1="16" y1="13" x2="8" y2="13" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
        <line x1="16" y1="17" x2="8" y2="17" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
        <polyline points="10,9 9,9 8,9" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
      </svg>
    </div>
    <div class="download-content">
      <h3>Complete Project Proposal</h3>
      <p>Download the full detailed proposal document with comprehensive analysis, technical specifications, and implementation roadmap.</p>
      <a href="Proposal%20Template.docx" class="download-btn" download>
        <svg width="20" height="20" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
          <path d="M21 15V19C21 19.5304 20.7893 20.0391 20.4142 20.4142C20.0391 20.7893 19.5304 21 19 21H5C4.46957 21 3.96086 20.7893 3.58579 20.4142C3.21071 20.0391 3 19.5304 3 19V15" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
          <polyline points="7,10 12,15 17,10" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
          <line x1="12" y1="15" x2="12" y2="3" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
        </svg>
        Download Word Document
      </a>
    </div>
  </div>
</div>

<style>
.download-section {
  margin: 2rem 0;
  display: flex;
  justify-content: center;
}

.download-card {
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  border-radius: 16px;
  padding: 2rem;
  max-width: 500px;
  width: 100%;
  color: white;
  box-shadow: 0 20px 40px rgba(102, 126, 234, 0.3);
  transition: all 0.3s ease;
  position: relative;
  overflow: hidden;
}

.download-card::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: linear-gradient(135deg, rgba(255,255,255,0.1) 0%, rgba(255,255,255,0.05) 100%);
  pointer-events: none;
}

.download-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 25px 50px rgba(102, 126, 234, 0.4);
}

.download-icon {
  text-align: center;
  margin-bottom: 1.5rem;
  opacity: 0.9;
}

.download-content h3 {
  margin: 0 0 1rem 0;
  font-size: 1.5rem;
  font-weight: 600;
  text-align: center;
}

.download-content p {
  margin: 0 0 1.5rem 0;
  opacity: 0.9;
  line-height: 1.6;
  text-align: center;
  font-size: 0.95rem;
}

.download-btn {
  display: inline-flex;
  align-items: center;
  gap: 0.5rem;
  background: rgba(255, 255, 255, 0.2);
  color: white;
  padding: 0.75rem 1.5rem;
  border-radius: 8px;
  text-decoration: none;
  font-weight: 500;
  transition: all 0.3s ease;
  backdrop-filter: blur(10px);
  border: 1px solid rgba(255, 255, 255, 0.3);
  width: 100%;
  justify-content: center;
}

.download-btn:hover {
  background: rgba(255, 255, 255, 0.3);
  transform: translateY(-2px);
  box-shadow: 0 10px 20px rgba(0, 0, 0, 0.2);
  color: white;
  text-decoration: none;
}

.download-btn svg {
  transition: transform 0.3s ease;
}

.download-btn:hover svg {
  transform: translateY(2px);
}

@media (max-width: 768px) {
  .download-card {
    margin: 1rem;
    padding: 1.5rem;
  }
  
  .download-content h3 {
    font-size: 1.3rem;
  }
  
  .download-content p {
    font-size: 0.9rem;
  }
}
</style>

## 1. Executive Summary

**Blood Donation Support System (BDSS)** is a web platform that supports blood donation management and connects blood donors with healthcare facilities. The project is developed by a student team in Ho Chi Minh City to optimize the blood donation process, reduce the burden of finding donors, and improve healthcare communication efficiency.

The system is built on **AWS Cloud architecture**, utilizing **Amazon EC2**, **Amazon RDS**, **API Gateway**, **Cognito**, and **CI/CD Pipeline (GitLab + CodePipeline)** for automated deployment. BDSS supports four user groups (Guest, Member, Staff, Admin), providing features for lookup, blood donation registration, blood bank management, donation process tracking, and visual reporting.

---

## 2. Problem Statement

### Current Problem:

Healthcare facilities are currently managing blood donation processes manually or through disparate tools. Finding suitable blood donors by blood type or location is challenging, especially in emergency situations. Additionally, the data storage system is not synchronized, making it difficult to analyze, report, and optimize blood donation campaigns.

### Proposed Solution:

Develop a **comprehensive blood donation support platform on AWS Cloud**, with features for blood donation management, finding donors and recipients by blood type or geographic location, integrating user authentication via Amazon Cognito, and data management on Amazon RDS.

The frontend is deployed via **Route 53 + CloudFront**, backend through **API Gateway – EC2**, MySQL database on **Amazon RDS**, and automated CI/CD pipeline using **GitLab – CodePipeline**.

### Benefits and ROI:

- Reduce 60–70% of time searching for suitable blood donors.
- Increase accuracy of blood type and location information.
- Optimize operational costs with flexible cloud architecture, pay-as-you-go pricing.
- Improve response capability in emergency blood situations.

---

## 3. Solution Architecture

### Overall Architecture:

![AWS Blood Donation Architecture](AWS%20architecture%20diagrams%20blood%20donation%20support%20systems.png)

The system is designed with a **3-tier architecture on AWS Cloud** with the following main components:

### 1. Frontend & Content Delivery Layer:

- **Users**: Access the system via web browsers or mobile devices.
- **Route 53**: DNS service managing domain names and routing traffic to CloudFront.
- **CloudFront**: CDN distributing static content with low latency, cached at edge locations.
- **Amazon S3**: Stores static assets (HTML, CSS, JS, images) for frontend application.

### 2. Application & Compute Layer:

- **API Gateway**: REST API endpoint, handling requests/responses between frontend and backend.
- **VPC (Virtual Private Cloud)**: Isolated virtual network with configuration:
  - **Internet Gateway**: Allows public subnet to connect to the Internet.
  - **Public Subnet**: Contains EC2 instances processing business logic.
  - **Private Subnet**: Contains RDS database, no direct Internet access.
  - **NAT Gateway**: Allows private subnet to access Internet outbound only.
- **Amazon EC2**: Compute instances running backend API (Node.js/Express).
- **Amazon RDS (MySQL)**: Relational database storing blood donor data, blood types, donation history.

### 3. CI/CD & DevOps Pipeline:

- **GitLab**: Source code repository and version control.
- **AWS CodePipeline**: Orchestrates automated CI/CD workflow.
- **AWS CodeBuild**: Builds and tests code before deployment.
- **Automated Deployment**: Automatically deploys to EC2 on code changes.

### 4. Monitoring, Security & Management Layer:

- **Amazon Cognito**: User authentication and authorization (Guest, Member, Staff, Admin roles).
- **AWS IAM**: Manages access permissions for users and services.
- **AWS Secrets Manager**: Securely stores database credentials and API keys.
- **Amazon CloudWatch**: Monitors metrics, logs, and creates alarms.
- **AWS CloudTrail**: Audit logs for all API calls and user activities.
- **Amazon Athena**: Queries and analyzes logs from S3.
- **Amazon SNS**: Sends notifications (email/SMS) for critical events (emergency blood needs, matching donors).

### System Workflow:

1. **User Access**: Users → Route 53 → CloudFront → S3 (Frontend)
2. **API Requests**: Frontend → API Gateway → EC2 (Backend) → RDS (Database)
3. **Data Flow**: EC2 instances in public subnet connect to RDS in private subnet
4. **Outbound Traffic**: Private subnet → NAT Gateway → Internet Gateway
5. **CI/CD Flow**: GitLab → CodePipeline → CodeBuild → EC2 deployment
6. **Monitoring**: CloudWatch collects metrics → SNS sends alerts → Athena analyzes logs

---

## 4. Technical Implementation

### Implementation Phases:

#### 1. Analysis & Design (Month 1)
- Gather requirements, define use cases, design ERD and AWS architecture.

#### 2. Infrastructure & Pipeline Setup (Month 2)
- Configure Route 53, CloudFront, EC2, RDS, and CI/CD on AWS.

#### 3. Development & Testing (Month 3–4)
- Build main modules: blood donation registration, search, blood bank management.
- Integrate Cognito and SNS alert system.

#### 4. Deployment & Operations (Month 5)
- Deploy production system and monitor with CloudWatch.

### Key Technical Requirements:

- **Frontend:** React/Next.js or Angular (deployed via S3/CloudFront).
- **Backend:** Node.js/Express on EC2, communicating via REST API Gateway.
- **Database:** Amazon RDS MySQL, optimized queries and periodic backups.
- **CI/CD:** GitLab → CodeBuild → CodePipeline → EC2.
- **Auth:** Cognito (4 roles: Guest, Member, Staff, Admin).
- **Alert & Logs:** SNS + CloudWatch + CloudTrail.

---

## 5. Roadmap & Milestones

| Timeline | Phase | Key Deliverables |
|----------|-------|------------------|
| **Month 1** | Requirements Analysis & Design | AWS architecture + use case diagrams |
| **Month 2** | Infrastructure & Pipeline Setup | EC2, RDS, API Gateway operational |
| **Month 3–4** | Development & Testing | Complete main modules |
| **Month 5** | Production Deployment | System operational and stable with Dashboard reports |

---

## 6. Budget Estimation

| Service | Estimated Cost/Month (USD) | Notes |
|---------|---------------------------|-------|
| EC2 (t3.nano) | 3.50 | Backend REST API |
| Amazon RDS (MySQL) | 2.80 | 20 GB storage |
| API Gateway | 0.50 | 5,000 requests |
| CloudFront + S3 | 0.80 | Website + CDN |
| Route 53 | 0.50 | Domain & DNS |
| Cognito | 0.10 | <100 users |
| CloudWatch + Logs | 0.30 | Monitoring and alerts |
| CI/CD (CodePipeline, CodeBuild) | 0.40 | Automated deployment |
| **Total** | **8.9 USD/month** | ~106.8 USD/year |

> Total costs can be adjusted based on AWS Free Tier or using spot instances.

---

## 7. Risk Assessment

| Risk | Impact | Probability | Mitigation Measures |
|------|--------|-------------|---------------------|
| Internet Connection Loss | Medium | Medium | Backup on EC2 instances |
| DDoS Attack | High | Low | AWS WAF + CloudFront |
| User Data Errors | High | Low | RDS backup + IAM access restrictions |
| Budget Overrun | Medium | Low | AWS budget alerts |
| CI/CD Pipeline Disruption | Low | Medium | Test pipeline before merge |

---

## 8. Expected Outcomes

- **Technical:** Cloud-native system, automated CI/CD, multi-user support with high security.
- **Application:** Helps healthcare facilities manage blood donations efficiently, minimizing manual processes.
- **Scalability:** Can be scaled to multiple hospitals, integrate AI for blood type demand analysis or predict upcoming donation drives.
