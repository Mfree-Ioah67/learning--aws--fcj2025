---
title: "Week 1 Worklog"
date: 2025-09-11
weight: 1
chapter: false
pre: " <b> 1.1. </b> "
---
{{% notice warning %}}
⚠️ **Note:** The following information is for reference purposes only. Please **do not copy verbatim** for your own report, including this warning.
{{% /notice %}}

### Week 1 Objectives:

* Connect and get acquainted with members of First Cloud Journey.
* Understand fundamental AWS services and learn to use both the AWS Management Console and AWS CLI.
* Grasp cloud computing concepts and the AWS ecosystem through guided video modules.

### Tasks to be carried out this week:


| Day | Task | Start Date | Completion Date | Reference Material |
|-----|------|------------|-----------------|--------------------|
| 1| - Get acquainted with FCJ members <br> - Read and take note of internship unit rules and regulations | 09/11/2025 | 09/11/2025 | |
| 2| - Learn about AWS and its types of services <br> &emsp;+ Understand Cloud Computing as on-demand delivery of IT resources <br> &emsp;+ Explore the benefits of cloud computing, including cost optimization, increased development speed, and global scalability <br> &emsp;+ Learn about core AWS service groups: Compute, Storage, Networking, and Database | 09/12/2025 | 09/12/2025 |https://cloudjourney.awsstudygroup.com/1-explore/ <hr> <a href="image1.png" target="_blank"><img src="/images/image1.png"> The differences of AWS</a>|
| 3| - Create AWS Free Tier account <br> - Learn about AWS Console & AWS CLI <br> - Practice: <br> &emsp;+ Create an AWS account and secure the root user with MFA <br> &emsp;+ Install and configure AWS CLI <br> &emsp;+ Use AWS CLI and AWS Management Console to perform basic operations in parallel <br> &emsp;+ Set up and use AWS Budgets to track and manage costs | 09/13/2025 | 09/13/2025 | https://000001.awsstudygroup.com/<hr> https://000007.awsstudygroup.com/ <hr>  https://000011.awsstudygroup.com/ <hr> <a href="image2.png" target="_blank"><img src="/images/image2.png"> AWS Services Management Tools</a> |
| 4| - Learn about the AWS Global Infrastructure <br> &emsp;+ Understand the core concepts of Data Centers, Availability Zones (AZs), and Regions <br> &emsp;+ Explore how AWS's global network and Edge Locations (PoPs) support services like CloudFront, WAF, and Route 53 <br> - Learn basic EC2: <br> &emsp;+ Instance types, AMI, EBS <br> &emsp;+ How to connect to an EC2 instance via SSH <br> &emsp;+ Understanding Elastic IP | 09/14/2025 | 09/14/2025 | https://000006.awsstudygroup.com/ <hr> https://000004.awsstudygroup.com/5-amazonec2basic/ <hr> https://000011.awsstudygroup.com/4-infras/ |
| 5| - Practice: <br> &emsp;+ Launch an EC2 instance <br> &emsp;+ Connect to an EC2 instance via SSH <br> &emsp;+ Attach an EBS volume to the instance <br> - Additional Research: <br> &emsp;+ Study the AWS Well-Architected Framework, focusing on its five pillars: Operational Excellence, Security, Reliability, Performance Efficiency, and Cost Optimization | 09/15/2025 | 09/15/2025 |https://000011.awsstudygroup.com <hr> https://cloudjourney.awsstudygroup.com/ |

### Week 1 Achievements:

* Understood what AWS is and its basic service groups, along with its core benefits.

  * Learned that cloud computing is the on-demand delivery of IT resources over the internet, with a pay-as-you-go pricing model.

  * Understood key advantages, including the ability to scale resources up or down, increased development speed, and the power to deploy applications globally using AWS's expansive infrastructure.

  * Mastered the basic service groups: Compute, Storage, Networking, Database, and more.

* Successfully created and configured an AWS Free Tier account.

  * Created an AWS account for practical, hands-on experience, and secured the root user account with multi-factor authentication (MFA).

  * Understood how to create and manage IAM users and groups for controlled access.

* Became familiar with the AWS Management Console and learned how to find, access, and use services via the web interface.

  * Used the console to explore and manage AWS services, understanding the distinction between the root account and IAM users.

* Installed and configured AWS CLI on the computer.

  * Understood that the AWS CLI is a command-line tool that allows you to interact with AWS services, providing an alternative to the Management Console.

  * Successfully configured the CLI with an access key and a secret key to authenticate and perform operations.

* Used AWS CLI to perform basic operations such as:

  * Check account and configuration information.

  * Retrieve the list of regions.

  * View EC2 service information.

  * Create and manage key pairs.

  * Check information about running services.

* Acquired the ability to connect between the web interface and CLI to manage AWS resources in parallel.

* Learned about key cost optimization methods and AWS support tiers.

  * Explored different pricing models, including On-Demand, Reserved Instances (RIs), Savings Plans, and Spot Instances, and understood when to use each for cost savings.

  * Learned about different AWS Support plans (Basic, Developer, Business, Enterprise) and the level of technical assistance each provides.

* Completed practical exercises and supplementary research.

  * Used AWS Budgets to create alerts for cost and usage thresholds.

  * Began studying the AWS Well-Architected Framework, understanding its role in building secure, high-performing, resilient, and efficient cloud infrastructure.

### Week 1 Challenges:

* Registering for AWS Free Tier: difficulty verifying the credit card or having the $1 authorization declined.  
* Account security: confusion between the root account and IAM users/groups when setting up MFA or managing permissions.  
* AWS CLI: installation and configuration errors (incorrect path, missing environment variables, mistyped Access Key/Secret Key).  
* EC2 connectivity: SSH failures due to wrong key pair, port 22 not opened in the security group, or incorrect .pem file permissions.  
* Cost management: unfamiliarity with AWS Budgets and difficulty estimating Free Tier resource usage.  
* Technical terminology overload: many industry-specific terms (on-demand, scalability, elasticity, regions, availability zones) causing confusion.  
* Volume of new knowledge: remembering numerous AWS services (EC2, S3, RDS, VPC, etc.) leading to information overload.  
* Service differentiation: difficulty understanding the distinctions between service groups (Compute vs. Storage vs. Networking).  
* Pricing models complexity: On-Demand, Reserved Instances, Spot Instances, Savings Plans are complex and challenging to apply appropriately.  
* Understanding the Well-Architected Framework: abstract concepts requiring time to map the five pillars into real-world practice.  
