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

Security Hub

![Security Hub](/img/security-hub.png)

- `Identity and Access Management`
  1. `AWS Identity and Access Management (IAM)` - Securely manage identities and access to AWS services and resources.
  2. `AWS IAM Identity Center (formerly AWS SSO)` - Centrally manage workforce access to multiple AWS accounts and applications.
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
  8. `AWS Trusted Advisor` - AWS Trusted Advisor is a service that inspects your AWS accounts.
  9. `Amazon CloudWatch` - Observe and monitor resources and applications on AWS, on premises, and on other clouds.
  10. `AWS CloudTrail` - Track user activity and API usage.
  11. `AWS IoT Device Defender` - Security management across your IoT devices and fleets.
  12. `AWS Elastic Disaster Recovery`- Scalable, cost-effective application recovery to AWS.

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

##### Identity and Access Management - Each compontent's breif discussion

1. `AWS Identity and Access Management (IAM)` - Securely manage identities and access to AWS services and resources.

AWS Identity and Access Management (IAM) is a foundational security service in AWS that lets you control who can access your AWS resources, and what actions they can perform.

- AWS IAM allows you to:
  - `Authenticate:` Verify who is making the request (user, role, application).
  - `Authorize:` Decide whether they’re allowed to perform an action on a resource.

###### Core Concepts of IAM

| **IAM Component**             | **Description**                                                                 |
| ----------------------------- | ------------------------------------------------------------------------------- |
| **Users**                     | Individuals with long-term credentials (passwords, access keys).                |
| **Groups**                    | User collections sharing the same permissions via attached policies.            |
| **Roles**                     | Identities with temporary credentials for apps, services, or cross-account use. |
| **Policies**                  | JSON rules defining allowed or denied actions on AWS resources.                 |
| **Permissions Boundaries**    | Set a max limit on a user's or role’s effective permissions.                    |
| **Identity Providers (IdPs)** | Enable external user access via SAML, OIDC, or social logins.                   |

> IAM defines who can do what on which resources — and under what conditions.

2. `AWS IAM Identity Center (formerly AWS SSO)` - Centrally manage workforce access to multiple AWS accounts and applications.

AWS IAM Identity Center is a centralized service for managing workforce access to AWS accounts and business applications.

- IAM Identity Center enables:
  - Single Sign-On (SSO) for AWS accounts and cloud/SaaS apps
  - User and group management, or connection to external identity providers (like Microsoft AD, Okta, etc.)
  - Centralized access control across AWS Organizations
  - Attribute-based access control (ABAC) for fine-grained permissions

- Key Features

| **Feature**                  | **Description**                                                                 |
| ---------------------------- | ------------------------------------------------------------------------------- |
| **SSO Access**               | Sign in once to access multiple AWS accounts and apps (e.g., Salesforce, O365). |
| **User Directory Options**   | Use built-in directory or connect external IdPs (like Azure AD, Okta, AD).      |
| **Fine-Grained Permissions** | Assign IAM roles and permissions based on groups or user attributes.            |
| **Multi-Account Access**     | Grant users access to multiple AWS accounts from a single portal.               |
| **Audit & Monitoring**       | Logs activity with AWS CloudTrail; supports access reviews.                     |

3. `Amazon Cognito` - Implement secure, frictionless customer identity and access management that scales.

Amazon Cognito is a user authentication, authorization, and user management service provided by AWS (Amazon Web Services). It's designed to help developers easily add secure sign-up, sign-in, and access control to web and mobile apps.

- Core Features

  1. User Pools (Authentication)

  - User directories to manage sign-up/sign-in.
  - Supports
    - Email, phone, username/password
    - Social identity providers (Google, Facebook, Apple, etc.)
    - SAML and OpenID Connect (OIDC) providers
    - Multi-factor authentication (MFA)
    - Password policies and account recovery

  2. Identity Pools (Authorization via Federated Identities)

  - Grants temporary AWS credentials to users to access AWS services.
  - Can work with
    - Cognito User Pools
    - Social and SAML identity providers
    - Anonymous guest users

  3. User Directory Management

  - Manage users, groups, and roles
  - Enable/disable accounts, reset passwords, etc.

4. `Amazon Verified Permissions` - Manage fine-grained permissions and authorization within custom applications.

Amazon Verified Permissions is a fully managed authorization service from AWS that enables fine‑grained, policy‑based access control for custom applications (not just AWS resources).

- Key points:
  - It helps decouple authorization logic from your application code → you define policies separately, and your app asks: “Is this principal allowed to perform action X on resource Y, given context Z?”
  - Uses the open‑source policy language Cedar to express policies (both role‑based and attribute‑based) rather than the AWS IAM policy language
  - Enables centralization of permissions (policy store) + auditing + continuous enforcement → helps implement Zero Trust, least‑privilege models.

5. `AWS Directory Service` - Gain efficiency with a fully managed Microsoft Active Directory service.

AWS Directory Service is a fully managed service that lets you run Microsoft Active Directory (AD) or connect to existing AD environments in the cloud. It’s designed to support Windows-based applications that rely on directory services, user authentication, group policies, and domain-joining of instances.

- Key Use Case:
Enable Windows workloads and applications (like SharePoint, SQL Server, or custom apps) to integrate with Active Directory in AWS — without needing to manage domain controllers yourself.

6. `AWS Resource Access Manager` - Simply and securely share your AWS resources across multiple accounts.

AWS Resource Access Manager (RAM) is a service that lets you securely share AWS resources across:

- Accounts in your AWS Organization
- Organizational Units (OUs)
- Or individual AWS accounts

7. `AWS Organizations` - Centrally manage your environment as you scale your AWS resources.

AWS Organizations is a free AWS service that lets you centrally manage and govern multiple AWS accounts in a scalable, secure way. Instead of managing each AWS account individually, Organizations allows you to:

- Group accounts into organizational units (OUs)
- Apply service control policies (SCPs) across accounts
- Automate account creation and management
- Use consolidated billing for all linked accounts

##### Detection and Response - Each compontent's breif discussion

1. `Amazon GuardDuty` - Protect AWS accounts with intelligent threat detection.

GuardDuty is a managed threat‑detection service from Amazon Web Services (AWS) that continuously monitors your AWS environment (accounts, workloads, data) for suspicious or malicious activity.

- Key points:
  - It analyzes AWS “data sources” like logs (CloudTrail, VPC Flow Logs, DNS logs) to spot anomalies.
  - It uses threat intelligence (known malicious IPs/domains/hashes), machine learning (ML), behavioral monitoring.
  - It is fully managed — you don’t need to deploy sensors/appliances (for the baseline features).
  - It can be enabled across multiple AWS accounts (integrates with AWS Organizations) to centralize detection.

2. `Amazon Inspector` - Automated and continual vulnerability management at scale.

Amazon Inspector is a fully managed vulnerability management service by AWS that helps you identify and remediate software vulnerabilities and unintended network exposure across your AWS workloads. It automates the discovery and scanning of resources such as Amazon EC2 instances, container images in Amazon ECR, AWS Lambda functions, and code repositories

- Key points:
  - `Resource Discovery:` Amazon Inspector automatically discovers resources like EC2 instances, Lambda functions, and container images in Amazon ECR.
  - `Continuous Scanning:` It continuously scans these resources for software vulnerabilities and unintended network exposure, ensuring up-to-date security assessments.
  - `Findings Generation:` When a vulnerability or exposure is detected, Amazon Inspector generates a detailed finding, which includes information about the issue and recommendations for remediation.
  - `Integration for Remediation:` Findings can be integrated with other AWS services like AWS Security Hub and Amazon EventBridge to automate remediation workflows, such as triggering AWS Systems Manager Automation runbooks or creating tickets in issue tracking systems

4. `Amazon Security Lake` - Automatically centralize your security data in a few steps.

Amazon Security Lake is a fully managed service that centralizes security data from AWS, SaaS, on-premises, and other cloud sources into a secure data lake in your AWS account. It normalizes data using the Open Cybersecurity Schema Framework (OCSF) for easier analysis and better protection.

