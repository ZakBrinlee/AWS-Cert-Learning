# [AWS Cloud Quest: Cloud Practioner](https://explore.skillbuilder.aws/learn/course/11458/aws-cloud-quest-cloud-practitioner)
Started: March 17th, 2023
Started: March 18th, 2023

## Assignments
#### First estimate
https://calculator.aws/#/estimate?id=ffb1a100465ad697a6b6a9c23ae7f543de9a1f83

#### Connecting VPCs
- VPC
  - Requirements when creating a VPC
    - CIDR block (range of IP addresses)
    - Subnets
      - Can have only one NACL
      - 
    - Route tables
    - Internet Gateway (only for public subnets)
      - Allows communication between the VPC and the internet
      - IPv4 and IPv6
      - horizontally scaled, redundant, and highly available
      - NAT Gateway
        - Allows private subnets to access the internet
        - IPv4 only
      - Egress-only Internet Gateway
        - Allows IPv6 traffic from the VPC to the internet
        - Stateful
    - Security Groups
      - Instance level firewall
        - Default **deny** all **inbound** traffic
        - Default **allow** all **outbound** traffic
      - stateful
      - All rules are evaulated before deciding to allow traffic
      - Can be chained together to strickly control the access of traffic
    - Network ACLs
      -  Multiple subnets can share the same ACL
      -  Firewall of a subnet boundary
      - Default NACL 
        - Allows all traffic by default (inbound/outbound)
      - Custom NACL
        - Denies all traffic by default (inbound/outbound)
      - Stateless
      - Rules are evaluated in order
  - VPC Peering
    - Connects two VPCs
    - No transitive peering
    - No overlapping CIDR blocks
    - No transitive peering
    - No overlapping CID
    - Uses private IP addresses
    - Simple and cost effective way to share resources and communicate between VPCs
    - Runs on AWS Backbone, never on the public internet


#### Databases in Practice
- RDS Overview
  - Managed relational database service
  - Supports multiple database engines
    - MySQL
    - PostgreSQL
    - MariaDB
    - Oracle
    - SQL Server
    - Amazon Aurora
  - Read replicas
    - Increase performance with read only copies of the database
- Availability and Durability
  - Automated backups
  - Database snapshots are full copies of your db. only for restore use
  - Automatic failover with standby DB instances
- DB paramater groups acts as a container for the configuration of a dB


#### First NoSQL Database
- DynamoDB
  - Fully managed NoSQL database
  - Supports both document and key-value data models
  - Scales to handle any amount of traffic
  - Single-digit millisecond latency
  - Fully managed, multi-region, multi-master, durable database with built-in security, backup and restore, and in-memory caching for internet-scale applications
  - Flexible schema (data model)
  - DynamoDB Accelerator (DAX)
    - In-memory cache for DynamoDB
    - Improves read performance
    - Read 10x faster
  - Provisioned Capacity
    - Instantly scale up/down to previously reached capacity
  - On-Demand Capacity
    - Automatically scales up/down based on traffic
  - Encryption at rest
- Massive parrellel, high performance data processing
- Table Terms
  - Items
    - A collection of attributes
  - Attributes
    - A name-value pair
  - Primary Key
    - Unique identifier for each item in a table
- Scan Operation
  - Reads every item in a table
  - Very heavy and should be avoided
  - Eventually consistent reads
- Scan Features
  - Pagination
  - Parallel scans
    - splits a table into segments and uses multiple threads to scan the segments
- Queries
  - Find items based on primary key
  - optional sort key
  - sorted ascending by default
    - ScanIndexForward to false to reverse the order
- Queries Features
  - limit
  - filter expression
  - eventually consistent reads
  - Consistent reads by setting ConsistentRead to true


#### Security Concepts
- IAM
  - Identity and Access Management
  - Users
    - End users such as employees
  - Groups
    - A collection of users
  - Roles
    - A way to delegate permissions to entities that you trust
  - Policies
    - A document that defines permissions
  - MFA
    - Multi-Factor Authentication
    - Adds an extra layer of security
  - IAM Best Practices
    - Delete root access keys
    - Use groups to assign permissions
    - Use roles for applications running on EC2
    - Rotate security credentials regularly
    - Use policy conditions for extra security
    - Monitor activity in your AWS account
- AWS Security Responsibility
  - AWS Facilities
    - Physical security
    - Network security
    - Environmental security

#### File Systems in the Cloud
- EFS
  - Elastic File System
  - Fully managed file storage service
  - Supports the NFSv4 protocol
  - Support up to petabytes of data
  - Automatically scales
- Regional service
  - Can be accessed from multiple AZs
  - Can be accessed from on-premises
  - Can be accessed from other regions
- Broad spectrum of uses
- POSIX compliant shared file storage
- Fully managed service
- Pay for what you use
  - No minimum fee
- Lifecycle management
  - Automatically moves files to lower cost storage
- Features
  - Storage classes
    - Standard
    - Infrequent Access
      - lower cost for file not accessed daily
  - Lifecycle management
    - Automatically moves files to lower cost storage by setting rules
  - Performance modes
    - General Purpose
    - Max I/O
      - Ideal for highly parallelized workloads (thousands of EC2 instances)
  - Throughput modes
    - Bursting
    - Provisioned
      - Required higher dedicated
  - Encryption
    - At rest
    - In transit
    - Uses AWS KMS
  - AWS Backup 
    - Centralized backup service


#### Auto-Healing and Scaling Applications
- Amazon EBS
  - Performance for any workload
  - Media and entertainment
  - Financial services
  - Analytics
- Highly available and durable
  - 99.999% availability
  - Automatically replicated within an AZ
  - persisted data and backup snapshots
- Cost effective
  - Pay for what you use
  - No minimum fee
  - No upfront costs
- Auto Scaling
  - Automatically adjust capacity to maintain steady, predictable performance at the lowest possible cost
  - Ability to scale across multiple applications
  - Lifecycle hooks can trigger auto scaling actions

#### Highly Available Web Applications
- Minimizes service interruptions
- Enable resources to be available when they are needed
- Design for failure
- Embrace elasticity and automation
  - AWS CloudWatch
  - AutoScaling groups
- Loosely coupled components
- Become stateless
- Use parallelism
- Security as a forethought
- Elastic Load Balancing
  - Automatically scales to meet traffic demands
  - Across multiple AZs
  - Incoming traffic is directed by Listeners
  - Monitors the health of its registered targets and routes traffic only to the healthy targets
- Load Balancer Types
  - Application Load Balancer
    - Layer 7
    - Application level
    - HTTP, HTTPS, gRPC
    - Supports path-based routing
  - Network Load Balancer
    - Layer 4
    - TCP/UDP/TLS
    - High performance
    - Low latency
  - Gateway Load Balancer
    - Layer 3 Gateway
    - Layer 4 load balaner
    - IP
    - Analytics
  - Classic Load Balancer
    - Layer 4 and 7
    - Legacy
    - Basic routing
    - Application in classic EC2 network