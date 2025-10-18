### let’s design a practical, production-ready 3-tier web application architecture on AWS.

#### Three tier VPC consists of:

- A VPC spanning multiple Availability Zones.
- Two public subnets (Web Tier) across two AZs.
- Two private subnets (API Tier) across two AZs.
- Two private subnets (Database Tier) across two AZs.
- One public route table linking public subnets to the Internet Gateway.
- One private route table linking application subnets to a NAT Gateway for outbound access.

#### Step 01

- Select `VPC and more`
- VPC name `my-test-vpc`
- Name tag auto-generation `Auto-generate`
- IPv4 CIDR is `10.0.0.0/16`
- IPv6 CIDR block `No IPv6 CIDR block`
- Tenancy `Default`
- Number of Availability Zones (AZs) `2`
- Number of public subnets `2`
- Number of private subnets `4`
- NAT gateways ($) `None`
- VPC endpoints `None`
- DNS options
  - Enable DNS hostnames `Checked`
  - Enable DNS resolution `Checked`
- Tage > `name` > `my-test-vpc`
- Press `VPC Create`

#### Step 02

- Enable auto-assign IPv4 for both `public` subnets.
  - Go to VPC > Subnets > subnet-07e4f92321fd08768 > Edit subnet settings &
  - Check `Enable auto-assign public IPv4 address`
  - Press `Ok`
  - Go to VPC > Subnets > subnet-0ae30c066ff07db64 > Edit subnet settings &
  - Check `Enable auto-assign public IPv4 address`
  - Press `Ok`

#### Step 03

- Set main route table