- Key Features
  - Centralized Data Aggregation: Automatically collects and stores security data from AWS, on-premises, and third-party sources into your Amazon S3 buckets.
  - Standardized Data Format: Converts data to Apache Parquet and normalizes it using OCSF for easy analysis.
  - Multi-Account & Multi-Region Support: Provides centralized security data visibility across multiple AWS accounts and regions.
  - Access Control & Data Sharing: Allows configurable access levels and supports data access notifications and query sharing.
  - AWS Service Integration: Integrates with AWS AppFabric and Amazon OpenSearch for enhanced security analytics and incident response.

5. `Amazon Detective` - Analyze and visualize security data to investigate potential security issues.

Amazon Detective is an AWS security service that helps you investigate, analyze, and identify the root cause of security issues or suspicious activities in your AWS environment by automatically collecting and analyzing log data.

- Key Features
  - Automatically collects and analyzes logs from AWS services like CloudTrail, VPC Flow Logs, and GuardDuty.
  - Uses machine learning and graph theory to visualize relationships between resources, users, and events.
  - Supports multi-account analysis for centralized investigation.
  - Integrates with AWS Security Hub and GuardDuty for seamless security findings investigation.
  - No agents required — no impact on system performance.
  - Pay-as-you-go pricing with a 30-day free trial.

6. `AWS Security Incident Response` - Prepare for, respond to, and recover from security events

Security incident response in AWS means preparing for, detecting, analyzing, containing, eradicating, and recovering from security incidents impacting your cloud environment.

- Key Components
- Preparation
  - Define an incident response plan.
  - Assign roles and responsibilities.
  - Set up monitoring and alerting (CloudTrail, GuardDuty, Config).
  - Automate evidence collection with AWS Lambda.
- Detection & Analysis
  - Use AWS GuardDuty for threat detection.
  - Monitor AWS CloudTrail logs for suspicious API calls.
  - Use Amazon CloudWatch for real-time alerts.
  - Analyze logs with AWS Athena or ElasticSearch.
- Containment, Eradication, and Recovery
  - Isolate affected resources (e.g., by modifying security groups).
  - Remove malicious code or compromised instances.
  - Patch vulnerabilities.
  - Restore services from known good backups.
- Post-Incident
  - Perform root cause analysis.
  - Update incident response playbooks.
  - Train teams based on lessons learned.
  - Report incidents if needed (depending on compliance).

7. `AWS Config` - Assess, audit, and evaluate configurations of your resources.

AWS Config is a fully managed service that provides you with an AWS resource inventory, configuration history, and configuration change notifications to enable security and governance.

- Key Features
  - Resource Inventory: Tracks AWS resources and their configurations.
  - Configuration History: Records changes over time for audit and troubleshooting.
  - Compliance Monitoring: Evaluates resource configurations against desired rules.
  - Change Notifications: Sends alerts for configuration changes.
  - Integration: Works with AWS CloudTrail, Security Hub, and other AWS security services.

8. `AWS Trusted Advisor` - AWS Trusted Advisor is a service that inspects your AWS accounts.

AWS Trusted Advisor is a service that inspects your AWS account's, gives you recommendations and helps you optimize costs, increase performance, improve security and resilience, and operate at scale in the cloud. to help you follow AWS best practices — specifically to:

- Reduce costs,
- Improve performance,
- Strengthen security,
- Increase fault tolerance/resilience, and
- Monitor service limits (quotas).

- Benefits of AWS Trusted Advisor:
  - Cost savings: Finds unused or idle resources to reduce spend.
  - Better performance: Flags misconfigurations or under-optimized resources.
  - Improved security: Detects open ports, missing encryption, and other risks.
  - Higher resilience: Identifies single points of failure or missing redundancy.
  - Quota awareness: Alerts on service limit usage to prevent disruptions.
  - Best practice alignment: Keeps your setup aligned with AWS recommendations.

9. `Amazon CloudWatch` - Observe and monitor resources and applications on AWS, on premises, and on other clouds.

Amazon CloudWatch provides data and **actionable insights** to monitor your applications, respond to system-wide performance changes, optimize resource utilization, and get a unified view of operational health.

Key Features

| Feature                | Description                                                                                             |
| ---------------------- | ------------------------------------------------------------------------------------------------------- |
| **Metrics Monitoring** | Collects and tracks standard and custom metrics from AWS services and your applications.                |
| **Logs Monitoring**    | Ingests, stores, and analyzes log data from AWS resources and on-premises servers.                      |
| **Alarms**             | Triggers actions (like sending notifications or auto-scaling) based on defined thresholds.              |
| **Dashboards**         | Visualizes your metrics and logs in customizable, real-time dashboards.                                 |
| **Events**             | Responds to changes in your AWS resources using **CloudWatch Events/EventBridge**.                      |
| **Insights**           | Provides analytics on logs using **CloudWatch Logs Insights**, useful for querying and troubleshooting. |

10. `AWS CloudTrail` - Track user activity and API usage.

CloudTrail records all API calls and related events made on your AWS account. This includes actions taken through the AWS Management Console, SDKs, command line tools, and other AWS services.

Key Features

| Feature                              | Description                                                                                                            |
| ------------------------------------ | ---------------------------------------------------------------------------------------------------------------------- |
| **Event Logging**                    | Captures details of every API call, including who made it, when, from where, and what was requested or returned.       |
| **Multi-Region Logging**             | Records events across all AWS regions.                                                                                 |
| **Management and Data Events**       | Tracks both high-level operations (e.g., creating a user) and low-level data access (e.g., reading an object from S3). |
| **Integration with CloudWatch Logs** | Sends logs to CloudWatch for real-time monitoring and alerts.                                                          |
| **Insights**                         | Detects unusual activity patterns in your account (e.g., sudden spikes in access or usage).                            |
| **Long-Term Archival**               | Stores logs in S3 for auditing, analysis, or forensic purposes.                                                        |

CloudTrail Components

| Component           | Purpose                                                                                        |
| ------------------- | ---------------------------------------------------------------------------------------------- |
| **Trail**           | A configuration that delivers log files to an S3 bucket. Can be single-region or multi-region. |
| **Event**           | A record of an individual API call, including parameters and results.                          |
| **CloudTrail Lake** | A managed data lake for querying events using SQL.                                             |
| **Insights Events** | Automatically detects unusual operational activity in your account.                            |

CloudWatch vs CloudTrail

|         | CloudWatch                          | CloudTrail                           |
| ------- | ----------------------------------- | ------------------------------------ |
| Purpose | Monitoring and operational insights | Governance, compliance, and auditing |
| Data    | Metrics and logs                    | API calls and activity               |
| Use     | Performance and health monitoring   | Security and auditing                |

11. `AWS IoT Device Defender` - Security management across your IoT devices and fleets.

AWS IoT Device Defender is a fully‑managed service from Amazon Web Services that helps you audit, monitor, and secure your fleet of IoT devices (especially those connected via AWS IoT Core).

- Key points:
  - It audits your device‑related resources (certificates, policies, etc.) against IoT security best practices.
  - It monitors device behaviour (traffic, connection patterns, ports, etc.) for anomalies either via rules you set or via built‑in machine‑learning models.
  - It supports mitigation — when issues are found it can trigger alerts and help you act (for example isolate a device, update a certificate, etc.).

12. `AWS Elastic Disaster Recovery`- Scalable, cost-effective application recovery to AWS.

AWS Elastic Disaster Recovery (AWS DRS) is a managed disaster‑recovery service that lets you replicate on‑premises, virtual, and cloud workloads into AWS and recover them quickly when needed.

- Key points:
  - It continuously replicates your source servers (physical, virtual, or cloud) into a “staging area” in AWS, minimizing downtime and data loss.
  - It supports launching the replicated workloads in AWS (failover) within minutes, either from the latest replicated state or a prior point‑in‑time.
  - After recovery, you can either continue running in AWS or fail back (“return”) to your original site.
  - It’s designed to reduce the cost and complexity of maintaining a dedicated DR site (on‑premises or in a data centre) by using AWS infrastructure as your recovery site.

##### Network and Application Protection - Each compontent's breif discussion

1. `AWS Firewall Manager > AWS Network Firewall` - Deploy network firewall security across your VPCs.

AWS Network Firewall is a managed security service offered by Amazon Web Services (AWS) that helps you protect your Amazon Virtual Private Cloud (VPC) networks by filtering traffic at the perimeter of your VPC.

