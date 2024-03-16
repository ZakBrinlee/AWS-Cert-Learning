# [AWS Cloud Practitioner Essentials](https://explore.skillbuilder.aws/learn/course/external/view/elearning/134/aws-cloud-practitioner-essentials)

Started: March 16, 2023

## Top Notes
- Container: provide you with a standard way to package your application's code and dependencies into a single object.
Course coverage:
- Summarize the working definition of AWS
- Differentiate between on-premises, hybrid-cloud, and all-in cloud
- Describe the basic global infrastructure of the AWS Cloud
- Explain the six benefits of the AWS Cloud
- Describe and provide an example of the core AWS services, including compute, network, databases, and storage
- Identify an appropriate solution using AWS Cloud services with various use cases
- Describe the AWS Well-Architected Framework
- Explain the shared responsibility model
- Describe the core security services within the AWS Cloud
- Describe the basics of AWS Cloud migration
- Articulate the financial benefits of the AWS Cloud for an organization’s cost management
- Define the core billing, account management, and pricing models
- Explain how to use pricing tools to make cost-effective choices for AWS services


## Links
- [AWS Customer Compliance Center](https://aws.amazon.com/compliance/customer-center/)
- []()

### Introduction to Amazon Web Services
- Basic computing revolves around a client/server model
  - Client makes a request
  - Server processes the request and sends a response (w/wo the resource that was requested)
- Key concept of cloud computing is to only pay for what resources are used
  - On-demand services that are available 24/7 for as little or long as needed
- Definition: 
- **Cloud Computing** is the on-demand delivery of IT resources over the internet with pay-as-you-go pricing

### Compute in the Cloud
#### EC2 Intro
  - highly flexible, cost effective, and quick
  - Multitenancy: multiple customers share the same physical hardware (but are isolated from each other)
    - Hypervisor: software that runs virtual machines and manages the physical hardware
  - Configurations
    - OS (windows, linux)
    - Software (web server, database)
    - 3rd party software
  - Vertically scaling
    - Increase the size of the instance (more CPU, memory, storage)
  - Horizontally scaling
    - Increase the number of instances
#### EC2 Instance Types
  - When selecting an instance type, consider the specific needs of your workloads and applications. This might include requirements for compute, memory, or storage capabilities.
  - EC2 Instance families
    - **General Purpose**
      - Balanced resources
      - Diversity of workloads (web servers, dev environments, small databases)
    - **Compute Optimized**
      - Compute intensive workloads
      - High performance processors (Gaming servers, high performance computing, scientific modeling)
    - **Memory Optimized**
      - Memory intensive workloads
    - **Accelerated Computing**
      - Floating point number calculations
      - Graphics processing
      - Data pattern matching
      - Utilizes hardware accelerators
    - **Storage Optimized**
      - High performance for locally stored data
#### EC2 Pricing
- Purchase options
  - On-Demand
    - Pay for what you use by the time
  - Savings Plans
    - Commit to a consistent amount of usage (1 or 3 years)
  - Reserved
    - Steady workloads that require constant usage
    - Up front / partial up front / no up front
  - Spot
    - Bid on unused EC2 capacity
    - Can be terminated at any time (2 min warning if AWS takes it back)
  - Dedicated Hosts
    - Physical server with EC2 instance capacity fully dedicated to your use
#### Scaling EC2
- Adjusting the capacity of the EC2 instances automatically based on demand
- Scale up
  - Add more power to the instance that is being used
- Scale out
  - Increase the amount of instances being used

#### Directing Traffic w Elastic Load Balancing
- Acts as a host at a resturant to direct customers to the right server
- Load Balancer: distributes incoming application traffic across multiple targets, such as EC2 instances, in multiple availability zones
- Elastic Load Balancing
  - regional construct (runs at region level)
  - operates between aws services
  - single point of contact for all incoming web traffic
  
#### Messaging and Queuing
- Amazon Simple Queue Service (SQS)
  - Fully managed message queuing service
  - Decouples the components of a cloud application
  - Allows for asynchronous communication
  - Can be used to build a distributed system
- Amazon Simple Notification Service (SNS)
  - pub/sub model
  - Fully managed messaging service for both application-to-application and application-to-person communication
  - Can be used to build a distributed system
  - Can be used to send notifications to a large number of subscribers

#### Additional Compute Services
- Serverless : unable to see or access the underlying infrastructure
- AWS Lambda
  - Serverless computing
  - Run code without provisioning or managing servers
  - Pay only for the compute time consumed
  - Automatically scales
- Amazon Elastic Container Service (ECS)
  - Highly scalable, high performance container management service
  - Supports Docker containers
  - Can be used to build a distributed system
- Amazon Elastic Kubernetes Service (EKS)
  - Managed Kubernetes service
  - Can be used to build a distributed system

### Global Infrastructure and Reliability
#### Introduction to AWS Global Infrastructure
- High Availability and Fault Tolerance through distributed systems and regions
#### AWS Global Infrastructure
- Region
  - Physical location in the world
  - Consists of 2 or more availability zones
  - Connected to other regions through High Speed Fiber Optic Network
  - Each region is isolated from other regions and data will not leave the region w/o your permission
- 4 Business factors to choose a region
  - Compliance (legal and regulatory requirements)
  - Proximity (to end users)
  - Feature Availability (some regions offer more services/features than others)
  - Pricing
- Availability Zones
  - A single or group of AWS Data Centers
  - redundant data centers with independent power, cooling, and networking

#### Edge Locations
- Amazon CloudFront to store cached copies of your content closer to customer for faster delivery
- Route 53: DNS service that routes end users to the closest edge location
- AWS Outpost: fully managed service that extends AWS infrastructure, AWS services, APIs, and tools to virtually any datacenter, co-location space, or on-premises facility for a truly consistent hybrid experience
- Edge Locations
  - CDN (Content Delivery Network) endpoints for CloudFront
  - Used for caching content
  - Used for delivering content to end users with lower latency
  - Used for delivering content to end users with higher data transfer speeds

#### How to Provision AWS Resources
- AWS resources can be provisioned using AWS APIs
- API: Application Programming Interface
  - AWS Management Console
  - AWS Command Line Interface (CLI)
  - AWS Software Development Kits (SDKs)
- AWS Elastic Beanstalk
  - Deploys resources as necessary with code and configuration settings provided by you
    - Adjust capacity
    - Load balancing
    - Automatic scaling
    - Application health monitoring
- AWS CloudFormation
  - Infrastructor as code by building an enviroment from a template
  - Template is a JSON or YAML file that describes the resources you want to provision
  - Stack: collection of resources that are created and managed as a single unit

### Networking
#### Connectivity to AWS
- Subnets
  - A subnet is a section of a VPC in which you can group resources based on security or operational needs. Subnets can be public or private.
- Network Access Control Lists (NACLs)
  - Stateless
  - Allow or deny traffic based on rules
- VPC must have an Internet Gateway to allow access
- AWS Direct Connect
  - Dedicated network connection from your on-premises network to AWS

#### Subnets and Network Access Control Lists
- Network Harding
  - Subnets are used to control access to resources
  - Allows control of traffic flow
- Network Access Controls Lists
  - Tells the network which traffic is allowed and which is denied at the SUBNET level
  - Checked on the way in and the way out
  - Just detects the access to the subnet, not the resources within the subnet
- Security Groups are used to control access to resources
  - Can be used to control traffic flow by the type of traffic (HTTP, OS requests, etc)
  - Think of it as the doorman to the security group resources
  - Stateful and keeps track of who can/cannot access

#### Global Networking
- Route 53
  - Domain Name Service (DNS) website names to IP addresses
  - Routes end users to the closest edge location
- AWS CloudFront
  - Content Delivery Network (CDN) that caches content closer to the end user

### Storage and Databases
#### Instance Stores & Amazon Elastic Block Store
- Instance Store
  - Temporary storage
  - Data is lost when the instance is stopped or terminated
  - Good for temporary storage
- Amazon Elastic Block Store (EBS) virtual hardrives
  - Persistent storage
  - Data is not lost when the instance is stopped or terminated
  - Good for long term storage
  - Can be attached to an EC2 instance
  - Can be detached and reattached to another EC2 instance
  - Can be used to create snapshots of the data
  - Can be used to create volumes from snapshots
#### Amazon S3
- Object storage
  - Consists of data, metadata, and a key
- S3 Buckets
  - A container for objects
  - Data is stored across 3 buckets for redundency
- S3 storage classes
  - Two factors when determining
    - How often you plan to retrieve your data
    - How available you need your data to be
  - Standard
    - 99.999999999% durability
  - Standard Infrequent Access
    - Lower cost but slower access
  - Glacier Flexible Retrieval
    - Lower cost but slower access
    - Retrieval times can be minutes to hours
    - vault/lock policy
- S3 Lifecycle policies
  - Automate moving objects between storage classes
- Comparing EBS and S3
  - EBS
    - HDD options
    - solidate state
    - survives EC2 termination
    - Block storage
    - 
  - S3
    - Unlimited storage
    - Object storage
    - write once, ready many
    - Web Enabled
    - Regionally distributed
    - Serverless

#### Amazon Elastic File System
- Muliple instances of EC2 can access the same file system
- Linux file system
- Regional resource
- Automatically scales

#### Amazon Relational Database Service
- RDMS (Relational Database Management System)
  - Works to store, manage and handle connection between databases
- Lift and Shift migration options
  - Migrate your database to AWS without changing the code
- Amazon RDs
  - Automated patching
  - backups
  - etc
- Amazon Aurora
  - MySQL and PostgreSQL compatible
  - 5x faster than standard MySQL
  - 3x faster than standard PostgreSQL
  - 1/10th the cost of commercial databases

#### Amazon DynamoDB
- Serverless Database
- Store and query data in tables
- Auto scaling, replication, and backup
- NoSQL database, non-relational database
- Compare DynamoDB to Amazon RDS
  - RDS
    - Auto high-availability w/recovery provided
    - Customer ownership of data
    - Customer ownership of schema
    - customer control of network
  - DynamoDB
    - key-value pair with no schema
    - Massive throughput capabilities
    - PB size potential
    - Granular API access

#### Amazon Redshift
- Data warehouse service 
- Popular for big data analytics. 
- Ability to collect data form many sources
- Data is set and will not be changed, only more added

#### Amazon Database Migration Service
- Ability to migrate any database to AWS
- Source DB remains operational during migration
- Hetrogenous migrations
  - Schema, Data types and code is different between source and destination
  - 2 step process
    - Use the AWS Schema conversion tool
    - Use DMS to migrate the data
- Ability to use to copy DB for testing/development
- Continous replication of data is another use

#### Additional Database Services
- AWS DocumentDB: Document database service that supports MongoDb
- AWS Neptune: Graph database service (recommendations, fraud detection, social networking)
- AWS Quantum Ledger Database: Fully managed ledger database that provides a transparent, immutable, and cryptographically verifiable transaction log
- AWS Managed Blockchain: service that you can use to create and manage blockchain networks with open-source frameworks.
- AWS ElastiCache: adds caching layers on top of your databases to help improve the read times of common requests.
- DynamoDB Accelerator: In-memory cache for DynamoDB

### Security
#### AWS Shared Responsibility Model
- Customer Responsibility
  - Security in the cloud
  - Everything the customer creates and puts in the cloud
- AWS Responsibility
  - Security of the cloud
  - Operates, manages, anc controls the components at all layers of infrastructure of services
  - Physical security of data centers
  - Hardware and software infrastructure
  - Network infrastructure
  - Virtualization infrastructure

#### User Permissions and Access
- IAM (Identity and Access Management)
  - Centralized control of your AWS account access to services and resources
  - Root user has full access to all resources
  - Principle of Least privilege
    - Only give the permissions that are needed
  - IAM user
    - An entity that you create in AWS to represent the person or application that uses it
  - IAM Policy
    - document that allows or denies permissions to AWS services and resources
    - Typical policy config
    - ```json
      {
        "Version": "2012-10-17",
        "Statement": [
          {
            "Effect": "Allow", // Allow || Deny
            "Action": "s3:ListBucket", // any AWS API Call
            "Resource": "arn:aws:s3:::my_bucket/*" // The resource the API call is for
          }
        ]
      }
      ```
    - IAM Group
      - A collection of IAM users
      - Policies can be attached to groups
    - IAM Roles
      - an identity that you can assume to gain temporary access to permissions.

#### AWS Organizations
- Centralized management of multiple AWS accounts
- AWS automatically creates a root, which is the parent container for all the accounts in the organization
  - Consolidated Billing w/bulk discounts
  - Hierarchical structure of accounts
  - Service Control Policies (SCPs)
    - AWS service and api actions access control
    - Can be applied to individual member account or OU
- Organizational Units is a group of accounts
  - Legal, Finance, HR, IT, etc type of separation of accounts to create these groups

#### Compliance
- Tools to help you meet compliance requirements within your cloud resources
- AWS Artifact
  - Provides on-demand access to AWS compliance reports and online agreements
- Customer Compliance Center
  - you can read customer compliance stories to discover how companies in regulated industries have solved various compliance, governance, and audit challenges.

#### Denial-of-Service Attacks
- DDoS (Distributed Denial of Service)
  - Attack that attempts to make an online service unavailable by overwhelming it with traffic from multiple sources
- Security Groups
  - Operates at the AWS network level
  - Malicious attempts would never reach your EC2
- Elastic Load Balancer
  - Has built in DDoS protection
- AWS Shield
  - Managed DDoS protection service
  - Protects against DDoS attacks
  - **Standard and Advanced Editions**
    - Standard: Protects against most common DDoS attacks and is automatically enabled for all AWS customers at no additional charge
    - Advanced: Protects against more sophisticated DDoS attacks, provides enhanced protections for your applications running on Elastic Load Balancing, Amazon CloudFront, and Amazon Route 53, and is available as an optional paid service
- AWS WAF (Web Application Firewall)
  - Protects web applications from common web exploits
  - Protects against SQL injection, cross-site scripting, and more
  - ML capabilities to detect and block bad traffic
- Well architected system is already protected by AWS

#### Additional Security Services
- AWS Key Management Service (KMS)
  - Managed service that makes it easy for you to create and control the encryption keys used to encrypt your data
- Amazon Inspector
  - Automated security assessment service to help improve the security and compliance of applications deployed on AWS
  - 3 parts
    - Network configuration reachability piece
    - Agent: installed on EC2
    - Security assessment service
- Amazon GuardDuty
  - Threat detection service that continuously monitors for malicious activity and unauthorized behavior to protect your AWS accounts and workloads
  - Indepentent of the resources

### Monitoring and Analytics

### Pricing and Support

### Migration and Innovation

### The Cloud Journey

### AWS Certified Cloud Practitioner Basics