## Core Services Cheat Sheet:
### Compute
- EC2: Virtual Server
- Elastic Beanstalk: Automatically "grows" your application
- Elastic Load Balancing: Balances incoming traffic loads
- Lambda: Runs serverless code
- Lightsail: Pre-configured virtual servers
### Storage
- S3: Object storage
- Elastic Block Store: Block storage for EC2
- Snowball: Data migration tool (huge amount with physical device)
- Storage Gateway: Connects on-premises software appliance with cloud-based storage
### Database
- DynamoDb: NoSQL database
- RDS: Relational Database that supports six types of database engines
- Aurora: Relational Database running on TDS
- Redshift: Data warehouse for huge amounts of data
### Network and Content Delivery
- VPC: Virtual Private Cloud
- CloudFront: Caches content to edge locations to load faster
- Route 53: Routes domains to services and IP addresses
### Management Tools
- CloudFormation: Form resources with templates
- CloudTrail: Tracks "trails" of action (audit logs)
- CloudWatch: Watches for issues - and can automatically act on triggers


### Intro
- Technology Domain
  - 33% of the exam
  - Four parts
    - Define methods of deploying and operating in the AWS Cloud
    - Define the AWS global infrastructure
    - Identify the core AWS services
    - Identify resources for technology support

### Compute
- EC2 (Elastic Compute Cloud)
  - Virtual servers in the cloud on demand
- Elastic Beanstalk
  - Platform as a Service (PaaS)
  - Deploy and manage applications (load balancing, auto scaling, etc)
- Elastic Load Balancing
  - Distribute incoming application traffic across multiple targets
  - Fault tolerant
  - Monitor health of servers
- Lambda
  - Runs code in response to an event
  - runs and scales automatically
- Lightsail
  - Pre-configured and ready to use OS, web apps, and dev stacks
  - Simple and easy to use applications
- Deploying and operating in AWS
  - AWS Management Console
    - GUI
  - AWS Command Line Interface (CLI)
    - Command line
  - AWS Software Development Kit (SDK)
    - Libraries and tools for software developers
- AWS Global Infrastructure
  - Availability Zones (independent data centers)
    - Two or more availability zones make up a Region

### Storage
- S3
  - Amazon Simple Storage Service
    - Object storage, each file is an object
    - High availability, security and scalability
    - Store and retrieve any amount of data of any type of almost any size
- Elastic Block Store
  - Adds extra block storage to EC2 instances
  - Raw, unformatted block device attached
  - Use as file systems or hard drives
  - External hard drives for virtual servers
- Snowball
  - Data migration tool
  - Hardware solution to transfer data to AWS
- Storage Gateway
  - Connects on-premises software appliance with cloud-based storage
  - Hybrid cloud storage
  - Files Gateway
    - S3 files
  - Volume Gateway
    - Blocks like virtual hard drives
    - Stored and cached column modes
  - Tape Gateway
    - Uses existing tape based backup infrastructure to backup to virtual tapes
    - Virtual tape library
    - Archive for long term storage

### Database
- DynamoDb
  - NoSQL database
  - Automatically scaled by AWS
- RDS
  - Relation Database Service
  - Compatible with MySQL, PostgreSQL, Oracle, SQL Server, MariaDB
- Aurora
  - One of six relational databases supported by RDS
  - MySQL and PostgreSQL compatible
- Redshift
  - Fully managed petabyte-scale data warehouse
  - Analyze data using SQL and BI tools

### Network and Content Delivery
- VPC
  - Virtual Private Cloud
  - Flexible and secure allowing granular control over network
  - Subnets, route tables, security groups, and gateways are auto provisioned
- CloudFront
  - Content Delivery Network
  - Distribute content to end users with low latency, high data transfer speeds
  - Uses edge location to cache content for faster delivery of resources
  - Origin servers are the source of the files that the CDN will distribute (S3, EC2, etc)
  - Edge locations are the locations where content will be cached (data center, caching data, etc)
  - User requests are routed to the nearest edge location (web application/chrome/mobile device)
- Route 53
  - Domain Name System (DNS) web service
  - Domain Registration
  - Health check of web apps
  - Create websites/apps with high availability

### Management Tools
- CloudFormation
  - Templates used as recipes for AWS resource deployment
  - Infrastructure as code
- CloudTrail
  - Helps to track user activity and API usage
  - Log and monitor account activity
  - provide visibility into user and resource activity by recording AWS Management Console actions and API calls
  - actions from AWS console, SDKs or CLI
- CloudWatch
  - Monitoring and management system for AWS infrastructure
  - Get notification in real time on data, metrics and events.
  - Monitor AWS resources and applications to collect and track metrics
- CloudTrail vs CloudWatch
  - CloudTrail
    - Audit logs
    - Detective tools
  - CloudWatch
    - Monitors
    - Can react to events
    - analyze usage tools