- Key Features
  - **Deep Packet Inspection (DPI)** - Inspects beyond IP headers (e.g., HTTP, DNS) to detect malware and threats.
  - **Stateless and Stateful Rule Engines** - Stateless: Fast, simple IP/port/protocol matching, Stateful: Tracks connections for complex packet stream inspection.
  - **Integration with AWS Services** Works seamlessly with VPC routing, CloudWatch logging, and Firewall Manager.
  - **Suricata-Compatible Rules** Supports Suricata open-source rule sets for customizable stateful inspection.

2. `AWS Firewall Manager > AWS Shield` - Maximize application availability and responsiveness with managed DDoS protection.

AWS Shield is a managed Distributed Denial of Service (DDoS) protection service that safeguards applications running on AWS by automatically detecting and mitigating DDoS attacks, helping to maintain application availability and performance.

- **Managed DDoS Protection Service** for applications running on AWS.
- Provides **automatic detection and mitigation** of Distributed Denial of Service (DDoS) attacks.
- Comes in two tiers:
  - **AWS Shield Standard** (free)
    - Protects against common, large-scale network and transport layer attacks.
    - Automatically enabled for all AWS customers.
  - **AWS Shield Advanced** (paid)
    - Provides enhanced detection, mitigation, and 24/7 access to the AWS DDoS Response Team (DRT).
    - Includes cost protection against scaling charges during attacks.
    - Offers detailed attack diagnostics and integration with AWS WAF.
- Helps maintain **application availability and performance** during attacks.
- Integrates with **Amazon CloudFront, Route 53, ELB, and Global Accelerator**.

3. `AWS Firewall Manager > AWS Web Application Firewall (WAF)` - Protect your web applications from common exploits.

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

4. `AWS Verified Access` - Provide secure access to corporate applications without a VPN.

AWS Verified Access is a zero-trust access control service that enables secure, conditional access to your applications and resources without using traditional VPNs or bastion hosts. It verifies every user and device before granting access, improving security and simplifying remote access management.

- Key Points
  - Zero-trust access service: verifies every user and device before granting access.
  - No VPN or bastion host required: simplifies remote access to applications and resources.
  - Conditional access: enforces policies based on user identity, device posture, location, and more.
  - Seamless integration: works with existing identity providers like AWS IAM Identity Center, Okta, etc.
  - Improves security: reduces risk of unauthorized access with strict access controls.
  - Centralized management: manage access policies and audit logs from a single console.

5. `Amazon Route 53 Resolver DNS Firewall` - Filter and control outbound DNS traffic for your VPCs.

Amazon Route 53 Resolver DNS Firewall helps protect your Amazon VPC by filtering and controlling outbound DNS requests. It allows you to block or allow DNS queries based on domain lists, helping prevent access to malicious or unwanted domains.

- Key Features
  - **Domain Filtering:** Block or allow DNS requests based on domain lists (blocklists/allowlists).
  - **Integration with Route 53 Resolver:** Works seamlessly with DNS queries in your VPC.
  - **Customizable Rule Groups:** Create and manage multiple domain lists with different filtering policies.
  - **Logging and Monitoring:** Provides DNS query logs for visibility and auditing.
  - **Protects Against Malware & Phishing:** Prevents communication with known malicious domains.
  - **Easy to Deploy:** Managed service, no infrastructure to maintain.

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

AWS Key Management Service (KMS) is a managed service that makes it easy to create and control the cryptographic keys used to encrypt your data. It integrates with many AWS services to help protect data at rest and in transit.

- Key Features
  - **Centralized Key Management:** Create, rotate, disable, and audit cryptographic keys centrally.
  - **Integrated with AWS Services:** Works seamlessly with services like S3, EBS, RDS, Lambda, and more.
  - **High Security:** Keys are stored securely in hardware security modules (HSMs) validated under FIPS 140-2.
  - **Access Control:** Use AWS Identity and Access Management (IAM) policies and key policies to control who can use and manage keys.
  - **Auditability:** Integration with AWS CloudTrail allows tracking of key usage for compliance and auditing.
  - **Automatic Key Rotation:** Supports automatic yearly rotation of customer-managed keys.
  - **Symmetric and Asymmetric Keys:** Supports both symmetric encryption keys (for encrypt/decrypt) and asymmetric keys (for digital signing and verification).

3. `AWS CloudHSM` - Manage single-tenant hardware security modules (HSMs) on AWS.

AWS CloudHSM is a cloud-based hardware security module (HSM) that allows you to generate and use your own encryption keys in a dedicated, single-tenant hardware appliance. It provides secure key storage and cryptographic operations with high performance and compliance.

- Key Features
  - **Dedicated Hardware Security Modules:** You get exclusive access to physical HSMs, providing strong security and isolation.
  - **FIPS 140-2 Level 3 Compliance:** The HSMs meet stringent federal security standards.
  - **Full Control Over Keys:** You manage and control your encryption keys directly, with no AWS access.
  - **Integration with AWS Services:** Can be integrated with services like Amazon RDS, Amazon Redshift, and others.
  - **High Performance:** Designed for applications with intensive cryptographic workloads.
  - **Scalable and Highly Available:** You can cluster multiple HSMs for redundancy and increased throughput.
  - **Support for Industry Standards:** Compatible with PKCS#11, Java Cryptography Architecture (JCA), and Microsoft CryptoNG (CNG).

4. `AWS Certificate Manager` - Provision and manage SSL/TLS certificates with AWS services and connected resources.

AWS Certificate Manager (ACM) is a service that lets you easily provision, manage, and deploy SSL/TLS certificates for your AWS-based websites and applications. It helps you secure network communications and establish the identity of websites over the internet.

- Key Features
  - **Easy Provisioning:** Quickly request public and private SSL/TLS certificates with just a few clicks.
  - **Automatic Renewal:** ACM automatically renews certificates before they expire, minimizing downtime.
  - **Integration with AWS Services:** Seamlessly integrates with services like Elastic Load Balancing, CloudFront, and API Gateway.
  - **Free Public Certificates:** AWS provides public SSL/TLS certificates at no extra cost.
  - **Private Certificate Authority:** Supports issuing private certificates for internal use with ACM Private CA (additional charges apply).
  - **Managed Deployment:** Automatically deploy certificates to supported AWS services.
  - **Secure and Reliable:** Uses industry-standard encryption and follows best practices for certificate management.

5. `AWS Payment Cryptography` - Simplify cryptography operations in your cloud-hosted payment applications.

AWS Payment Cryptography is a fully managed service designed to help financial institutions and payment service providers securely process payment transactions and protect sensitive payment data. It offers a scalable and compliant environment for cryptographic operations specific to the payments industry.

- Key Features
  - **Industry-Standard Support:** Supports payment-specific cryptographic algorithms and protocols such as DES, TDES, AES, and more.
  - **Hardware Security Module (HSM) Backed:** Uses FIPS 140-2 Level 3 validated HSMs to protect keys and cryptographic operations.
  - **Integrated Payment Workflows:** Facilitates key management, encryption, decryption, and tokenization workflows required in payment processing.
  - **Regulatory Compliance:** Helps meet PCI DSS and other payment industry compliance requirements.
  - **Scalable and Highly Available:** Built on AWS infrastructure for high availability and scalability.
  - **Simplified Key Management:** Centralized management of payment keys with fine-grained access control.
  - **Audit and Monitoring:** Integration with AWS CloudTrail for monitoring and audit logging of cryptographic operations.

6. `AWS Private Certificate Authority` - Create private certificates to identify resources and protect data.

AWS Private Certificate Authority (Private CA) is a managed private certificate authority service that helps you create and manage your own private certificates for internal applications, devices, and users. It enables secure communication within your organization without relying on public certificate authorities.

- Key Features
  - **Private PKI Management:** Easily create and manage private certificate authorities in the AWS Cloud.
  - **Integration with AWS Services:** Works with AWS Certificate Manager (ACM) and other AWS services to automate certificate issuance and renewal.
  - **Customizable Certificate Templates:** Define policies and templates to control certificate issuance.
  - **High Security:** Keys are stored securely in hardware security modules (HSMs) validated at FIPS 140-2 Level 3.
  - **Automated Certificate Lifecycle:** Simplifies issuing, renewing, and revoking private certificates.
  - **Scalable and Highly Available:** Built on AWS infrastructure to provide availability and scalability.
  - **Compliance and Auditability:** Supports logging with AWS CloudTrail for auditing certificate-related activities.

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

