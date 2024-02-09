[![LinkedIn][linkedin-shield-lapissoft]][linkedin-url-lapissoft]
[![Facebook-Page][facebook-shield-lapissoft]][facebook-url-lapissoft]
[![Youtube][youtube-shield-lapissoft]][youtube-url-lapissoft]

## Visit Us [Lapis Soft](http://www.lapissoft.com)

### AWS Certified DevOps Engineer Professional

This is designed for individuals who have experience working in a DevOps role and using AWS services. This certification validates your knowledge and skills in various areas related to implementing and managing continuous delivery systems and methodologies on the AWS platform. Key topics covered in the AWS Certified DevOps Engineer – Professional exam include:

- ***SDLC Automation:*** Implementing and managing continuous delivery systems and methodologies.
- ***Configuration Management and Infrastructure as Code (IaC):*** Implementing and managing the deployment pipeline, including infrastructure as code (IaC).
- ***Monitoring and Logging:*** Implementing monitoring and logging systems on AWS.
- ***Policies and Standards Automation:*** Implementing systems that are highly available, scalable, and self-healing on the AWS platform.
- ***Incident and Event Response:*** Designing, managing, and maintaining tools to automate operational processes.
To prepare for the exam, it's recommended to have hands-on experience with various AWS services and understand how to design, manage, and maintain tools for automating operational processes. Additionally, reviewing the official exam guide provided by AWS, along with relevant AWS documentation and whitepapers, can help you prepare effectively.

#### Cloud Computing
Cloud computing is the on-demand delivery of compute power, database, storage, applications, and other IT resources through a cloud services platform via the internet with pay-as-you-go pricing.

#### [Types of Cloud Computing Deployment Models](https://aws.amazon.com/types-of-cloud-computing/)
- [Private Cloud](https://aws.amazon.com/what-is/private-cloud/#:~:text=A%20private%20cloud%20is%20a,the%20control%20of%20one%20organization.)
  - This service used by a single organization, not exposed to public.
  - Complete self control
  - Secure for senserive applications.
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

#### The Five Characteristics of Cloud Computing
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

#### Problems solved by the Cloud
- Flexibility: change resource types when needed
- Cost-Effectiveness: pay as you go, for what you use
- Scalability: accommodate larger loads by making hardware stronger or adding additional nodes
- Elasticity: ability to scale out and scale-in when needed
- High-availability and fault-tolerance: build across data centers
- Agility: rapidly develop, test and launch software applications

#### [Types of Cloud Computing Model](https://aws.amazon.com/types-of-cloud-computing/)
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
![Cloud Computing Model](./img/cloud-computing-model.png)

#### Price of Cloud
AWS has 3 pricing fundamentals, following the pay-as-you-go pricing model
1. Compute: Pay for compute time
2. Storage: Pay for data stored in the Cloud
3. Data transfer out of the Cloud: Data transfer IN is free
Its the expensive issue then traditional IT

#### AWS Availability Zones
- Each region has many availability zones
  - Usually 3, Minimum 3, Maximum 6
  - Example: ap-southeast-2a, ap-southeast-2b, ap-southeast-2c
- Each availability zone (AZ) is one or more discrete data centers with redundant power, networking, and connectivity
- They’re separate from each other, so that they’re isolated from disasters
- They’re connected with high bandwidth, ultra-low latency networking

![Availability Zones](./img/availability-zones.png)

#### Visit of the AWS Console
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

#### [Shared Responsibility Model](https://aws.amazon.com/compliance/shared-responsibility-model/)
Security and Compliance is a shared responsibility between AWS and the customer. This shared model can help relieve the customer’s operational burden as AWS operates, manages and controls the components from the host operating system and virtualization layer down to the physical security of the facilities in which the service operates. The customer assumes responsibility and management of the guest operating system (including updates and security patches), other associated application software as well as the configuration of the AWS provided security group firewall. 
![shared-responsibility-model](./img/shared-responsibility-model.png)

###  [Identity & Access Management (IAM)](https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction.html)
AWS Identity and Access Management (IAM) is a web service that helps you securely control access to AWS resources. With IAM, you can centrally manage permissions that control which AWS resources users can access. Features of Identity and Access Management;
- It is global service
- Root account created by default, shouldn’t be used or shared
- Users are people within your organization, & can be grouped
- Groups only contain users, not other groups
- Users don’t have to belong to a group, and user can belong to multiple groups
- For an Example of group as follows
![iam-user](./img/iam-user.png)

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
      "Condition": {"Bool": {"aws:MultiFactorAuthPresent": "true"}} // conditions for when this policyis in effect  (optional)
    }
  ]
}

