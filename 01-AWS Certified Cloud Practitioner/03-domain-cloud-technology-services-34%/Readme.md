#### 03 Domain - Cloud Technology and Services
This is the **largest domain** on the AWS Certified Cloud Practitioner (CLF-C02) exam, focusing on **core AWS services** and how they enable businesses to build, deploy, and operate applications in the cloud.

##### Different Ways of Provisioning and Operating in the AWS Cloud
AWS offers several methods for provisioning and managing resources:
- AWS Management Console
  - A web-based GUI to interact with AWS services.
  - Best for beginners and manual operations.
- AWS CLI (Command Line Interface)
  - Text-based tool to script and automate tasks.
  - Useful for developers and admins who prefer terminal-based control.
- AWS SDKs (Software Development Kits)
  - Libraries available for languages like Python (Boto3), JavaScript, Java, etc.
  - Ideal for integrating AWS into applications programmatically.
- AWS CloudFormation
  - Infrastructure as Code (IaC) tool to define AWS resources in JSON or YAML.
  - Great for replicable, consistent deployments.
- AWS CDK (Cloud Development Kit)
  - Define infrastructure using familiar programming languages like TypeScript or Python.
  - Combines IaC with real code logic.
- Terraform (by HashiCorp)
  - Third-party IaC tool, cloud-agnostic.
  - Popular for managing infrastructure across multiple cloud providers.
- AWS Systems Manager
  - Provides operational insights and automation tools for managing resources securely at scale.

##### Different Ways to Access AWS Services
- You can interact with AWS in several ways:
- AWS Management Console
- AWS CLI
- AWS SDKs/APIs
- AWS CloudShell – Browser-based shell preconfigured with CLI tools.
- AWS Tools for PowerShell – For Windows users to script AWS tasks.
- Programmatic Access via APIs and Lambda functions.

##### Connectivity Options
Several ways to connect to AWS resources:
- Internet Access (Public endpoints)
  - Using the internet to access AWS services like S3, EC2.
- Virtual Private Network (VPN)
  - Secure connection between on-premises and AWS over the internet.
- AWS Direct Connect
  - Dedicated, private network connection to AWS.
  - Lower latency and more secure than VPN.
- VPC Peering
  - Connects two VPCs for communication.
- AWS Transit Gateway
  - Central hub to connect multiple VPCs and on-premises networks.
- Elastic Load Balancing (ELB)
  - Automatically distributes incoming application traffic.
- AWS PrivateLink
  - Private connectivity to AWS services without using public IPs.

#### AWS global infrastructure.
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

#### AWS Compute Services
AWS offers a wide range of compute services for diverse workloads, from virtual servers to serverless functions and container orchestration. Key services include Amazon EC2 (Elastic Compute Cloud), AWS Fargate, AWS Lambda, Amazon ECS (Elastic Container Service) and Amazon EKS (Elastic Kubernetes Service), along with other specialized services like AWS Batch and Lightsail. 

##### Elastic Compute Cloud (EC2 use as IaaS)
It is a very popular cloud-computing platform of AWS, that allows users to rent virtual computers on which to run their own computer applications. Its mainly consist to following resources.
- Eleatic Block Storage (EBS) > Store data on virtual drives.
- Elastic Load Balancer (ELB) > Load distribution across the EC2.
- Auto Scaling Group (ASG) > Scaling the traffic for user utility.

##### EC2 Volume & Configuration Options
- Supported OS: Linux (recommendation), Windows or Mac OS.
- How much compute power & cores (CPU).
- How much random-access memory (RAM).
- How much storage space:
  - Network Attached (EBS & EFS)
  - Hardware (EC2 Instance Store)
- Network card: speed of the card, Public IP address
- Firewall rules: security group (SG)
- Bootstrap script (configure at first launch): EC2 User Data

