#### 02 Domain - [Security and Compliance](https://aws.amazon.com/products/security/)
In AWS, **security** is a shared responsibility between AWS and the customer. To help customers fulfill their responsibilities, AWS provides **security services, documentation, and tools**.

**Overview**
- Identity and access management
- Detection and response
- Data protection
- Compliance
- Network and application protection

**Key Security Components in AWS**
- Identity and Access Management
  1. AWS Identity and Access Management (IAM) - Securely manage identities and access to AWS services and resources.
  2. AWS IAM Identity Center - Centrally manage workforce access to multiple AWS accounts and applications.
  3. Amazon Cognito - Implement secure, frictionless customer identity and access management that scales.
  4. Amazon Verified Permissions - Manage fine-grained permissions and authorization within custom applications.
  5. AWS Directory Service - Gain efficiency with a fully managed Microsoft Active Directory service.
  6. AWS Resource Access Manager - Simply and securely share your AWS resources across multiple accounts.
  7. AWS Organizations - Centrally manage your environment as you scale your AWS resources.

- Detection and Response
  1. Amazon GuardDuty - Protect AWS accounts with intelligent threat detection.
  2. Amazon Inspector - Automated and continual vulnerability management at scale.
  3. AWS Security Hub - Automate AWS security checks and centralize security alerts.
  4. Amazon Security Lake - Automatically centralize your security data in a few steps.
  5. Amazon Detective - Analyze and visualize security data to investigate potential security issues.
  6. AWS Security Incident Response - Prepare for, respond to, and recover from security events
  7. AWS Config - Assess, audit, and evaluate configurations of your resources.
  8. Amazon CloudWatch - Observe and monitor resources and applications on AWS, on premises, and on other clouds.
  9. AWS CloudTrail - Track user activity and API usage.
  10. AWS IoT Device Defender - Security management across your IoT devices and fleets.
  11. AWS Elastic Disaster Recovery - Scalable, cost-effective application recovery to AWS.

- Network and Application Protection
  1. AWS Firewall Manager - Centrally configure and manage firewall rules across your accounts.
  2. AWS Network Firewall - Deploy network firewall security across your VPCs.
  3. AWS Shield - Maximize application availability and responsiveness with managed DDoS protection.
  4. AWS Verified Access - Provide secure access to corporate applications without a VPN.
  5. AWS Web Application Firewall (WAF) - Protect your web applications from common exploits.
  6. Amazon Route 53 Resolver DNS Firewall - Filter and control outbound DNS traffic for your VPCs.

- Data Protection
  1. Amazon Macie - Discover and protect your sensitive data at scale.
  2. AWS Key Management Service (AWS KMS) - Create and control keys to encrypt or digitally sign your data.
  3. AWS CloudHSM - Manage single-tenant hardware security modules (HSMs) on AWS.
  4. AWS Certificate Manager - Provision and manage SSL/TLS certificates with AWS services and connected resources.
  5. AWS Payment Cryptography - Simplify cryptography operations in your cloud-hosted payment applications.
  6. AWS Private Certificate Authority - Create private certificates to identify resources and protect data.
  7. AWS Secrets Manager - Centrally manage the lifecycle of secrets.

- Compliance
  1. AWS Artifact - No cost, self-service portal for on-demand access to AWS’ compliance reports.
  2. AWS Audit Manager - Continually audit your AWS usage to simplify risk and compliance assessment.

##### [Shared Responsibility Model](https://aws.amazon.com/compliance/shared-responsibility-model/)
Security and Compliance is a shared responsibility between AWS and the customer. This shared model can help relieve the customer’s operational burden as AWS operates, manages and controls the components from the host operating system and virtualization layer down to the physical security of the facilities in which the service operates. The customer assumes responsibility and management of the guest operating system (including updates and security patches), other associated application software as well as the configuration of the AWS provided security group firewall. 
![shared-responsibility-model](/img/shared-responsibility-model.png)

###### AWS Responsibilities (Security of the Cloud)
AWS takes care of the infrastructure that runs all the services in the AWS Cloud:
- Physical security of data centers
- Hardware and networking
- Storage, compute, database infrastructure
- Hypervisor, AWS global network, and foundation services
- Patch management of the AWS-managed infrastructure

###### Customer Responsibilities (Security in the Cloud)
Customers are responsible for everything they put in the cloud:
- Securing your data
- Managing identity & access (IAM)
- Configuring security groups & firewall rules
- Application-level security
- Patching OS (on EC2, for example)
- Encryption of your data (if not managed by AWS)

###### Shared Responsibilities
Some responsibilities are shared, depending on the service and use case:
- AWS manages infrastructure-level encryption, but you manage application-level encryption.
- AWS offers compliance certifications, but you need to ensure your workloads follow them.

###### Here’s how customer responsibilities shift depending on the service
[Comparison](/img/security-share-responsibilty.png)

##### Compliance and Governance concepts
AWS compliance and governance concepts, benefits of cloud security, and how to handle logs related to cloud security:

