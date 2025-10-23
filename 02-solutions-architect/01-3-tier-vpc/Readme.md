### let’s design a practical, production-ready 3-tier web application architecture on AWS.

#### Three tier VPC consists of:

- A VPC spanning multiple Availability Zones.
- Three public subnets (Web Tier) across Three AZs.
- Three private subnets (API Tier) across Three AZs.
- Three private subnets (Database Tier) across Three AZs.
- One public route table linking public subnets to the Internet Gateway.
- Two private route table linking application subnets to a NAT Gateway for outbound access.

#### Step 01 - Create VPC

- Resources to create `VPC only`
- Name tag - optional `devops-vpc`
- IPv4 CIDR block `IPv4 CIDR manual input`
- IPv4 CIDR `10.0.0.0/16`
- IPv6 CIDR block `No IPv6 CIDR block`
- Tenancy `Default`
- Tags - Name `devops-vpc`

#### Step 02 Create Subnets

- VPC ID `vpc-0a9de09215a9475a6(devops-vpc)`
- Subnet name `public-web-subnet-1`
- Availability Zone `us-east-1`
- IPv4 VPC CIDR block `10.0.0.0/16`
- IPv4 subnet CIDR block `10.0.5.0/24`
- Tags - Name `public-web-subnet-1`

- VPC ID `vpc-0a9de09215a9475a6(devops-vpc)`
- Subnet name `public-web-subnet-2`
- Availability Zone `us-east-1`
- IPv4 VPC CIDR block `10.0.0.0/16`
- IPv4 subnet CIDR block `10.0.6.0/24`
- Tags - Name `public-web-subnet-2`

- VPC ID `vpc-0a9de09215a9475a6(devops-vpc)`
- Subnet name `public-web-subnet-3`
- Availability Zone `us-east-1`
- IPv4 VPC CIDR block `10.0.0.0/16`
- IPv4 subnet CIDR block `10.0.7.0/24`
- Tags - Name `public-web-subnet-3`

- VPC ID `vpc-0a9de09215a9475a6(devops-vpc)`
- Subnet name `private-app-subnet-1`
- Availability Zone `us-east-1`
- IPv4 VPC CIDR block `10.0.0.0/16`
- IPv4 subnet CIDR block `10.0.8.0/24`
- Tags - Name `private-app-subnet-1`

- VPC ID `vpc-0a9de09215a9475a6(devops-vpc)`
- Subnet name `private-app-subnet-2`
- Availability Zone `us-east-1`
- IPv4 VPC CIDR block `10.0.0.0/16`
- IPv4 subnet CIDR block `10.0.9.0/24`
- Tags - Name `private-app-subnet-2`

- VPC ID `vpc-0a9de09215a9475a6(devops-vpc)`
- Subnet name `private-app-subnet-3`
- Availability Zone `us-east-1`
- IPv4 VPC CIDR block `10.0.0.0/16`
- IPv4 subnet CIDR block `10.0.10.0/24`
- Tags - Name `private-app-subnet-3`

- VPC ID `vpc-0a9de09215a9475a6(devops-vpc)`
- Subnet name `private-db-subnet-1`
- Availability Zone `us-east-1`
- IPv4 VPC CIDR block `10.0.0.0/16`
- IPv4 subnet CIDR block `10.0.11.0/24`
- Tags - Name `private-db-subnet-1`

- VPC ID `vpc-0a9de09215a9475a6(devops-vpc)`
- Subnet name `private-db-subnet-2`
- Availability Zone `us-east-1`
- IPv4 VPC CIDR block `10.0.0.0/16`
- IPv4 subnet CIDR block `10.0.12.0/24`
- Tags - Name `private-db-subnet-2`

- VPC ID `vpc-0a9de09215a9475a6(devops-vpc)`
- Subnet name `private-db-subnet-3`
- Availability Zone `us-east-1`
- IPv4 VPC CIDR block `10.0.0.0/16`
- IPv4 subnet CIDR block `10.0.13.0/24`
- Tags - Name `private-db-subnet-3`

- Press `Create subnet`

#### Step 03 Create route tables

- Name - optional `devops-public-web-rt`
- VPC `vpc-0a9de09215a9475a6(devops-vpc)`
- Tags - Name `devops-public-web-rt`
- Press `Create route table`

- Name - optional `devops-private-app-rt`
- VPC `vpc-0a9de09215a9475a6(devops-vpc)`
- Tags - Name `devops-private-app-rt`
- Press `Create route table`

- Name - optional `devops-private-db-rt`
- VPC `vpc-0a9de09215a9475a6(devops-vpc)`
- Tags - Name `devops-private-db-rt`
- Press `Create route table`

#### Step 04 Update subnet associations

- Checked `devops-public-web-rt`
- Click `subnet associations` > `Edit subnet associations`
- Checked all `public-web-subnet`
  - `public-web-subnet-1`
  - `public-web-subnet-2`
  - `public-web-subnet-3`
- Press `Save associations`

- Checked `devops-private-app-rt`
- Click `subnet associations` > `Edit subnet associations`
- Checked all `private-app-subnet`
  - `private-app-subnet-1`
  - `private-app-subnet-2`
  - `private-app-subnet-3`
