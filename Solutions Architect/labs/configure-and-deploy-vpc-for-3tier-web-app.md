# [Configuring and Deploying Amazon VPC for a 3-tier Web App](https://explore.skillbuilder.aws/learn/course/7675/configuring-and-deploying-amazon-vpc-for-a-3-tier-web-app;lp=1046)

Started: June 13th, 2024
Completed: June 13th, 2024

## Links
- [How Amazon VPC works](https://docs.aws.amazon.com/vpc/latest/userguide/how-it-works.html)
- [IPv4 Address Planner](https://www.site24x7.com/tools/ipv4-subnetcalculator.html)

#### Lab Overview
- This lab provides you with a overview of how to configure a VPC and deploy a 3-tier web application.
- VPC to allow for public and private subnets
  - Public subnet
    - contains web servers
    - accessible from the internet
  - Private subnet
    - contains application and database servers
    - not accessible from the internet

#### Lab Objectives
- Build a VPC
- Create public and private subnets
- Configure the internet gateway and NAT gateway

## Notes 
- When you create a VPC, you must specify an IPv4 CIDR block for the VPC
  - allowed block size is between a /16 netmask (65,536 IP addresses) and /28 netmask (16 IP addresses)
- the CIDR blocks of the subnets cannot overlap

- Lab details to learn from:
  - two public subnets for the Application Load Balancer in two different Availability Zones
  - two subnets for the EC2 instances in two different Availability Zones
  - two subnets for the RDS instances in two different Availability Zones

- Internet Gateway serves two purposes:
  - Provide a target in route tables to connect to the internet
  - Perform network address translation (NAT) for instances that have been assigned public IPv4 addresses

- Network Address Translation (NAT) gateway to enable instances in a private subnet to connect to the internet or other AWS services.
  - configure the route table of the private subnets to use the NAT gateway
  - use a NAT gateway, you must update the route table associated with one or more of your private subnets to point internet-bound traffic to the NAT gateway

- Route Tables
  - Each subnet in your VPC must be associated with a route table
  - A subnet’s route table must contain a route that directs internet-bound traffic to the internet gateway
    - This subnet is called a public subnet

- Security Groups
  - operates at the instance network interface level
  - firewall for instances