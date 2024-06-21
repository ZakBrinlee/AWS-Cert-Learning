# [Building Your First Amazon Virtual Private Cloud](https://explore.skillbuilder.aws/learn/course/409/play/78205/building-your-first-amazon-virtual-private-cloud-vpc;lp=1046)

Started: June 21st, 2024
Completed: June 21st, 2024

#### Lab Overview
- in this lab, you create a basic Amazon Virtual Private Cloud (Amazon VPC) without using the VPC Wizard.

#### Lab Objectives
- Create an Amazon Virtual Private Cloud (VPC)
- Create a public and private subnets
- Create an Internet gateway
- Create a Route Table and add a route to the Internet
- Create a security group for your web server to only allow HTTP traffic to your web server
- Create a security group for your MySQL RDS instance to only allow MySQL traffic from your public subnet
- Deploy a web server and a MySQL RDS instance
- Configure your application to connect to your MySQL RDS instance

## Notes 
- Amazon Virtual Private Cloud (Amazon VPC) lets you provision a logically isolated section of the Amazon Web Services (AWS) cloud where you can launch AWS resources in a virtual network that you define
  - Complete control of
    - networking environment
    - IP address range
    - subnets
    - route tables
    - network gateways

- Subnet
  - a range of IP addresses in your VPC
  - private subnet for resources that should not be accessed from the internet
  - **Enable auto-assign public IPv4 address** provides a public IPv4 address for all instances launched into the selected subnet
  - Requires an Internet Gateway to connect to the internet

- Internet Gateway
  - a horizontally scaled, redundant, and highly available VPC component that allows communication between instances in your VPC and the internet
  - two purposes
    - provide a target in your VPC route tables for internet-routable traffic
    - perform network address translation (NAT) for instances that have been assigned public IPv4 addresses

- Route Table
  - a set of rules, called routes, that are used to determine where network traffic from your subnet or gateway is directed
  - controls the routing of a subnet

- Security Group
  - acts as a virtual firewall for your instance to control inbound and outbound traffic
  - limit of 5 security groups per instance/resource
  - SGID: sg-090b17da150833b78