8. `AWS Secrets Manager` - Centrally manage the lifecycle of secrets.

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

AWS Artifact is a self-service portal that provides on-demand access to AWS’s security and compliance reports. It helps customers assess the compliance of AWS services and manage their own compliance requirements by providing audit artifacts like certifications and attestations.

- Key Features
  - **Access to Compliance Reports:** Get access to AWS compliance reports such as SOC, ISO, PCI DSS, HIPAA, and more.
  - **On-Demand Downloads:** Download audit artifacts and certifications whenever you need them.
  - **Compliance Management:** Helps customers understand the security and compliance posture of AWS services they use.
  - **Agreement Management:** Manage, review, and accept AWS business agreements and compliance documents.
  - **Centralized Portal:** Single location to access all AWS compliance-related documentation.

2. `AWS Audit Manager` - Continually audit your AWS usage to simplify risk and compliance assessment.

AWS Audit Manager is a service that helps you continuously audit your AWS usage to simplify how you assess risk and compliance with industry standards and regulations. It automates evidence collection and organizes it to help reduce manual effort during audits.

- Key Features
  - **Automated Evidence Collection:** Continuously collects evidence from AWS services to simplify audits.
  - **Pre-built Frameworks:** Supports popular compliance frameworks such as PCI DSS, HIPAA, GDPR, SOC 2, and more.
  - **Custom Frameworks:** Create custom audit frameworks tailored to your organization’s specific requirements.
  - **Centralized Audit Management:** Organize and manage audit reports and evidence in a single place.
  - **Collaboration:** Allows multiple team members to work on audits and review evidence.
  - **Integration with AWS Services:** Works with AWS Config, CloudTrail, and others to gather relevant data.
  - **Compliance Reporting:** Generates audit-ready reports to support compliance assessments.

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

#### [Amazon VPC, DNS, Networking and content delivery](https://docs.aws.amazon.com/whitepapers/latest/aws-overview/networking-services.html)

- Amazon Route 53
  - **Highly available and scalable DNS web service.**
  - **Domain registration:** Register domain names directly.
  - **DNS Routing:** Supports routing policies like Simple, Weighted, Latency-based, Failover, and Geo DNS.
  - **Health Checks & Monitoring:** Route traffic away from unhealthy endpoints.
  - **Integration:** Works with other AWS services and external endpoints.

- Amazon VPC (Virtual Private Cloud) - Networking
  - **Create isolated virtual networks within AWS.**
  - **Customizable IP address ranges, subnets, route tables, and gateways.**
  - **Security:** Use security groups and network ACLs to control traffic.
  - **VPC Peering:** Connect different VPCs privately.
  - **VPN & Direct Connect:** Secure hybrid connectivity between on-premises and AWS.

- AWS Transit Gateway
  - **Central hub for connecting multiple VPCs and on-premises networks.**
  - **Simplifies network management and scales connectivity.**

- Content Delivery - Amazon CloudFront
  - **Global Content Delivery Network (CDN).**
  - **Delivers websites, APIs, video content, and other assets with low latency.**
  - **Supports SSL/TLS encryption and DDoS protection with AWS Shield.**
  - **Edge locations worldwide for caching content close to users.**

- AWS Global Accelerator
  - **Improves availability and performance of applications with static IP addresses.**
  - **Uses AWS global network to route traffic optimally.**

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

#### [Amazon API Gateway](https://aws.amazon.com/api-gateway/)

Amazon API Gateway is a fully managed service that makes it easy for developers to create, publish, maintain, monitor, and secure APIs at any scale. It acts as a front door for applications to access data, business logic, or functionality from backend services like AWS Lambda, EC2, or other web services.

- Key Features
  - **Create RESTful and WebSocket APIs:** Support for HTTP-based APIs including REST and real-time communication with WebSocket APIs.
  - **Scalable and Fully Managed:** Automatically handles traffic management, authorization, and access control.
  - **Security:** Supports AWS IAM, Amazon Cognito, and custom authorizers for securing APIs.
  - **Throttling and Quotas:** Protect backend systems by setting request limits.
  - **Monitoring and Analytics:** Integration with Amazon CloudWatch for logging and metrics.
  - **Request and Response Transformation:** Modify incoming requests and outgoing responses without changing backend code.
  - **Caching:** Reduce backend load and improve latency by enabling response caching.
  - **API Versioning and Stages:** Manage multiple versions and deployment stages of APIs easily.

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

#### Services from Additional Relevant AWS Categories

- `Application Integration Services`
  1. `Amazon EventBridge:` Event bus for building event-driven applications at scale.
  2. `Amazon SNS (Simple Notification Service):` Pub/sub messaging for decoupled microservices.
  3. `Amazon SQS (Simple Queue Service):` Managed message queuing for distributed systems.
- `Business Application Services`
  1. `Amazon Connect:` Cloud-based contact center service.
  2. `Amazon SES (Simple Email Service):` Scalable email sending for marketing or transactional purposes.
- `Customer Engagement Services`
  1. `AWS Activate for Startups:` Credits, training, and support for startup growth.
  2. `AWS IQ:` Connects customers with AWS-certified freelancers and consultants.
  3. `AWS Managed Services (AMS):` Operational support and automation for AWS infrastructure.
- `Developer Tools`
  1. `AWS AppConfig:` Feature flagging and configuration management.
  2. `AWS Cloud9:` Cloud-based IDE for writing, running, and debugging code.
  3. `AWS CloudShell:` Browser-based shell for command-line access to AWS.
  4. `AWS CodeArtifact:` Artifact repository for software packages.
  5. `AWS CodeBuild:` Continuous integration service to compile and test code.
  6. `AWS CodeCommit:` Fully managed Git-based source control.
  7. `AWS CodeDeploy:` Automates code deployments to compute services.
  8. `AWS CodePipeline:` CI/CD pipeline orchestration tool.
  9. `AWS CodeStar:` Unified interface for software development.
  10. `AWS X-Ray:` Distributed tracing system for analyzing and debugging applications.
- `End-User Computing Services`
  1. `Amazon AppStream 2.0:` Stream desktop apps to users over the web.
  2. `Amazon WorkSpaces:` Managed virtual desktops in the cloud.
  3. `Amazon WorkSpaces Web:` Secure browser access to internal websites and apps.
- `Frontend Web and Mobile Services`
  1. `AWS Amplify:` Set of tools to build, ship, and host full-stack applications.
  2. `AWS AppSync:` Managed GraphQL service for querying and syncing data in real-time.
- `IoT Services`
  1. `AWS IoT Core:` Secure device communication with cloud apps and services.
  2. `AWS IoT Greengrass:` Brings AWS compute, messaging, and data caching to edge devices.

#### Services from Additional Relevant AWS Categories - brief discuss

- `Application Integration Services`
  1. `Amazon EventBridge:` Event bus for building event-driven applications at scale.

Amazon EventBridge is a fully managed event bus service from AWS that enables event-driven architecture by connecting applications using events from your own apps, AWS services, and SaaS providers.

- Key Features
  - **Event Routing:** Filter and route events based on rules to various AWS targets (Lambda, SNS, SQS, Step Functions, etc.).
  - **AWS Service Integration:** Seamless integration with many AWS services like EC2, S3, Lambda.
  - **SaaS Integrations:** Ingest events from popular SaaS platforms such as Zendesk, Datadog, and more.
  - **Schema Registry:** Discover, create, and manage event schemas for better development experience.
  - **Fully Managed:** No infrastructure management required, scales automatically.

- Common Use Cases
  - Automating workflows triggered by system or application events.
  - Building event-driven microservices architectures.
  - Monitoring system changes and triggering alerts.
  - Integrating third-party SaaS event data into AWS environments.

  2. `Amazon SNS (Simple Notification Service):` Pub/sub messaging for decoupled microservices.

Amazon SNS is a fully managed pub/sub messaging service from AWS that enables message delivery to distributed systems, microservices, and event-driven serverless applications.

- Key Features
  - **Pub/Sub Messaging:** Publish messages to topics and deliver them to multiple subscribers.
  - **Multiple Protocols Supported:** Push notifications to HTTP/S endpoints, AWS Lambda, SQS queues, email, SMS, and mobile push notifications.
  - **Scalable & Durable:** Automatically scales to handle high throughput and guarantees message durability.
  - **Fan-out Pattern:** Send a single message to multiple subscribers simultaneously.
  - **Message Filtering:** Subscribers can filter messages based on message attributes.
  - **Security:** Supports encryption at rest and in transit, and integrates with AWS IAM for access control.