###### AWS Compliance and Governance Concepts
- Shared Responsibility Model
  - AWS manages security of the cloud (hardware, software, networking).
  - Customers manage security in the cloud (data, access, applications).
- Compliance Programs
  - AWS supports a broad set of industry certifications (e.g., HIPAA, PCI-DSS, SOC 1/2/3, ISO 27001).
  - AWS Artifact provides on-demand access to compliance reports.
- Governance Tools
  - AWS Organizations – Manage and govern multiple AWS accounts.
  - Service Control Policies (SCPs) – Set permission guardrails.
  - AWS Config – Track resource configurations and compliance over time.
  - AWS Control Tower – Automates landing zone setup with built-in governance.

###### Benefits of Cloud Security (e.g., Encryption)
- Data Protection
  - Encryption at rest and in transit (via AWS KMS, TLS, etc.).
  - Automatic key rotation and policy enforcement.
- Scalability and Flexibility
  - Security tools scale with your infrastructure.
  - Integrates with services like Amazon GuardDuty and Amazon Inspector for threat detection.
- Identity and Access Management
  - AWS IAM for fine-grained access control.
  - MFA and role-based access enhance security posture.
- Continuous Monitoring
  - Real-time visibility with CloudWatch, CloudTrail, and AWS Security Hub.

