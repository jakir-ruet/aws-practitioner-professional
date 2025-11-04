## More About Me – [Take a Look!](http://www.mjakaria.me)

## Welcome to AWS Certified Solutions Architect - Associate **SAA-C03**

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
| 11111111 | 11111111 | 00000000 | 00000000 | **255.255.0.0**    |

> Network Block: The `1s` in the binary mask (/16) represent the network portion (first two octets).
> Host Block: The `0s` in the last two octets represent the host portion.
> Allowing for `2^16` = `65,536` addresses per /16, of which 65,534 are usable (exclude network IP (10.0.0.0) & broadcast IP (10.0.255.255)).

Given:

- x = number of 1’s in 2nd octet = 8
- y = number of 0’s in 2nd octet = 0
- z = Given mask /16 = 16
- k = Default mask = 8 (Class A)
- LOSM (Last Octet of Subnet Mask) = 2^7 + 2^6 + 2^5 + 2^4 + 2^3 + 2^2 + 2^1 + 2^0 = 128 + 64 + 32 + 16 + 8 + 4 + 2 + 1 = 255

**Answer**

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

##### Three-Tier Architecture on AWS for Web Applications

![Three-Tier Architecture on AWS for Web Applications](/img/vpc-design.jpg)

##### Understanding and Analysis

The foundational network architecture includes the following components:

- A `Virtual Private Cloud (VPC)` — the primary network environment for all application resources.
- Sunnets
  - Two (2) public subnets distributed across two Availability Zones, forming the Web Tier.
  - Two (2) private subnets distributed across two Availability Zones, forming the Application Tier.
  - Two (2) additional private subnets distributed across two Availability Zones, forming the Database Tier.
- Route Table
  - One (1) public route table that routes internet-bound traffic from the public subnets through an `Internet Gateway (IGW)`.
  - One (2) private route table that connects the Application Tier private subnets to a `NAT Gateway` for outbound internet access.
- Security Group (SG)
  - Public-SG
  - App-SG
  - Database-SG
- Internet Gateway (IGW)
- NAT Gateway
- Auto scaling group (ASG)
- Application load balancer (ALB)
- Bastion/Jump Server

### Handson VPC

#### Go to `VPC` > `Your VPCs` > `Create VPC`

- VPC settings `devops-vpc`
- IPv4 CIDR block > Check > `IPv4 CIDR manual input`
- IPv4 CIDR `10.0.0.0/16`
- IPv6 CIDR block > `No IPv6 CIDR block`
- Tenancy `Default`
- Tags > `devops-vpc`
- Press `Create VPC`

#### Go to `VPC` > `Subnets`

- Press `Create subnet`
- Select VPC ID `vpc-04cfb5cf7249c4f48 (devops-vpc)`
- Subnet 1 of 6 > Subnet name `webapp-subnet-1`
- Availability Zone > `United States (N. Virginia) / use1-az4 (us-east-1a)`
- IPv4 VPC CIDR block `10.0.0.0/16`
- IPv4 subnet CIDR block `10.0.5.0/24`
- Tag `webapp-subnet-1`

- Press `Create subnet`
- Select VPC ID `vpc-04cfb5cf7249c4f48 (devops-vpc)`
- Subnet 2 of 6 > Subnet name `webapp-subnet-2`
- Availability Zone > `United States (N. Virginia) / use1-az4 (us-east-1b)`
- IPv4 VPC CIDR block `10.0.0.0/16`
- IPv4 subnet CIDR block `10.0.6.0/24`
- Tag `webapp-subnet-2`

- Press `Create subnet`
- Select VPC ID `vpc-04cfb5cf7249c4f48 (devops-vpc)`
- Subnet 3 of 6 > Subnet name `app-subnet-1`
- Availability Zone > `United States (N. Virginia) / use1-az4 (us-east-1a)`
- IPv4 VPC CIDR block `10.0.0.0/16`
- IPv4 subnet CIDR block `10.0.10.0/24`
- Tag `app-subnet-1`

- Press `Create subnet`
- Select VPC ID `vpc-04cfb5cf7249c4f48 (devops-vpc)`
- Subnet 4 of 6 > Subnet name `app-subnet-2`
- Availability Zone > `United States (N. Virginia) / use1-az4 (us-east-1b)`
- IPv4 VPC CIDR block `10.0.0.0/16`
- IPv4 subnet CIDR block `10.0.11.0/24`
- Tag `app-subnet-2`