- Common Use Cases
  - Sending notifications to distributed systems and microservices.
  - Fan-out message delivery to multiple subscribers (e.g., Lambda, SQS).
  - Mobile push notifications for apps.
  - Alerting and monitoring systems.
  - Workflow triggering in event-driven architectures.

  3. `Amazon SQS (Simple Queue Service):` Managed message queuing for distributed systems.

Amazon SQS is a fully managed message queuing service from AWS that enables decoupling and scaling of microservices, distributed systems, and serverless applications.

- Key Features
  - **Message Queues:** Provides reliable, highly scalable hosted queues for storing messages as they travel between components.
  - **Two Queue Types:**
    - **Standard Queues:** Offer maximum throughput, at-least-once delivery, and best-effort ordering.
    - **FIFO Queues:** Guarantee exactly-once processing and strict message ordering.
  - **Decoupling:** Helps decouple application components to improve fault tolerance and scalability.
  - **Visibility Timeout:** Controls the period a message is hidden after being received, preventing multiple consumers from processing it simultaneously.
  - **Dead-Letter Queues (DLQ):** Handle messages that can’t be processed successfully after multiple attempts.
  - **Security:** Supports encryption at rest, access control via IAM, and VPC endpoints.

- Common Use Cases
  - Buffering and decoupling microservices or distributed systems.
  - Asynchronous task processing.
  - Workload leveling and throttling.
  - Managing retries and error handling with DLQs.

**Amazon SNS vs Amazon SQS**

| Feature                | Amazon SNS (Simple Notification Service)                       | Amazon SQS (Simple Queue Service)                             |
| ---------------------- | -------------------------------------------------------------- | ------------------------------------------------------------- |
| **Type of Service**    | Pub/Sub messaging (push-based delivery)                        | Message queueing (pull-based delivery)                        |
| **Message Delivery**   | Pushes messages to subscribers (e.g., Lambda, HTTP/S, email)   | Stores messages until consumers poll and process them         |
| **Use Case**           | Broadcast notifications to multiple subscribers simultaneously | Decouple components with reliable, ordered message processing |
| **Message Ordering**   | No guaranteed ordering (best effort only)                      | FIFO queues guarantee ordering; standard queues do not        |
| **Message Durability** | Durable, but designed for real-time notifications              | Durable storage with retry and dead-letter queue support      |
| **Message Retention**  | Messages delivered immediately, no long-term storage           | Messages stored up to 14 days if not processed                |
| **Delivery Protocols** | HTTP/S, Lambda, SQS, Email, SMS, Mobile Push                   | Consumers poll via API or SDK                                 |
| **Fan-out Pattern**    | Supports fan-out to multiple subscribers                       | Typically one consumer processes each message                 |
| **Scaling**            | Automatically scales to millions of messages per second        | Scales with workload, can handle high throughput              |
| **Use Case Examples**  | Notifications, alerts, mobile push, triggering workflows       | Asynchronous task queues, buffering, decoupling services      |

> Summary

- **Use SNS when you want to broadcast messages to multiple subscribers in real-time.**
- **Use SQS when you need reliable message queuing, asynchronous processing, and decoupling between components.**

- `Business Application Services`
  1. `Amazon Connect:` Cloud-based contact center service.

Amazon Connect is a cloud-based contact center service from AWS that enables businesses to deliver better customer service at lower cost. It provides an easy-to-use, scalable, and flexible solution for inbound and outbound customer communications.

- Key Features
  - **Omnichannel Support:** Handle voice calls, chat, and task management from a single platform.
  - **Easy Setup:** No specialized skills needed to set up or manage the contact center.
  - **AI and Automation:** Built-in integrations with AWS AI services like Amazon Lex for chatbots, and Amazon Polly for text-to-speech.
  - **Scalable & Pay-as-you-go:** Scales automatically to handle any volume, you pay only for usage.
  - **Real-time & Historical Analytics:** Track agent performance, customer satisfaction, and operational metrics.
  - **Customizable Workflows:** Create and modify contact flows visually using drag-and-drop tools.
  - **Integration:** Integrates with CRM systems, AWS Lambda, and other AWS services for custom workflows and data retrieval.

- Common Use Cases
  - Customer support centers (voice and chat).
  - Automated self-service using chatbots.
  - Outbound campaigns and notifications.
  - Interactive voice response (IVR) systems.

  2. `Amazon SES (Simple Email Service):` Scalable email sending for marketing or transactional purposes.

Amazon SES is a cloud-based email sending service designed to help businesses send marketing, notification, and transactional emails reliably and at scale.

- Key Features
  - **High Deliverability:** Uses a global network of trusted IP addresses to maximize email deliverability.
  - **Flexible Email Sending:** Supports SMTP interface, AWS SDKs, and API for sending emails.
  - **Bulk & Transactional Emails:** Suitable for marketing campaigns, notifications, and transactional emails.
  - **Email Receiving:** Can receive inbound emails, which can be processed, stored, or forwarded.
  - **Email Authentication:** Supports DKIM, SPF, and DMARC to improve email authenticity.
  - **Reputation Dashboard:** Monitor your sending statistics, bounce rates, complaints, and reputation.
  - **Cost-Effective:** Pay-as-you-go pricing with a generous free tier for AWS users.

- Common Use Cases
  - Sending transactional emails (order confirmations, password resets).
  - Sending marketing newsletters and promotions.
  - Handling inbound emails for processing (e.g., support tickets).
  - Bulk email sending with deliverability tracking.

- `Customer Engagement Services`
  1. `AWS Activate for Startups:` Credits, training, and support for startup growth.

AWS Activate is a program designed to provide startups with the resources they need to get started quickly on AWS. It offers credits, training, technical support, and other resources to help startups build and scale their businesses on AWS.

- Key Features
  - **AWS Credits:** Startup credits to help offset the cost of AWS services.
  - **Technical Support:** Access to AWS Support plans to assist with architecture, troubleshooting, and best practices.
  - **Training & Resources:** Free training materials, webinars, and tutorials tailored for startups.
  - **Exclusive Offers:** Discounts and offers from AWS partners and third-party tools.
  - **Architectural Guidance:** Access to AWS solutions architects and best practice guidance.
  - **Community Access:** Connect with other startups and AWS experts through forums and events.

- Eligibility
  - Early-stage startups (generally less than 10 years old).
  - Must be associated with an approved accelerator, incubator, seed fund, or VC, or apply as a self-startup in certain cases.
  - Subject to program terms and conditions.

- Common Benefits
  - AWS credits ranging from $1,000 to $100,000+ depending on the package.
  - Access to AWS Business Support or Developer Support plans.
  - Invitations to startup-focused events and bootcamps.

  2. `AWS IQ:` Connects customers with AWS-certified freelancers and consultants.

AWS IQ is a service that connects AWS customers with certified AWS experts and consultants for on-demand project help, guidance, and professional services.

- Key Features
  - **Access Certified Experts:** Connect with AWS Certified professionals who can assist with architecture, migrations, troubleshooting, and more.
  - **On-Demand Engagement:** Request help for specific tasks or projects without long-term contracts.
  - **Secure & Transparent:** Work through AWS IQ platform with clear pricing and project tracking.
  - **Wide Range of Expertise:** Includes architects, developers, DevOps engineers, security specialists, and more.
  - **Direct Communication:** Collaborate directly with experts via chat and video calls.
  - **Payment & Billing:** Managed through AWS billing, providing easy payment and invoicing.

- Common Use Cases
  - AWS infrastructure design and optimization.
  - Cloud migration projects.
  - Troubleshooting and performance tuning.
  - Security audits and compliance assistance.
  - Custom development and automation.

  3. `AWS Managed Services (AMS):` Operational support and automation for AWS infrastructure.

AWS Managed Services (AMS) is a fully managed offering that helps enterprises operate their AWS infrastructure securely and efficiently. AMS handles day-to-day infrastructure management, allowing organizations to focus on their applications and business outcomes.

