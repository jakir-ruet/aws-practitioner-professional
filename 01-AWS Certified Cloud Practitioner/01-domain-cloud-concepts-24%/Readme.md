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

##### Identify design principles of the AWS Cloud
The design principles of the AWS Cloud, primarily guided by the `AWS Well-Architected Framework`. These principles help you build secure, high-performing, resilient, and efficient infrastructure on the cloud.

#### [AWS Well-Architected Framework](https://docs.aws.amazon.com/wellarchitected/latest/framework/welcome.html)
The AWS Well-Architected Framework helps you understand the `pros` and `cons` of decisions you make while building systems on AWS. By using the Framework you will learn architectural best practices for designing and operating `reliable`, `secure`, `efficient`, `cost-effective`, and `sustainable` systems in the cloud.

##### AWS Well-Architected and the [Six Pillars](https://aws.amazon.com/architecture/well-architected/?ref=wellarchitected-wp&wa-lens-whitepapers.sort-by=item.additionalFields.sortDate&wa-lens-whitepapers.sort-order=desc&wa-guidance-whitepapers.sort-by=item.additionalFields.sortDate&wa-guidance-whitepapers.sort-order=desc)
- Operational Excellence Pillar
- Security Pillar
- Reliability Pillar
- Performance Efficiency Pillar
- Cost Optimization Pillar
- Sustainability Pillar

##### The Six Pillars of the AWS Well-Architected Framework
1. `Operational Excellence:` Run and monitor systems to deliver business value and continually improve processes. Key Design Principles:
- Perform operations as code
- Annotate documentation
- Make frequent, small, reversible changes
- Refine operations procedures
- Anticipate failure
- Learn from all operational events and failures

2. `Security:` Protect information, systems, and assets while delivering business value. Key Design Principles:
- Implement a strong identity foundation
- Enable traceability
- Apply security at all layers
- Automate security best practices
- Protect data in transit and at rest
- Keep people away from data
- Prepare for security events

3. `Reliability:` Ensure a workload performs its intended function correctly and consistently. Key Design Principles:
- Test recovery procedures
- Automatically recover from failure
- Scale horizontally to increase availability
- Stop guessing capacity
- Manage change in automation

4. `Performance Efficiency:` Use computing resources efficiently to meet system requirements and maintain efficiency as demand changes. Key Design Principles:
- Democratize advanced technologies
- Go global in minutes
- Use serverless architectures
- Experiment more often
- Consider mechanical sympathy (use the right tool for the job)

5. `Cost Optimization:` Avoid unnecessary costs and understand where money is being spent. Key Design Principles:
- Adopt a consumption model
- Measure overall efficiency
- Stop spending money on undifferentiated heavy lifting
- Analyze and attribute expenditures
- Use managed and serverless services to reduce costs

6. `Sustainability (Introduced in 2021):` Minimize environmental impact of running cloud workloads. Key Design Principles:
- Understand your impact
- Establish sustainability goals
- Maximize utilization
- Reduce downstream impact (e.g., client-side optimization)
- Continually innovate for sustainability

**Summary of Pillar**
| **Pillar**             | **Focus Area**                                        |
| ---------------------- | ----------------------------------------------------- |
| Operational Excellence | Monitoring, incident response, continuous improvement |
| Security               | Identity, access, detection, data protection          |
| Reliability            | Fault tolerance, recovery, scaling                    |
| Performance Efficiency | Optimal resource selection and usage                  |
| Cost Optimization      | Spend control, budgeting, resource management         |
| Sustainability         | Environmental impact and energy efficiency            |

#### Understand the benefits of and strategies for migration to the AWS Cloud.
Migrating to the AWS Cloud offers a wide range of benefits and follows well-defined strategies to ensure a successful transition.

##### [Cloud Adoption Framework (CAF):](https://aws.amazon.com/what-is/cloud-adoption-framework/)
A cloud adoption framework (CAF) is a set of best practices, tools, and guidance that helps organizations get started with cloud technologies. Moving to the cloud is challenging due to legacy technologies, complex application interdependencies, existing infrastructure bottlenecks, plus knowledge and skill gaps. The cloud adoption framework helps organizations identify and mitigate risks, manage costs, and ensure compliance as they move their workloads to the cloud. It also provides guidance on how to optimize governance and security in the cloud for improved efficiency.

##### Benefits of a cloud adoption framework?
- Reduce business risk
- Accelerate innovation
- Enhance agility

##### Use cases of cloud adoption frameworks?
- Resource organization
- Technology adoption
- Process improvement



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