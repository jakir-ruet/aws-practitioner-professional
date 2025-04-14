### Welcome to AWS Certified Cloud Practitioner (CLF-C02) Exam Guide
#### Introduction
The AWS Certified Cloud Practitioner exam is designed for individuals who can demonstrate foundational knowledge of the AWS Cloud, independent of a specific job role. The exam validates a candidate’s ability to complete the following tasks: 
- Explain the value of the AWS Cloud. 
- Understand and explain the AWS shared responsibility model. 
- Understand security best practices. 
- Understand AWS Cloud costs, economics, and billing practices. 
- Describe and position the core AWS services, including compute, network, database, and storage services. 
- Identify AWS services for common use cases.

#### Target Candidate
The target candidate has up to 6 months of exposure to AWS Cloud design, implementation, and/or operations. This certification is ideal for candidates who are from non-IT backgrounds. These candidates might be in the early stages of pursuing an AWS Cloud career or might work with people in AWS Cloud roles. 

#### Recommended AWS Knowledge 
The target candidate should have AWS knowledge in the following areas: 
- AWS Cloud concepts 
- Security and compliance in the AWS Cloud 
- Core AWS services 
- Economics of the AWS Cloud

#### Not Need to Know (Job tasks that are out of scope for the target candidate)
The following list contains job tasks that the target candidate is not expected to be able to 
perform. This list is non-exhaustive. These tasks are out of scope for the exam: 
- Coding 
- Cloud architecture design 
- Troubleshooting 
- Implementation 
- Load and performance testing 
Refer to `Appendix A` for a list of technologies and concepts that might appear on the exam, a list of in-scope AWS services and features, and a list of out-of-scope AWS services and features.

#### Exam Content 
Response types `>` There are two types of questions on the exam: 
- `Multiple choice:` Has `one correct` response and three incorrect responses (distractors) 
- `Multiple response:` Has `two or more correct` responses out of five or more response 
options

`Instructions`
- Select one or more responses that `best complete` the statement or answer the question.
- Distractors, or incorrect answers, are response options that a candidate with incomplete knowledge or skill might choose. 
- Distractors are generally plausible responses that match the content area. 
- Unanswered questions are scored as `incorrect`; there is `no penalty` for guessing. 
- The exam includes `50` questions that affect your score.


#### Exam Score
| SL  | Title           | Marks                                        |
| --- | --------------- | -------------------------------------------- |
| 1   | Total Questions | 65 (50 Scored + 15 Un-scored)                |
| 2   | Passing Score   | 700/1000                                     |
| 3   | Scoring Model   | Compensatory (Pass Overall, Not per Section) |
| 4   | Validity        | 3 Years                                      |

#### Exam Domains & Weights
| Domain | Description                   | Weight |
| ------ | ----------------------------- | ------ |
| 1      | Cloud Concepts                | 24%    |
| 2      | Security and Compliance       | 30%    |
| 3      | Cloud Technology and Services | 34%    |
| 4      | Billing, Pricing, and Support | 12%    |

#### 01 Domain - Cloud Concepts
##### Overview 
This domain ensures you understand what the `cloud` is, why `organizations` use AWS, and how `cloud economics` and `design principles` apply to `real-world` scenarios.

- `Task Statement 1.1:` Benefits of the AWS Cloud such as
  - Cost Savings: No upfront investment, pay-as-you-go.
  - Elasticity: Automatically scale resources up/down as needed.
  - Global Reach: Deploy globally in minutes using AWS Regions.
  - High Availability: Design fault-tolerant applications with built-in redundancy.
  - Agility: Experiment quickly using managed services and templates.

- `Task Statement 1.2:` AWS Cloud Design Principles. AWS Well-Architected Framework – `6 Pillars`:
   - Operational Excellence – Monitoring, automation, and continuous improvement.
   - Security – Protecting data, systems, and assets.
   - Reliability – System recovery, failure management.
   - Performance Efficiency – Use right resources and adapt to changing needs.
   - Cost Optimization – Avoid unnecessary costs and optimize spend.
   - Sustainability – Environmental impact and energy efficiency.

- `Task Statement 1.3:` Migration Strategies and Benefits. Key Concepts:
  - AWS CAF (Cloud Adoption Framework): Provides guidance on migrating workloads. 
    - Benefits of CAF:
      - Increased business agility
      - Reduced risk and operational overhead
      - ESG (Environmental, Social, and Governance) improvements
      - Common Migration Tools:
  - AWS Snowball – Move large data sets securely.
  - AWS DMS – Database migration service.

