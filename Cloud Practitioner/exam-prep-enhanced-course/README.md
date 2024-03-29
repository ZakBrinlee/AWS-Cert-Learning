# [Exam Prep Enhanced Course: AWS Certified Cloud Practitioner](https://explore.skillbuilder.aws/learn/course/16485/exam-prep-enhanced-course-aws-certified-cloud-practitioner-clf-c02-english)

Started: March 27rd, 2024
Completed: March 28th, 2024

## Labs
- Exercise 1: Exploring AWS Lambda and Amazon EventBridge
  - In this lab exercise, you will create an AWS Lambda function that will monitor an Amazon Elastic Compute Cloud (Amazon EC2) instance. You will then create an Amazon EventBridge rule that invokes the Lambda function when an EC2 instance is launched. Finally, you will launch an EC2 instance to confirm that your Lambda function is invoked when the instance state changes to running.

### Cloud Concepts
#### Define the benefits of the AWS Cloud
- Define the benefits of the AWS Cloud
- What is AWS??
  - On-demand self-service
    - No human intervention or interaction to receive and consume services
  - Access to the network
  - Resource pooling
    - Large amount of resources that are pooled together and served to multiple consumers
  - Elasticity
    - Ability to scale with demand (up/down)
  - Resource usage monitored and billed
    - All resources are monitored and billed (pay for what you use)

- Design Targets
  - High availability
    - means designing systems that are available and operational at all times
    - Designing for MINIMAL downtime
  - Fault Tolerance
    - means designing systems that can continue to operate in the event of a failure
    - Designing for ZERO downtime
  - Diaster Recovery
    - Designing for systems to OPERATE THROUGH a disaster

- Scaling
  - Vertical Scaling
    - Increase the **size** of the instance
  - Horizontal Scaling
    - Increase the **number** of instances

#### Identify design principles of the AWS Cloud
- Design Principles
  - Stop Guessing capacity
  - Test systems at production scale
  - Automate architecture
  - Allow for evolutionary changes
  - Use data to make changes
  - Improve through game days
  - Run test

- Architecture Framework Core Pillars
  - **Operational Excellence** (design principles)
    - Running and monitoring systems to deliver business value
      - Perform operations as code
      - Make frequent, small, reversible changes
      - Refine operations procedures frequently
      - Anticipate failure
      - Learn from all operational failures
  - **Security**
    - Protecting information, systems, and assets while delivering business value
      - Implement a strong identity foundation
      - Maintain traceability
      - Apply security at all layers
      - Automate security best practices
      - Protect data in transit and at rest
      - Keep people away from data
      - Prepare for security events
  - **Reliability**
    - Ensuring a system is able to perform it's intended function correctly and consistently
      - Test recovery procedures
      - Automatically recover from failure
      - Scale horizontally to increase aggregate system availability
      - Stop guessing capacity
      - Manage change in automation
  - **Performance Efficiency**
    - Using computing resources efficiently to meet system requirements and maintain that efficiency as demand changes
      - Democratize advanced technologies
      - Go global in minutes
      - Use serverless architecture
      - Experiment more often
      - Consider mechanical sympathy
  - **Cost Optimization**
    - Avoiding unnecessary costs
      - Adopt a consumption model
      - Measure overall efficiency
      - Stop spending money on data center operations
      - Analyze and attribute expenditure
      - Use managed services to reduce cost
      - Use reserved capacity
      - Use the right pricing model
  - **Sustainability**
    - Environment impacts with energy consumption and efficiency
      - Understand your impact
      - Establish sustainability goals
      - Maximize utilization
      - Anticipate and adopt new, more efficient hardware and software offerings
      - Use managed services
      - Reduce the downstream impact of your cloud workloads

#### Understand the benefits of the strategies for migration to the AWS Cloud
- AWS Cloud Adoption Framework
  - Identifies specific organizational capabilities for optimal cloud adoption
  - Can reduce the business risk through increase reliability and security

