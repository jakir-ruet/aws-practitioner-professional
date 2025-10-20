## More About Me – [Take a Look!](http://www.mjakaria.me)

## Welcome to AWS Certified Cloud Practitioner **CLF-C02**

This AWS Certified Cloud Practitioner (CLF-C02) learning path gives you everything you need to prepare for the exam with confidence. The courses follow the official exam guide and offer in-depth coverage of each of the `four` key domains.

### Domain 1: Cloud Concepts

#### Cloud Computing

Cloud computing is the on-demand delivery of `compute power`, `database`, `storage`, `applications`, and other IT resources through a cloud services platform via the internet with pay-as-you-go pricing.

#### Types of Cloud Computing Model

- Infrastructure as a Service (`IaaS`)
  - Provide building blocks for cloud IT
  - Provides networking, computers, data storage space
  - Highest level of flexibility
  - Easy parallel with traditional on-premises IT
  - For example
    - Amazon EC2 (on AWS)
    - GCP, Azure, Rackspace, Digital Ocean, Linode
- Platform as a Service (`PaaS`)
  - Removes the need for your organization to manage the underlying infrastructure
  - Focus on the deployment and management of your applications
  - For example
    - Elastic Beanstalk (on AWS)
    - Heroku, Google App Engine (GCP), Windows Azure (Microsoft)
- Software as a Service (`SaaS`)
  - Completed product that is run and managed by the service provider
  - For example
    - Many AWS services (ex: Rekognition for Machine Learning)
    - Google Apps (Gmail), Dropbox, Zoom

- IaaS vs PaaS vs SaaS

| Feature                    | IaaS                    | PaaS               | SaaS                  |
| -------------------------- | ----------------------- | ------------------ | --------------------- |
| Level of Control           | High                    | Medium             | Low                   |
| Who Manages Infrastructure | Customer                | Provider           | Provider              |
| Typical User               | Sysadmins, IT teams     | Developers         | End users             |
| Flexibility                | Very High               | Medium             | Low                   |
| Example on AWS             | EC2                     | Elastic Beanstalk  | Rekognition, WorkMail |
| Other Examples             | DigitalOcean, Azure VMs | Heroku, App Engine | Gmail, Dropbox, Zoom  |

#### The Five Characteristics of Cloud Computing

1. `On-demand self service:`
   Users can provision resources and use them without human interaction from the service provider
2. `Broad network access:`
   Resources available over the network, and can be accessed by diverse client platforms
3. `Multi-tenancy and resource pooling:`
   Multiple customers can share the same infrastructure and applications with security and privacy.
   Multiple customers are serviced from the same physical resources
4. `Rapid elasticity and scalability:`
   Automatically and quickly acquire and dispose resources when needed
   Quickly and easily scale based on demand
5. `Measured service:`
   Usage is measured, users pay correctly for what they have used

#### Challenges Addressed by Cloud Computing/How Cloud Computing Overcomes Traditional IT Limitations

- `Flexibility:` change resource types when needed
- `Cost-Effectiveness:` pay as you go, for what you use
- `Scalability:` accommodate larger loads by making hardware stronger or adding additional nodes
- `Elasticity:` ability to scale out and scale-in when needed
- `High-availability and fault-tolerance:` build across data centers
- `Agility:` rapidly develop, test and launch software applications

#### Types of Cloud Computing Deployment Models