- `Task Statement 1.4:` Cloud Economics. Key Concepts:
  - CapEx vs. OpEx:
  - Traditional IT: Capital Expenditure (hardware)
  - Cloud: Operational Expenditure (usage-based)
  - Rightsizing: Match resources to workload needs.
  - Automation: Use services like CloudFormation for repeatable infrastructure.
  - Licensing: Choose between `Bring Your Own License` (BYOL) or AWS-provided.
  - Examples of Managed Services:
    - Amazon RDS – Managed relational databases
    - Amazon ECS/EKS – Managed container orchestration
    - Amazon DynamoDB – Managed NoSQL database

##### Cloud Computing - Task Statement 1.1:
Cloud computing is the on-demand delivery of compute power, database, storage, applications, and other IT resources through a cloud services platform via the internet with pay-as-you-go pricing.

##### [Types of Cloud Computing Deployment Models](https://aws.amazon.com/types-of-cloud-computing/)
- [Private Cloud](https://aws.amazon.com/what-is/private-cloud/#:~:text=A%20private%20cloud%20is%20a,the%20control%20of%20one%20organization.)
  - This service used by a single organization, not exposed to public.
  - Complete self control
  - Secure for sensitive applications.
  - Fulfill specified requirements.
  - For example [RackSpace](https://www.rackspace.com), [Hewlett Packard Enterprise (HPE)](https://www.hpe.com/emea_europe/en/home.html) and so on.
- Public Cloud
  - Cloud resources owned and operated by a third- party cloud service provider delivered over the Internet.
  - [Six Advantages](https://docs.aws.amazon.com/whitepapers/latest/aws-overview/six-advantages-of-cloud-computing.html) of Cloud Computing.
    - Trade fixed expense (Capital Expense - ***CapEx***) for variable expense (Operational Expense - ***OpEx***).
      - Pay on demand: Don't own hardware.
      - Reduce Total Cost of Ownership (TCO) & Operational Expense (OpEx).
    - Benefit from massive economies of scale
      - Prices are reduced as AWS is more efficient due to large scale
    - Stop guessing capacity
      - Scale based on actual measured usage
    - Increase speed and agility
    - Stop spending money running and maintaining data centers
    - Go global in minutes
  - For example AWS, Google Cloud Platform (GCP) & Microsoft Azure.
- [Hybrid Cloud](https://aws.amazon.com/hybrid/)
  - Keep some servers on premises and extend some capabilities to the Cloud
  - Control over sensitive assets in your private infrastructure
  - Flexibility and cost- effectiveness of the public cloud
  - For example, On-premises with Public cloud.

##### The Five Characteristics of Cloud Computing
1. On-demand self service:
   Users can provision resources and use them without human interaction from the service provider
2. Broad network access:
   Resources available over the network, and can be accessed by diverse client platforms
3. Multi-tenancy and resource pooling:
   Multiple customers can share the same infrastructure and applications with security and privacy.
   Multiple customers are serviced from the same physical resources
4. Rapid elasticity and scalability:
   Automatically and quickly acquire and dispose resources when needed
   Quickly and easily scale based on demand
5. Measured service:
   Usage is measured, users pay correctly for what they have used

##### Problems solved by the Cloud
- Flexibility: change resource types when needed
- Cost-Effectiveness: pay as you go, for what you use
- Scalability: accommodate larger loads by making hardware stronger or adding additional nodes
- Elasticity: ability to scale out and scale-in when needed
- High-availability and fault-tolerance: build across data centers
- Agility: rapidly develop, test and launch software applications

##### [Types of Cloud Computing Model](https://aws.amazon.com/types-of-cloud-computing/)
- Infrastructure as a Service (IaaS)
  - Provide building blocks for cloud IT
  - Provides networking, computers, data storage space
  - Highest level of flexibility
  - Easy parallel with traditional on-premises IT
  - For example
    - Amazon EC2 (on AWS)
    - GCP, Azure, Rackspace, Digital Ocean, Linode
- Platform as a Service (PaaS)
  - Removes the need for your organization to manage the underlying infrastructure
  - Focus on the deployment and management of your applications
  - For example
    - Elastic Beanstalk (on AWS)
    - Heroku, Google App Engine (GCP), Windows Azure (Microsoft)
- Software as a Service (SaaS)
  - Completed product that is run and managed by the service provider
  - For example
    - Many AWS services (ex: Rekognition for Machine Learning)
    - Google Apps (Gmail), Dropbox, Zoom
  
##### Cloud Computing Model
![Cloud Computing Model](/img/cloud-computing-model.png)

##### Highly Available and Scalable Resources
High availability means your application or service remains **accessible and operational** even when one or more components fail. Key Features:
- Redundancy
- Failover mechanisms
- Health checks and monitoring

AWS Services Supporting High Availability:
| Service                         | High Availability Feature                         |
| ------------------------------- | ------------------------------------------------- |
| **Amazon EC2**                  | Use Auto Scaling + Load Balancer across AZs       |
| **Elastic Load Balancer (ELB)** | Distributes traffic across multiple instances/AZs |
| **Amazon RDS (Multi-AZ)**       | Automatic failover to standby instance            |
| **Amazon S3**                   | Stores data across multiple AZs                   |
| **Route 53**                    | DNS-level failover and health checks              |
| **Amazon DynamoDB**             | Automatically replicates data across multiple AZs |

##### Scalability vs Elasticity
Both Scalability and Elasticity are core cloud concepts that help applications handle varying loads efficiently — but they are `not the same` thing.

###### Scalability
The ability of a system to increase or decrease its capacity (usually compute, storage, or throughput) based on workload. Types of Scalability:
- Vertical Scaling (Scaling Up/Down)
  - Add more power (CPU/RAM) to an existing instance.
  - Example: Change an EC2 instance from `t2.micro` to `t3.large`.
- Horizontal Scaling (Scaling Out/In)
  - Add or remove multiple instances to distribute the load.
  - Example: Add more EC2 instances to a load balancer group.

- AWS Services That Support Scalability:
  - EC2 Auto Scaling
  - Elastic Load Balancing
  - Amazon RDS (Read Replicas for horizontal read scalability)
  - Amazon DynamoDB (auto scaling read/write capacity)

###### Elasticity
The ability of the system to automatically adjust capacity to maintain performance as demand changes in real-time. Think of it as automated and reactive scalability.
- AWS Services That Provide Elasticity:
  - EC2 Auto Scaling Groups (ASG): Automatically increase/decrease EC2 instances based on demand.
  - AWS Lambda: Automatically scales based on the number of incoming requests.
  - Amazon Aurora Serverless: Automatically adjusts database capacity.

**Key Differences Between Scalability and Elasticity**
| Feature        | Scalability                              | Elasticity                                 |
| -------------- | ---------------------------------------- | ------------------------------------------ |
| Focus          | Capacity expansion                       | Real-time responsiveness                   |
| Trigger        | Manual or rule-based                     | Automated and reactive                     |
| Example        | Add more EC2 instances with Auto Scaling | Lambda scales automatically with requests  |
| Resource Usage | Grows with load (needs configuration)    | Expands/contracts on demand without effort |

###### Agility in AWS
**Agility** in cloud computing refers to the ability to **quickly adapt** to changes in demand or business needs by leveraging scalable, flexible, and automated cloud resources. In AWS, agility allows businesses to deploy, scale, and modify their infrastructure with minimal time and effort.

**Agility vs Traditional IT**
| Aspect           | Traditional IT                         | Cloud Agility (AWS)                   |
| ---------------- | -------------------------------------- | ------------------------------------- |
| Deployment Speed | Slow, manual provisioning of hardware  | Fast, automated resource provisioning |
| Scalability      | Limited by hardware, requires planning | Auto-scaling based on demand          |
| Flexibility      | Difficult to change configurations     | Easily adaptable to meet new needs    |
| Cost Efficiency  | High upfront costs                     | Pay-as-you-go, no upfront investment  |

**Key Features of Agility**
- `Rapid Deployment:` Launch services, applications, and infrastructure quickly without needing to wait for physical hardware or lengthy configuration processes.
- `Flexibility and Adaptability:` Change infrastructure configurations in real-time to meet new demands or operational requirements.
- `Cost Efficiency:` Only pay for what you use, enabling teams to experiment with new ideas without worrying about upfront costs.
- `Automation:` Automate resource management and application deployment to save time and reduce human error.

##### Price of Cloud
AWS has 3 pricing fundamentals, following the pay-as-you-go pricing model
1. Compute: Pay for compute time
2. Storage: Pay for data stored in the Cloud
3. Data transfer out of the Cloud: Data transfer IN is free
Its the expensive issue then traditional IT

##### AWS Availability Zones
- Each region has many availability zones
  - Usually 3, Minimum 3, Maximum 6
  - Example: ap-southeast-2a, ap-southeast-2b, ap-southeast-2c
- Each availability zone (AZ) is one or more discrete data centers with redundant power, networking, and connectivity
- They’re separate from each other, so that they’re isolated from disasters
- They’re connected with high bandwidth, ultra-low latency networking

![Availability Zones](/img/availability-zones.png)

##### Visit of the AWS Console
- AWS has Global Services:
  - Identity and Access Management (IAM)
  - Route 53 (DNS service)
  - CloudFront (Content Delivery Network)
  - WAF (Web Application Firewall)
- Most AWS services are Region-scoped:
  - Amazon EC2 (Infrastructure as a Service)
  - Elastic Beanstalk (Platform as a Service)
  - Lambda (Function as a Service)
  - Rekognition (Software as a Service)
- See here [Region Services:](https://aws.amazon.com/about-aws/global-infrastructure/regional-product-services/)

##### [Shared Responsibility Model](https://aws.amazon.com/compliance/shared-responsibility-model/)
Security and Compliance is a shared responsibility between AWS and the customer. This shared model can help relieve the customer’s operational burden as AWS operates, manages and controls the components from the host operating system and virtualization layer down to the physical security of the facilities in which the service operates. The customer assumes responsibility and management of the guest operating system (including updates and security patches), other associated application software as well as the configuration of the AWS provided security group firewall. 
![shared-responsibility-model](/img/shared-responsibility-model.png)

#### 02 Domain - [Security and Compliance](https://aws.amazon.com/products/security/)
In AWS, **security** is a shared responsibility between AWS and the customer. To help customers fulfill their responsibilities, AWS provides **security services, documentation, and tools**.

**Overview**
- Identity and access management
- Detection and response
- Data protection
- Compliance
- Network and application protection

**Key Security Components in AWS**
1. Identity and Access Management
  1. AWS Identity and Access Management (IAM) - Securely manage identities and access to AWS services and resources.
  2. AWS IAM Identity Center - Centrally manage workforce access to multiple AWS accounts and applications.
  3. Amazon Cognito - Implement secure, frictionless customer identity and access management that scales.
  4. Amazon Verified Permissions - Manage fine-grained permissions and authorization within custom applications.
  5. AWS Directory Service - Gain efficiency with a fully managed Microsoft Active Directory service.
  6. AWS Resource Access Manager - Simply and securely share your AWS resources across multiple accounts.
  7. AWS Organizations - Centrally manage your environment as you scale your AWS resources.

2. Detection and Response
  1. Amazon GuardDuty - Protect AWS accounts with intelligent threat detection.
  2. Amazon Inspector - Automated and continual vulnerability management at scale.
  3. AWS Security Hub - Automate AWS security checks and centralize security alerts.
  4. Amazon Security Lake - Automatically centralize your security data in a few steps.
  5. Amazon Detective - Analyze and visualize security data to investigate potential security issues.
  6. AWS Security Incident Response - Prepare for, respond to, and recover from security events.
  7. AWS Config - Assess, audit, and evaluate configurations of your resources.
  8. Amazon CloudWatch - Observe and monitor resources and applications on AWS, on premises, and on other clouds.
  9. AWS CloudTrail - Track user activity and API usage.
  10. AWS IoT Device Defender - Security management across your IoT devices and fleets.
  11. AWS Elastic Disaster Recovery - Scalable, cost-effective application recovery to AWS.

3. Network and Application Protection
  1. AWS Firewall Manager - Centrally configure and manage firewall rules across your accounts.
  2. AWS Network Firewall - Deploy network firewall security across your VPCs.
  3. AWS Shield - Maximize application availability and responsiveness with managed DDoS protection.
  4. AWS Verified Access - Provide secure access to corporate applications without a VPN.
  5. AWS Web Application Firewall (WAF) - Protect your web applications from common exploits.
  6. Amazon Route 53 Resolver DNS Firewall - Filter and control outbound DNS traffic for your VPCs.

4. Data Protection
  1. Amazon Macie - Discover and protect your sensitive data at scale.
  2. AWS Key Management Service (AWS KMS) - Create and control keys to encrypt or digitally sign your data.
  3. AWS CloudHSM - Manage single-tenant hardware security modules (HSMs) on AWS.
  4. AWS Certificate Manager - Provision and manage SSL/TLS certificates with AWS services and connected resources.
  5. AWS Payment Cryptography - Simplify cryptography operations in your cloud-hosted payment applications.
  6. AWS Private Certificate Authority - Create private certificates to identify resources and protect data.
  7. AWS Secrets Manager - Centrally manage the lifecycle of secrets.

5. Compliance
  1. AWS Artifact - No cost, self-service portal for on-demand access to AWS’ compliance reports.
  2. AWS Audit Manager - Continually audit your AWS usage to simplify risk and compliance assessment.

#### 03 Domain - Cloud Technology and Services

#### 04 Domain - Billing, Pricing, and Support