- Cloud Adoption Strategies
  - 7Rs to Cloud Migration
    - Retire
      - decommissioning or shutting down a system
    - Retain
      - Not ready to migrate
    - Rehost
      - Lift and shift no changes to code
    - Relocate
      - lift and shift with some changes
    - Repurchase
      - 
    - Replatform
      - lift -> tinker -> shift
    - Refactor or re-architect
      - apps to migrate and take advantage of cloud features with some refactoring

#### Understand the concepts of cloud economics
- Total Cost of Ownership (TCO)
  - Operational Costs
    - Costs that are incurred in the day-to-day operations of the business
  - Capital Expenses
    - Costs that are incurred in the acquisition of assets
  - Labor Costs
    - Costs that are incurred in the employment of staff
  - Software Licensing Costs
    - Costs that are incurred in the acquisition of software licenses

### Security and Compliance
#### Understand the Shared Responsibility Model
- AWS Responsibility
  - Hardware/AWS Global Infrastructure
    - Regions
    - Availability Zones
    - Edge Locations
  - Software
    - Compute
    - Storage
    - Database
    - Networking

- Customer Responsibility
  - Client-side data encryption & data integrity authentication
  - Server-side encryption (file system and/or data)
  - Networking traffic protection (encryption, integrity, identity)
  - Operating system, network, and firewall configuration
  - Platform, Application, Identity and Access Management (IAM)

#### Understand Cloud security, governance, and compliance concepts
- Understand
  - Compliance needs for locations and industries differ
  - AWS Compliance
  - AWS Artifact
    - Gives on-demand access to AWS compliance reports
  - Understand where to find compliance information
- Encryption data at rest
- Encryption data in transit
- Compliance needs for locations and industries differ
- Amazon CloudWatch
- AWS CloudTrail
- AWS Audit Manager

#### Identify AWS access management capabilities
- Understand
  - Why do you need to control user access?
  - How to control access to your account?
  - What is an AWS account

- Understand IAM
  - Users
  - Groups
  - Roles
  - Policies
    - Managed
      - 
    - Un-managed
      - 
  - Integration with AWS services

#### Identify components and resources for security
- Understand
  - Basical functionality & usage
    - NACL
    - WAF
- Security groups cannot explicitly deny traffic

- AWS Security services
  - AWS WAF
    - control traffic that block common attach patterns
  - AWS Trusted Advisor
  - Amazon Inspector
  - AWS MarketPlace
  - AWS Knowledge Center

### Cloud Technology and Services
#### Define methods of deploying and operating in the AWS Cloud
- Deployment and operating in AWS
  - Programmatic access
  - AWS CLI
  - AWS management console
  - Infrastructure as code
    - CloudFormation
    - Terraform

- Cloud Deployment Models
  - On-premises
  - Hybrid
  - Cloud

- AWS public and private services
  - AWS separates services by the network zone they are in
    - Public
      - These services are accessible from the public internet
    - Private
      - Services that are not accessible or connected to the public internet

- AWS network connectivity
  - AWS Direct Connect
    - DEDICATED connection
  - AWS VPN
  - Internet Gateway
    - horizontally scaled gateway for VPC and public internet
  - NAT Gateway
    - 

#### Define the AWS global infrastructure
- Globally resilient service
  - Regions can fail but a service will run
- What level of resilience a service has

- AWS Global Infrastructure
  - Regions
    - Geographical area
  - Availability Zones
    - Data centers
  - Edge Locations
    - CDN endpoints (cloud front)

- CloudFront vs Global Accelerator
  - CloudFront
    - Improves cache content
  - Global Accelerator
    - Improves performance for applications
    - HTTP uses cases for a static IP
    - Fast regional failover

- Models for cloud
  - IaaS
    - Infrastructure as a Service
  - PaaS
    - Platform as a Service
  - SaaS
    - Software as a Service
  - DaaS
    - Database as a Service