- Key Features
  - **Infrastructure Operations:** Automated provisioning, monitoring, patching, backup, and security management.
  - **Security & Compliance:** Enforces AWS best practices, compliance frameworks (e.g., HIPAA, PCI), and continuous security monitoring.
  - **Change Management:** Standardized change requests and incident management to minimize risk.
  - **Cost Optimization:** Provides reporting and recommendations to optimize AWS usage and cost.
  - **Integration with Existing Processes:** Works alongside enterprise IT processes and tools.
  - **24/7 Support:** Around-the-clock operational support by AWS experts.

- Common Use Cases
  - Enterprises needing secure, compliant AWS operations.
  - Organizations lacking internal cloud operations expertise.
  - Companies wanting to reduce operational overhead.
  - Migration projects requiring managed post-migration operations.

- `Developer Tools`
  1. `AWS AppConfig:` Feature flagging and configuration management.

AWS AppConfig is a feature of AWS Systems Manager that enables you to deploy application configurations safely and quickly. It helps reduce errors and downtime by validating configurations before deployment and controlling how changes are rolled out.

- Key Features
  - **Safe Configuration Deployment:** Validates configurations using validators such as JSON schema or AWS Lambda functions.
  - **Controlled Rollouts:** Supports gradual deployment strategies like canary or linear rollouts to minimize risk.
  - **Integration:** Works with applications, containers, and serverless architectures.
  - **Immediate Updates:** Allows applications to retrieve updated configurations without redeploying code.
  - **Environment Segmentation:** Supports multiple environments (e.g., dev, test, prod) with isolated configurations.
  - **Monitoring and Rollback:** Monitors deployments and can roll back automatically if issues are detected.

- Common Use Cases
  - Feature flag management and gradual feature releases.
  - Dynamic configuration updates without redeploying applications.
  - Managing operational parameters (e.g., thresholds, connection strings).
  - Safely deploying configuration changes in distributed applications.

  2. `AWS Cloud9:` Cloud-based IDE for writing, running, and debugging code.

AWS Cloud9 is a cloud-based integrated development environment (IDE) that allows developers to write, run, and debug code with just a browser. It provides a rich code-editing experience with built-in tools and seamless integration with AWS.

- Key Features
  - **Cloud-Based IDE:** Accessible from anywhere without installing software locally.
  - **Multi-Language Support:** Supports popular programming languages such as Python, JavaScript, PHP, Java, and more.
  - **Collaboration:** Enables multiple developers to collaborate in real-time within the same environment.
  - **Pre-Configured Environment:** Comes with essential tools, AWS CLI, SDKs, and debuggers pre-installed.
  - **Seamless AWS Integration:** Direct access to AWS resources, making it easy to develop and test cloud applications.
  - **Terminal Access:** Full Linux terminal access within the browser.
  - **Customizable Environment:** Allows configuration of compute and storage resources as needed.

- Common Use Cases
  - Developing and testing AWS Lambda functions.
  - Building serverless applications.
  - Collaborative coding sessions.
  - Quick prototyping and experimenting with AWS services.
  - Learning and teaching programming in a cloud environment.

  3. `AWS CloudShell:` Browser-based shell for command-line access to AWS.

AWS CloudShell is a browser-based, pre-authenticated shell environment provided by Amazon Web Services (AWS). It gives you command-line access to AWS resources without needing to install or configure anything on your local machine.

- Key Features
  - **Pre-authenticated:** Automatically uses your AWS Management Console credentials.
  - **Pre-configured tools:** Comes with popular AWS CLI, SDKs, and utilities like Python, Node.js, git, Docker, etc.
  - **Temporary storage:** Provides 1 GB of persistent storage for your scripts and files.
  - **Runs in your browser:** No need for local setup or VPN.
  - **Access to AWS resources:** You can manage your AWS services and resources directly via CLI.

- Common Use Cases
  - Quickly running AWS CLI commands.
  - Testing scripts or commands without installing software.
  - Debugging and managing AWS resources on the fly.
  - Learning and experimenting with AWS services.

  4. `AWS CodeArtifact:` Artifact repository for software packages.

AWS CodeArtifact is a fully managed artifact repository service that makes it easy for organizations to securely store, publish, and share software packages used in their software development process. It supports popular package managers and formats like Maven, npm, PyPI, and NuGet.

- Key Features
  - **Fully managed:** No infrastructure to set up or maintain.
  - **Secure:** Integrated with AWS IAM for fine-grained access control.
  - **Supports multiple package formats:** Maven, npm, PyPI (Python), NuGet (Microsoft), and more.
  - **Dependency resolution:** Automatically fetches packages from public repositories if not found locally.
  - **Version control:** Manage multiple versions of packages.
  - **Integration:** Works well with AWS CodeBuild, CodePipeline, and CI/CD tools.

- Common Use Cases
  - Hosting private software packages for internal use.
  - Sharing packages securely across teams or projects.
  - Proxying public repositories to improve build stability and security.
  - Managing dependencies in build pipelines.

  5. `AWS CodeBuild:` Continuous integration service to compile and test code.

AWS CodeBuild is a fully managed continuous integration service that compiles source code, runs tests, and produces software packages ready for deployment. It scales automatically, so you don’t need to provision, manage, or scale your own build servers.

- Key Features
  - **Fully managed:** No infrastructure to provision or manage.
  - **Scalable:** Automatically scales to handle multiple builds concurrently.
  - **Supports multiple build environments:** Java, Python, Node.js, Docker, and more.
  - **Integration:** Works seamlessly with AWS CodePipeline, GitHub, Bitbucket, and other source repositories.
  - **Customizable builds:** Define build steps with buildspec.yml.
  - **Secure:** Integrated with AWS IAM and supports encrypted environment variables and artifacts.

- Common Use Cases
  - Building and testing code in CI/CD pipelines.
  - Automating build and test workflows for multiple environments.
  - Creating Docker images as part of the build process.
  - Running automated unit, integration, or end-to-end tests.

  6. `AWS CodeCommit:` Fully managed Git-based source control.

AWS CodeCommit is a fully managed source control service that hosts secure Git-based repositories. It makes it easy for teams to collaborate on code and securely store and version their source code.

- Key Features
  - **Fully managed:** No need to host, scale, or maintain Git servers.
  - **Secure:** Data is encrypted at rest and in transit; integrates with AWS IAM for access control.
  - **High availability:** Designed for durability and uptime.
  - **Supports Git:** Works with standard Git tools and clients.
  - **Integration:** Works with AWS CodePipeline, CodeBuild, and other AWS services.
  - **Collaboration:** Supports pull requests, code reviews, and notifications.

- Common Use Cases
  - Hosting private Git repositories for teams.
  - Managing source code in secure and scalable infrastructure.
  - Integrating source control with AWS CI/CD pipelines.
  - Enabling collaboration with built-in code review workflows.

  7. `AWS CodeDeploy:` Automates code deployments to compute services.

AWS CodeDeploy is a fully managed deployment service that automates application deployments to Amazon EC2 instances, on-premises servers, AWS Lambda functions, or Amazon ECS services. It helps you rapidly release new features, avoid downtime during deployment, and handle the complexity of updating applications.

- Key Features
  - **Automated deployments:** Deploy applications automatically across multiple compute platforms.
  - **Flexible deployment targets:** Supports EC2, on-premises servers, AWS Lambda, and Amazon ECS.
  - **Deployment strategies:** Supports in-place and blue/green deployments.
  - **Monitoring & rollback:** Monitors deployment health and can automatically roll back on failures.
  - **Integration:** Works with CodePipeline, CodeBuild, CloudWatch, and other AWS services.
  - **Customizable lifecycle hooks:** Run scripts at various deployment stages for advanced deployment workflows.

- Common Use Cases
  - Deploying updates to web servers or backend services.
  - Rolling out new features with minimal or zero downtime.
  - Managing deployments in hybrid environments (cloud + on-premises).
  - Automating Lambda function version updates.

  8. `AWS CodePipeline:` CI/CD pipeline orchestration tool.

AWS CodePipeline is a fully managed continuous integration and continuous delivery (CI/CD) service that automates the building, testing, and deploying of your applications every time there is a code change.

It helps you rapidly deliver features and updates with high quality and reliability.

- Key Features
  - **Fully managed:** No need to manage or provision servers.
  - **Automated workflows:** Automates the entire release process from source to deployment.
  - **Integrations:** Supports AWS services like CodeCommit, CodeBuild, CodeDeploy, and third-party tools like GitHub, Jenkins, etc.
  - **Customizable:** Build pipelines with multiple stages, actions, and approval steps.
  - **Parallel execution:** Supports parallel and sequential actions within pipelines.
  - **Visual monitoring:** Provides a visual interface to track pipeline execution and status.

