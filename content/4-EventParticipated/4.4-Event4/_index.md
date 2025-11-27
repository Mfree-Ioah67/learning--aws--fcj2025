---
title: "DevOps on AWS Workshop"
date: 2025-11-17
weight: 4
chapter: false
pre: " <b> 4.4. </b> "
---

{{% notice warning %}}
⚠️ **Note:** The information below is for reference purposes only. Please **do not copy it verbatim** into your report, including this warning.
{{% /notice %}}

# Summary Report: "DevOps on AWS Workshop"

### Event Objectives

- Understand DevOps culture, principles, and best practices
- Learn AWS DevOps services for CI/CD automation
- Explore Infrastructure as Code with CloudFormation and CDK
- Master container services: ECR, ECS, EKS, and App Runner
- Implement monitoring and observability with CloudWatch and X-Ray
- Apply DevOps practices to real-world scenarios

### Event Details

- **Location**: AWS Vietnam Office
- **Date & Time**: 8:30 AM – 5:00 PM, Monday, November 17, 2025

### Speakers & Facilitators

**Instructors:**

- **Truong Quang Tinh** – AWS Community Builder – DevOps Culture and CI/CD Fundamentals
- **Van Hoang Kha** – AWS Community Builder – Infrastructure as Code with CloudFormation
- **Nguyen Khanh Phuc Thinh** – AWS Community Builder – AWS CDK Deep Dive
- **Le Huynh Nghiem** – AWS Community Builder – Container Services on AWS
- **Huynh Hoang Long** – AWS Community Builder – Monitoring and Observability
- **Pham Hoang Quy** – AWS Community Builder – DevOps Best Practices and Case Studies

**Facilitators:**

- **AWS Vietnam Team**
- **AWS Community Builders Vietnam**

### Event Agenda

#### 8:30 AM - 9:00 AM: Registration and Welcome

- Registration and networking
- Welcome remarks and workshop overview
- Introduction to AWS DevOps services

#### 9:00 AM - 10:30 AM: DevOps Culture and CI/CD Pipeline

**Presented by Truong Quang Tinh**

- **DevOps Mindset**: Understanding the cultural shift from traditional development to DevOps
  - **Collaboration**: Breaking down silos between Development and Operations teams
  - **Automation**: Automating repetitive tasks to increase efficiency
  - **Continuous Improvement**: Embracing feedback loops and iterative development
  - **Shared Responsibility**: Everyone owns quality, security, and reliability
- **DORA Metrics**: Measuring DevOps success with industry-standard metrics
  - **Deployment Frequency**: How often code is deployed to production
  - **Lead Time for Changes**: Time from commit to production deployment
  - **Mean Time to Recovery (MTTR)**: How quickly systems recover from failures
  - **Change Failure Rate**: Percentage of deployments causing production issues
- **CI/CD Pipeline Components**:
  - **AWS CodeCommit**: Secure, scalable Git repository hosting
  - **AWS CodeBuild**: Fully managed build service that compiles code and runs tests
  - **AWS CodeDeploy**: Automated deployment to EC2, Lambda, ECS, and on-premises servers
  - **AWS CodePipeline**: Orchestration service that automates the entire release process
- **Deployment Strategies**:
  - **Blue/Green Deployment**: Minimize downtime by switching traffic between environments
  - **Canary Deployment**: Gradually roll out changes to a subset of users
  - **Rolling Deployment**: Update instances incrementally to maintain availability
- **Live Demo**: Building a complete CI/CD pipeline from scratch

#### 10:30 AM - 10:45 AM: Coffee Break

- Networking and refreshments

#### 10:45 AM - 12:00 PM: Infrastructure as Code with CloudFormation

**Presented by Van Hoang Kha**

- **Infrastructure as Code (IaC) Principles**:
  - **Version Control**: Track infrastructure changes like application code
  - **Repeatability**: Deploy identical environments consistently
  - **Documentation**: Infrastructure code serves as living documentation
  - **Testing**: Validate infrastructure before deployment
- **AWS CloudFormation Fundamentals**:
  - **Templates**: JSON or YAML files defining AWS resources
  - **Stacks**: Collections of AWS resources managed as a single unit
  - **Change Sets**: Preview changes before applying them
  - **Drift Detection**: Identify manual changes to stack resources