#### Identify AWS compute resources
- EC2
  - Virtualization as a service
  - Default aws compute service
  - Instances are isolated even when using a shared host
  - **Instance store**
    - temp storage for EC2 instances
- EBS
  - Elastic Block Store
  - Persistent storage
  - Can be attached to EC2 instances
  - AZ resilient

- Amazon Elastic Container Service (ECS)
  - One OS per system instead of Hypervisor
  - Container management service
  - Docker containers
  - ECS is a container orchestration service

- AWS Lambda
  - Function as a Service
  - Accepts functions
  - event driven
  - Serverless

#### Identify AWS database resources
- Amazon RDS
  - single AZ
  - DBaaS
  - managed service
  - Supports
    - MySQL
    - PostgreSQL
    - MariaDB
    - Oracle
    - SQL Server
  - Suggested to create a stand-by instance in another AZ
  - 

- Amazon Auroa
  - Shared storage cluster of instances
  - Primary and Read Replicas
- Auroa Serverless
  - No need to manage DB
  - Scales automatically
- Auroa Global DB
  - Multi-region
  - Global replication
    - occurs at the storage layer

- Amazon DynamoDB
  - Public service in the public network zone
  - Highly resilient across multiple AZs

- In memory DBs
  - AWS ElastiCache
    - Managed in-memory cache
    - Performance for reads
    - Redis and memcacheD
    - Store session states
    - **Redis**
  - AWS DynamoDB Accelerator (DAX)
    - In-memory cache for DynamoDB
    - Performance for reads
    - access in ms
    - eventually consistent reads

- Amazon Redshift
  - Data warehousing petabyte scale
  - Column-based
  - OLAP (great for transactions and query)
  - analytical query
  - Amazon S3

#### Identify AWS network resources
- Amazon VPC
  - Helps to control access to your AWS resources
  - Virtual private networks
  - Has a VPC router by default
  - Has an **Internet Gateway** by default
  - Subnets
    - Logical division of the VPC
    - Can be public or private
  - Two types of VPC
    - Default
      - comes with 1 default CIDR range
        - Classless Inter-Domain Routing (CIDR) is an IP address allocation method
    - Custom (configured by customer)

- Gateway Endpoints
  - targets specific IP routes in an Amazon VPC route table, in the form of a prefix-list, used for traffic destined to Amazon DynamoDB or Amazon Simple Storage Service (Amazon S3)
- Interface Endpoints
  - enable connectivity to services over AWS PrivateLink

- Amazon Route 53
  - DNS service
  - Register domains and host zones
  - Routing policies

#### Identify AWS storage resources
- Storage capabilities in a pay-as-you-go model
- AWS Storage options
  - **Object**
    - Amazon S3
      - Global resilient
      - Public service in the public zone
      - Unlimited amount of data storage
      - Object storage
      - Scalable
      - Durable
      - Secure
      - S3 Glacier
        - Long-term storage
        - Low cost
        - Retrieval time
      - S3 Glacier Deep Archive
        - Long-term storage
        - Lowest cost
        - Retrieval time
  - **File**
    - Amazon Elastic File System
      - Network based file storage
      - Great for repositories and directory style storage
      - **Linux** is a keyword for EFS
    - Lustre
      - High performance file system
      - Parallel file system
      - High performance computing
      - High level of distribution
  - **Block**
    - Amazon Elastic Block Store
      - Persistent storage
      - Can be attached to EC2 instances
      - AZ resilient
      - Network attached storage
  - AWS Storage Gateway
    - virtual appliance to run on-premises
    - connects to AWS storage services
    - 3 types
      - File Gateway
        - NFS and SMB
        - Stores objects in S3 with on-premise cache
      - Volume Gateway
        - block level access over network
        - stored volumes
      - Virtual Tape
        - Virtual tape library
        - Backup and archive into S3

- Storage backup and recovery
  - Amazon S3
    - storage classes
    - lifecycle management
  - AWS Backups
    - Centralized backup service
    - fully managed service