###### Where to Capture and Locate Cloud Security Logs
- [AWS CloudTrail](https://docs.aws.amazon.com/cloudtrail/)
  It's a service that records and monitors actions taken in your AWS account, providing a history of API calls and user activity.
  - Logs all API calls and account activity across services.
  - Useful for auditing, compliance, and incident response.
  - Stored in S3, can be analyzed with Athena or CloudWatch Logs Insights.
- [Amazon CloudWatch](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/cloudwatch_architecture.html)
  It's a monitoring service for Amazon Web Services (AWS) cloud resources and applications. It collects data, including metrics, logs, and events, to provide a comprehensive view of resource utilization, application performance, and operational health, according to Amazon AWS. 
  - Monitors logs, metrics, and events.
  - Collects application logs, system logs, and custom logs.
  - Enables setting alarms and automated responses.
- [VPC Flow Logs](https://docs.aws.amazon.com/vpc/latest/userguide/flow-logs.html)
  Flow log data can be published to the following locations: Amazon CloudWatch Logs, Amazon S3, or Amazon Data Firehose.
  - Capture network traffic metadata.
  - Useful for diagnosing network issues or detecting suspicious activity.
- [AWS Config](https://docs.aws.amazon.com/controltower/latest/userguide/config.html)
  AWS Config provides a detailed view of the resources associated with your AWS account, including how they are configured, how they are related to one another, and how the configurations and their relationships have changed over time.
  - Logs changes to resource configurations.
  - Useful for compliance monitoring and audit trails.
- [Amazon GuardDuty](https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/guard-duty-rds-protection.html)
  Amazon GuardDuty uses AI and ML with integrated threat intelligence from AWS and leading third parties to help protect your AWS accounts, workloads, and data from threats.
  - Threat detection service that generates security findings from logs.
  - Pulls from VPC Flow Logs, CloudTrail, and DNS logs.

###  [Identity & Access Management (IAM)](https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction.html)
AWS Identity and Access Management (IAM) is a web service that helps you securely control access to AWS resources. With IAM, you can centrally manage permissions that control which AWS resources users can access. Features of Identity and Access Management;
- It is global service
- Root account created by default, shouldn’t be used or shared
- Users are people within your organization, & can be grouped
- Groups only contain users, not other groups
- Users don’t have to belong to a group, and user can belong to multiple groups
- For an Example of group as follows
![iam-user](/img/iam-user.png)

#### Why use group
- The policies define the permission to the users.
- Users or Groups can be assigned JSON documents called policies
- These policies define the permissions of the users
- In AWS you apply the least privilege principle: don’t give more permissions than a user needs
- [Policies Structure](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies.html)

#### [Policies Structure](https://docs.aws.amazon.com/IAM/latest/UserGuide/intro-structure.html)
***Principal:***
A principal is a human user or workload that can make a request for an action or operation on an AWS resource. After authentication, the principal can be granted either permanent or temporary credentials to make requests to AWS, depending on the principal type. IAM users and root user are granted permanent credentials, while roles are granted temporary credentials. As a best practice, we recommend that you require human users and workloads to access AWS resources using temporary credentials.
```JSON
{
  "Version": "2024-01-30",              // policy language version, always include
  "Id": "Account-Permission"            // an identifier for the policy (optional)
  "Statement": [                        // one/more individual statements (required)
    {
      "Sid": "FirstStatement",          // an identifier for the statement (optional)
      "Effect": "Allow",                // whether the statement allows/denies access (Allow, Deny)
      "Action": ["iam:ChangePassword"], // list of actions this policy allows/denies
      "Resource": "*"                   // list of resources to which the actions applied to
    },
    {
      "Sid": "SecondStatement",
      "Effect": "Allow",
      "Action": [
        "s3:List*",
        "s3:Get*"
      ],
      "Resource": [
        "arn:aws:s3:::confidential-data",
        "arn:aws:s3:::confidential-data/*"
      ],
      "Condition": {"Bool": {"aws:MultiFactorAuthPresent": "true"}} // conditions for when this policies in effect  (optional)
    }
  ]
}

```
#### Create IAM user in Hands on Class.
- Go the IAM section & press 'Create User'.
- Give the user name (JakirIam) as you like.
- Select the user type
  - Specify a user in Identity Center (Recommended)
  - I want to create an IAM user (selected)
  - Give the password as you like
- Press Next
- Create user group including define the permissions.
- Give the tag name (optional)
- Download credential csv file
- IAM user created.
- Create Access keys (Access & Secret Access key)

##### Users access types
To access AWS, you have three options:
 - AWS Management Console (protected by password + MFA)
   - Access Keys are generated through the AWS Console
 - AWS Command Line Interface (CLI): protected by access keys
   - Access Key ID ~= username
   - Secret Access Key ~= password
 - AWS Software Developer Kit (SDK)- for code: protected by access keys
   - Language-specific APIs (set of libraries)
   - Enables you to access and manage AWS services programmatically
   - Embedded within your application
   - Supported SDKs (JavaScript, Python, PHP, .NET, Ruby, Java, Go, Node.js, C++)
   - Mobile SDKs (Android, iOS, …)
   - IoT Device SDKs (Embedded C, Arduino, …)
   - Example: AWS CLI is built on AWS SDK for Python

#### IAM Roles for Services
Some AWS service will need to perform actions on your behalf
 - To do so, we will assign permissions to AWS services with IAM Roles
 - Common roles: 
 - EC2 Instance Roles
   - Lambda Function Roles
   - Roles for CloudFormation

#### IAM Security Tools
- IAM Credentials Report (account-level)
  A report that lists all your account's users and the status of their various credentials
- IAM Access Advisor (user-level)
  - Access advisor shows the service permissions granted to a user and when those services were last accessed.
  - You can use this information to revise your policies.

#### Shared Responsibility Model of IAM
| AWS (Provider)                           | User                                                     |
| :--------------------------------------- | :------------------------------------------------------- |
| Infrastructure (global network security) | Users, Groups, Roles, Policies management and monitoring |
| Configuration and vulnerability analysis | Enable MFA on all accounts                               |
| Compliance validation                    | Rotate all your keys often                               |
| -                                        | Use IAM tools to apply appropriate permissions           |
| -                                        | Analyze access patterns & review permissions             |

##### Security Groups (SG)
- Security Groups are the fundamental of network security in AWS. Its working like as firewall.
- They control how traffic is allowed into or out of our EC2 Instances. Inbound traffic
- Security groups only contain rules
- Security groups rules can reference by IP or by security group.

Illustration shown as follows;
![Security Group](/img/security-group.png)

**Security Groups Deeper Dive**
- Security groups are acting as a “firewall” on EC2 instances
- They regulate:
  - Access to Ports
  - Authorized IP ranges – IPv4 and IPv6
  - Control of inbound network (from other to the instance)
  - Control of outbound network (from the instance to other)

Illustration shown as follows;
![Security Group Details](/img/sg-details.png)

Security Group Diagram
Illustration shown as follows;
![Security Group Diagram](/img/sg-diagram.png)

**Security Groups Good to know**
- Can be attached to multiple instances
- Locked down to a region / VPC combination
- Does live “outside” the EC2 – if traffic is blocked the EC2 instance won’t see it
- It’s good to maintain one separate security group for SSH access
- If your application is not accessible (time out), then it’s a security group issue
- If your application gives a “connection refused“ error, then it’s an application error or it’s not launched
- All inbound traffic is blocked by default
- All outbound traffic is authorized by default

**SG Diagram Ref Other SG**
Illustration shown as follows;
![SG Diagram Ref Other SG](/img/sg-diagram-ref-other-sg.png)

**Some important Port**
|  SL   | Port | Protocol                      |
| :---: | :--- | :---------------------------- |
|   1   | 21   | FTP                           |
|   2   | 22   | SSH                           |
|   3   | 22   | SFTP                          |
|   4   | 80   | HTTP                          |
|   5   | 443  | HTTPS                         |
|   6   | 3389 | Remote Desktop Protocol (RDP) |

##### [Network Access Control List (ACL)](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-network-acls.html)
A network access control list (ACL) allows or denies specific inbound or outbound traffic at the subnet level. You can use the default network ACL for your VPC, or you can create a custom network ACL for your VPC with rules that are similar to the rules for your security groups in order to add an additional layer of security to your VPC.

##### [Web Application Firewall (WAF)](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/distribution-web-awswaf.html)
AWS WAF is a web application firewall that helps secure your web applications and APIs by blocking requests before they reach your servers. For more information, see Accelerate and protect your websites using CloudFront and AWS WAF and Guidelines for Implementing AWS WAF.