- Common Use Cases
  - Automating build-test-deploy workflows for applications.
  - Implementing CI/CD pipelines for rapid software delivery.
  - Coordinating multiple build and deploy actions across environments.
  - Enforcing manual approval steps for production deployments.

  9. `AWS CodeStar:` Unified interface for software development.

AWS CodeStar is a cloud-based service that provides a unified user interface, enabling you to easily manage software development activities in one place. It simplifies setting up complete continuous delivery toolchains for developing, building, and deploying applications on AWS.

- Key Features
  - **Integrated experience:** Combines project management, code, build, and deploy tools in a single dashboard.
  - **Quick project setup:** Launch ready-to-use templates for various programming languages and platforms.
  - **Collaboration:** Enables teams to work together with role-based access and notifications.
  - **CI/CD pipelines:** Automatically provisions AWS CodePipeline, CodeCommit, CodeBuild, and CodeDeploy.
  - **Pre-built templates:** Supports popular frameworks like Java, Node.js, Python, .NET, and more.
  - **Project management:** Integrates with issue tracking and Agile tools.

- Common Use Cases
  - Quickly starting new AWS development projects with best-practice pipelines.
  - Centralizing team collaboration and project tracking.
  - Accelerating software delivery with automated CI/CD.
  - Managing multi-role access and project permissions easily.

  10. `AWS X-Ray:` Distributed tracing system for analyzing and debugging applications.

AWS X-Ray is a distributed tracing service that helps developers analyze and debug production, distributed applications, such as those built using a microservices architecture.

It provides insights into the performance of your applications by tracing requests as they travel through your system.

- Key Features
  - **Distributed tracing:** Tracks requests across services and resources.
  - **Service map:** Visualizes application components and their interactions.
  - **Performance analysis:** Identifies latency bottlenecks and errors.
  - **Root cause analysis:** Pinpoints where failures or exceptions occur.
  - **Integration:** Works with AWS Lambda, EC2, ECS, API Gateway, Elastic Beanstalk, and more.
  - **Annotations & metadata:** Customize traces with additional data for deeper insights.

- Common Use Cases
  - Debugging and troubleshooting microservices.
  - Monitoring latency and performance across distributed systems.
  - Understanding application dependencies.
  - Detecting errors and performance issues in production.

- `End-User Computing Services`
  1. `Amazon AppStream 2.0:` Stream desktop apps to users over the web.

Amazon AppStream 2.0 is a fully managed, secure application streaming service that allows you to stream desktop applications to any device running a web browser, without rewriting them. It enables users to access desktop apps from anywhere, with centralized management and scalable infrastructure.

- Key Features
  - **Fully managed:** No infrastructure to manage or scale.
  - **Secure:** Data never leaves AWS; secure user access with AWS IAM and SSO.
  - **Broad device support:** Stream apps to Windows, Mac, Linux, Chromebooks, and tablets.
  - **Scalable:** Automatically scales capacity based on user demand.
  - **Customizable:** Build custom application images and fleets.
  - **Integration:** Integrates with Active Directory and AWS services.

- Common Use Cases
  - Providing remote access to desktop applications.
  - Enabling secure application delivery for remote or mobile workforces.
  - Supporting Bring Your Own Device (BYOD) policies.
  - Delivering resource-intensive applications without local installation.

  2. `Amazon WorkSpaces:` Managed virtual desktops in the cloud.

Amazon WorkSpaces is a fully managed, secure Desktop-as-a-Service (DaaS) solution that allows you to provision cloud-based Windows or Linux desktops for your users. It provides users with a persistent, cloud-hosted desktop experience accessible from anywhere.

- Key Features
  - **Fully managed:** No hardware to provision or manage.
  - **Flexible desktop options:** Choose from Windows or Linux desktops with various hardware configurations.
  - **Secure:** Data is stored securely in AWS; supports multi-factor authentication and encryption.
  - **Anywhere access:** Access desktops from Windows, macOS, Linux, iOS, Android, or web browsers.
  - **Scalable:** Easily scale up or down based on user demand.
  - **Integration:** Works with AWS Directory Service and on-premises Active Directory.

- Common Use Cases
  - Providing remote desktops for telecommuting or contractors.
  - Secure desktop environments for regulated industries.
  - Supporting Bring Your Own Device (BYOD) policies.
  - Quickly provisioning desktops for temporary or seasonal workers.

  3. `Amazon WorkSpaces Web:` Secure browser access to internal websites and apps.

Amazon WorkSpaces Web is a fully managed, cloud-based web browsing service that provides secure, fast, and scalable access to internal websites and SaaS applications through a browser. It helps organizations enable secure remote web access without the need for traditional VPNs or complex network configurations.

- Key Features
  - **Secure browsing:** Isolates user browsing sessions from your corporate network to reduce risk.
  - **Fully managed:** No infrastructure to manage or maintain.
  - **Simple access:** Users access internal web apps via standard web browsers.
  - **Scalable:** Automatically scales to meet demand.
  - **Integration:** Integrates with AWS Directory Service and identity providers for authentication.
  - **Policy enforcement:** Control access with fine-grained policies.

- Common Use Cases
  - Providing secure remote access to internal web applications.
  - Protecting corporate networks from web-based threats.
  - Enabling browser-based access for contractors or remote employees.
  - Reducing reliance on VPNs or remote desktops for web access.

- `Frontend Web and Mobile Services`
  1. `AWS Amplify:` Set of tools to build, ship, and host full-stack applications.

AWS Amplify is a set of tools and services that enables frontend web and mobile developers to build scalable full-stack applications powered by AWS. It simplifies backend development, hosting, and integration with AWS services, so developers can focus on building great user experiences.

- Key Features
  - **Backend as a Service:** Easily configure and manage backend services like authentication, APIs, databases, and storage.
  - **Frontend Framework Support:** Integrates with React, Angular, Vue, iOS, Android, and more.
  - **Hosting & CI/CD:** Provides continuous deployment and hosting for web apps with built-in workflows.
  - **GraphQL & REST APIs:** Automatically generate scalable APIs with AWS AppSync or API Gateway.
  - **Authentication:** Built-in support for user sign-up, sign-in, and multi-factor authentication via Amazon Cognito.
  - **Storage & Data:** Manage file storage and real-time data syncing.

- Common Use Cases
  - Building serverless web and mobile apps quickly.
  - Adding user authentication and authorization.
  - Creating real-time collaborative apps.
  - Deploying frontend apps with global content delivery.
  - Integrating with AI/ML services easily.

  2. `AWS AppSync:` Managed GraphQL service for querying and syncing data in real-time.

AWS AppSync is a fully managed service that makes it easy to develop GraphQL APIs by handling the heavy lifting of securely connecting to data sources like DynamoDB, Lambda, and more. It enables real-time data synchronization and offline capabilities for applications.

- Key Features
  - **Managed GraphQL API:** Simplifies building flexible APIs with GraphQL.
  - **Real-time subscriptions:** Supports real-time updates with WebSockets.
  - **Offline support:** Enables apps to work seamlessly offline and sync changes later.
  - **Multiple data sources:** Integrates with DynamoDB, Lambda, Elasticsearch, RDS, and HTTP APIs.
  - **Fine-grained access control:** Integrates with AWS IAM, Cognito, and API keys.
  - **Scalable:** Automatically scales with your application needs.

- Common Use Cases
  - Building real-time collaborative apps (chat, dashboards).
  - Mobile and web apps needing offline access and sync.
  - Simplifying backend data integration for frontend developers.
  - Creating unified APIs aggregating multiple data sources.

- `IoT Services`
  1. `AWS IoT Core:` Secure device communication with cloud apps and services.

AWS IoT Core is a managed cloud service that lets connected devices securely interact with cloud applications and other devices. It enables you to easily build Internet of Things (IoT) solutions that gather, process, analyze, and act upon data generated by connected devices.

- Key Features
  - **Secure device connectivity:** Supports mutual authentication and encryption.
  - **Device registry:** Manage and organize devices at scale.
  - **Message broker:** Enables bi-directional communication between devices and cloud.
  - **Rules engine:** Filters, processes, and routes device data to AWS services.
  - **Device shadows:** Maintain a virtual representation of device state for apps.
  - **Integration:** Works with AWS Lambda, S3, DynamoDB, Kinesis, and more.