- Press `Save associations`

- Checked `devops-private-db-rt`
- Click `subnet associations` > `Edit subnet associations`
- Checked all `private-db-subnet`
  - `private-db-subnet-1`
  - `private-db-subnet-2`
  - `private-db-subnet-3`
- Press `Save associations`

#### Step 05 Internet gateway and NAT gatway

- Create Internet gateway gateway
  - Name tag `devops-igw`
  - Tags - Name `devops-igw`
  - Press `Create internet gateway`
- Attach to `vpc-0a9de09215a9475a6(devops-vpc)`

- Create NAT gateway
  - Name - optional`private-web-app-ngw`
  - Subnet `vpc-0a9de09215a9475a6(devops-vpc)`
  - Connectivity type `Public`
  - Elastic IP allocation ID `Allocate Elastic IP`
  - Tags - Name `private-web-app-ngw`
  - Press `Create NAT gateway`

- Create NAT gateway
  - Name - optional`private-web-db-ngw`
  - Subnet `vpc-0a9de09215a9475a6(devops-vpc)`
  - Connectivity type `Public`
  - Elastic IP allocation ID `Allocate Elastic IP`
  - Tags - Name `private-web-db-ngw`
  - Press `Create NAT gateway`

#### Step 06 Assign routes

- Select `devops-public-web-rt`
- Go `Routes` tab `Edit routes`
- Add `Add route`
  - `0.0.0.0/0`
  - Target `Internet Gateway` > `igw-0b803a2b52b42438d`
- Press `Save changes`

- Select `devops-private-app-rt`
- Go `Routes` tab `Edit routes`
- Add `Add route`
  - `0.0.0.0/0`
  - Target `NAT Gateway` > `nat-01bffffc1982f48ad`
- Press `Save changes`

- Select `devops-private-db-rt`
- Go `Routes` tab `Edit routes`
- Add `Add route`
  - `0.0.0.0/0`
  - Target `NAT Gateway` > `nat-0cf84d438db907517`
- Press `Save changes`

#### Step 06 Create ec2 instance

- Name `public-web-ec2-1`
- Application and OS Images `Ubuntu`
- Instance type `t.micro`
- Key pair (login) `public-web-ec2-kp`
- Network settings > `Edit`
  - VPC - required `vpc-0a9de09215a9475a6(devops-vpc)`
  - Subnet `subnet-03654b9c0ec01a4ce (public-web-subnet-1)`
  - Auto-assign public IP `Enable`
  - Firewall (security groups) `public-web-ec2-sg`
  - Description - required `public-web-ec2-sg created 2025-10-23T08:27:52.872Z`
- Press `Launch instance`

- Name `private-app-ec2-1`
- Application and OS Images `Ubuntu`
- Instance type `t.micro`
- Key pair (login) `private-app-ec2-kp`
- Network settings > `Edit`
  - VPC - required `vpc-0a9de09215a9475a6(devops-vpc)`
  - Subnet `subnet-06c3be3e88e9b4020 (private-app-subnet-1)`
  - Auto-assign public IP `Disable`
  - Firewall (security groups) `private-app-ec2-sg`
  - Description - required `private-app-ec2-sg created 2025-10-23T08:27:52.872Z`
- Press `Launch instance`

- Name `private-db-ec2-1`
- Application and OS Images `Ubuntu`
- Instance type `t.micro`
- Key pair (login) `private-db-ec2-kp`
- Network settings > `Edit`
  - VPC - required `vpc-0a9de09215a9475a6(devops-vpc)`
  - Subnet `subnet-0c0453dd21b54081b (private-db-subnet-1)`
  - Auto-assign public IP `Disable`
  - Firewall (security groups) `private-db-ec2-sg`
  - Description - required `private-db-ec2-sg created 2025-10-23T08:27:52.872Z`
- Press `Launch instance`

#### Step 07 Load Balancer

- Create Application Load Balancer
- Basic configuration > Load balancer name `devops-public.elb`
- Scheme `Internet-facing`
- Load balancer IP address type `IPv4`
- VPC `vpc-0a9de09215a9475a6(devops-vpc)`
- Availability Zones and subnets
  - us-east-1a (use1-az4)
    - Peak `subnet-03654b9c0ec01a4ce (public-web-subnet-1)`
  - us-east-1b (use1-az6)
    - Peak `subnet-a47c29de13f08b6df (public-web-subnet-2)`
  - us-east-1c (use1-az1)
    - Peak `subnet-59e02bcad7148f30a (public-web-subnet-3)`
- Create Security groups
- Name `public-elb-sg`
- Description `public-elb-sg`
- VPC `vpc-0a9de09215a9475a6(devops-vpc)`
- Listeners and routing `ListenerHTTP:80`
- Create Target Group `public-web-tg`
- Protocol `http, 80`
- IP address type `IPv4`
- VPC `vpc-0a9de09215a9475a6(devops-vpc)`
- Health checks `http`
- Register targets
  - `i-0df411294f9d38dab`
  - `i-0d4b2a78079cad33c`
  - `i-06cd11f90e3c024ca`
- Press `Create load balancer`