- Press `Create subnet`
- Select VPC ID `vpc-04cfb5cf7249c4f48 (devops-vpc)`
- Subnet 5 of 6 > Subnet name `db-subnet-1`
- Availability Zone > `United States (N. Virginia) / use1-az4 (us-east-1a)`
- IPv4 VPC CIDR block `10.0.0.0/16`
- IPv4 subnet CIDR block `10.0.15.0/24`
- Tag `db-subnet-1`

- Press `Create subnet`
- Select VPC ID `vpc-04cfb5cf7249c4f48 (devops-vpc)`
- Subnet 6 of 6 > Subnet name `db-subnet-2`
- Availability Zone > `United States (N. Virginia) / use1-az4 (us-east-1b)`
- IPv4 VPC CIDR block `10.0.0.0/16`
- IPv4 subnet CIDR block `10.0.16.0/24`
- Tag `db-subnet-2`

#### Internet Gateway

- Got to `VPC` > `Internet gateways` > `Create internet gateway`
- Name `devops-igw`
- Tags `devops-igw`
- Press `Create internet gateway`
- Select `devops-igw` & click `Action` Prees `Attach to VPC`
- Select Available VPCs `vpc-04cfb5cf7249c4f48 - devops-vpc`
- Press `Attach internet gateway`

#### NAT Gateway

- Got to `VPC` > `NAT gateways` > `Create NAT gateway`
- Name `app-ngw`
- Subnet `subnet-0df665df28e681436 (webapp-subnet-1)`
- Connectivity type `Public`
- Elastic IP allocation ID `Allocate Elastic IP`
- Tags `app-ngw`
- Press `Create NAT gateway`

- Got to `VPC` > `NAT gateways` > `Create NAT gateway`
- Name `db-ngw`
- Subnet `subnet-0df665df28e681436 (db-subnet-1)`
- Connectivity type `Private`
- Tags `db-ngw`
- Press `Create NAT gateway`

#### Route Table (Public-APP)

- Go to `VPC` > `Route tables` > `Create route table`
- Name `public-rt`
- VPC `vpc-04cfb5cf7249c4f48 (devops-vpc)`
- Tags `public-rt`
- Press `Create route table`

##### Public Route table configuration

- Go to `VPC` > `Route tables` > `rtb-0d37ac80cc784daa5 / public-rt`
- Select `Routes` tab and `Edit routes`
- Allow `internet gateway - igw-0798eae69dc8ed95d` for public from anywhere
- Press `Save Changes`
- Select `Subnet associations` add public subnets `webapp-subnet-1` and `webapp-subnet-2`
- Press `Save associations`

#### Route Table (Private-Webapp)

- Go to `VPC` > `Route tables` > `Create route table`
- Name `app-rt`
- VPC `vpc-04cfb5cf7249c4f48 (devops-vpc)`
- Tags `app-rt`
- Press `Create route table`

##### Private (App) Route table configuration

- Go to `VPC` > `Route tables` > `rtb-0091ff71c0f979014 / app-rt`
- Select `Routes` tab and `Edit routes`
- Allow `NAT gateway - nat-092fd7c853752f559` for Private from anywhere
- Press `Save Changes`
- Select `Subnet associations` add Private subnets `app-subnet-1` and `app-subnet-2`
- Press `Save associations`

#### Route Table (Private-db)

- Go to `VPC` > `Route tables` > `Create route table`
- Name `db-rt`
- VPC `vpc-04cfb5cf7249c4f48 (devops-vpc)`
- Tags `db-rt`
- Press `Create route table`

##### Private (App) Route table configuration

- Go to `VPC` > `Route tables` > `rtb-07a5d0434c9edbfe8 / db-rt`
- Select `Routes` tab and `Edit routes`
- Allow `NAT gateway - nat-0c192583c07f696ff` for Private from anywhere
- Press `Save Changes`
- Select `Subnet associations` add Private subnets `db-subnet-1` and `db-subnet-2`
- Press `Save associations`

#### Create public ec2 instance

- Name `public-ec2-1`
- Application and OS Images `Ubuntu`
- Instance type `t2.nano`
- Key pair (login) `public-kp`
- Network settings `vpc-04cfb5cf7249c4f48 (devops-vpc)`
- Subnet `subnet-0df665df28e681436 (webapp-subnet-1)`
- Auto-assign public IP `Enable`
- Firewall (security groups) `public-sg`
- Allow `SSH`, `HTTP` and `HTTPS`
- Press `Launch instance`

##### Try to login

```bash
chmod 400 "public-kp.pem"
ssh -i "public-kp.pem" ubuntu@98.88.75.48
```

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
