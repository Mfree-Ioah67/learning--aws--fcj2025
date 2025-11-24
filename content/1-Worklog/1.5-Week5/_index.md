---
title: "Week 5 Worklog"
date: 2025-10-06
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---

### Week 5 Objectives:

- Understand AWS Shared Responsibility Model and security best practices
- Master IAM fundamentals: Users, Groups, Roles, and Policies
- Learn AWS security services: KMS, Security Hub, CloudTrail
- Implement resource tagging and access control strategies
- Practice least privilege principle with IAM policies

### Tasks to be carried out this week:

| Day | Task | Start Date | Completion Date | Reference Material |
|-----|------|------------|-----------------|-------------------|
| 1 | - Study Shared Responsibility Model <br>&emsp; + AWS vs Customer responsibilities <br> - Learn IAM fundamentals: <br>&emsp; + Users, Groups, Roles, Policies <br>&emsp; + MFA and password policies | 2025/10/06 | 2025/10/06 | <https://docs.aws.amazon.com/IAM/> |
| 2 | - Deep dive into AWS security services: <br>&emsp; + Amazon Cognito for user authentication <br>&emsp; + AWS Organizations for multi-account management <br>&emsp; + AWS Identity Center (SSO) <br>&emsp; + KMS for encryption key management | 2025/10/07 | 2025/10/07 | <https://docs.aws.amazon.com/kms/> |
| 3 | - **Lab 18:** Security Hub implementation <br>&emsp; + Enable Security Hub <br>&emsp; + Review security scores <br> - **Lab 27:** Resource tagging <br>&emsp; + Create and manage tags <br>&emsp; + Filter resources by tags <br>&emsp; + Create Resource Groups | 2025/10/08 | 2025/10/08 | <https://000018.awsstudygroup.com/> <br> <https://000027.awsstudygroup.com/> |
| 4 | - **Lab 28:** IAM Policies and Roles <br>&emsp; + Create IAM users and policies <br>&emsp; + Configure IAM roles <br>&emsp; + Switch roles and test permissions <br>&emsp; + Implement tag-based access control | 2025/10/09 | 2025/10/09 | <https://000028.awsstudygroup.com/> |
| 5 | - **Lab 30:** IAM user restrictions <br>&emsp; + Create restriction policies <br>&emsp; + Test limited user permissions <br> - **Lab 44:** Advanced IAM <br>&emsp; + Create IAM groups and users <br>&emsp; + Configure switch role with IP/time restrictions | 2025/10/10 | 2025/10/10 | <https://000030.awsstudygroup.com/> <br> <https://000044.awsstudygroup.com/> |
| 6 | - **Lab 33:** KMS and CloudTrail <br>&emsp; + Create KMS keys <br>&emsp; + Encrypt S3 data <br>&emsp; + Enable CloudTrail logging <br>&emsp; + Query logs with Athena <br> - **Lab 48:** IAM roles vs Access keys | 2025/10/11 | 2025/10/11 | <https://000033.awsstudygroup.com/> <br> <https://000048.awsstudygroup.com/> |
| 7 | - **Lab 22:** Automation with Lambda <br>&emsp; + Create Lambda functions for EC2 start/stop <br>&emsp; + Configure Slack notifications <br> - Weekly review and cleanup | 2025/10/12 | 2025/10/12 | <https://000022.awsstudygroup.com/> |

### Week 5 Achievements:

- **IAM Mastery:**
  - Created and managed IAM users, groups, and roles
  - Implemented custom IAM policies with least privilege principle
  - Configured MFA for enhanced security
  - Understood policy evaluation logic and permission boundaries

- **Security Services:**
  - Enabled AWS Security Hub for centralized security monitoring
  - Reviewed security scores and compliance standards
  - Configured AWS Organizations for multi-account governance
  - Implemented AWS Identity Center for SSO access