- **CloudFormation Best Practices**:
  - **Modular Templates**: Use nested stacks for reusability
  - **Parameters**: Make templates flexible with input parameters
  - **Outputs**: Export values for use in other stacks
  - **Cross-Stack References**: Share resources between stacks
- **Advanced Features**:
  - **Stack Policies**: Protect critical resources from updates
  - **Rollback Triggers**: Automatically rollback on CloudWatch alarms
  - **StackSets**: Deploy stacks across multiple accounts and regions
- **Live Demo**: Deploying a multi-tier application with CloudFormation

#### 12:00 PM - 1:00 PM: Lunch Break

- Lunch and networking

#### 1:00 PM - 2:15 PM: AWS CDK Deep Dive

**Presented by Nguyen Khanh Phuc Thinh**

- **Introduction to AWS CDK**:
  - **What is CDK**: Cloud Development Kit for defining infrastructure in code
  - **Benefits**: Use familiar programming languages (TypeScript, Python, Java, C#, Go)
  - **Abstraction Levels**: L1 (CloudFormation resources), L2 (curated constructs), L3 (patterns)
- **CDK Core Concepts**:
  - **Constructs**: Reusable cloud components
  - **Stacks**: Deployment units containing constructs
  - **Apps**: Collections of stacks
  - **Synthesis**: Converting CDK code to CloudFormation templates
- **CDK vs CloudFormation**:
  - **Programmatic**: Use loops, conditionals, and functions
  - **Type Safety**: Catch errors at compile time
  - **IDE Support**: Autocomplete and inline documentation
  - **Testing**: Unit test infrastructure code
- **CDK Best Practices**:
  - **Construct Libraries**: Leverage pre-built patterns
  - **Environment Agnostic**: Write code that works across environments
  - **Logical IDs**: Stable identifiers for resources
  - **Context Values**: Environment-specific configuration
- **Live Demo**: Building a serverless application with CDK

#### 2:15 PM - 2:30 PM: Coffee Break

- Networking and refreshments

#### 2:30 PM - 3:45 PM: Container Services on AWS

**Presented by Le Huynh Nghiem**

- **Container Fundamentals**:
  - **What are Containers**: Lightweight, portable application packages
  - **Benefits**: Consistency, portability, efficiency, scalability
  - **Docker Basics**: Images, containers, registries
- **Amazon Elastic Container Registry (ECR)**:
  - **Private Registry**: Secure storage for container images
  - **Image Scanning**: Automated vulnerability detection
  - **Lifecycle Policies**: Automatically clean up old images
  - **Cross-Region Replication**: Distribute images globally
- **Amazon Elastic Container Service (ECS)**:
  - **AWS-Native Orchestration**: Simple, integrated container management
  - **Task Definitions**: Blueprint for running containers
  - **Services**: Maintain desired number of tasks
  - **Fargate**: Serverless compute for containers
  - **EC2 Launch Type**: More control over infrastructure
- **Amazon Elastic Kubernetes Service (EKS)**:
  - **Managed Kubernetes**: Run Kubernetes without managing control plane
  - **Compatibility**: Standard Kubernetes APIs and tools
  - **Flexibility**: Support for complex orchestration needs
  - **Add-ons**: Integrated AWS services (ALB, EBS, EFS)
- **AWS App Runner**:
  - **Simplest Option**: From source code to running service
  - **Automatic Scaling**: Scale based on traffic
  - **Built-in CI/CD**: Deploy from source repository
  - **Use Cases**: Web applications, APIs, microservices
- **Choosing the Right Service**:
  - **ECS**: AWS-native, simple, integrated
  - **EKS**: Kubernetes expertise, complex orchestration
  - **App Runner**: Fastest time to deployment, minimal configuration
- **Live Demo**: Deploying a containerized application to ECS and EKS

#### 3:45 PM - 4:45 PM: Monitoring and Observability

**Presented by Huynh Hoang Long**

- **Observability vs Monitoring**:
  - **Monitoring**: Collecting and displaying metrics
  - **Observability**: Understanding system behavior from outputs
  - **Three Pillars**: Logs, metrics, traces
- **Amazon CloudWatch**:
  - **Metrics**: Collect and track key performance indicators
  - **Logs**: Centralized log management and analysis
  - **Alarms**: Automated notifications and actions
  - **Dashboards**: Visualize metrics and logs
  - **Insights**: Query and analyze log data
  - **Events**: Respond to changes in AWS resources
- **AWS X-Ray**:
  - **Distributed Tracing**: Track requests across microservices
  - **Service Map**: Visualize application architecture
  - **Trace Analysis**: Identify performance bottlenecks
  - **Error Analysis**: Debug and troubleshoot issues
  - **Integration**: Works with Lambda, ECS, EKS, API Gateway
- **Best Practices**:
  - **Structured Logging**: Use consistent log formats
  - **Custom Metrics**: Track business-specific KPIs
  - **Proactive Monitoring**: Set alarms before issues impact users
  - **Correlation**: Link logs, metrics, and traces
  - **Retention Policies**: Balance cost and compliance
- **Live Demo**: Setting up comprehensive monitoring for a microservices application

#### 4:45 PM - 5:00 PM: DevOps Best Practices and Q&A

**Presented by Pham Hoang Quy**

- **DevOps Best Practices**:
  - **Automate Everything**: From testing to deployment to monitoring
  - **Fail Fast, Learn Faster**: Embrace failures as learning opportunities
  - **Blameless Postmortems**: Focus on systems, not individuals
  - **Progressive Delivery**: Use feature flags and canary deployments
  - **Continuous Learning**: DevOps is an ongoing journey
- **Real-World Case Studies**:
  - **Startup**: Rapid iteration with CI/CD and serverless
  - **Enterprise**: Multi-account strategy with StackSets
  - **E-commerce**: High availability with blue/green deployments
- **Q&A Session**: Interactive discussion with attendees

### Key Takeaways

#### DevOps Culture and Mindset

- **Collaboration**: DevOps breaks down silos between teams
- **Automation**: Automate repetitive tasks to focus on value
- **Measurement**: Use DORA metrics to track progress
- **Continuous Improvement**: Always iterate and optimize
- **Shared Responsibility**: Everyone owns quality and reliability

#### CI/CD Pipeline Automation

- **CodeCommit**: Secure Git repository for source control
- **CodeBuild**: Automated build and test execution
- **CodeDeploy**: Reliable deployment with multiple strategies
- **CodePipeline**: Orchestrates the entire CI/CD workflow
- **Integration**: Works seamlessly with AWS services and third-party tools

#### Infrastructure as Code

- **CloudFormation**: Declarative IaC with JSON/YAML templates
- **CDK**: Programmatic IaC with familiar programming languages
- **Benefits**: Version control, repeatability, and consistency
- **Drift detection**: Identify and remediate manual changes
- **Choose wisely**: Select IaC tools based on team skills and requirements

#### Container Services

- **ECR**: Secure container image storage with scanning
- **ECS**: AWS-native container orchestration, simple and integrated
- **EKS**: Kubernetes on AWS for complex orchestration needs
- **App Runner**: Simplest option for containerized web applications
- **Right tool for the job**: Choose based on complexity and requirements

#### Monitoring and Observability

- **CloudWatch**: Comprehensive monitoring for AWS resources
- **X-Ray**: Distributed tracing for microservices debugging
- **Observability**: Understanding system behavior from outputs
- **Proactive monitoring**: Detect issues before they impact users
- **Data-driven decisions**: Use metrics and traces to optimize performance

#### DevOps Best Practices

- **Automate everything**: From testing to deployment to monitoring
- **Fail fast, learn faster**: Embrace failures as learning opportunities
- **Blameless postmortems**: Focus on systems, not individuals
- **Progressive delivery**: Use feature flags and canary deployments
- **Continuous learning**: DevOps is an ongoing journey

### Applying to Work

- **Implement CI/CD**: Start with CodePipeline for automated deployments
- **Adopt IaC**: Use CloudFormation or CDK for infrastructure management
- **Containerize applications**: Migrate to ECS or EKS for scalability
- **Enhance monitoring**: Set up CloudWatch dashboards and X-Ray tracing
- **Practice DevOps culture**: Foster collaboration between teams
- **Measure and improve**: Track DORA metrics and optimize processes
- **Pursue certification**: AWS DevOps Engineer certification validates skills

### Event Experience

Attending the **"DevOps on AWS Workshop"** was an intensive full-day learning experience that provided comprehensive coverage of DevOps practices and AWS services. Key experiences included:

#### Learning from AWS Experts

- **AWS DevOps Specialists** provided deep insights into CI/CD best practices and automation strategies
- **AWS Solutions Architects** demonstrated real-world container deployments and monitoring setups
- Practical examples illustrated how companies successfully implement DevOps on AWS
- Expert guidance on choosing the right tools and services for specific use cases

#### Hands-on Demonstrations

- Witnessed complete **CI/CD pipeline** creation from scratch
- Saw **Infrastructure as Code** in action with both CloudFormation and CDK
- Explored **container deployment** across ECS, EKS, and App Runner
- Learned **monitoring and tracing** setup for production systems
- Understood the differences between various deployment strategies

#### Understanding DevOps Practices

- Gained insights into **DevOps culture** beyond just tools and automation
- Learned about **DORA metrics** and how to measure DevOps success
- Understood the importance of **observability** in modern systems
- Discovered **best practices** from real-world case studies
- Explored **incident management** and blameless postmortem processes

#### Networking and Community Building

- Connected with fellow developers and DevOps engineers
- Exchanged ideas about DevOps transformation challenges
- Built relationships with AWS experts for ongoing support
- Joined the AWS DevOps community for continuous learning

#### Practical Insights Gained

- **CI/CD automation** significantly reduces deployment time and errors
- **Infrastructure as Code** ensures consistency and repeatability
- **Containers** provide flexibility and portability for applications
- **Monitoring and observability** are critical for production systems
- **DevOps culture** is as important as the tools and technologies

#### Next Steps

- Begin implementing **CI/CD pipelines** using AWS CodePipeline
- Adopt **Infrastructure as Code** with CloudFormation or CDK
- Containerize applications and deploy to **ECS or EKS**
- Set up comprehensive **monitoring** with CloudWatch and X-Ray
- Work towards **AWS DevOps Engineer certification**
- Continue engaging with the **AWS DevOps community**

> Overall, this full-day workshop provided a comprehensive introduction to DevOps on AWS, covering everything from CI/CD pipelines to container services to monitoring and observability. The hands-on demonstrations and real-world case studies made complex concepts accessible and immediately applicable. The key takeaway is that DevOps is not just about tools, but about culture, collaboration, and continuous improvement. AWS provides a complete ecosystem for implementing DevOps practices, making it easier than ever to build, deploy, and operate applications at scale.

### Event Pictures

![DevOps Workshop](images/1.jpg)

---

![DevOps Workshop](images/2.jpg)

---

![DevOps Workshop](images/3.jpg)

---

![DevOps Workshop](images/4.jpg)

---

![DevOps Workshop](images/5.jpg)

---

![DevOps Workshop](images/6.jpg)

---

![DevOps Workshop](images/7.jpg)

---

![DevOps Workshop](images/8.jpg)

---

![DevOps Workshop](images/9.jpg)

---

![DevOps Workshop](images/10.jpg)

---

![DevOps Workshop](images/11.jpg)

---

![DevOps Workshop](images/12.jpg)

---

![DevOps Workshop](images/13.jpg)

---

![DevOps Workshop](images/14.jpg)

---

![DevOps Workshop](images/15.jpg)

---

![DevOps Workshop](images/16.jpg)

---

![DevOps Workshop](images/17.jpg)

---

![DevOps Workshop](images/18.jpg)

---

![DevOps Workshop](images/19.jpg)

---

![DevOps Workshop](images/20.jpg)

---

![DevOps Workshop](images/21.jpg)

---

![DevOps Workshop](images/22.jpg)

---

![DevOps Workshop](images/23.jpg)

---

![DevOps Workshop](images/24.jpg)

---

![DevOps Workshop](images/25.jpg)

---

![DevOps Workshop](images/26.jpg)

---

![DevOps Workshop](images/27.jpg)

---

![DevOps Workshop](images/28.jpg)

---

![DevOps Workshop](images/30.jpg)

---

![DevOps Workshop](images/31.jpg)

---

![DevOps Workshop](images/32.jpg)

---

![DevOps Workshop](images/33.jpg)

---

![DevOps Workshop](images/34.jpg)
