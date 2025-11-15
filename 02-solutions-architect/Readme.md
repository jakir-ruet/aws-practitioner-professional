## More About Me – [Take a Look!](http://www.mjakaria.me)

## Welcome to AWS Certified Solutions Architect - Associate `SAA-C03`

### The Shared Responsibility Model and Well-architected Framework

### Installing and Configuring the AWS CLI

- Control multiple AWS services from this command line.
- How to [Install](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html)?
- Let's me check aws --version
- If its okay then we will see `aws-cli/2.15.4 Python/3.11.6 Darwin/23.2.0 exe/x86_64 prompt/off`
- Configuration using security credential
- Go to AWS Management Console > Services > IAM
- Select the IAM User Name: Your User Name [NB: You must use IAM's Information only not Root User]
- Click on `Security credentials`
- Click on `Create access key`
- Copy Access ID & Secret access key
- Go to your Terminal and implement as below format
- Run the `aws configure` command
- AWS Access Key ID [None]: Put your ID here and press Enter.
- AWS Secret Access Key [None]: Put your secret key here and press Enter
- Default region name [None]: us-east-1
- Default output format [None]: json
- Let's me check whether the configuration is done.
- `aws ec2 describe-vpcs`
- If it is done then we will see the details of the default vpc.

### Bastion host/Jump host/Jump server

A `bastion host` (also called a `jump host` or `jump server`) is a special-purpose server used to securely access devices or servers in a private network from an external network, usually the internet. Think of it as a “gateway” that you pass through to reach internal systems that are otherwise inaccessible directly.

#### Work flow

- `[Your Laptop]` --> `SSH/RDP` --> `[Bastion Host]` --> `SSH/RDP` --> `[Internal Server]`

> Use cases:

- Secure access to private/internal servers (databases, apps)
- Centralized logging and auditing for compliance
- Temporary or controlled access for contractors or temporary staff
- Single access point for multi-cloud or hybrid networks
- Remote work access without a full VPN
- Emergency recovery and troubleshooting of internal servers
- Reducing attack surface by exposing only the bastion host to the internet
- Enforcing multi-factor authentication and strong security policies

### Virtual Private Cloud (VPC) Analysis

A VPC (Virtual Private Cloud) is a logically isolated virtual network within AWS where you can launch and manage your AWS resources securely. Two types VPC default VPC and Custom VPC.

#### Core Components:

- Subnets - Subdivisions of your VPC's IP address range
- Route Tables - Control traffic routing between subnets
- Internet Gateway - Connects VPC to the internet
- Security Groups - Virtual firewalls for EC2 instances
- NACLs - Network-level security (subnet level)

#### Must need to know when creating VPC's

- IP, CIDR, Sub-Netting ete.
- Private IPv4 CIDR blocks are required and range from `/16` to `/28`.
- IPv6 CIDR blocks are optional and range from `/44` to `/60`.
- CIDR must be from RFC 1918 range from `10.0.0.0`, `127.16.0.0` & `192.168.0.0`.
- Carefully consider your IP planning when creating a VPC.
- Know these private IP range `10.0.0.0/8`, `127.16.0.0/12` & `192.168.0.0/16`.

##### Let'e explore an example

Suppose, we have VPC's IP is 10.0.0.0/16.

Let’s understand the problem

- IP address: `10.0.0.0`
- CIDR notation: `/16` means the first `16 bits are network bits`
- Default mask of `class A`: /8
- IP address length: `32 bits total`
- /16 means 16 bits are `1 in the subnet mask`, remaining `16 bits are 0`
- Binary & Decimal subnet mask:

| Octet 1  | Octet 2  | Octet 3  | Octet 4  | Decimal Equivalent |
| -------- | -------- | -------- | -------- | ------------------ |
| 11111111 | 11111111 | 00000000 | 00000000 | `255.255.0.0`      |

> Network Block: The `1s` in the binary mask (/16) represent the network portion (first two octets).
> Host Block: The `0s` in the last two octets represent the host portion.
> Allowing for `2^16` = `65,536` addresses per /16, of which 65,534 are usable (exclude network IP (10.0.0.0) & broadcast IP (10.0.255.255)).

Given:

- x = number of 1’s in 2nd octet = 8
- y = number of 0’s in 2nd octet = 0
- z = Given mask /16 = 16
- k = Default mask = 8 (Class A)
- LOSM (Last Octet of Subnet Mask) = 2^7 + 2^6 + 2^5 + 2^4 + 2^3 + 2^2 + 2^1 + 2^0 = 128 + 64 + 32 + 16 + 8 + 4 + 2 + 1 = 255

`Answer`

- Subnet Mask is 255.255.0.0
- Block size = 256 - LOSM = 256 - 255 = 1
- Number of Subnets = 2^(y - k) = 2^(16 - 8) = 2^6 = 256
- Number of Hosts per Subnet = 2^(Total IP Bits - Given Mask) - 2 = 2^(32 - 16) - 2 = 65536 - 2 = 65534.

> Notes (Subtract 2 for network and broadcast addresses)

- Subnet addresses (Host)

| Subnet | Subnet ID     | First Host | Last Host      | Broadcast Address |
| ------ | ------------- | ---------- | -------------- | ----------------- |
| 1      | 10.0.0.0/16   | 10.0.0.1   | 10.0.255.254   | 10.0.255.255      |
| 2      | 10.1.0.0/16   | 10.1.0.1   | 10.1.255.254   | 10.1.255.255      |
| 3      | 10.2.0.0/16   | 10.2.0.1   | 10.2.255.254   | 10.2.255.255      |
| ...    | ...           | ...        | ...            | ...               |
| 256    | 10.255.0.0/16 | 10.255.0.1 | 10.255.255.254 | 10.255.255.255    |

- Locate which subnet 10.0.0.0 belongs to:
  Subnet ID = 10.0.0.0/16 (this address is the network address of the first /16)

Range note: For the 10.0.0.0/16 subnet the address space runs from 10.0.0.0 through 10.0.255.255 (inclusive).

- First valid host: 10.0.0.1
- Last valid host: 10.0.255.254
- Broadcast address: 10.0.255.255

Summary:

| Item                            | Value               |
| ------------------------------- | ------------------- |
| IP Address                      | 10.0.0.0            |
| Subnet Mask                     | 255.255.0.0         |
| Block Size                      | 1 (in second octet) |
| Number of Subnets (from /8→/16) | 256                 |
| Hosts per Subnet (usable)       | 65,534              |
| Subnet ID                       | 10.0.0.0/16         |
| First Valid Host                | 10.0.0.1            |
| Last Valid Host                 | 10.0.255.254        |
| Broadcast Address               | 10.0.255.255        |

##### Finally, Consider as below

- VPC CIDR				= 10.0.0.0/16
- Subnet CIDR			= 10.0.0.0/24 # Make smaller easy to manage
- Network Address		= 10.0.0.0
- VPC Address			= 10.0.0.1
- VPC DNS Address		= 10.0.0.2
- Future Use			= 10.0.0.3
- Broadcast Address	= 10.0.0.255

#### Building a Scalable and Secure Three-Tier Architecture on AWS for Web Applications

##### Prerequisites

Before you begin, ensure you have the following:

- An AWS account with appropriate `IAM user permissions`.
- Basic familiarity with the `AWS Management Console`.
- Understanding of `core AWS services`, including `VPC networking`, `EC2 instances`, `Auto Scaling groups`, and `Security Groups`.
- Working knowledge of `Linux`, including `basic commands`, `shell scripting`, and `SSH` connectivity.
- Access to a `command-line interface (CLI)` or terminal environment for running configuration commands.

### Three-Tier Architecture on AWS for Web Applications

![Three-Tier Architecture on AWS for Web Applications](/img/vpc-design.jpg)

#### Understanding and Plan

##### Configuration CI/CD pipeline

![CI/CD pipeline](/img/pipeline.jpg)

###### Frontend pipeline

###### Backend pipeline

##### Design three tier architecture

##### Deployment from version and rollback plan

##### Monitoring and logging for reliability

### AWS Storage, Transfer, and Migration Services

### Big Data

Big Data on AWS refers to using Amazon’s cloud services to `store`, `process`, `analyze`, and `visualize massive volumes` of data at `high speed` and `low cost`. AWS provides a full ecosystem of managed tools that eliminate the complexity of building big data infrastructure yourself. In big data has three properties/dimension.

#### The 5 V's of Big Data

- `Volume` - Massive amounts of data (terabytes to petabytes)
- `Velocity` - High-speed data generation and processing
- `Variety` - Different data types (structured, semi-structured, unstructured)
- `Veracity` - Data quality and accuracy concerns
- `Value` - Extracting meaningful insights from data

#### AWS Big Data Services

- `Data Ingestion:`
  - `Amazon Kinesis` - Real-time data streaming
  - `AWS DataSync` - Online data transfer
  - `AWS Snow Family` - Offline data transfer
  - `Amazon MSK` - Managed Kafka service

- `Data Storage:`
  - `Amazon S3` - Data lake storage
  - `Amazon Redshift` - Data warehouse
  - `AWS Lake Formation` - Secure data lakes

- `Data Processing:`
  - `Amazon EMR` - Managed Hadoop/Spark
  - `AWS Glue` - Serverless ETL
  - `Amazon Athena` - Serverless SQL queries

- `Analytics & ML:`
  - `Amazon SageMaker` - Machine learning platform
  - `Amazon QuickSight` - Business intelligence
  - `Amazon OpenSearch` - Search and analytics

#### Big Data Architecture Patterns

`Batch Processing:`

```
S3 Data Lake → AWS Glue ETL → Amazon Redshift → QuickSight
```

`Real-time Streaming:`

```
Kinesis Data Streams → Kinesis Analytics → Lambda → DynamoDB
```

`Lambda Architecture:`

```
Batch Layer: S3 → EMR → Redshift
Speed Layer: Kinesis → Lambda → DynamoDB
Serving Layer: QuickSight
```

#### Cost Optimization

- Use `Spot Instances` for EMR (up to 90% savings)
- Implement `S3 lifecycle policies`
- Use `serverless services` for sporadic workloads
- `Compress data` with Parquet/ORC formats

#### Security Best Practices

- `Encrypt data` at rest and in transit
- Use `IAM roles` for fine-grained access
- Enable `VPC endpoints` for private connectivity
- Implement `data lineage` tracking

### Machine Learning

Machine Learning on AWS provides a comprehensive set of services to build, train, and deploy ML models at scale. AWS offers tools for every skill level, from no-code solutions to advanced deep learning frameworks.

#### AWS ML Service Categories

- `AI Services (Pre-built Models):`
  - `Amazon Rekognition` - Image and video analysis
  - `Amazon Comprehend` - Natural language processing
  - `Amazon Polly` - Text-to-speech service
  - `Amazon Transcribe` - Speech-to-text service
  - `Amazon Translate` - Language translation
  - `Amazon Textract` - Extract text from documents
  - `Amazon Forecast` - Time-series forecasting
  - `Amazon Personalize` - Real-time recommendations
  - `Amazon Fraud Detector` - Fraud detection
  - `Amazon CodeGuru` - Code review and optimization

- `ML Platform Services:`
  - `Amazon SageMaker` - Complete ML platform
  - `Amazon Bedrock` - Generative AI with foundation models
  - `Amazon Q` - AI-powered assistant
  - `AWS DeepLens` - Deep learning camera
  - `AWS Panorama` - Computer vision at the edge

- `ML Infrastructure Services:`
  - `Amazon EC2 P4/G4 Instances` - GPU-powered compute
  - `AWS Batch` - Batch processing for ML workloads
  - `Amazon EKS` - Kubernetes for ML containers
  - `AWS Lambda` - Serverless ML inference

#### Amazon SageMaker Deep Dive

- `Core Components:`
  - `SageMaker Studio` - Integrated development environment
  - `SageMaker Notebooks` - Jupyter notebook instances
  - `SageMaker Training` - Managed training jobs
  - `SageMaker Endpoints` - Real-time inference
  - `SageMaker Batch Transform` - Batch inference
  - `SageMaker Pipelines` - ML workflow orchestration

- `SageMaker Features:`
  - `AutoML` - Automated model building
  - `Ground Truth` - Data labeling service
  - `Model Registry` - Model versioning and governance
  - `Feature Store` - Centralized feature repository
  - `Clarify` - Model explainability and bias detection
  - `Data Wrangler` - Visual data preparation
  - `JumpStart` - Pre-built ML solutions

#### ML Architecture Patterns

`Pattern 1: Real-time Inference`

```
Application → API Gateway → Lambda → SageMaker Endpoint → Model
```

`Pattern 2: Batch Processing`

```
S3 Data → SageMaker Processing → Trained Model → Batch Transform → S3 Results
```

`Pattern 3: Streaming ML`

```
Kinesis Data Streams → Lambda → SageMaker Endpoint → Kinesis Analytics → Dashboard
```

`Pattern 4: MLOps Pipeline`

```
Code Commit → CodeBuild → SageMaker Training → Model Registry → SageMaker Endpoints
```

#### ML Workflow Steps

`1. Data Preparation:`
    - `Data Collection` - S3, databases, streaming sources
    - `Data Labeling` - SageMaker Ground Truth
    - `Data Processing` - SageMaker Processing, Glue
    - `Feature Engineering` - SageMaker Feature Store

`2. Model Development:`
    - `Algorithm Selection` - Built-in algorithms, custom containers
    - `Training` - SageMaker Training Jobs
    - `Hyperparameter Tuning` - Automatic model tuning
    - `Model Evaluation` - SageMaker Experiments

`3. Model Deployment:`
    - `Real-time Endpoints` - Low latency inference
    - `Batch Transform` - Large-scale batch predictions
    - `Multi-model Endpoints` - Host multiple models
    - `Auto Scaling` - Scale based on traffic

`4. Model Monitoring:`
    - `Data Drift Detection` - SageMaker Model Monitor
    - `Model Performance` - CloudWatch metrics
    - `A/B Testing` - Traffic splitting
    - `Model Retraining` - Automated pipelines

#### AI Services Use Cases

`Computer Vision:`

```
Amazon Rekognition:
- Face detection and recognition
- Object and scene detection
- Content moderation
- Celebrity recognition
- Text in images (OCR)
```

`Natural Language Processing:`

```
Amazon Comprehend:
- Sentiment analysis
- Entity extraction
- Language detection
- Topic modeling
- Custom classification
```

`Speech Services:`

```
Amazon Transcribe + Polly:
- Call center analytics
- Voice assistants
- Accessibility features
- Content creation
```

#### Cost Optimization for ML

- `Training Optimization:`
  - Use `Spot Instances` for training (up to 90% savings)
  - `Managed Spot Training` in SageMaker
  - `Multi-model training` to share resources
  - `Distributed training` for large datasets

- `Inference Optimization:`
  - `Serverless Inference` for sporadic traffic
  - `Multi-model Endpoints` for similar models
  - `Auto Scaling` based on demand
  - `Batch Transform` for non-real-time predictions

- `Storage Optimization:`
  - Use `S3 Intelligent Tiering` for training data
  - `Compress datasets` before training
  - `Delete unused model artifacts`
  - `Use EFS for shared datasets`

#### Security Best Practices

- `Data Security:`
  - `Encrypt data` at rest and in transit
  - `VPC endpoints` for private connectivity
  - `IAM roles` for service access
  - `S3 bucket policies` for data access control

- `Model Security:`
  - `Model encryption` in SageMaker
  - `Network isolation` for training and inference
  - `Private Docker registries` for custom containers
  - `Audit logging` with CloudTrail

- `Compliance:`
  - `HIPAA compliance` for healthcare data
  - `GDPR compliance` for EU data
  - `SOC compliance` for enterprise requirements
  - `Data residency` controls

#### ML Monitoring and Troubleshooting

- `Key Metrics:`
  - `Training metrics` - Loss, accuracy, convergence
  - `Inference metrics` - Latency, throughput, errors
  - `Resource utilization` - CPU, GPU, memory
  - `Cost metrics` - Training and inference costs

- `Common Issues:`
  - `Overfitting` - Use regularization, cross-validation
  - `Slow training` - Optimize data loading, use distributed training
  - `High inference latency` - Model optimization, caching
  - `Data drift` - Implement monitoring and retraining

#### Real-World ML Examples

`E-commerce Recommendation:`

```
User Behavior → Kinesis → S3 → SageMaker Training → Personalize → Real-time Recommendations
```

`Fraud Detection:`

```
Transaction Data → Feature Engineering → SageMaker → Fraud Detector → Real-time Scoring
```

`Document Processing:`

```
Document Upload → S3 → Textract → Comprehend → Processed Results → Database
```

`Predictive Maintenance:`

```
IoT Sensors → Kinesis → SageMaker → Forecast → Maintenance Alerts → Dashboard
```

#### Getting Started with AWS ML

`For Beginners:`

1. Start with `AI Services` (Rekognition, Comprehend)
2. Use `SageMaker JumpStart` for pre-built solutions
3. Try `SageMaker Canvas` for no-code ML
4. Explore `SageMaker Studio` tutorials

`For Data Scientists:`

1. Use `SageMaker Notebooks` for experimentation
2. Leverage `built-in algorithms` for common use cases
3. Implement `SageMaker Pipelines` for MLOps
4. Use `SageMaker Experiments` for tracking

`For ML Engineers:`

1. Build `custom containers` for specific frameworks
2. Implement `multi-model endpoints` for efficiency
3. Set up `automated retraining` pipelines
4. Use `SageMaker Model Registry` for governance

### Load Balancer

A Load Balancer distributes incoming network or application traffic across multiple servers to ensure high availability, fault tolerance, and optimal resource utilization.

#### AWS Load Balancer Types

`Application Load Balancer (ALB) - Layer 7:`

- `HTTP/HTTPS traffic` routing
- `Content-based routing` (path, host, headers)
- `WebSocket and HTTP/2` support
- `SSL termination` and certificate management
- `Integration` with AWS WAF, Cognito
- `Target types`: EC2, IP addresses, Lambda functions

`Network Load Balancer (NLB) - Layer 4:`

- `TCP/UDP/TLS` traffic routing
- `Ultra-high performance` (millions of requests/second)
- `Static IP addresses` and Elastic IP support
- `Preserve source IP` addresses
- `Cross-zone load balancing` optional
- `Target types`: EC2, IP addresses, ALB

`Gateway Load Balancer (GWLB) - Layer 3:`

- `Third-party virtual appliances` (firewalls, IDS/IPS)
- `Transparent network gateway`
- `GENEVE protocol` on port 6081
- `Target types`: EC2 instances, IP addresses

`Classic Load Balancer (CLB) - Legacy:`

- `Layer 4 and 7` support
- `Basic load balancing` features
- `Being phased out` (use ALB/NLB instead)

#### Load Balancer Features

`Health Checks:`

- `Target health monitoring`
- `Configurable intervals` and thresholds
- `Custom health check paths`
- `Automatic failover` for unhealthy targets

`Routing Algorithms:`

- `Round Robin` (default for ALB)
- `Least Outstanding Requests` (ALB)
- `Flow Hash` (NLB)
- `Weighted routing` with target groups

#### Load Balancing Algorithms Deep Dive

`Application Load Balancer (ALB) Algorithms:`

1. `Round Robin (Default)`

   ```
   How it works:
   Request 1 → Server A
   Request 2 → Server B
   Request 3 → Server C
   Request 4 → Server A (cycle repeats)

   Pros:
   - Simple and fair distribution
   - Good for servers with similar capacity

   Cons:
   - Doesn't consider server load
   - May not be optimal for varying request complexity
   ```

2. `Least Outstanding Requests`

   ```
   How it works:
   - Routes to target with fewest active requests
   - Considers pending/processing requests
   - Dynamic load-aware routing

   Example:
   Server A: 5 active requests
   Server B: 3 active requests ← Next request goes here
   Server C: 7 active requests

   Pros:
   - Better performance under varying loads
   - Adapts to server processing speed

   Cons:
   - Slightly more complex
   - May cause request clustering
   ```

`Network Load Balancer (NLB) Algorithms:`

1. `Flow Hash Algorithm`

   ```
   Hash Components:
   - Source IP address
   - Source port
   - Destination IP address
   - Destination port
   - Protocol

   How it works:
   hash = hash(src_ip + src_port + dst_ip + dst_port + protocol)
   target = targets[hash % target_count]

   Benefits:
   - Consistent routing for same flow
   - Maintains connection affinity
   - Stateless load balancing
   ```

#### Algorithm Selection Guidelines

`Choose Round Robin when:`

- Servers have similar specifications
- Requests have similar processing complexity
- Simple, predictable load distribution needed

`Choose Least Outstanding Requests when:`

- Servers have different processing capabilities
- Request complexity varies significantly
- Need optimal performance under load

`Choose Flow Hash when:`

- Need connection persistence (NLB)
- Stateful applications requiring session affinity
- Gaming or real-time applications

#### Weighted Routing Implementation

`Target Group Weights:`

```yaml
Target Group A (Weight: 70):
  - 70% of traffic
  - Production servers

Target Group B (Weight: 30):
  - 30% of traffic
  - Canary deployment
```

#### Algorithm Performance Comparison

| Algorithm           | Latency  | Throughput | Complexity | Use Case       |
| ------------------- | -------- | ---------- | ---------- | -------------- |
| `Round Robin`       | Low      | High       | Simple     | Stateless apps |
| `Least Outstanding` | Medium   | Very High  | Medium     | Variable loads |
| `Flow Hash`         | Very Low | Very High  | Medium     | Stateful apps  |
| `Weighted`          | Low      | High       | Simple     | A/B testing    |

`SSL/TLS Support:`

- `SSL termination` at load balancer
- `End-to-end encryption` support
- `AWS Certificate Manager` integration
- `SNI (Server Name Indication)` support

#### Target Groups and Routing

`ALB Routing Rules:`

```yaml
Path-based routing:
  /api/* → API servers
  /images/* → Image servers
  /* → Web servers

Host-based routing:
  api.example.com → API target group
  www.example.com → Web target group

Header-based routing:
  User-Agent: Mobile → Mobile target group
  User-Agent: Desktop → Desktop target group
```

`Target Group Configuration:`

```yaml
Target Group Settings:
  Protocol: HTTP/HTTPS
  Port: 80/443
  Health Check Path: /health
  Health Check Interval: 30 seconds
  Healthy Threshold: 2
  Unhealthy Threshold: 5
  Timeout: 5 seconds
```

#### Load Balancer Architecture Patterns

`Pattern 1: Internet-facing ALB`

```
Internet → ALB (Public Subnets) → EC2 Instances (Private Subnets)
```

`Pattern 2: Internal Load Balancing`

```
Web Tier → Internal ALB → App Tier → Internal NLB → Database Tier
```

`Pattern 3: Multi-tier with NLB`

```
Internet → NLB → ALB → EC2 Instances
```

`Pattern 4: Cross-zone Load Balancing`

```
AZ-1: LB → Targets (25%)
AZ-2: LB → Targets (25%)
AZ-3: LB → Targets (50%)
```

#### Auto Scaling Integration

`Auto Scaling Group Configuration:`

```yaml
Auto Scaling Group:
  Min Size: 2
  Max Size: 10
  Desired Capacity: 4
  Target Group: web-servers-tg
  Health Check Type: ELB
  Health Check Grace Period: 300 seconds
```

`Scaling Policies:`

```yaml
Scale Out Policy:
  Metric: CPU Utilization > 70%
  Duration: 2 minutes
  Action: Add 2 instances

Scale In Policy:
  Metric: CPU Utilization < 30%
  Duration: 5 minutes
  Action: Remove 1 instance
```

#### Load Balancer Security

`Security Groups:`

```yaml
ALB Security Group:
  Inbound:
    - HTTP (80) from 0.0.0.0/0
    - HTTPS (443) from 0.0.0.0/0
  Outbound:
    - HTTP (80) to Target SG
    - HTTPS (443) to Target SG

Target Security Group:
  Inbound:
    - HTTP (80) from ALB SG
    - HTTPS (443) from ALB SG
  Outbound:
    - All traffic
```

`SSL/TLS Configuration:`

```yaml
SSL Policy: ELBSecurityPolicy-TLS-1-2-2017-01
Certificate: ACM Certificate ARN
Redirect: HTTP to HTTPS (301)
HSTS: Enabled
```

#### Monitoring and Logging

`CloudWatch Metrics:`

- `RequestCount` - Number of requests
- `TargetResponseTime` - Response time from targets
- `HTTPCode_Target_2XX_Count` - Successful responses
- `HTTPCode_ELB_5XX_Count` - Load balancer errors
- `HealthyHostCount` - Number of healthy targets
- `UnHealthyHostCount` - Number of unhealthy targets

`Access Logs:`

```yaml
Access Logs Configuration:
  S3 Bucket: my-alb-access-logs
  Prefix: alb-logs/
  Enabled: true

Log Format:
  timestamp elb client:port target:port request_processing_time
  target_processing_time response_processing_time elb_status_code
  target_status_code received_bytes sent_bytes request
```

`Connection Logs (NLB):`

```yaml
Connection Logs:
  S3 Bucket: my-nlb-connection-logs
  Fields: timestamp, client_ip, client_port, target_ip,
          target_port, connection_time, tls_handshake_time
```

#### Cost Optimization

`ALB Pricing:`

- `Fixed cost`: ~$16/month per ALB
- `Variable cost`: $0.008 per LCU-hour
- `LCU dimensions`: New connections, active connections, bandwidth, rule evaluations

`NLB Pricing:`

- `Fixed cost`: ~$16/month per NLB
- `Variable cost`: $0.006 per NLCU-hour
- `NLCU dimensions`: New connections, active connections, bandwidth

`Cost Optimization Tips:`

- `Consolidate` multiple applications on single ALB using path-based routing
- `Use NLB` for high-performance, low-latency requirements
- `Monitor LCU/NLCU` usage to optimize costs
- `Delete unused` load balancers

#### Troubleshooting Common Issues

`HTTP 502 Bad Gateway:`

- Check target health status
- Verify security group rules
- Check application response time
- Review target group configuration

`HTTP 503 Service Unavailable:`

- No healthy targets available
- Target group has no registered targets
- All targets failing health checks

`HTTP 504 Gateway Timeout:`

- Target response time exceeds timeout
- Increase idle timeout settings
- Optimize application performance

`Connection Timeouts:`

- Check NACLs and security groups
- Verify target group port configuration
- Check target application binding

#### Best Practices

`High Availability:`

- Deploy load balancers in `multiple AZs`
- Use `cross-zone load balancing` for even distribution
- Configure `health checks` appropriately
- Set up `CloudWatch alarms` for monitoring

`Security:`

- Use `HTTPS` with valid SSL certificates
- Implement `security groups` with least privilege
- Enable `access logging` for audit trails
- Use `AWS WAF` for application-layer protection

`Performance:`

- Choose appropriate `load balancer type` for use case
- Configure `connection draining` for graceful shutdowns
- Use `sticky sessions` only when necessary
- Monitor and optimize `target response times`

`Cost Management:`

- `Right-size` load balancer capacity
- Use `path-based routing` to consolidate
- `Monitor usage` metrics regularly
- `Clean up` unused resources

Load balancers with their sophisticated algorithms are essential for building resilient, scalable applications on AWS.

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