- Common Use Cases
  - Collecting telemetry and sensor data from devices.
  - Remote monitoring and control of connected devices.
  - Building smart home, industrial, or automotive IoT applications.
  - Real-time analytics and machine learning on IoT data.

  2. `AWS IoT Greengrass:` Brings AWS compute, messaging, and data caching to edge devices.

AWS IoT Greengrass is a software that extends AWS cloud capabilities to local devices, allowing them to collect and analyze data closer to the source, respond quickly to local events, and operate with intermittent cloud connectivity. It enables edge computing by running AWS Lambda functions, managing device messaging, and maintaining device shadows locally.

- Key Features
  - **Local compute:** Run AWS Lambda functions on edge devices.
  - **Secure communication:** Encrypts messages and authenticates devices locally.
  - **Offline operation:** Devices can operate and sync data when reconnected.
  - **Seamless cloud integration:** Sync data and device state with AWS IoT Core.
  - **Machine learning inference:** Run ML models on edge devices.
  - **Device management:** Manage and update devices and software remotely.

- Common Use Cases
  - Industrial automation and predictive maintenance.
  - Smart homes and buildings with local control.
  - Autonomous vehicles and robotics requiring low latency.
  - Processing data locally to reduce cloud costs and latency.
  - Running machine learning inference at the edge.

### Domain 4: Billing, Pricing, and Support

#### Total Cost of Ownership?

**Total Cost of Ownership (TCO)** refers to the **total cost of acquiring, operating, and maintaining** a service or system over its entire lifecycle. In the context of AWS, TCO includes not just the direct service charges, but also costs related to infrastructure, maintenance, administration, scaling, and opportunity cost.

##### Key Components of AWS TCO

1. **Direct AWS Costs**
   - **Compute** (EC2, Lambda, Greengrass, etc.)
   - **Storage** (S3, EBS, DynamoDB, etc.)
   - **Data Transfer**
   - **Service-specific charges** (e.g., WorkSpaces hourly/monthly costs, IoT Core message volume)

2. **Operational Costs**
   - Time and effort to set up and manage services
   - Monitoring and logging (CloudWatch, X-Ray)
   - Maintenance of custom code or containers

3. **Security & Compliance Costs**
   - Identity and Access Management (IAM) setup
   - Encryption, auditing, and compliance reporting

4. **Software & Licensing**
   - OS licensing (e.g., Windows WorkSpaces)
   - Third-party integrations and subscriptions

5. **Training and Staffing**
   - Time for staff to learn AWS services
   - Cost of DevOps/Cloud engineers

##### Benefits of AWS in Reducing TCO

- **Pay-as-you-go pricing:** Only pay for what you use
- **Scalability:** Automatically scale without over-provisioning
- **Managed services:** Reduce need for in-house infrastructure and ops
- **Global infrastructure:** Avoid capital expense (CapEx) for data centers
- **Faster innovation:** Reduce time to market and opportunity costs

##### AWS IoT Greengrass TCO Considerations

| Cost Category     | Examples                                                     |
| ----------------- | ------------------------------------------------------------ |
| Hardware          | Edge device (Raspberry Pi, Jetson Nano, industrial gateways) |
| AWS Services      | IoT Greengrass, IoT Core, Lambda, CloudWatch                 |
| Maintenance       | Updating Greengrass components, managing Lambda versions     |
| Connectivity      | Data transfer from edge to cloud (can vary significantly)    |
| Monitoring & Logs | CloudWatch usage for monitoring deployments and logs         |

[Core AWS Pricing Concepts](https://aws.amazon.com/economics/)

#### Six Advantages of Cloud Computing

##### Cost Efficiency

- **Pay-as-you-go:** Only pay for the resources you use.
- **No upfront investment:** Avoid capital expenditures (CapEx) on hardware.
- **Reduced maintenance costs:** Managed services eliminate infrastructure upkeep.

##### Scalability

- **Vertical and horizontal scaling:** Instantly scale resources up or down based on demand.
- **Automatic scaling:** Many services adjust resources automatically (e.g., AWS Auto Scaling).
- **Global reach:** Deploy applications closer to users across the globe.

##### High Availability & Reliability

- **Redundancy:** Cloud providers offer multi-region, fault-tolerant infrastructure.
- **Disaster recovery:** Built-in backup and failover systems reduce downtime.
- **Service Level Agreements (SLAs):** Providers guarantee high uptime (e.g., 99.99%).

##### Speed and Agility

- **Rapid deployment:** Launch servers, databases, and services in minutes.
- **Faster innovation:** Quickly experiment and iterate without infrastructure constraints.
- **DevOps friendly:** Integrated tools for CI/CD, monitoring, and automation.

##### Security

- **Built-in security controls:** Encryption, access control, firewalls, etc.
- **Compliance:** Cloud platforms meet industry standards like ISO, HIPAA, GDPR.
- **Shared responsibility model:** Providers secure the infrastructure; you secure the data.

##### Global Access and Collaboration

- **Remote accessibility:** Access resources from anywhere via the internet.
- **Collaboration tools:** Real-time collaboration using cloud-hosted apps and storage.
- **Cross-platform support:** Work from multiple devices and operating systems.

Cloud economics refers to the financial principles and business value derived from cloud computing. It helps organizations understand how to optimize costs, `improve return on investment (ROI)`, and maximize the value of cloud adoption.

#### Price of Cloud

AWS has 3 pricing fundamentals, following the pay-as-you-go pricing model

1. Compute: Pay for compute time
2. Storage: Pay for data stored in the Cloud
3. Data transfer out of the Cloud: Data transfer in is free
Its the expensive issue then traditional IT

#### BYOL (Bring Your Own License)?

BYOL is a licensing model that lets you use your existing software licenses (like Windows, SQL Server, Oracle, etc.) when migrating or deploying workloads on AWS. Instead of buying new licenses through AWS, you "bring" the ones you already own—usually through volume licensing agreements from Microsoft, Oracle, etc.

#### Data Transfer Cost

**Data transfer** refers to the movement of data in and out of cloud services or between cloud resources. Cloud providers often charge for **outbound data** (data sent from the cloud to the internet or other regions), while **inbound data** (into the cloud) is usually free.

##### Types of Data Transfer

| Type                              | Description                                                                 |
| --------------------------------- | --------------------------------------------------------------------------- |
| **Inbound (Internet → Cloud)**    | Usually free across all major cloud providers                               |
| **Outbound (Cloud → Internet)**   | Charged per GB after free tier is used                                      |
| **Inter-AZ (within region)**      | Typically free or very low-cost (some exceptions)                           |
| **Inter-region**                  | Charged at a higher rate (moving data between different geographic regions) |
| **VPC Peering / Transit Gateway** | May incur charges depending on setup and region                             |
| **CloudFront (CDN)**              | Lower outbound costs due to edge caching                                    |

##### Cost Optimization Tips

- **Use CloudFront (CDN):** Reduces data transfer costs by serving content from edge locations.
- **Keep data within the same region:** Avoid cross-region traffic to reduce costs.
- **Use AWS PrivateLink or VPC Endpoints:** Avoid unnecessary public data transfer charges.
- **Compress data:** Reduce volume before transfer.
- **Use S3 Transfer Acceleration** only when speed is more important than cost.

> Summary

Data transfer costs can become significant, especially for **high-traffic applications** or **multi-region architectures**. Understanding your data flow and optimizing accordingly is essential to controlling cloud costs.

#### Resource Group?

A **resource group** in AWS is a collection of AWS resources that are grouped based on **tags** or **CloudFormation stacks**. While resource groups themselves don't directly show cost, they are used **in combination with tags** for **cost tracking and allocation**.

##### How Cost Allocation Works

AWS doesn't bill you by “resource group” directly. Instead, it uses:

- **Cost Allocation Tags**
- **AWS Cost Explorer**
- **Budgets**
- **Reports**

By tagging resources appropriately and optionally using **resource groups** to organize them, you can allocate and track costs more effectively.

##### Steps to Track Costs by Resource Group **Apply Tags to Resources**

Tag key examples:

- `Project`
- `Environment`
- `Department`
- `Team`
- `CostCenter`

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