```
#### Create IAM user in Hands on Class.
- Go the IAM section & press 'Create User'.
- Give the user name (JakirIam) as you like.
- Select the user type
  - Sepecify a user in Identity Center (Recommended)
  - I want to create an IAM user (selected)
  - Give the password as you like
- Press Next
- Create user group including define the permissions.
- Give the tag name (optional)
- Download credential csv file
- IAM user created.
- Create Access keys (Access & Secret Access key)

#### AWS CLI Configuration
- Control multiple AWS services from this command line.
- How to [Install?](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html)
- Let's me check `aws --version`
- If its okay then we will see `aws-cli/2.15.4 Python/3.11.6 Darwin/23.2.0 exe/x86_64 prompt/off`
- Configuration using security credential
 - Go to AWS Management Console > Services > IAM
 - Select the IAM User Name: Your User Name [_**NB**_: You must use IAM's Information only not Root User]
 - Click on `Security credentials`
 - Click on `Create access key`
 - Copy Access ID & Secret access key
 - Go to your Terminal and implement as below format
 - `aws configure`
 - AWS Access Key ID [None]: Put your ID here and press Enter.
 - AWS Secret Access Key [None]: Put your secret key here and press Enter
 - Default region name [None]: us-east-1
 - Default output format [None]: json
- Let's me check whether the configuration is done.
 - `aws ec2 describe-vpcs`
 - If it is done then we will see the details of the default vpc.

#### Users access types
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
|                                          | Use IAM tools to apply appropriate permissions           |
|                                          | Analyze access patterns & review permissions             |

## Courtesy of Jakir

[![LinkedIn][linkedin-shield-jakir]][linkedin-url-jakir]
[![Facebook-Page][facebook-shield-jakir]][facebook-url-jakir]
[![Youtube][youtube-shield-jakir]][youtube-url-jakir]

### Have a good day, stay with me
<!-- Personal profile -->

[linkedin-shield-jakir]: https://img.shields.io/badge/linkedin-%230077B5.svg?style=for-the-badge&logo=linkedin&logoColor=white
[linkedin-url-jakir]: https://www.linkedin.com/in/jakir-ruet/
[facebook-shield-jakir]: https://img.shields.io/badge/Facebook-%231877F2.svg?style=for-the-badge&logo=Facebook&logoColor=white
[facebook-url-jakir]: https://www.facebook.com/jakir-ruet/
[youtube-shield-jakir]: https://img.shields.io/badge/YouTube-%23FF0000.svg?style=for-the-badge&logo=YouTube&logoColor=white
[youtube-url-jakir]: https://www.youtube.com/@mjakaria-ruet/featured

<!-- Company profile -->

[linkedin-shield-lapissoft]: https://img.shields.io/badge/linkedin-%230077B5.svg?style=for-the-badge&logo=linkedin&logoColor=white
[linkedin-url-lapissoft]: https://www.linkedin.com/company/lapis-soft/
[facebook-shield-lapissoft]: https://img.shields.io/badge/Facebook-%231877F2.svg?style=for-the-badge&logo=Facebook&logoColor=white
[facebook-url-lapissoft]: https://www.facebook.com/GoLapisSoft/
[youtube-shield-lapissoft]: https://img.shields.io/badge/YouTube-%23FF0000.svg?style=for-the-badge&logo=YouTube&logoColor=white
[youtube-url-lapissoft]: https://www.youtube.com/@LapisSoft/featured