- **Encryption & Key Management (Lab 33):**
  - Created and managed KMS customer-managed keys
  - Encrypted S3 objects with KMS keys
  - Configured key policies and grants
  - Enabled CloudTrail for API logging
  - Queried CloudTrail logs using Amazon Athena

- **Resource Tagging (Lab 27):**
  - Implemented tagging strategy for resource organization
  - Created tags using Console and CLI
  - Filtered resources by tags
  - Created Resource Groups for bulk management
  - Used tags for cost allocation and access control

- **Advanced IAM (Labs 28, 30, 44):**
  - Implemented tag-based access control (ABAC)
  - Created IAM roles with assume role policies
  - Configured switch role with IP and time restrictions
  - Tested permission boundaries and service control policies
  - Limited user actions based on resource tags

- **IAM Best Practices (Lab 48):**
  - Compared IAM roles vs access keys
  - Implemented IAM roles for EC2 instances
  - Eliminated hardcoded credentials
  - Configured temporary security credentials

- **Automation (Lab 22):**
  - Created Lambda functions for EC2 lifecycle management
  - Configured EventBridge rules for scheduling
  - Integrated Slack webhooks for notifications
  - Implemented tag-based automation

### Challenges Encountered:

- **Policy Syntax:** JSON policy syntax errors → Used IAM Policy Simulator to validate policies
- **Permission Denied:** User couldn't access resources → Added missing permissions and checked SCPs
- **KMS Key Policy:** Unable to use KMS key → Added IAM user/role to key policy
- **CloudTrail Logs:** Logs not appearing in S3 → Waited 15 minutes for log delivery
- **Switch Role Failed:** IP restriction blocking access → Updated condition to allow current IP
- **Tag Propagation:** Tags not applying to new resources → Enabled tag inheritance in Organizations
- **Lambda Timeout:** Function timing out → Increased timeout and optimized code

### References:

**AWS Official Documentation:**
- [AWS IAM User Guide](https://docs.aws.amazon.com/IAM/) - Complete IAM documentation
- [AWS Shared Responsibility Model](https://aws.amazon.com/compliance/shared-responsibility-model/) - Security responsibilities
- [AWS KMS](https://docs.aws.amazon.com/kms/) - Key Management Service guide
- [AWS Security Hub](https://docs.aws.amazon.com/securityhub/) - Security monitoring
- [AWS Organizations](https://docs.aws.amazon.com/organizations/) - Multi-account management
- [AWS CloudTrail](https://docs.aws.amazon.com/cloudtrail/) - API logging service
- [Amazon Cognito](https://docs.aws.amazon.com/cognito/) - User authentication

**AWS Workshops & Labs:**
- [Security Hub Workshop](https://000018.awsstudygroup.com/) - Lab 18: Security monitoring
- [Lambda Automation Workshop](https://000022.awsstudygroup.com/) - Lab 22: EC2 automation
- [Tagging Workshop](https://000027.awsstudygroup.com/) - Lab 27: Resource tagging
- [IAM Workshop](https://000028.awsstudygroup.com/) - Lab 28: IAM policies and roles
- [IAM Restrictions Workshop](https://000030.awsstudygroup.com/) - Lab 30: User limitations
- [KMS Workshop](https://000033.awsstudygroup.com/) - Lab 33: Encryption and logging
- [Advanced IAM Workshop](https://000044.awsstudygroup.com/) - Lab 44: Advanced IAM
- [IAM Roles Workshop](https://000048.awsstudygroup.com/) - Lab 48: Roles vs access keys

**Technical Articles:**
- [IAM Best Practices](https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html) - Security recommendations
- [IAM Policy Evaluation Logic](https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies_evaluation-logic.html) - How policies work
- [Tagging Best Practices](https://docs.aws.amazon.com/general/latest/gr/aws_tagging.html) - Tagging strategies
- [KMS Best Practices](https://docs.aws.amazon.com/kms/latest/developerguide/best-practices.html) - Key management guide
- [CloudTrail Best Practices](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/best-practices-security.html) - Logging recommendations