#### Identify AWS artificial intelligence and machine learning services and analytics services
- Data analytic services
  - Amazon Athena
    - interactive query service
    - SQL queries for S3
    - pay per query
  - Amazon Macie
    - AWS Security service
    - Discover, classify, and protect sensitive data stored in S3

- Amazon Redshift
  - Data warehousing petabyte scale
  - OLAP
- Amazon Kinesis
  - Real-time data streaming
  - Data analytics
  - Data processing 
- AWS Glue
  - Serverless data integration to discover, prepare, move and integrate data
  - prepare, move and find data across data sources
- Amazon QuickSight
  - Business intelligence service
  - Visualize data
- Amazon EMR
  - Service that helps to run big data frameworks to process and analyze large data sets

#### Identify services from other in-scope AWS service categories
- Monitoring Services
  - Amazon CloudWatch
    - Monitor AWS resources
    - Collect and track metrics
    - Set alarms
    - Automatically react to changes
 
- **Application Integration** services
  - Amazon EventBridge
  - Amazon Simple Notification Service (SNS)
    - pub/sub messaging
    - requires network connection
    - push notifications
  - Amazon Simple Queue Service (SQS)
    - provides full manage message queues
    - async way for applications to communicate
    - short and long polling
    - queue types
      - Standard (can be delivered more than once)
      - FIFO (First In First Out)
  - Amazon CloudWatch
  - Amazon EC2 Auto Scaling

- **Business Application** services
  - Amazon Connect
    - omnichannel cloud contact center
    - pay as you go
    - personalized experiences for customers
  - Amazon Simple Email Service (SES)
    - email service
    - send and receive email
    - email marketing
    - email notifications

- **Customer Engagement** services
  - AWS Activate
  - AWS IQ
  - AWS Managed Services
    - AWS service to manage your cloud resources
  - AWS Support

- **Developer** services
  - AWS AppConfig
  - AWS CodePipeline
  - AWS CodeCommit
  - AWS CodeArtifact
  - AWS CodeBuild
  - AWS CodeStar
  - AWS X-ray
  - AWS Cloud9
  - AWS Cloud Shell

- **End user computing** services
  - Amazon AppStream 2.0
  - Amazon Workspaces
  - Amazon Workspaces Web
    - fully managed linux browser-based desktop

- **Frontend web and mobile** services
  - AWS Amplify
    - build, ship and host full stack apps
  - AWS AppSync 
    - graphql service to combine resources

- **IoT** services
  - AWS IoT Core
    - connect devices to the cloud
    - secure communication
    - device management
  - AWS IoT Greengrass
    - local compute, messaging, and data caching

### Billing, Pricing, and Support
#### Compare AWS pricing models
- AWS Cost Optimization Services
  - AWS Cost Explorer
  - AWS Trusted Advisor
  - AWS Budgets
  - AWS Cost and Usage Report
  - Reserved Instance Reporting

- Achieving cost optimization
  - Right-sizing of resources
  - increasing elasticity
  - Choose the right pricing model
  - Match storage to usage
  - Data transfer options
  - measure, monitor and improve

- Cost optimization best practices
  - Define and enforce tags
  - Define your account structure
  - Define and use metrics
  - Share ownership
  - Create a Cloud Center of Excellence (CCoE)

#### Understand resources for billing, budget, and cost management
- AWS Cost Management Tools
  - AWS Cost Explorer
  - AWS Cost and Usage Report
    - break down costs very granularly
  - AWS Budgets
    - set custom budgets
    - track costs
    - receive alerts

- AWS Organizations benefits
  - Consolidated billing
- AWS Billing Conductor
  - Show charges and chargeback
  - Simplify billing and reporting with customizable pricing and cost visibility

#### Identify AWS technical resources and AWS Support options
- AWS Support Options
  - AWS Enterprise Support
  - AWS Developer Support
  - AWS Enterprise on-Ramp support
  - AWS Basic Support
  - AWS Business Support