##### EC2 Instance Overview
As per AWS has the following naming convention: ***m5.2xlarge***
Here
- ***5*** > Generation (AWS improves them over time)
- ***m*** > Instance Class
- ***2xlarge*** > Size within the instance class

[EC2 Instance Types](https://aws.amazon.com/ec2/instance-types/?gclid=CjwKCAiAlJKuBhAdEiwAnZb7lZtz6Hg-Nr2dW7JErl0Xng7mOGfkBspN09gheGCmnx6VajROvTDejxoCc_QQAvD_BwE&trk=32f4fbd0-ffda-4695-a60c-8857fab7d0dd&sc_channel=ps&ef_id=CjwKCAiAlJKuBhAdEiwAnZb7lZtz6Hg-Nr2dW7JErl0Xng7mOGfkBspN09gheGCmnx6VajROvTDejxoCc_QQAvD_BwE:G:s&s_kwcid=AL!4422!3!536392685920!e!!g!!ec2%20instance%20types!11539707735!118057054048)

- General Purpose
  - Great for a diversity of workloads such as web servers or code repositories
  - Balance among: Compute, Memory & Networking
  - For t2.micro is a General Purpose EC2 instance

- Compute Optimized
  - Great for compute-intensive tasks that require high performance processors:
  - Batch processing workloads
  - Media transcoding
  - High performance web servers
  - High performance computing (HPC)
  - Scientific modeling & machine learning
  - Dedicated gaming servers

- Memory Optimized
  - Fast performance for workloads that process large data sets in memory
  - Use cases:
    - High performance, relational/non-relational databases
    - Distributed web scale cache stores
    - In-memory databases optimized for BI (business intelligence)
    - Applications performing real-time processing of big unstructured data

- Storage Optimized
  - Great for storage-intensive tasks that require high, sequential read and write access to large data sets on local storage
  - Use cases:
    - High frequency online transaction processing (OLTP) systems
    - Relational & NoSQL databases
    - Cache for in-memory databases (for example, Redis)
    - Data warehousing applications
    - Distributed file systems

Example (Instance Type)
![Instance Type](/img/instance-types.png)

EC2 Instances Purchasing Options
|  SL   | Instance Name         |   Period   | Description                                                |
| :---: | :-------------------- | :--------: | :--------------------------------------------------------- |
|   1   | On-Demand             | Short Time | short workload, predictable pricing, pay by second         |
|   1   | Reserved Instances    | 1-3 Years  | long workloads with flexible instances                     |
|   2   | Savings Plans         | 1-3 Years  | commitment to an amount of usage, long workload            |
|   3   | Spot Instances        | Short Time | short workloads, cheap, can lose instances (less reliable) |
|   4   | Dedicated Hosts       | Long Time  | book an entire physical server, control instance placement |
|   5   | Dedicated Instances   |    N/A     | no other customers will share your hardware                |
|   6   | Capacity Reservations |    N/A     | reserve capacity in a specific AZ for any duration         |

***Mentioned features of each instance below as follows;***

***On Demand***
- Pay for what you use:
  - Linux or Windows
    - Billing per second, after the first minute 
    - All other operating systems - billing per hour
- Has the highest cost but no upfront payment
- No long-term commitment
- Recommended for short-term and un-interrupted workloads, where you can't predict how the application will behave

***Reserved Instances***
- Up to 72% discount compared to On-demand
- You reserve a specific instance attributes (Instance Type, Region,Tenancy, OS)
- Reservation Period
  - 1 year (+discount) or 
  - 3 years (+++discount)
- Payment Options
  - No Upfront (+), 
  - Partial Upfront (++), 
  - All Upfront (+++)
- Reserved Instance’s Scope: Regional or Zonal (reserve capacity in an AZ)
- Recommended for steady-state usage applications (think database)
- You can buy and sell in the Reserved Instance Marketplace
- Convertible Reserved Instance
  - Can change the EC2 instance type, instance family, OS, scope and tenancy
  - Up to 66% discount

***Savings Plans***
- Get a discount based on long-term usage
  - up to 72% - same as Reserved Instance’s
  - Commit to a certain type of usage ($10/hour for 1 or 3 years)
- Usage beyond EC2 Savings Plans is billed at the On-Demand price
- Locked to a specific instance family & AWS region (e.g., M5 in us-east-1)
- Flexible across:
  - Instance Size (e.g., m5.xlarge, m5.2xlarge)
  - OS (e.g., Linux, Windows)
  - Tenancy (Host, Dedicated, Default)

***Spot Instances***
- Can get a discount of up to 90% compared to On-demand
- Instances that you can ***lose*** at any point of time if your max price is less than the current spot price
- The MOST ***cost-efficient*** instances in AWS
- Useful for workloads that are resilient to failure • Batch jobs
  - Data analysis
  - Image processing
  - Any distributed workloads
  - Workloads with a flexible start and end time
  - Not suitable for critical jobs or databases

***Dedicated Hosts***
- A physical server with EC2 instance capacity fully dedicated to your use
- Allows you address compliance requirements and use your existing server- bound software licenses (per-socket, per-core, pe—VM software licenses)
- Purchasing Options:
  - On-demand – pay per second for active Dedicated Host
  - Reserved - 1 or 3 years (No Upfront,Partial Upfront,All Upfront)
- The most expensive option
- Useful for software that have complicated licensing model (BYOL – Bring Your Own License)
- Or for companies that have strong regulatory or compliance needs

***Dedicated Instances***
- Instances run on hardware that’s dedicated to you
- May share hardware with other instances in same account
- No control over instance placement (can move hardware after Stop / Start)

Service comparison between 'dedicated instance' & 'dedicated hosts'
|  SL   | Characteristic                                      | Dedicated Instances | Dedicated Hosts |
| :---: | :-------------------------------------------------- | :-----------------: | :-------------: |
|   1   | Enable the use of dedicated physical servers        |          x          |        x        |
|   2   | Per instance billing (subject to $2 per region fee) |          x          |        -        |
|   3   | Per host billing                                    |          -          |        x        |
|   4   | Visibility of sockets, cores, host ID               |          -          |        x        |
|   5   | Affinity between a host and instance                |          -          |        x        |
|   6   | Targeted instance placement                         |          -          |        x        |
|   7   | Automatic instance placement                        |          x          |        x        |
|   8   | Add capacity using an allocation request            |          -          |        x        |

***Capacity Reservations***
- Reserve On-Demand instances capacity in a specific AZ for any duration
- You always have access to EC2 capacity when you need it
- No time commitment (create/cancel anytime), no billing discounts
- Combine with Regional Reserved Instances and Savings Plans to benefit from billing discounts
- You’re charged at On-Demand rate whether you run instances or not
- Suitable for short-term, uninterrupted workloads that needs to be in a specific AZ

##### Shared Responsibility Model of EC2 Instance
| AWS (Provider)                           | User                                                   |
| :--------------------------------------- | :----------------------------------------------------- |
| Infrastructure (global network security) | Security Groups rules                                  |
| Isolation on physical hosts              | Operating-system patches and updates                   |
| Replacing faulty hardware                | Software and utilities installed on the EC2 instance   |
| Compliance validation                    | IAM Roles assigned to EC2 & IAM user access management |
| -                                        | Data security on your instance                         |

#### [AWS Database Service](https://aws.amazon.com/free/database/?gclid=EAIaIQobChMInunfv-LZjAMVSqtmAh1omStKEAAYASAAEgK7I_D_BwE&trk=a049d6a3-611f-4ee9-9d3b-e88a4b66272f&sc_channel=ps&ef_id=EAIaIQobChMInunfv-LZjAMVSqtmAh1omStKEAAYASAAEgK7I_D_BwE:G:s&s_kwcid=AL!4422!3!548730526963!p!!g!!amazon%20cloud%20database!11542049405!107751951010&gbraid=0AAAAADjHtp8v8DEsy08OPZK56vPhBTqVe)
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

#### AWS Network Services
**Elastic Load Balancing (ELB) & Auto Scaling Groups (ASG)**
Scalability & High Availability
- Scalability means that an application/system can handle greater loads by adapting. There are two kinds of scalability:
  - Vertical Scalability
  - Horizontal Scalability (= elasticity)
- Scalability is linked but different to High Availability

Vertical Scalability
- Vertical Scalability means increasing the size/capacity of the instance
- For example, your application runs on a t2.micro to t2.large
- Vertical scalability is very common for ***non distributed systems***, such as a ***database***.
- There’s usually a limit to how much you can vertically scale (hardware limit)

Horizontal Scalability
- Horizontal Scalability means increasing the number of instances/systems for your application
- Horizontal scaling implies distributed systems.
- This is very common for web applications/modern applications
- It’s easy to horizontally scale thanks the cloud offerings such as EC2

High Availability
- High Availability usually goes hand in hand with horizontal scaling
- High availability means running your application/system in at least 2 Availability Zones
- The goal of high availability is to survive a data center loss (disaster)

High Availability & Scalability For EC2
- Vertical Scaling: Increase instance size (scale up/down)
  - From: t2.nano - 0.5G of RAM, 1 vCPU - To: u-12tb1.metal – 12.3 TB of RAM, 448 vCPUs
- Horizontal Scaling: Increase number of instances (scale out/in)
  - Auto Scaling Group
  - Load Balancer
- High Availability: Run instances for the same application across multi AZ
  - Auto Scaling Group multi AZ
  - Load Balancer multi AZ

Scalability vs Elasticity (Agility)
- Scalability: ability to accommodate a larger load by making the hardware stronger (scale up), or by adding nodes (scale out)
- Elasticity: once a system is scalable, elasticity means that there will be some “auto-scaling” so that the system can scale based on the load. This is “cloud-friendly”: pay-per-use, match demand, optimize costs
- Agility: (not related to scalability - distractor) new IT resources are only a click away, which means that you reduce the time to make those resources available to your developers from weeks to just minutes.

***What is load balancing?***
- Load balancers are servers that forward internet traffic to multiple servers (EC2 Instances) downstream.
![Load Balancing](/img/load-balancing.png)

***Why use a load balancer?***
- Spread load across multiple downstream instances
- Expose a single point of access (DNS) to your application
- Seamlessly handle failures of downstream instances
- Do regular health checks to your instances
- Provide SSL termination (HTTPS) for your websites
- High availability across zones

***Why use an Elastic Load Balancer?***
- An ELB (Elastic Load Balancer) is a managed load balancer.
  - AWS guarantees that it will be working
  - AWS takes care of upgrades, maintenance, high availability
  - AWS provides only a few configuration knobs
- It costs less to setup your own load balancer but it will be a lot more effort on your end (maintenance, integrations)
- 4 kinds of load balancers offered by AWS:
  - Application Load Balancer (HTTP / HTTPS only) – Layer 7 (APS TNDP)
    - 7 Layer (Application > Presentation > Session > Transport > Network > Data Link > Physical)
  - Network Load Balancer (ultra-high performance, allows for TCP) – Layer 4
    - 4 Layer (Application > Transport > Internet > Network)
  - Gateway Load Balancer – Layer 3
  - Classic Load Balancer (retired in 2023) – Layer 4 & 7
![Elastic Load Balancer](/img/elastic-load-balancer.png)

***What’s an Auto Scaling Group?***
- In real-life, the load on your websites and application can change
- In the cloud, you can create and get rid of servers very quickly
- The goal of an Auto Scaling Group (ASG) is to:
- Scale out (add EC2 instances) to match an increased load
- Scale in (remove EC2 instances) to match a decreased load
- Ensure we have a minimum and a maximum number of machines running
- Automatically register new instances to a load balancer
- Replace unhealthy instances
- Cost Savings: only run at an optimal capacity (principle of the cloud)

Auto Scaling Group
![Auto Scaling Group](/img/auto-scaling-group.png)

Auto Scaling Group with Load Balancer
![Auto Scaling Group with Load Balancer](/img/auto-scaling-group-load-balancer.png)

Difference between Load Balancer and Auto Scaling
|    Factors     | Load Balancer                   | Auto Scaling                    |
| :------------: | :------------------------------ | :------------------------------ |
|    Purpose     | Distribute the incoming traffic | Adjust the number of resources  |
| Algorithm used | Round-Robin algorithm or least  | Step Scaling or Target Tracking |

#### AWS Storage Services
There are three types of storage in Amazon Web Services
1. Object Storage
   - S3 Storage
   - S3 Glacier Storage
   - Snowball Storage
2. File Storage
   - Elastic File System (EFS)
   - FSx Storage (Windows)
   - FSx Storage (Lustre)
3. Block Storage
   - [Elastic Block Storage (EBS)](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-volume-types.html)
     - SSD Storage volumes
       - General Purpose (GP2) volumes
       - Provisioned IOPS SSD (io1) volumes
       - Provisioned IOPS SSD (io2) volumes
     - HDD Storage
       - Throughput Optimized (ST1)
       - Cold HDD (SC1)
     - Magnetic Storage
   - EC2 Instance Storage

IOPS (eye-ops):
Input/Output Operation per Second is use as I/O performance management measurement to characterize computer storage devices like HDD, SSD & Storage Area Network (SAN). This Operations (reads or writes) that a storage system can perform in one second. It focuses on the speed at which individual read and write operations can be completed. Its measure in KiB.
- Maximum amount of data that a volume type counts as 'Single I/O'.
- I/O size capped at 256 KiB for SSD.
- I/O size capped at 1024 KiB for HDD.
- SSD volumes handle small/random I/O more efficiently than HDD volumes.

IOPS Calculation:
Average Seek Time = (Read Time + Write Time)/2
IOPS = 1 / (RPM Average Latency Time + Average Seek Time)
Suppose, Rotational Speed = 15,000, RPM Average Latency Time = 3 ms = 0.003 Seconds, Average Seek Time = {4.2 (R) + 4.45 (W)}/2 = 4.45 ms = 0.0045 Second

IOPS = 1 / (0.003 + 0.0045) = 133 IOPS (Approximately)

Throughput
Its refers to the rate at which data is transferred successfully between two points in a system, such as between a storage device and a server, or within a network. Throughput can be affected by IOPS & packet size.

Each type of storage is discussed in detail that is as follows;

##### [1.1- Object Storage (S3 Storage)](https://aws.amazon.com/pm/serv-s3/?trk=b8b87cd7-09b8-4229-a529-91943319b8f5&sc_channel=ps&ef_id=CjwKCAiA_aGuBhACEiwAly57MX61bi-mAlAD0os3_jPx0l3oYV-mkTDNdI8gy4MVE8cY776K1fRZxRoCi6gQAvD_BwE:G:s&s_kwcid=AL!4422!3!536456067065!e!!g!!s3%20storage!11539706604!115473954914&gclid=CjwKCAiA_aGuBhACEiwAly57MX61bi-mAlAD0os3_jPx0l3oYV-mkTDNdI8gy4MVE8cY776K1fRZxRoCi6gQAvD_BwE)
It is an object storage service offering industry-leading scalability, data availability, security, and performance.
***Uses of S3***  (as like Google Drive, One Drive, Drop Box etc.)
- Backup and storage
- Disaster Recovery
- Archive
- Hybrid Cloud storage
- Application hosting
- Media hosting
- Data lakes & big data analytics
- Software delivery
- Static website

***Buckets***
- Amazon S3 allows people to store objects (files) in “buckets” (directories)
- Buckets must have a globally unique name (across all regions all accounts)
- Buckets are defined at the region level
- S3 looks like a global service but buckets are created in a region
  - Naming convention
  - No uppercase, No underscore
  - 3-63 characters long
  - Not an IP
  - Must start with lowercase letter or number
  - Must NOT start with the prefix xn--
  - Must NOT end with the suffix -s3alias

***Objects***
- Objects (files) have a Key
- The key is the FULL path:
  - s3://my-bucket/my_file.txt
  - s3://my-bucket/my_folder1/another_folder/my_file.txt
- The key is composed of prefix + object name
  - s3://my-bucket/my_folder1/another_folder/my_file.txt
- There’s no concept of “directories” within buckets (although the UI will trick you to think otherwise)
- Just keys with very long names that contain slashes (“/”)
- Object values are the content of the body:
  - Max. Object Size is 5TB (5000GB)
  - If uploading more than 5GB, must use “multi-part upload”
- Metadata (list of text key / value pairs – system or user metadata)
- Tags (Unicode key / value pair – up to 10) – useful for security / lifecycle
- Version ID (if versioning is enabled)

***Security***
- User-Based
  - IAM Policies – which API calls should be allowed for a specific user from IAM
- Resource-Based
  - Bucket Policies – bucket wide rules from the S3 console - allows cross account
  - Object Access Control List (ACL) – finer grain (can be disabled)
  - Bucket Access Control List (ACL) – less common (can be disabled)
- Note: an IAM principal can access an S3 object if
  - The user IAM permissions ALLOW it OR the resource policy ALLOWS it
  - AND there’s no explicit DENY
- Encryption: encrypt objects in Amazon S3 using encryption keys

***S3 Bucket Policies***
- JSON based policies
  - Resources: buckets and objects
  - Effect: Allow / Deny
  - Actions: Set of API to Allow or Deny
  - Principal:The account or user to apply the policy to
- Use S3 bucket for policy to:
  - Grant public access to the bucket
  - Force objects to be encrypted at upload
  - Grant access to another account (Cross Account)

Example (S3 Bucket Policies)
```JSON
{
  "Version": "2024-02-12",
  "Statement": [
    {
      "Sid": "PublicRead",
      "Effect": "Allow",
      "Principal": "*",
      "Action": [
        "s3:GetObject"
      ],
      "Resource": [
        "arn:aws:s3:::my_sweet_bucket/*"
      ]
    }
  ]
}
```

##### [1.2- Object Storage (S3 Glacier Storage)](https://aws.amazon.com/pm/s3-glacier/?trk=b8b87cd7-09b8-4229-a529-91943319b8f5&sc_channel=ps&ef_id=CjwKCAiA_aGuBhACEiwAly57Mdp21CgKnEvgufcIeYZ_cnX3_6l4342RMJhP5OBESh-aP2g1mjr_dBoCxecQAvD_BwE:G:s&s_kwcid=AL!4422!3!674509861659!e!!g!!amazon%20s3%20glacier!11539706604!154273570032&gclid=CjwKCAiA_aGuBhACEiwAly57Mdp21CgKnEvgufcIeYZ_cnX3_6l4342RMJhP5OBESh-aP2g1mjr_dBoCxecQAvD_BwE)
- The Amazon S3 Glacier storage classes are purpose-built for data archiving, providing you with the highest performance, most retrieval flexibility, and the lowest cost archive storage in the cloud.
- Choose from three archive storage classes optimized for different access patterns and storage duration.
- The S3 Glacier storage classes provide virtually unlimited scalability and are designed for 99.999999999% (11 nines) of data durability.

##### [1.3- Object Storage (Snowball Storage)](https://aws.amazon.com/snowball/)
Accelerate moving offline data or remote storage to the cloud. Description: Snowball is a petabyte-scale data transport solution that uses secure appliances to transfer large amounts of data into and out of the AWS cloud. Using Snowball addresses common challenges with large-scale data transfers including high network costs, long transfer times, and security concerns.
Features:
- A service fee for each job you run, 
- Data transfer fees from Amazon S3,
- The shipping costs to transport a Snowball appliance to and from your address, and 
- The number of days you keep Snowball onsite. [For details](https://aws.amazon.com/snowball/pricing/)

##### 2.1- File Storage [Elastic File System (EFS)]
***EFS Infrequent Access (EFS-IA)***
- Managed NFS (network file system) that can be mounted on 100s of EC2
- EFS works with Linux EC2 instances in multi-AZ
- Highly available, scalable, expensive (3x gp2), pay per use, no capacity planning
- Storage class that is cost-optimized for files not accessed every day
- Up to 92% lower cost compared to EFS Standard
- EFS will automatically move your files to EFS-IA based on the last time they were accessed
- Enable EFS-IA with a Lifecycle Policy
- Example: move files that are not accessed for 60 days to EFS-IA
- Transparent to the applications accessing EFS
- cost-optimized storage class for infrequent accessed files

##### 2.2- File Storage [FSx Storage (Windows)]
Launch 3rd party high-performance file systems on AWS. Fully managed service
- A fully managed, highly reliable, and scalable Windows native shared file system
- Built on Windows File Server
- Supports SMB protocol & Windows NTFS
- Integrated with Microsoft Active Director y
- Can be accessed from AWS or your on-premise infrastructure
- Network File System for Windows servers

##### 2.3- File Storage [FSx Storage (Lustre)]
- A fully managed, high-performance, scalable file storage for High Performance Computing (HPC)
- The name Lustre is derived from “Linux” and “cluster”
- Machine Learning, Analytics,Video Processing, Financial Modeling, ...
- Scales up to 100s GB/s, millions of IOPS, sub-ms latencies

##### 3.1- Block Storage [Elastic Block Storage (EBS)]
An EBS (Elastic Block Store) Volume is a network drive (i.e. not a physical drive) you can attach to your instances while they run
- It allows your instances to persist data, even after their termination
- They can only be mounted to one instance at a time (at the Certified Cloud Practitioner (CCP) level)
- They are bound to a specific availability zone
- Analogy:Think of them as a “network USB stick”
- Free tier: 30 GB of free EBS storage of type General Purpose (SSD) or Magnetic per month
- It uses the network to communicate the instance, which means there might be a bit of latency
- It can be detached from an EC2 instance and attached to another one quickly
- It’s locked to an Availability Zone (AZ)
- An EBS Volume in ***us-east-1a*** cannot be attached to ***us-east-1b***
- To move a volume across, you first need to snapshot it
- Have a provisioned capacity (size in GBs, and IOPS)
- You get billed for all the provisioned capacity
- You can increase the capacity of the drive over time

***EBS Snapshots Features***
- EBS Snapshot Archive
  - Move a Snapshot to an ”archive tier” that is 75% cheaper
  - Takes within 24 to 72 hours for restoring the archive
- Recycle Bin for EBS Snapshots
  - Setup rules to retain deleted snapshots so you can recover them after an accidental deletion
  - Specify retention (from 1 day to 1 year)

##### [3.2 Block Storage (EC2 Instance Storage)](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/InstanceStorage.html)
An instance store provides temporary block-level storage for your instance. This storage is located on disks that are physically attached to the host computer. Instance store is ideal for temporary storage of information that changes frequently, such as buffers, caches, scratch data, and other temporary content. It can also be used to store temporary data that you replicate across a fleet of instances, such as a load-balanced pool of web servers.
Features:
An instance store consists of one or more instance store volumes exposed as block devices. The size of an instance store as well as the number of devices available varies by instance type and instance size. [For more](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/InstanceStorage.html)

***Amazon Machine Image (AMI)***
- AMI are a customization of an EC2 instance
  - You add your own software, configuration, operating system, monitoring... 
  - Faster boot/configuration time because all your software is pre-packaged
- AMI are built for a specific region (and can be copied across regions)
- You can launch EC2 instances from:
  - A Public AMI: AWS provided
  - Your own AMI: you make and maintain them yourself
  - An AWS Marketplace AMI: an AMI someone else made (and potentially sells)

***AMI Process (from an EC2 instance)***
- Start an EC2 instance and customize it
- Stop the instance (for data integrity)
- Build an AMI – this will also create EBS snapshots 
- Launch instances from other AMIs

***EC2 Image Builder***
- Used to automate the creation ofVirtual Machines or container images
- Automate the creation, maintain, validate and test EC2 AMIs
- Can be run on a schedule (weekly, whenever packages are updated, etc...)
- Free service (only pay for the underlying resources)
Illustration shown below;
![Image builder](/img/image-builder.png)

##### Shared Responsibility Model of Storage Volume
| AWS (Provider)                                    | User                                               |
| :------------------------------------------------ | :------------------------------------------------- |
| Infrastructure                                    | Setting up backup / snapshot procedures            |
| Replication for data for EBS volumes & EFS drives | Setting up data encryption                         |
| Replacing faulty hardware                         | Responsibility of any data on the drives           |
| Ensuring their employees cannot access your data  | Understanding the risk of using EC2 Instance Store |

#### Services from other in-scope AWS Service Categories
- Application Integration Services
  These services help applications communicate and process events or messages reliably.
  - Amazon EventBridge: Event bus for building event-driven applications at scale.
  - Amazon SNS (Simple Notification Service): Pub/sub messaging for decoupled microservices.
  - Amazon SQS (Simple Queue Service): Managed message queuing for distributed systems.
- Business Application Services
  Enable customer service and communication workflows.
  - Amazon Connect: Cloud-based contact center service.
  - Amazon SES (Simple Email Service): Scalable email sending for marketing or transactional purposes.
- Customer Engagement Services
  These services support customer success and AWS account management.
  - AWS Activate for Startups: Credits, training, and support for startup growth.
  - AWS IQ: Connects customers with AWS-certified freelancers and consultants.
  - AWS Managed Services (AMS): Operational support and automation for AWS infrastructure.
  - AWS Support: Tiered support plans offering guidance and troubleshooting.
- Developer Tools
  Helps developers build, test, and deliver code quickly and securely.
  - AWS AppConfig: Feature flagging and configuration management.
  - AWS Cloud9: Cloud-based IDE for writing, running, and debugging code.
  - AWS CloudShell: Browser-based shell for command-line access to AWS.
  - AWS CodeArtifact: Artifact repository for software packages.
  - AWS CodeBuild: Continuous integration service to compile and test code.
  - AWS CodeCommit: Fully managed Git-based source control.
  - AWS CodeDeploy: Automates code deployments to compute services.
  - AWS CodePipeline: CI/CD pipeline orchestration tool.
  - AWS CodeStar: Unified interface for software development.
  - AWS X-Ray: Distributed tracing system for analyzing and debugging applications.
- End-User Computing Services
  Provides remote desktops and application streaming for users.
  - Amazon AppStream 2.0: Stream desktop apps to users over the web.
  - Amazon WorkSpaces: Managed virtual desktops in the cloud.
  - Amazon WorkSpaces Web: Secure browser access to internal websites and apps.
- Frontend Web and Mobile Services
  Helps developers build full-stack web and mobile applications.
  - AWS Amplify: Set of tools to build, ship, and host full-stack applications.
  - AWS AppSync: Managed GraphQL service for querying and syncing data in real-time.
- IoT Services
  Connect and manage IoT devices and edge computing.
  - AWS IoT Core: Secure device communication with cloud apps and services.
  - AWS IoT Greengrass: Brings AWS compute, messaging, and data caching to edge devices.