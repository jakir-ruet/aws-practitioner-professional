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

#### 02 Domain - Security and Compliance

#### 03 Domain - Cloud Technology and Services

#### 04 Domain - Billing, Pricing, and Support