- Private Cloud
  - This service used by a single organization, not exposed to public.
  - Complete self control
  - Secure for sensitive applications.
  - Fulfill specified requirements.
  - For example [RackSpace](https://www.rackspace.com), [Hewlett Packard Enterprise (HPE)](https://www.hpe.com/emeaeurope/en/home.html) and so on.
- Public Cloud
  - Cloud resources owned and operated by a third- party cloud service provider delivered over the Internet.
  - [Six Advantages](https://docs.aws.amazon.com/whitepapers/latest/aws-overview/six-advantages-of-cloud-computing.html) of Cloud Computing.
    - Trade fixed expense (Capital Expense - **CapEx**) for variable expense (Operational Expense - **OpEx**).
      - Pay on demand: Don't own hardware.
      - Reduce Total Cost of Ownership (TCO) & Operational Expense (OpEx).
    - Benefit from massive economies of scale
      - Prices are reduced as AWS is more efficient due to large scale
    - Stop guessing capacity
      - Scale based on actual measured usage
    - Increase speed and agility
    - Stop spending money running and maintaining data centers
    - Go global in minutes
  - For example `AWS`, `Google Cloud Platform` (GCP) & `Microsoft Azure`.
- [Hybrid Cloud](https://aws.amazon.com/hybrid/)
  - Keep some servers on premises and extend some capabilities to the Cloud
  - Control over sensitive assets in your private infrastructure
  - Flexibility and cost- effectiveness of the public cloud
  - For example, On-premises with Public cloud.

#### Shared Responsibility Model/Cloud Computing Model

![Cloud Computing Model](/img/cloud-computing-model.png)

##### AWS Services Supporting High Availability:

| Service                         | High Availability Feature                         |
| ------------------------------- | ------------------------------------------------- |
| **Amazon EC2**                  | Use Auto Scaling + Load Balancer across AZs       |
| **Elastic Load Balancer (ELB)** | Distributes traffic across multiple instances/AZs |
| **Amazon RDS (Multi-AZ)**       | Automatic failover to standby instance            |
| **Amazon S3**                   | Stores data across multiple AZs                   |
| **Route 53**                    | DNS-level failover and health checks              |
| **Amazon DynamoDB**             | Automatically replicates data across multiple AZs |

#### Scalability, Elasticity & Agility

Scalability, Elasticity, and Agility are core principles that underpin the cloud computing model, enabling businesses to meet fluctuating demand, optimize costs, and innovate faster. These are cloud concepts that help applications handle varying loads efficiently — but they are `not the same` thing.

##### Scalability

The ability of a system to increase or decrease its capacity (usually compute, storage, or throughput) based on workload. Types of Scalability:

- `Vertical Scaling (Scaling Up/Down)`
  - Add more power (CPU/RAM) to an existing instance.
  - Example: Change an EC2 instance from `t2.micro` to `t3.large`.
- `Horizontal Scaling (Scaling Out/In)`
  - Add or remove multiple instances to distribute the load.
  - Example: Add more EC2 instances to a load balancer group.

- AWS Services That Support Scalability:
  - EC2 Auto Scaling
  - Elastic Load Balancing
  - Amazon RDS (Read Replicas for horizontal read scalability)
  - Amazon DynamoDB (auto scaling read/write capacity)

##### Elasticity

The ability of the system to automatically adjust capacity to maintain performance as demand changes in real-time. Think of it as automated and reactive scalability.

- AWS Services That Provide Elasticity:
  - EC2 Auto Scaling Groups (ASG): Automatically increase/decrease EC2 instances based on demand.
  - AWS Lambda: Automatically scales based on the number of incoming requests.
  - Amazon Aurora Serverless: Automatically adjusts database capacity.

##### Agility

**Agility** in cloud computing refers to the ability to **quickly adapt** to changes in demand or business needs by leveraging scalable, flexible, and automated cloud resources. In AWS, agility allows businesses to deploy, scale, and modify their infrastructure with minimal time and effort.

- Key Features of Agility
  - `Rapid Deployment:` Launch services, applications, and infrastructure quickly without needing to wait for physical hardware or lengthy configuration processes.
  - `Flexibility and Adaptability:` Change infrastructure configurations in real-time to meet new demands or operational requirements.
  - `Cost Efficiency:` Only pay for what you use, enabling teams to experiment with new ideas without worrying about upfront costs.
  - `Automation:` Automate resource management and application deployment to save time and reduce human error.

#### Scalability vs Elasticity vs Agility

| Aspect           | **Scalability**                     | **Elasticity**                       | **Agility**                                      |
| ---------------- | ----------------------------------- | ------------------------------------ | ------------------------------------------------ |
| **Definition**   | Add/remove capacity to meet demand. | Auto-adjust capacity in real time.   | Rapidly adapt to change and deploy fast.         |
| **Nature**       | Planned / manual (can automate).    | Dynamic and automatic.               | Strategic and flexible.                          |
| **When Used**    | Predictable growth.                 | Unpredictable or fluctuating demand. | Innovation, quick response to business needs.    |
| **Example**      | Add more EC2 or upgrade instance.   | Auto-scale EC2 or Lambda.            | Launch new service quickly with minimal effort.  |
| **Key Benefit**  | Handles larger workloads.           | Optimizes cost & performance.        | Speeds up innovation & time to market.           |
| **AWS Services** | EC2 ASG, ELB, RDS, DynamoDB         | ASG, Lambda, Aurora Serverless       | CloudFormation, Beanstalk, ECS/EKS, CodePipeline |

- >**Key Point:**
  - `Scalability` > Grow or shrink capacity (manual or automated).
  - `Elasticity` > Automatic real-time scaling.
  - `Agility` > Move fast and adapt easily.

#### Agility vs Traditional IT

| Aspect           | Traditional IT                         | Cloud Agility (AWS)                   |
| ---------------- | -------------------------------------- | ------------------------------------- |
| Deployment Speed | Slow, manual provisioning of hardware  | Fast, automated resource provisioning |
| Scalability      | Limited by hardware, requires planning | Auto-scaling based on demand          |
| Flexibility      | Difficult to change configurations     | Easily adaptable to meet new needs    |
| Cost Efficiency  | High upfront costs                     | Pay-as-you-go, no upfront investment  |

#### Region & Availability Zones

##### Region

A Region is a geographical area where AWS has multiple data centers. AWS currently operates 38 launched Regions globally. Each Region is completely independent from the others to ensure maximum fault tolerance and stability like as:

- us-east-1 > N. Virginia (USA)
- eu-west-1 > Ireland
- ap-south-1 > Mumbai (India)

**Key Features**

- Physically separated and isolated from other regions.
- Designed for data residency and compliance requirements.
- Each region contains multiple Availability Zones.
- Some AWS services are regional (e.g., EC2, RDS), while some are global (e.g., IAM, Route 53, CloudFront).

> If your users are in India, deploying workloads in ap-south-1 (Mumbai) can `reduce` latency.

##### Availability Zones (AZs)

AWS has 120 Availability Zones across those Regions. An Availability Zone is one or more distinct data centers with redundant power, networking, and connectivity within a Region like as:

- `us-east-1a`, `us-east-1b`, `us-east-1c` (within N. Virginia region)
- `ap-south-1a`, `ap-south-1b`, `ap-south-1c` (within Mumbai region)

**Key Features**

- Located physically apart (usually many kilometers) but close enough to provide low latency (usually <10 ms).
- Help you build high availability and disaster recovery solutions.
- AZs in a Region are connected through redundant, high-speed private fiber.
- If one AZ goes down, the others can still run workloads.

> You can deploy EC2 instances in multiple AZs within the same Region behind a Load Balancer to ensure uptime if one AZ fails.

##### Region vs Availability Zone

| Feature                   | **Region**                               | **Availability Zone (AZ)**                             |
| ------------------------- | ---------------------------------------- | ------------------------------------------------------ |
| Scope                     | Geographical area                        | Data center(s) within a Region                         |
| Purpose                   | Data residency, compliance, global reach | High availability and fault tolerance                  |
| Isolation                 | Isolated from other Regions              | Isolated but connected to other AZs in the same Region |
| Number                    | ~35+ Regions worldwide                   | Each Region has at least 3 AZs (usually 3–6)           |
| Latency between locations | Higher between Regions                   | Low (sub-10ms) between AZs                             |

#### Edge Location

An Edge Location is a data center that’s part of the Amazon CloudFront content delivery network (CDN). These locations are strategically distributed around the world to bring content closer to end users, improving speed, latency, and reliability.

**Key Points**

- Deliver cached copies of content like `websites`, `media`, `APIs`, and `applications` to users with low latency.
- Handle DNS queries (via `Route 53`), security (`AWS Shield` & `WAF`), and data acceleration (`Global Accelerator`, `S3` Transfer Acceleration).

##### Difference from AWS Regions and Availability Zones

| Feature              | Region                  | Availability Zone            | Edge Location                          |
| -------------------- | ----------------------- | ---------------------------- | -------------------------------------- |
| Primary Purpose      | Full AWS infrastructure | High availability & failover | Low-latency content delivery           |
| Services Hosted      | EC2, S3, RDS, etc.      | Same as region (redundant)   | CloudFront, Route 53, WAF, Shield      |
| Number of Sites      | ~35+ Regions (growing)  | Multiple per Region          | 500+ Edge Locations globally (growing) |
| Latency Optimization | Medium                  | Low                          | Very low (closest to users)            |

#### AWS Well-Architected Framework/Reliability & Security Design Framework

The AWS Well-Architected Framework helps you understand the `pros` and `cons` of decisions you make while building systems on AWS. By using the Framework you will learn architectural best practices for designing and operating `reliable`, `secure`, `efficient`, `cost-effective`, and `sustainable` systems in the cloud.

##### AWS Well-Architected and the Six Pillars

- Operational Excellence Pillar
- Security Pillar
- Reliability Pillar
- Performance Efficiency Pillar
- Cost Optimization Pillar
- Sustainability Pillar

##### The Six Pillars of the AWS Well-Architected Framework

1. `Operational Excellence:` Run and monitor systems to deliver business value and continually improve processes. Key Design

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

##### Summary of Pillar

| **Pillar**             | **Focus Area**                                        |
| ---------------------- | ----------------------------------------------------- |
| Operational Excellence | Monitoring, incident response, continuous improvement |
| Security               | Identity, access, detection, data protection          |
| Reliability            | Fault tolerance, recovery, scaling                    |
| Performance Efficiency | Optimal resource selection and usage                  |
| Cost Optimization      | Spend control, budgeting, resource management         |
| Sustainability         | Environmental impact and energy efficiency            |

#### [Cloud Adoption Framework (CAF):](https://aws.amazon.com/cloud-adoption-framework/)

It's leverages AWS experience and best practices to help you digitally transform and accelerate your business outcomes through innovative use of AWS. AWS CAF identifies specific organizational capabilities that underpin successful cloud transformations. These capabilities provide best practice guidance that helps you improve your cloud readiness. AWS CAF groups its capabilities in `six` perspectives:

- Business,
- People,
- Governance,
- Platform,
- Security, and
- Operations.

##### How AWS CAF brings tangible benefits across different business goals:

1. Reduced Business Risk
   - Resilience & Continuity: By leveraging AWS's global infrastructure and built-in redundancy, organizations reduce the risk of outages and data loss.
   - Security Best Practices: The CAF emphasizes a strong security posture, helping identify and address vulnerabilities early in the cloud journey.
   - Regulatory Compliance: The framework guides compliance with industry and government regulations, reducing legal and financial risk.
2. Improved ESG (Environmental, Social, and Governance) Performance
   - Environmental: Migrating to AWS can reduce carbon emissions as AWS operates on renewable energy and efficiently manages data centers.
   - Social: Upskilling employees for cloud roles creates new career opportunities and enhances workforce development.
   - Governance: CAF promotes transparency, accountability, and strong governance models that align with ethical and compliance standards.
3. Increased Revenue
   - Faster Time-to-Market: With cloud agility, businesses can innovate faster, roll out products more quickly, and capitalize on market opportunities.
   - Customer Experience: Enhanced digital services lead to better customer satisfaction and retention.
   - Global Reach: Access to AWS's global infrastructure supports expansion into new regions and customer bases.
4. Increased Operational Efficiency
   - Automation & Optimization: CAF encourages automating routine tasks and optimizing cloud resources, reducing manual work and costs.
   - Scalability & Flexibility: Resources can be scaled up or down based on demand, avoiding overprovisioning
   - Process Improvements: The framework helps streamline operations through best practices, monitoring, and continuous improvement models.

#### Multi-Tenant Architectures

Multi-tenancy in the cloud refers to an architecture where a single instance of a cloud service or application serves multiple customers (tenants). Each tenant's data, configurations, and operations are isolated, but they share the same underlying infrastructure. This approach is commonly used in cloud computing to reduce costs and maximize resource utilization while maintaining data separation and security between tenants. Three types of Multi-Tenancy:

1. Silo Model
2. Bridge Model
3. Pool Model

![Multi-Tenant Architectures](/img/multi-tenant-architectures.png)

**Comparison Table: Silo Model vs. Bridge Model vs. Pool Model**

| Aspect               | **Silo**                                     | **Bridge**               | **Pool**                         |
| -------------------- | -------------------------------------------- | ------------------------ | -------------------------------- |
| **Isolation**        | High                                         | Medium                   | Low                              |
| **Connectivity**     | None                                         | Peer-to-peer             | Centralized (Hub-and-Spoke)      |
| **Scalability**      | High                                         | Limited (many peers)     | Very High                        |
| **Management**       | Decentralized                                | Mixed                    | Centralized                      |
| **Cost Efficiency**  | Low                                          | Medium                   | High                             |
| **Complexity**       | Simple                                       | Moderate                 | High (setup), easy later         |
| **Use Case**         | Strict isolation (e.g., finance, healthcare) | Limited resource sharing | Enterprise shared services       |
| **Key AWS Services** | Separate VPCs/Accounts                       | VPC Peering, PrivateLink | Transit Gateway, Shared VPC      |
| **Shared Services**  | None                                         | Selective                | Centralized (DNS, NAT, Firewall) |

#### Deployment, [Migration & Transfer](https://docs.aws.amazon.com/whitepapers/latest/aws-overview/migration-services.html) to the AWS Cloud.

In AWS (Amazon Web Services), deployment, migration, and transfer are key concepts related to moving applications, data, or infrastructure into or within the cloud. Here's a breakdown of each:

##### [Deployment](https://docs.aws.amazon.com/whitepapers/latest/introduction-devops-aws/deployment-strategies.html)

Deployment strategies define how you want to deliver your software. Organizations follow different deployment strategies based on their business model. Some choose to deliver software that is fully tested, and others might want their users to provide feedback and let their users evaluate under development features (such as Beta releases). The following section discusses various deployment strategies.

- Deployment Models:
  - [In-place deployments](https://docs.aws.amazon.com/whitepapers/latest/overview-deployment-options/in-place-deployments.html)
    An in-place deployment is a deployment strategy that updates the application version without replacing any infrastructure components. In an in-place deployment, the previous version of the application on each compute resource is stopped, the latest application is installed, and the new version of the application is started and validated.
  - [Blue/Green Deployment](https://docs.aws.amazon.com/whitepapers/latest/blue-green-deployments/welcome.html)
    The blue/green deployment technique enables you to release applications by shifting traffic between two identical environments that are running different versions of the application. Blue/green deployments can mitigate common risks associated with deploying software, such as downtime and rollback capability.
  - [Canary Deployment](https://docs.aws.amazon.com/whitepapers/latest/overview-deployment-options/canary-deployments.html)
    Canary deployments are a type of blue/green deployment strategy that is more risk-averse. This strategy involves a phased approach in which traffic is shifted to a new version of the application in two increments. The first increment is a small percentage of the traffic, which is referred to as the canary group.
  - [Linear deployment](https://docs.aws.amazon.com/whitepapers/latest/introduction-devops-aws/deployment-strategies.html)
    Linear deployment means traffic is shifted in equal increments with an equal number of minutes between each increment. You can choose from predefined linear options that specify the percentage of traffic shifted in each increment and the number of minutes between each increment.
  - [All-at-once deployment](https://docs.aws.amazon.com/whitepapers/latest/introduction-devops-aws/deployment-strategies.html)
    All-at-once deployment means all traffic is shifted from the original environment to the replacement environment all at once.
  - [Rolling Deployment](https://docs.aws.amazon.com/whitepapers/latest/overview-deployment-options/rolling-deployments.html)
    A rolling deployment is a deployment strategy that slowly replaces previous versions of an application with new versions of an application by completely replacing the infrastructure on which the application is running.
  - [Immutable Deployment](https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/environmentmgmt-updates-immutable.html)
    Immutable environment updates are an alternative to rolling updates. Immutable environment updates ensure that configuration changes that require replacing instances are applied efficiently and safely. If an immutable environment update fails, the rollback process requires only terminating an Auto Scaling group.

**Deployment Matrix**

| Deployment Strategy | Amazon ECS | AWS Lambda | Amazon EC2/on-premises |
| ------------------- | ---------- | ---------- | ---------------------- |
| In-place            | ✓          | ✓          | ✓                      |
| Blue/green          | ✓          | ✓          | ✓*                     |
| Canary              | ✓          | ✓          | X                      |
| Linear              | ✓          | ✓          | X                      |
| All-at-once         | ✓          | ✓          | X                      |

#### Migration

**Prerequisite of Migration**

| Phase       | Key Activities                                                            |
| ----------- | ------------------------------------------------------------------------- |
| Preparation | Current Architecture, assess environment, choose strategy                 |
| Planning    | Estimate cost, design architecture, monolithic to microservice            |
| Migrate     | Use AWS tools (MGN, DMS), test, validate, backup, cutover                 |
| Monitor     | Track performance with CloudWatch, CloudTrail, X-Ray, set alerts          |
| Optimize    | Right-size resources, cost optimization, enhance security, modernize apps |

**Migration Strategies (7 R’s)**

| Strategy   | Description                                                              |
| ---------- | ------------------------------------------------------------------------ |
| Refactor   | Redesign application for cloud-native architecture (e.g., microservices) |
| Replatform | "Lift, tinker, and shift" – make minimal changes (e.g., move DB to RDS)  |
| Repurchase | Replace with SaaS solutions (e.g., move to a cloud-based CRM)            |
| Rehost     | "Lift and shift" – move applications to AWS without changes              |
| Relocate   | Move without modification "Lift and shift"                               |
| Retain     | Keep some apps on-premises (temporarily or permanently)                  |
| Retire     | Decommission outdated or unused applications                             |

AWS offers a comprehensive suite of tools and services to facilitate cloud migration, including automated processes and specialized expertise.

- [AWS Migration Evaluator](https://aws.amazon.com/migration-evaluator/?p=ft&c=mg&z=3)
  Helps build a business case for cloud migration by analyzing on-premises infrastructure usage and costs. What it does:
  - Collects data from on-prem environments (agentless).
  - Provides cost projections for running workloads on AWS.
  - Helps identify underutilized resources and potential savings.
  - Best for: Pre-migration cost analysis and planning.
- [AWS Application Discovery Service](https://aws.amazon.com/application-discovery/?p=ft&c=mg&z=3)
  Discovers on-premises servers to gather information about their configuration, usage, and behavior What it does:
  - Can use agents or agentless discovery.
  - Collects data like CPU, memory, network usage, and running processes.
  - Helps map application dependencies.
  - Best for: Understanding your current environment before migration.
- [AWS Migration Hub](https://aws.amazon.com/migration-hub/?p=ft&c=mg&z=3)
  Centralized tracking and monitoring of migration progress across AWS services. What it does:
  - Provides a single pane of glass for tracking application migrations.
  - Integrates with other migration tools (like Application Migration Service and DMS).
  - Can group resources by application for easier tracking.
  - Best for: Managing and coordinating large-scale migrations.
- [AWS Application Migration Service - MGN](https://aws.amazon.com/application-discovery/?p=ft&c=mg&z=3)
  Simplifies and automates the lift-and-shift (rehost) of physical, virtual, or cloud servers to AWS. What it does:
  - Real-time replication of source servers.
  - Minimal downtime cutover.
  - Automated post-launch modernization (e.g., instance type changes).
  - Best for: Rehosting existing workloads with minimal changes.
- [AWS Database Migration Service - DMS](https://aws.amazon.com/migration-hub/?p=ft&c=mg&z=3)
  Migrates databases to AWS quickly and securely with minimal downtime. What it does:
  - Supports homogenous (e.g., Oracle to Oracle) and heterogeneous (e.g., SQL Server to Aurora) migrations.
  - Can handle on-going replication for hybrid scenarios.
  - Best for: Database-specific migrations, both one-time and continuous replication.
- [AWS Migration Acceleration Program (MAP)](https://aws.amazon.com/migration-acceleration-program/)
  The AWS Migration Acceleration Program (MAP) is a structured framework provided by Amazon Web Services to help organizations accelerate their cloud migration journey. It's especially useful for enterprises planning large-scale migrations from on-premises or other cloud environments to AWS.
- [Cloud Migration Factory (CMF)](https://aws.amazon.com/solutions/implementations/cloud-migration-factory-on-aws/)
  A Cloud Migration Factory is a centralized migration model that industrializes the migration process, breaking it into repeatable units. Think of it like an assembly line for cloud migration—each step is standardized to improve speed, reduce errors, and ensure consistency.

![Here's a comparison table that highlights the key differences between the AWS migration-related services you mentioned:](/img/cloud-migration.png)

#### Data Transfer

AWS Data Transfer Services, which help you move data to, from, and within the AWS Cloud — whether online, offline, in real-time, or bulk.

- [AWS Snow Family](https://aws.amazon.com/snowball/) > `Snowcone / Snowball / Snowmobile`
  The AWS Snow Family is a collection of physical devices that help you move data into and out of AWS, especially when dealing with large-scale data or limited internet connectivity.
  - Use case: Physical data transfer.
  - Snowcone: Up to 8 TB.
  - Snowball: ~50–80 TB per device.
  - Snowmobile: For exabyte-scale transfers.
  - Best for: Large offline transfers or when bandwidth is limited.
- [AWS Transfer Family](https://aws.amazon.com/aws-transfer-family/?c=mt&sec=srv)
  The AWS Transfer Family is all about enabling secure file transfers to and from AWS, using familiar and traditional protocols like SFTP, FTPS, and FTP — but fully managed and integrated with AWS services.
  - Use case: Managed SFTP, FTPS, FTP servers.
  - Supports: S3, EFS as backends.
  - Best for: Legacy systems integration via file transfer protocols.
- [AWS Mainframe Modernization Service](https://aws.amazon.com/mainframe-modernization/?c=mt&sec=srv)
  AWS Mainframe Modernization service is a unique platform that allows you to migrate and modernize your on-premises mainframe applications.
- [AWS DataSync](https://aws.amazon.com/datasync/?c=mt&sec=srv) > `Online`
  AWS DataSync is a fully managed data transfer service that simplifies, automates, and accelerates like `1.` On-prem → AWS (like S3, EFS, FSx), `2.` AWS → On-prem & `3.` Between AWS services/regions.
  - Use case: Automated data transfer between on-prem storage and AWS.
  - Supports: NFS, SMB, Amazon S3, EFS, FSx.
  - Pros: Fast, secure, can run on schedule.
  - Best for: Recurring or large-scale data migration.
- Developer-Friendly Tools
  - AWS CLI & SDKs
  - [Amazon Kinesis Data Firehose](https://aws.amazon.com/firehose/)
    It's a fully managed service provided by AWS that allows you to easily capture, transform, and load streaming data into various destinations like Amazon S3, Amazon Redshift, Amazon Elasticsearch Service (Amazon OpenSearch Service), and more. It’s part of the Kinesis family of services, which are designed to handle real-time data streaming.
    - Use case: Real-time streaming data to AWS services (S3, Redshift, etc.).
    - Best for: Logs, metrics, real-time data pipelines.
  - [AWS Glue](https://aws.amazon.com/glue/)
    It's a serverless data integration service provided by Amazon Web Services. It helps you discover, prepare, move, and transform data for analytics, machine learning, and application development.
    - Use case: ETL (Extract, Transform, Load).
    - Supports: S3, RDS, Redshift, JDBC, and more.
    - Best for: Data lakes, data warehouse migrations.

![Here's a comparison table that highlights the key differences between the AWS Data Transfer-related services you mentioned:](/img/data-transfer.png)

#### IaC, Provisioning - CloudFormation, Terraform

- `Faster deployments:` Automate the creation and management of infrastructure.
- `Consistency:` Reduce errors by using templates.
- `Scalability:` Easily replicate environments.
- `Better management:` Track changes with version control.
- `Example:` AWS CloudFormation lets you define your entire infrastructure in code (Infrastructure as Code, or IaC).

### Domain 2: Security and Compliance

In AWS, **security** is a shared responsibility between AWS and the customer. To help customers fulfill their responsibilities, AWS provides security services, documentation, and tools.

- Identity and access management
- Detection and response
- Data protection
- Compliance
- Network and application protection

#### AWS IAM Identity Center (Formerly AWS SSO)

IAM is the AWS service that controls access to AWS resources. It helps you securely manage access to AWS services and resources for users.

##### Key Features:

- `Users:` Individual identities with long-term credentials.
- `Groups:` Collections of users with common permissions.
- `Roles:` Identities with specific permissions that can be assumed by users or services.
- `Policies:` JSON documents that define permissions.

##### How IAM and IAM Identity Center Work Together

| Feature                      | IAM                  | IAM Identity Center (SSO)        |
| ---------------------------- | -------------------- | -------------------------------- |
| Manages AWS resources access | Yes                  | Yes (via permission sets)        |
| Supports SSO                 | No (local only)      | Yes                              |
| Federation support           | Limited              | Full (OIDC, SAML, SCIM, etc.)    |
| Multi-account access         | Manual (roles)       | Built-in                         |
| Directory integration        | Only limited via IAM | Supports AD, Entra ID, Okta etc. |

##### Shared Responsibility Model of IAM

| AWS (Provider)                           | User                                                     |
| :--------------------------------------- | :------------------------------------------------------- |
| Infrastructure (global network security) | Users, Groups, Roles, Policies management and monitoring |
| Configuration and vulnerability analysis | Enable MFA on all accounts                               |
| Compliance validation                    | Rotate all your keys often                               |
| -                                        | Use IAM tools to apply appropriate permissions           |
| -                                        | Analyze access patterns & review permissions             |

##### [Shared Responsibility Model](https://aws.amazon.com/compliance/shared-responsibility-model/)

Security and Compliance is a shared responsibility between AWS and the customer. This shared model can help relieve the customer’s operational burden as AWS operates, manages and controls the components from the host operating system and virtualization layer down to the physical security of the facilities in which the service operates. The customer assumes responsibility and management of the guest operating system (including updates and security patches), other associated application software as well as the configuration of the AWS provided security group firewall.
![shared-responsibility-model](/img/shared-responsibility-model.png)

##### Shared Responsibilities

Some responsibilities are shared, depending on the service and use case:

- AWS manages infrastructure-level encryption, but you manage application-level encryption.
- AWS offers compliance certifications, but you need to ensure your workloads follow them.

![Comparison](/img/security-share-responsibilty.png)

#### Management and Governance

##### AWS Control Tower

AWS Control Tower offers a straightforward way to set up and govern an AWS multi-account environment, following prescriptive best practices. AWS Control Tower orchestration extends the capabilities of AWS Organizations. AWS Control Tower applies preventive and detective controls (guardrails) to help keep your organizations and accounts from divergence from best practices (drift).

**Features for AWS Control Tower**

- Set up multi-account environment quickly
- Automation and built-in governance
- Pre-configured Controls
- Integrate third-party software at scale

##### AWS Organizations

AWS Organizations is a service from Amazon Web Services that lets you centrally manage and govern multiple AWS accounts. It’s especially useful for businesses that want to create separate AWS accounts for different departments, projects, or teams while still keeping control from a central location.

**Features for AWS Organizations**

- Manage your AWS accounts
- Define and manage your organization
- Secure and monitor your accounts
- Share resources across accounts
- Audit your environment for compliance
- Centrally manage billing and costs

**Architecture**

![Architecture](/img/organization-control-tower.png)

##### Landing Zone

A Landing Zone within AWS Control Tower is a securely architected multi-account AWS environment where you enforce certain compliance and security best practices. Basically, it is the container that holds all of your organization units, accounts, users, and other resources that you want to be subject to a particular set of compliance restrictions. It automates the setup using predefined blueprints for identity management, federated access, and account structures, which include centralized logging and cross-account security audits.

##### Service Control Policies

In AWS Organizations used to manage and enforce governance rules across multiple AWS accounts. SCPs enable you to define the maximum available permissions for accounts within your organization, providing a central way to control which AWS services and actions can be accessed by users and roles in those accounts.

**Comparison between AWS Organization and AWS Control Tower**

| Feature              | **AWS Organizations**                                        | **AWS Control Tower**                                               |
| -------------------- | ------------------------------------------------------------ | ------------------------------------------------------------------- |
| **Purpose**          | Manually manage multiple AWS accounts, billing, and policies | Automate the setup of a secure, compliant multi-account environment |
| **Setup Complexity** | Low-level, manual setup required                             | High-level, guided setup with automation                            |
| **Account Creation** | Manually create accounts via CLI/API or console              | Automates account creation via **Account Factory**                  |
| **Governance**       | Uses **Service Control Policies (SCPs)**                     | Uses SCPs, plus **Guardrails** (prebuilt SCPs and AWS Config rules) |
| **Landing Zone**     | You build your own                                           | Prebuilt landing zone architecture (AWS best practices)             |
| **UI**               | No dedicated UI – uses AWS Console/CLI                       | Dedicated dashboard for governance and account management           |
| **Ideal For**        | Advanced users, custom setups                                | Medium to large organizations looking for fast, standardized setup  |

#### Security Hub - AWS Security, Identity, & Compliance services

Unify your cloud security operations and prioritizes your critical security issues and helps you respond at scale.

- `Identity and Access Management`
  1. `AWS Identity and Access Management (IAM)` - Securely manage identities and access to AWS services and resources.
  2. `AWS IAM Identity Center` - Centrally manage workforce access to multiple AWS accounts and applications.
  3. `Amazon Cognito` - Implement secure, frictionless customer identity and access management that scales.
  4. `Amazon Verified Permissions` - Manage fine-grained permissions and authorization within custom applications.
  5. `AWS Directory Service` - Gain efficiency with a fully managed Microsoft Active Directory service.
  6. `AWS Resource Access Manager` - Simply and securely share your AWS resources across multiple accounts.
  7. `AWS Organizations` - Centrally manage your environment as you scale your AWS resources.

- `Detection and Response`
  1. `Amazon GuardDuty` - Protect AWS accounts with intelligent threat detection.
  2. `Amazon Inspector` - Automated and continual vulnerability management at scale.
  3. `AWS Security Hub` - Automate AWS security checks and centralize security alerts.
  4. `Amazon Security Lake` - Automatically centralize your security data in a few steps.
  5. `Amazon Detective` - Analyze and visualize security data to investigate potential security issues.
  6. `AWS Security Incident Response` - Prepare for, respond to, and recover from security events
  7. `AWS Config` - Assess, audit, and evaluate configurations of your resources.
  8. `Amazon CloudWatch` - Observe and monitor resources and applications on AWS, on premises, and on other clouds.
  9. `AWS CloudTrail` - Track user activity and API usage.
  10. `AWS IoT Device Defender` - Security management across your IoT devices and fleets.
  11. `AWS Elastic Disaster Recovery`- Scalable, cost-effective application recovery to AWS.

- `Network and Application Protection`
  1. `AWS Firewall Manager` - Centrally configure and manage firewall rules across your accounts.
     - `AWS Network Firewall` - Deploy network firewall security across your VPCs.
     - `AWS Shield` - Maximize application availability and responsiveness with managed DDoS protection.
     - `AWS Web Application Firewall (WAF)` - Protect your web applications from common exploits.
  2. `AWS Verified Access` - Provide secure access to corporate applications without a VPN.
  3. `Amazon Route 53 Resolver DNS Firewall` - Filter and control outbound DNS traffic for your VPCs.

- `Data Protection`
  1. `Amazon Macie` - Discover and protect your sensitive data at scale.
  2. `AWS Key Management Service (KMS)` - Create and control keys to encrypt or digitally sign your data.
  3. `AWS CloudHSM` - Manage single-tenant hardware security modules (HSMs) on AWS.
  4. `AWS Certificate Manager` - Provision and manage SSL/TLS certificates with AWS services and connected resources.
  5. `AWS Payment Cryptography` - Simplify cryptography operations in your cloud-hosted payment applications.
  6. `AWS Private Certificate Authority` - Create private certificates to identify resources and protect data.
  7. `AWS System Manager` - It's manage Session Manager, Parameter Store, or Patch Manager.
  8. `AWS Secrets Manager` - Centrally manage the lifecycle of secrets.

- `Compliance`
  1. `AWS Artifact` - No cost, self-service portal for on-demand access to AWS’ compliance reports.
  2. `AWS Audit Manager` - Continually audit your AWS usage to simplify risk and compliance assessment.

- Security Hub
![Security Hub](/img/security-hub.png)

##### Identity and Access Management - Each compontent's breif discussion

1. `AWS Identity and Access Management (IAM)` - Securely manage identities and access to AWS services and resources.

2. `AWS IAM Identity Center` - Centrally manage workforce access to multiple AWS accounts and applications.

3. `Amazon Cognito` - Implement secure, frictionless customer identity and access management that scales.

4. `Amazon Verified Permissions` - Manage fine-grained permissions and authorization within custom applications.

5. `AWS Directory Service` - Gain efficiency with a fully managed Microsoft Active Directory service.

6. `AWS Resource Access Manager` - Simply and securely share your AWS resources across multiple accounts.

7. `AWS Organizations` - Centrally manage your environment as you scale your AWS resources.

##### Detection and Response - Each compontent's breif discussion

1. `Amazon GuardDuty` - Protect AWS accounts with intelligent threat detection.

2. `Amazon Inspector` - Automated and continual vulnerability management at scale.

3. `AWS Security Hub` - Automate AWS security checks and centralize security alerts.

4. `Amazon Security Lake` - Automatically centralize your security data in a few steps.

5. `Amazon Detective` - Analyze and visualize security data to investigate potential security issues.

6. `AWS Security Incident Response` - Prepare for, respond to, and recover from security events

7. `AWS Config` - Assess, audit, and evaluate configurations of your resources.

8. `Amazon CloudWatch` - Observe and monitor resources and applications on AWS, on premises, and on other clouds.

9. `AWS CloudTrail` - Track user activity and API usage.

10. `AWS IoT Device Defender` - Security management across your IoT devices and fleets.

11. `AWS Elastic Disaster Recovery`- Scalable, cost-effective application recovery to AWS.

##### Network and Application Protection - Each compontent's breif discussion

1. `AWS Firewall Manager` - Centrally configure and manage firewall rules across your accounts.
   - `AWS Network Firewall` - Deploy network firewall security across your VPCs.

   - `AWS Shield` - Maximize application availability and responsiveness with managed DDoS protection.

   - `AWS Web Application Firewall (WAF)` - Protect your web applications from common exploits.

AWS WAF is a web application firewall that helps secure your web applications and APIs by blocking requests before they reach your servers. For more information, see Accelerate and protect your websites using CloudFront and AWS WAF and Guidelines for Implementing AWS WAF.

> Key Features

- Protection Against:
  - SQL Injection - Malicious database queries
  - Cross-Site Scripting (XSS) - Malicious scripts in web pages
  - DDoS attacks - Application layer floods
  - Bot attacks - Automated malicious traffic
  - OWASP Top 10 - Common web vulnerabilities

- Rule Types
  - IP-based rules - Block/allow specific IPs or ranges
  - Geographic rules - Block traffic from specific countries
  - Rate limiting - Limit requests per IP
  - String matching - Block requests containing specific patterns
  - Size constraints - Limit request size

- Where WAF Works
  - Supported Services:
  - CloudFront (CDN)
  - Application Load Balancer (ALB)
  - API Gateway
  - AppSync (GraphQL)

2. `AWS Verified Access` - Provide secure access to corporate applications without a VPN.

3. `Amazon Route 53 Resolver DNS Firewall` - Filter and control outbound DNS traffic for your VPCs.

##### Data Protection - Each compontent's breif discussion

1. `Amazon Macie` - Discover and protect your sensitive data at scale.

Amazon Macie is a fully managed data security and data privacy service `AI` tool that uses machine learning to discover, classify, and protect sensitive data in AWS.

> Key Features

- Data Discovery & Classification:
  - Automatically discovers sensitive data in S3 buckets
  - Identifies PII, PHI, financial data, credentials
  - Uses ML and pattern matching

- Supported Data Types:
  - Personal Identifiable Information (PII)
  - Protected Health Information (PHI)
  - Financial data (credit cards, bank accounts)
  - AWS credentials and API keys

- Security Findings:
  - Policy violations
  - Unusual access patterns
  - Data exposure risks
  - Unencrypted sensitive data

2. `AWS Key Management Service (KMS)` - Create and control keys to encrypt or digitally sign your data.

3. `AWS CloudHSM` - Manage single-tenant hardware security modules (HSMs) on AWS.

4. `AWS Certificate Manager` - Provision and manage SSL/TLS certificates with AWS services and connected resources.

5. `AWS Payment Cryptography` - Simplify cryptography operations in your cloud-hosted payment applications.

6. `AWS Private Certificate Authority` - Create private certificates to identify resources and protect data.

7. `AWS System Manager` - It's manage Session Manager, Parameter Store, or Patch Manager.

AWS Systems Manager is an integrated, Operations management service for AWS infrastructure

- Key Features
  - Parameter Store - Store configuration data and secrets
  - Session Manager - Secure shell access to EC2 without SSH keys
  - Patch Manager - Automate OS patching
  - Run Command - Execute commands across multiple instances
  - State Manager - Maintain consistent configurations

- Use Cases
  - Infrastructure management
  - Configuration management
  - Operational tasks automation
  - System maintenance

1. `AWS Secrets Manager` - Centrally manage the lifecycle of secrets.

AWS Secrets Manager is a Dedicated secrets management service

- Key Features
  - Automatic Rotation - Rotate secrets automatically
  - Encryption - Encrypt secrets at rest and in transit
  - Fine-grained Access - IAM-based access control
  - Audit Trail - CloudTrail integration for compliance
  - Cross-region Replication - Replicate secrets across regions

- Use Cases
  - Database credentials
  - API keys
  - OAuth tokens
  - Application secrets

##### Key Differences:

| **Feature**               | **AWS Systems Manager Parameter Store**                        | **AWS Secrets Manager**                                              |
| ------------------------- | -------------------------------------------------------------- | -------------------------------------------------------------------- |
| **Primary Purpose**       | Infrastructure and configuration management                    | Secure storage and management of secrets (credentials, keys, tokens) |
| **Automatic Rotation**    | No                                                             | Yes                                                                  |
| **Cost**                  | Free for standard parameters (Advanced tier incurs small cost) | Pay per secret                                                       |
| **Secret Size Limit**     | 4 KB (Standard), 8 KB (Advanced)                               | 64 KB                                                                |
| **Built-in Integrations** | Limited                                                        | Deep integrations with RDS, Redshift, DocumentDB, and others         |
| **Compliance Focus**      | Operational management                                         | Security and compliance (e.g., audit, encryption rotation)           |

##### Compliance - Each compontent's breif discussion

1. `AWS Artifact` - No cost, self-service portal for on-demand access to AWS’ compliance reports.

2. `AWS Audit Manager` - Continually audit your AWS usage to simplify risk and compliance assessment.

#### Security Group

An AWS Security Group acts as a virtual firewall for your EC2 instances to control inbound and outbound traffic at the instance level.

- Key Characteristics
  - Instance-Level Firewall – Controls traffic at the EC2 instance or Elastic Network Interface (ENI) level.
  - Stateful – Automatically allows return traffic for inbound and outbound connections.
  - Allow Rules Only – You can only allow traffic, not explicitly deny it.
  - Immediate Effect – Changes to rules apply instantly without restarting instances.
  - Multiple Security Groups per Instance – An EC2 instance can have more than one security group attached.
  - VPC-Specific – Security groups are tied to a specific VPC; they cannot span multiple VPCs.
  - Support for IP and SG References – Rules can allow traffic from IP ranges (CIDR blocks) or other security groups.
  - Separate Inbound and Outbound Rules – You must configure both inbound and outbound traffic rules separately.

- Default Security Group Behavior:
  - Allows all outbound traffic.
  - Allows inbound traffic only from resources associated with the same group.
  - Soft Limit on Number of Rules – There are limits (which can be increased) on the number of rules per security group and number of groups per instance.
  - Free to Use – There’s no additional cost for using security groups.

Illustration of Security Group
![Security Group](/img/security-group.png)

Illustration of Security Group Details
![Security Group Details](/img/sg-details.png)

Security Group Diagram
Illustration of Security Group Diagram
![Security Group Diagram](/img/sg-diagram.png)

Illustration of SG Diagram Ref Other SG
![SG Diagram Ref Other SG](/img/sg-diagram-ref-other-sg.png)

#### Network Access Control List (ACL)

A network access control list (ACL) allows or denies specific inbound or outbound traffic at the subnet level. You can use the default network ACL for your VPC, or you can create a custom network ACL for your VPC with rules that are similar to the rules for your security groups in order to add an additional layer of security to your VPC.

- Key Characteristics
  - Subnet-level firewall (applies to all instances in subnet)
  - Stateless - must configure both inbound and outbound rules
  - Numbered rules processed in order (lowest first)
  - Default NACL allows all traffic

- How it Works
  - Controls traffic entering/leaving subnets
  - Rules evaluated by rule number (1-32766)
  - First matching rule applies
  - Default deny rule (*) at end

##### NACL vs Security Groups:

| **Feature**          | **NACL (Network Access Control List)**            | **Security Groups**                   |
| -------------------- | ------------------------------------------------- | ------------------------------------- |
| **Level**            | Subnet level                                      | Instance level                        |
| **State**            | Stateless (needs both inbound and outbound rules) | Stateful (automatic response allowed) |
| **Rules**            | Allow and Deny rules                              | Allow rules only                      |
| **Processing**       | Rules are evaluated in order                      | All rules are evaluated together      |
| **Default Behavior** | Allows all traffic                                | Denies all traffic                    |

#### Firewalls & [Distributed Denial of Service (DDoS) Protection](https://aws.amazon.com/shield/ddos-attack-protection/)

- A firewall is a security system (hardware, software, or both) that monitors and controls incoming and outgoing network traffic based on predetermined security rules. To act as a barrier between a trusted internal network and untrusted external networks (like the internet), blocking malicious traffic.
- DDoS attacks attempt to overwhelm a network, server, or service with massive traffic from multiple sources to make it unavailable to legitimate users. To detect, mitigate, and recover from DDoS attacks before they cause downtime or service degradation.

##### Firewall vs. DDoS Protection

| Feature/Aspect              | **Firewall**                               | **DDoS Protection**                            |
| --------------------------- | ------------------------------------------ | ---------------------------------------------- |
| **Primary Function**        | Controls & filters network traffic         | Detects & mitigates traffic floods             |
| **Main Goal**               | Prevent unauthorized access                | Maintain service availability during attacks   |
| **Type of Threats Handled** | Malware, intrusions, unauthorized access   | Volume-based, protocol, and app-layer attacks  |
| **Traffic Analysis**        | Packet inspection (rules, policies)        | Behavior & pattern analysis (attack detection) |
| **Deployment**              | Network perimeter, host-based, cloud       | Cloud-based, edge network, inline appliances   |
| **Can Stop DDoS?**          | Not reliably (can be overwhelmed)          | Yes, specifically designed for that            |
| **Stateful Tracking**       | Yes (for stateful firewalls)               | Not typically, focuses on anomaly patterns     |
| **Real-Time Adaptation**    | Limited (static rules/policies)            | Advanced (dynamic mitigation, auto-scaling)    |
| **Best Use Case**           | Network access control and filtering       | Protecting against service downtime            |
| **Complementary?**          | Yes, part of overall security architecture | Yes, enhances firewall resilience              |

### Domain 3: Cloud Technology and Services

#### [AWS Compute Services](https://aws.amazon.com/products/compute/)

AWS offers a wide range of compute services for diverse workloads, from virtual servers to serverless functions and container orchestration. Key services include Amazon `EC2 (Elastic Compute Cloud)`, AWS `Fargate`, AWS `Lambda`, Amazon `ECS (Elastic Container Service)` and Amazon `EKS (Elastic Kubernetes Service)`, along with other specialized services like `AWS Batch` and `Lightsail`.

##### Elastic Compute - EC2

Amazon EC2 is a core AWS service that provides resizable compute capacity in the cloud. It allows you to run virtual servers (instances) on-demand, giving you full control over the operating system, software stack, and network settings.

- Key Components of EC2
  - Instances – Virtual machines running on physical hardware managed by AWS.
  - AMI (Amazon Machine Image) – A pre-configured OS image used to launch EC2 instances.
  - Instance Types – Define the compute, memory, and storage capacity (e.g., t3.micro, m5.large, c7g.xlarge).
  - EBS (Elastic Block Store) – Persistent block storage volumes attached to EC2 instances.
  - Security Groups – Firewalls that control inbound/outbound traffic at the instance level.
  - Key Pairs – SSH keys used to securely connect to Linux/Unix instances.
  - Elastic IPs – Static, public IPv4 addresses that can be associated with instances.
  - User Data – Scripts that run at instance launch (used for automation/configuration).
  - EC2 Metadata Service – Allows instances to query data about themselves (e.g., instance ID, IP address).

##### EC2 Instances Purchasing Options

|  SL   | Instance Name         |   Period   | Description                                                |
| :---: | :-------------------- | :--------: | :--------------------------------------------------------- |
|   1   | On-Demand             | Short Time | short workload, predictable pricing, pay by second         |
|   1   | Reserved Instances    | 1-3 Years  | long workloads with flexible instances                     |
|   2   | Savings Plans         | 1-3 Years  | commitment to an amount of usage, long workload            |
|   3   | Spot Instances        | Short Time | short workloads, cheap, can lose instances (less reliable) |
|   4   | Dedicated Hosts       | Long Time  | book an entire physical server, control instance placement |
|   5   | Dedicated Instances   |    N/A     | no other customers will share your hardware                |
|   6   | Capacity Reservations |    N/A     | reserve capacity in a specific AZ for any duration         |

#### [AWS Database Service](https://docs.aws.amazon.com/whitepapers/latest/aws-overview/database.html)

AWS offers a wide range of database services, covering everything from traditional relational databases to modern NoSQL, in-memory, and graph databases. Here's a breakdown of the major ones by type:

- Relational Databases (SQL)
  - [Amazon RDS (Relational Database Service)](https://aws.amazon.com/rds/?p=ft&c=db&z=3)
    - Fully managed database service for SQL-based engines.
    - Supports: MySQL, PostgreSQL, MariaDB, Oracle, SQL Server, Aurora.
    - Handles backups, patching, scaling, etc.
  - [Amazon Aurora](https://aws.amazon.com/rds/aurora/)
    - High-performance, cloud-native relational database.
    - Compatible with MySQL and PostgreSQL.
    - Up to 5x faster than standard MySQL, with built-in replication and high availability.
    - Serverless version: Aurora Serverless v2 (auto-scales capacity).
- NoSQL Databases
  - Amazon DynamoDB
    - Fully managed key-value and document NoSQL database.
    - Ultra-fast, scalable, and serverless.
    - Ideal for real-time apps, gaming, IoT, serverless apps.
  - Amazon ElastiCache
    - In-memory caching service.
    - Supports: Redis and Memcached.
    - Great for speeding up apps with frequently accessed data (e.g., sessions, leaderboards).
- Amazon Keyspaces (for Apache Cassandra)
  - Managed Cassandra-compatible NoSQL database.
  - Serverless and scalable.
- Graph, Time Series, and Ledger
  - Amazon Neptune
    - Graph database for highly connected data.
    - Supports: Gremlin and SPARQL.
    - Use cases: social networks, recommendation engines, fraud detection.

##### Comparison of Amazon RDS vs Amazon Aurora

| Feature                  | Amazon RDS                                     | Amazon Aurora                                         |
| ------------------------ | ---------------------------------------------- | ----------------------------------------------------- |
| **Engine Compatibility** | MySQL, PostgreSQL, MariaDB, Oracle, SQL Server | MySQL, PostgreSQL                                     |
| **Performance**          | Standard performance                           | Up to 5x faster than MySQL, 2x faster than PostgreSQL |
| **Availability**         | Multi-AZ deployment option                     | Multi-AZ replication, automatic failover              |
| **Storage Scaling**      | Scalable storage (up to 16 TB)                 | Automatic scaling up to 128 TB                        |
| **Cost**                 | Generally lower cost                           | Higher cost, but higher performance and scalability   |
| **Backup & Recovery**    | Automated backups with point-in-time recovery  | Continuous backups to S3, point-in-time recovery      |
| **Replication**          | Read replicas available (varies by engine)     | Aurora Replicas, up to 15 replicas                    |

#### AWS Lambda

A serverless compute service that runs your code in response to events. You don’t manage servers — AWS handles provisioning and scaling.

#### AWS Fargate

A serverless compute engine for containers, used with Amazon ECS or EKS. Lets you run containers without managing servers or clusters.

##### AWS Lambda vs AWS Fargate

| Feature                | **AWS Lambda**                   | **AWS Fargate**                         |
| ---------------------- | -------------------------------- | --------------------------------------- |
| **Use Case**           | Event-driven, short tasks        | Containerized apps, long-running tasks  |
| **Runtime**            | Managed by AWS runtimes          | Custom Docker containers                |
| **Startup Time**       | Very fast (cold starts possible) | Slower (container startup time)         |
| **Max Execution Time** | 15 minutes                       | No hard limit                           |
| **Stateful?**          | Stateless                        | Can be stateful (with volumes like EFS) |
| **Billing**            | Per request + GB-seconds         | Per vCPU + memory per second            |
| **Infrastructure**     | Fully managed                    | More control (networking, IAM, etc.)    |
| **Scaling**            | Auto-scales instantly            | Scales well (slower than Lambda)        |

#### Amazon Lightsail

Amazon Lightsail is a simplified cloud platform by AWS that offers easy-to-use virtual private servers (VPS) with bundled compute, storage, and networking.
It is designed for users who need a quick, cost-predictable, and beginner-friendly way to launch websites, web apps, or small databases without managing complex AWS infrastructure.

> Best for: Small websites, blogs, testing environments, and startups that want fixed monthly pricing.

#### AWS Elastic Beanstalk

AWS Elastic Beanstalk is a Platform as a Service (PaaS) that lets you deploy and manage web applications without worrying about the underlying infrastructure.
You simply upload your code, and Elastic Beanstalk automatically handles provisioning, load balancing, scaling, and monitoring.

> Best for: Developers building web apps or APIs who want AWS to manage the infrastructure but still need flexibility and control over the environment.

##### Amazon Lightsail vs AWS Elastic Beanstalk

| **Feature**                         | **Amazon Lightsail**                                          | **AWS Elastic Beanstalk**                                      |
| ----------------------------------- | ------------------------------------------------------------- | -------------------------------------------------------------- |
| **Target Audience**                 | Developers looking for simplicity, small businesses, startups | Developers requiring more flexibility and scaling options      |
| **Infrastructure Control**          | Minimal control, focuses on ease of use                       | More control over the infrastructure and configurations        |
| **Pricing**                         | Fixed, predictable pricing plans                              | Pay-as-you-go (EC2 instances, storage, etc.)                   |
| **Ease of Use**                     | Very easy to use, minimal configuration required              | Easy to use, but requires some understanding of AWS services   |
| **Scalability**                     | Limited scalability for larger apps                           | Autoscaling for high availability and large-scale apps         |
| **Customizability**                 | Limited customizability                                       | High degree of customization and configuration                 |
| **Supported Applications**          | Simple web apps, static sites, small applications             | Web apps, microservices, enterprise applications               |
| **Supported Programming Languages** | Limited to pre-configured stacks (e.g., LAMP, Node.js)        | Supports multiple programming languages and frameworks         |
| **Integration with AWS**            | Limited to Lightsail-specific features (e.g., S3, RDS)        | Full integration with AWS services (e.g., RDS, S3, CloudWatch) |

#### [DNS, Networking and content delivery](https://docs.aws.amazon.com/whitepapers/latest/aws-overview/networking-services.html)

##### [Amazon VPC](https://docs.aws.amazon.com/whitepapers/latest/aws-overview/networking-services.html)

##### [AWS VPN](https://docs.aws.amazon.com/whitepapers/latest/aws-overview/networking-services.html)

##### [Elastic Load Balancing](https://docs.aws.amazon.com/whitepapers/latest/aws-overview/networking-services.html)

Elastic Load Balancing (ELB) is an AWS service that automatically distributes incoming traffic across multiple targets — such as EC2 instances, containers, IP addresses, or Lambda functions — to ensure high availability, fault tolerance, and scalability of your application.
![Load Balancing](/img/load-balancing.png)

- Key Characteristics
  - High Availability – Spreads traffic across multiple targets in one or more Availability Zones.
  - Automatic Scaling – Handles sudden spikes in traffic by automatically scaling to meet demand.
  - Health Checks – Routinely checks the health of targets and stops sending traffic to unhealthy ones.
  - Secure – Supports SSL/TLS termination, integration with AWS Certificate Manager (ACM), and IAM.
  - Fully Managed – AWS handles maintenance, scaling, and failover.

- Types of Elastic Load Balancers

| Type                                       | Description                                                                                         | Use Case                                |
| ------------------------------------------ | --------------------------------------------------------------------------------------------------- | --------------------------------------- |
| **Application Load Balancer (ALB)**        | Works at **Layer 7 (HTTP/HTTPS)**. Routes requests based on **URL, host, headers**, etc.            | Web apps, microservices, REST APIs      |
| **Network Load Balancer (NLB)**            | Works at **Layer 4 (TCP/UDP)**. Handles **millions of requests per second** with ultra-low latency. | Real-time apps, gaming, high-throughput |
| **Gateway Load Balancer (GWLB)**           | Distributes traffic to **third-party virtual appliances** (firewalls, intrusion detection, etc.).   | Network security and monitoring         |
| **Classic Load Balancer (CLB)** *(legacy)* | Supports both Layer 4 and Layer 7, but with **limited features**.                                   | Legacy applications only                |

![Elastic Load Balancer](/img/elastic-load-balancer.png)

##### [Auto Scaling Group (ASG)](https://docs.aws.amazon.com/autoscaling/ec2/userguide/auto-scaling-groups.html)

An Auto Scaling Group (ASG) in AWS is a feature of EC2 Auto Scaling that automatically launches or terminates EC2 instances based on defined policies, to ensure your application maintains desired availability, performance, and cost-efficiency.

- Key Characteristics
  - Automatic Scaling – Adjusts EC2 instance count based on demand (e.g., CPU, traffic).
  - Desired Capacity Maintenance – Replaces unhealthy instances to maintain target capacity.
  - ELB Integration – Distributes traffic via Elastic Load Balancer.
  - Scaling Options
  - Manual – Set instance count manually.
  - Scheduled – Scale at predefined times.
  - Dynamic – Scale based on metrics (e.g., CPU, custom alarms).
  - Multi-AZ Support – Launches instances across Availability Zones for high availability.
  - Launch Template/Configuration – Defines how instances are launched (AMI, type, key, etc.).
  - Health Checks – Detects and replaces failed instances using EC2 or ELB health checks.

- Auto Scaling Group
![Auto Scaling Group](/img/auto-scaling-group.png)

- Auto Scaling Group with Load Balancer
![Auto Scaling Group with Load Balancer](/img/auto-scaling-group-load-balancer.png)

- Difference between Load Balancer and Auto Scaling

| **Factors**        | **Load Balancer**                    | **Auto Scaling**                   |
| :----------------- | :----------------------------------- | :--------------------------------- |
| **Purpose**        | Distribute incoming traffic          | Adjust the number of resources     |
| **Algorithm Used** | Round-robin, least connections, etc. | Step Scaling, Target Tracking      |
| **Function**       | Routes traffic to healthy targets    | Adds/removes EC2 instances         |
| **Type**           | Traffic management (Layer 4/7)       | Compute resource management        |
| **Health Checks**  | Detects unhealthy targets            | Replaces failed instances          |
| **Integration**    | Works with Auto Scaling & ELB        | Works with Load Balancer           |
| **Scaling**        | Does not scale resources             | Scales based on demand             |
| **Configuration**  | Target groups, listeners, rules      | Launch templates, scaling policies |

##### [Target Group (TG)](https://docs.aws.amazon.com/elasticloadbalancing/latest/network/load-balancer-target-groups.html)

A Target Group in AWS is a configuration that defines the set of targets (like EC2 instances, IP addresses, or Lambda functions) that a Load Balancer routes traffic. It is used primarily with Elastic Load Balancers (ELB) — especially Application Load Balancer (ALB) and Network Load Balancer (NLB).
![Target Group](/img/target-group.jpg)

- Key Characteristics
  - Defines Targets: EC2 instances, IP addresses, Lambda functions, or ECS tasks.
  - Health Checks: Monitors target health; excludes unhealthy targets from traffic.
  - Used by Load Balancers: Routes traffic to registered targets based on rules.
  - Target Type: Specifies how targets are identified (instance, ip, lambda, alb).
  - Port Configuration: Defines the port for sending traffic to targets.
  - Multiple Target Groups: Supports multiple groups per load balancer for fine-grained routing.

#### [Amazon API Gateway](https://docs.aws.amazon.com/whitepapers/latest/aws-overview/networking-services.html)

#### [Amazon CloudFront](https://docs.aws.amazon.com/whitepapers/latest/aws-overview/networking-services.html)

#### [Amazon Route 53](https://docs.aws.amazon.com/whitepapers/latest/aws-overview/networking-services.html)

Amazon Route 53 is a scalable and highly available Domain Name System (DNS) web service by AWS. A Route 53 record (or DNS record) is used to define how you want to route traffic for a domain or subdomain. Here's a quick breakdown of what you need to know:

- DNS Record

| Record Type | Purpose                                                     |
| ----------- | ----------------------------------------------------------- |
| A           | Maps a domain to an IPv4 address.                           |
| AAAA        | Maps a domain to an IPv6 address.                           |
| CNAME       | Maps a domain to another domain (used for aliasing).        |
| MX          | Specifies mail servers for email delivery.                  |
| TXT         | Holds arbitrary text (e.g., SPF, domain verification).      |
| NS          | Lists authoritative name servers for the domain.            |
| SOA         | Start of Authority – provides info about the domain/zone.   |
| SRV         | Specifies location of services (e.g., SIP, XMPP).           |
| Alias       | AWS-specific alias to AWS resources (e.g., S3, CloudFront). |

- A Record Example

| Record Type | Value             |
| ----------- | ----------------- |
| Name:       | <www.example.com> |
| Type:       | A                 |
| Value       | : 54.123.45.67    |
| TTL:        | 300 (seconds)     |

- Alias Record Example

| Record Type     | Value                |
| --------------- | -------------------- |
| Name:           | example.com          |
| Type:           | A (Alias)            |
| Alias Target:   | d1234.cloudfront.net |
| Routing Policy: | Simple               |

#### [AWS Storage Services](https://docs.aws.amazon.com/whitepapers/latest/aws-overview/storage-services.html)

There are `three` types of storage in Amazon Web Services

1. Object Storage
   - **S3 Storage:** Scalable, durable storage for storing and retrieving any amount of data as objects.
   - **S3 Glacier Storage:** Low-cost, long-term archival storage for infrequently accessed data.
   - **Snowball Storage:** Physical data transport solution to move large amounts of data in/out of AWS.
2. File Storage
   - **Elastic File System (EFS):** Scalable, elastic file storage accessible by multiple instances via NFS.
   - **FSx Storage (Windows):** Fully managed Windows file system with SMB protocol support.
   - **FSx Storage (Lustre):** High-performance file system optimized for compute-intensive workloads.

3. Block Storage
   - **Elastic Block Storage (EBS):** Persistent block-level storage volumes for EC2 instances.
     - **SSD Storage volumes:**
       - *General Purpose (GP2):* Balanced price/performance for a wide variety of workloads.
       - *Provisioned IOPS SSD (io1/io2):* High-performance volumes for latency-sensitive applications.
     - **HDD Storage:**
       - *Throughput Optimized (ST1):* Low-cost HDD for frequently accessed, throughput-intensive workloads.
       - *Cold HDD (SC1):* Lowest cost HDD for less frequently accessed data.
     - **Magnetic Storage:** Legacy magnetic volumes for infrequent access with low cost.
   - **EC2 Instance Storage:** Temporary block storage physically attached to the host instance (ephemeral).

##### Storage Types: Differences & Comparison

| Feature / Storage Type        | Object Storage                                                                       | File Storage                                        | Block Storage                                                      |
| ----------------------------- | ------------------------------------------------------------------------------------ | --------------------------------------------------- | ------------------------------------------------------------------ |
| **Data Organization**         | Stores data as objects (key-value)                                                   | Stores data as files and folders                    | Stores data as fixed-size blocks                                   |
| **Access Protocol**           | HTTP/HTTPS (REST API)                                                                | Network file systems (NFS, SMB)                     | Attached storage to instances (block device)                       |
| **Use Case**                  | Backup, archival, big data, web apps                                                 | Shared storage for applications & OS files          | Boot volumes, databases, transactional data                        |
| **Durability & Availability** | Very high (multiple AZ replication)                                                  | High (replicated across AZs)                        | High (depends on replication & volume type)                        |
| **Performance**               | Optimized for throughput & scalability                                               | Good for shared file access, moderate latency       | Low latency, high IOPS (especially SSD types)                      |
| **Scalability**               | Virtually unlimited                                                                  | Scales elastically with usage                       | Scales by adding volumes or resizing                               |
| **Cost**                      | Varies: S3 is standard, Glacier is cheapest for archives, Snowball for data transfer | Generally higher cost due to file system management | Varies by volume type; SSD more expensive than HDD                 |
| **Examples**                  | S3, S3 Glacier, Snowball                                                             | EFS, FSx (Windows), FSx (Lustre)                    | EBS (GP2, io1/io2, ST1, SC1), EC2 Instance Storage                 |
| **Data Persistence**          | Highly durable and persistent                                                        | Persistent and shared                               | Persistent (except EC2 Instance Storage is ephemeral)              |
| **Data Transfer**             | Internet/Network                                                                     | Network file access                                 | Attached to instance or network attached storage                   |
| **Latency**                   | Higher latency compared to block/file                                                | Moderate latency                                    | Lowest latency                                                     |
| **Best for**                  | Large scale unstructured data, backups, archives                                     | Shared access files, home directories, user data    | Operating system volumes, databases, applications needing fast I/O |

> Notes:

- **S3 Glacier** is optimized for data you rarely access and offers the lowest storage cost with longer retrieval times.
- **Snowball** is not storage you access remotely but a physical device to migrate data to/from AWS.
- **EFS** provides shared file storage for Linux-based workloads; **FSx for Windows** targets Windows-based SMB workloads.
- **FSx for Lustre** is designed for HPC or workloads requiring very fast file storage.
- **EBS SSD volumes (GP2/io1/io2)** provide high-performance block storage suitable for databases.
- **HDD EBS volumes (ST1/SC1)** are cheaper and used for throughput-heavy but less latency-sensitive workloads.
- **EC2 Instance Storage** is ephemeral and data is lost if the instance stops or terminates, used for temporary storage or caches.

##### Storage Decision Matrix

| Use Case                                        | Recommended Storage Type           | Why?                                     |
| ----------------------------------------------- | ---------------------------------- | ---------------------------------------- |
| **Backup & Archival**                           | S3 Glacier, S3 Standard            | Cost-effective, highly durable, scalable |
| **Large-scale data storage**                    | S3 Standard                        | Unlimited scale, easy to access via API  |
| **Bulk data migration**                         | Snowball                           | Physical transfer for large datasets     |
| **Shared file storage (Linux)**                 | Elastic File System (EFS)          | Shared NFS access, scalable, managed     |
| **Shared file storage (Windows)**               | FSx for Windows                    | SMB protocol, Windows native features    |
| **High-performance compute**                    | FSx for Lustre                     | High throughput & low latency for HPC    |
| **Boot volumes for EC2 instances**              | EBS GP2 (General Purpose SSD)      | Balanced performance & cost              |
| **Latency-sensitive DB workloads**              | EBS io1/io2 (Provisioned IOPS SSD) | High IOPS and low latency                |
| **Throughput-intensive workloads**              | EBS ST1 (Throughput Optimized HDD) | Cost-effective for large, streaming data |
| **Cold data, infrequent access**                | EBS SC1 (Cold HDD)                 | Lowest cost for rarely accessed data     |
| **Temporary storage during instance lifecycle** | EC2 Instance Storage               | Fast, ephemeral storage tied to instance |

> How to choose:

- If **scalability and durability** are priorities and latency is not critical → **Object Storage (S3)**.
- If you need **shared file access across multiple servers** → **File Storage (EFS or FSx)**.
- For **low-latency, high-performance storage attached to instances** → **Block Storage (EBS SSD/io1/io2)**.
- For **cost-sensitive, throughput-heavy workloads** → **EBS HDD (ST1 or SC1)**.
- For **moving large amounts of data offline** → **Snowball**.
- For **temporary or scratch data** → **EC2 Instance Storage**.

##### IOPS (eye-ops):

Input/Output Operation per Second is use as I/O performance management measurement to characterize computer storage devices like HDD, SSD & Storage Area Network (SAN). This Operations (reads or writes) that a storage system can perform in one second. It focuses on the speed at which individual read and write operations can be completed. Its measure in KiB.

- Maximum amount of data that a volume type counts as 'Single I/O'.
- I/O size capped at 256 KiB for SSD.
- I/O size capped at 1024 KiB for HDD.
- SSD volumes handle small/random I/O more efficiently than HDD volumes.

- `IOPS Calculation`

Average Seek Time = (`Read Time` + `Write Time`)/`2`
IOPS = 1 / (`RPM Average Latency Time` + `Average Seek Time`)

Suppose,
Rotational Speed = 15,000,
RPM Average Latency Time = 3 ms = 0.003 Seconds,
Average Seek Time = {4.2 (R) + 4.45 (W)}/2 = 4.45 ms = 0.0045 Second

IOPS = 1 / (0.003 + 0.0045) = 133 IOPS (Approximately)

- `Throughput`

Its refers to the rate at which data is transferred successfully between two points in a system, such as between a storage device and a server, or within a network. Throughput can be affected by IOPS & packet size.

#### Storage Gateway

An AWS Storage Gateway is a hybrid cloud storage service that connects your on-premises applications to AWS cloud storage. It allows you to seamlessly extend your local storage infrastructure into AWS, enabling backup, archiving, disaster recovery, or cloud data processing without fully migrating everything at once.

> Key Use Cases

- `Backup and restore:` Keep local data while backing it up to Amazon S3.
- `Disaster recovery:` Replicate on-premises data to the cloud for failover.
- `Archiving:` Move infrequently used data to low-cost Amazon S3 Glacier.
- `Hybrid cloud storage:` Access cloud data with local performance.

##### Types of AWS Storage Gateway

1. File Gateway (NFS/SMB)

- Acts like a network file share for on-premises servers.
- Files are stored as objects in Amazon S3, while recently accessed data is cached locally.
- Supports NFS and SMB protocols.
- Commonly used for file shares, backups, and archiving.

> Use Case
A company wants to store file server data in S3 but still access it locally.

2. Volume Gateway (iSCSI Block Storage)

- Provides cloud-backed block storage volumes.
- Cached Volumes: Primary data is stored in AWS, with frequently accessed data cached locally for low latency.
- Stored Volumes: Entire dataset is stored locally, but asynchronously backed up to AWS as snapshots in Amazon EBS.

> Use Case
Running applications on-premises but keeping a disaster recovery copy in AWS.

3. Tape Gateway (VTL – Virtual Tape Library)

- Emulates physical tape libraries.
- Data is stored on Amazon S3 and can be archived to Amazon S3 Glacier or S3 Glacier Deep Archive.
- Works with existing backup software (e.g., Veeam, Commvault, NetBackup).

> Use Case
Replacing old tape backup systems with a cloud-based solution.

#### Services from other in-scope AWS Service Categories

- `Application Integration Services`
  - `Amazon EventBridge:` Event bus for building event-driven applications at scale.
  - `Amazon SNS (Simple Notification Service):` Pub/sub messaging for decoupled microservices.
  - `Amazon SQS (Simple Queue Service):` Managed message queuing for distributed systems.
- `Business Application Services`
  - `Amazon Connect:` Cloud-based contact center service.
  - `Amazon SES (Simple Email Service):` Scalable email sending for marketing or transactional purposes.
- `Customer Engagement Services`
  - `AWS Activate for Startups:` Credits, training, and support for startup growth.
  - `AWS IQ:` Connects customers with AWS-certified freelancers and consultants.
  - `AWS Managed Services (AMS):` Operational support and automation for AWS infrastructure.
  - `AWS Support:` Tiered support plans offering guidance and troubleshooting.
- `Developer Tools`
  - `AWS AppConfig:` Feature flagging and configuration management.
  - `AWS Cloud9:` Cloud-based IDE for writing, running, and debugging code.
  - `AWS CloudShell:` Browser-based shell for command-line access to AWS.
  - `AWS CodeArtifact:` Artifact repository for software packages.
  - `AWS CodeBuild:` Continuous integration service to compile and test code.
  - `AWS CodeCommit:` Fully managed Git-based source control.
  - `AWS CodeDeploy:` Automates code deployments to compute services.
  - `AWS CodePipeline:` CI/CD pipeline orchestration tool.
  - `AWS CodeStar:` Unified interface for software development.
  - `AWS X-Ray:` Distributed tracing system for analyzing and debugging applications.
- `End-User Computing Services`
  - `Amazon AppStream 2.0:` Stream desktop apps to users over the web.
  - `Amazon WorkSpaces:` Managed virtual desktops in the cloud.
  - `Amazon WorkSpaces Web:` Secure browser access to internal websites and apps.
- `Frontend Web and Mobile Services`
  - `AWS Amplify:` Set of tools to build, ship, and host full-stack applications.
  - `AWS AppSync:` Managed GraphQL service for querying and syncing data in real-time.
- `IoT Services`
  - `AWS IoT Core:` Secure device communication with cloud apps and services.
  - `AWS IoT Greengrass:` Brings AWS compute, messaging, and data caching to edge devices.

### Domain 4: Billing, Pricing, and Support

 [Core AWS Pricing Concepts](https://aws.amazon.com/economics/)

Cloud economics refers to the financial principles and business value derived from cloud computing. It helps organizations understand how to optimize costs, `improve return on investment (ROI)`, and maximize the value of cloud adoption.

#### Price of Cloud

AWS has 3 pricing fundamentals, following the pay-as-you-go pricing model

1. Compute: Pay for compute time
2. Storage: Pay for data stored in the Cloud
3. Data transfer out of the Cloud: Data transfer in is free
Its the expensive issue then traditional IT

#### BYOL (Bring Your Own License)?

BYOL is a licensing model that lets you use your existing software licenses (like Windows, SQL Server, Oracle, etc.) when migrating or deploying workloads on AWS. Instead of buying new licenses through AWS, you "bring" the ones you already own—usually through volume licensing agreements from Microsoft, Oracle, etc.

## With Regards, `Jakir`

[![LinkedIn][linkedin-shield-jakir]][linkedin-url-jakir]
[![Facebook-Page][facebook-shield-jakir]][facebook-url-jakir]
[![Youtube][youtube-shield-jakir]][youtube-url-jakir]

### Wishing you a wonderful day! Keep in touch.

<!-- Personal profile -->

[linkedin-shield-jakir]: https://img.shields.io/badge/linkedin-%230077B5.svg?style=for-the-badge&logo=linkedin&logoColor=white
[linkedin-url-jakir]: https://www.linkedin.com/in/jakir-ruet/
[facebook-shield-jakir]: https://img.shields.io/badge/Facebook-%231877F2.svg?style=for-the-badge&logo=Facebook&logoColor=white
[facebook-url-jakir]: https://www.facebook.com/jakir.ruet/
[youtube-shield-jakir]: https://img.shields.io/badge/YouTube-%23FF0000.svg?style=for-the-badge&logo=YouTube&logoColor=white
[youtube-url-jakir]: https://www.youtube.com/@mjakaria-ruet/featured
