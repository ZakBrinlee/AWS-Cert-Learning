# [AWS Certified Solutions Architect - Associate (SAA-C03) Cert Prep: 1 Cloud Services Overview](https://www.linkedin.com/learning/aws-certified-solutions-architect-associate-saa-c03-cert-prep-1-cloud-services-overview)

Started: April 8, 2024
Completed: April 8, 2024

## Notes

### What I need to know:
- EFS - Elastic File System
  - $$ How it works within EC2 connections and how it is used

### Cloud Computing Overview
#### Cloud Computing Defined
- Examples
  - Dropbox
  - Google Drive
  - MSFT Azure
  - AWS
- Cloud computing is processing on the internet or a private network where the exact processing is done on a remote server rather than on a local server or personal computer.
#### Benefits of Cloud Computing
- Reduced
  - hardware costs
  - operational costs
  - deployment costs
- Increases
  - resiliency
  - performance
  - capacity
#### Cloud Computing Models
- All-in Cloud deployment
  - All services are in the cloud
    - database, processing, storage, app logic etc
- Hybrid deployment
  - Some services are in the cloud
    - processing, storage, app logic etc
  - Some services are on-premises
    - database, etc

- IaaS
  - entire infrastructure is in the cloud
  - platforms and sftwr runs on others infrastructure
- PaaS
  - apps are deployed on platforms
  - infrastructure is managed by others
  - (shogun frontend)
- SaaS
  - just a service that is consumed
  - email (gmail, hotmail)

#### History
- 2006 relaunch with AWS services
- 2008 Static ip for ec2
- 2009 Management console/VPC
- 2010 Route 53/SNS/IAM
- 2011 CloudFormation/Elasticache
- 2012 SWF/DynamoDB
- 2013 280+ features + AWS certifications launched
#### Platform
- Compute
- Storage
- Database (records of information)

### AWS Cloud Services
#### Part 1
- Compute
  - EC2
    - Primary focus of exam
  - Lambda
    - serverless function as code
  - Elastic Beanstalk
    - The way to launch an instance (automated by AWS)
  - Lightsail
  - Batch
- Storage
  - S3
    - Object storage
  - EFS
    - Elastic File System
    - $$ How it works within EC2 connections and how it is used
  - Glacier
    - Long term storage
    - archive
  - Storage Gateway
    - access storage in cloud locally or reversed
- Databases
  - RDS
    - Relational Database Service
  - DynamoDB
    - NoSQL
  - ElastiCache
    - Caching
    - fast retrieval
  - Neptune
    - Graph database
  - Redshift
    - Data warehousing
- Migration
  - AWS Migration Hub
  - Application Discovery Service
  - Database Migration Service
  - Server Migration Service
  - Snowball
    - Physical data transfer
- Network and Content Delivery
  - VPC
  - CloudFront
    - CDN
  - Route 53
    - DNS
  - API Gateway
    - API management
  - Direct Connect
    - Dedicated network connection
- Management Tools
  - CloudWatch
    - Monitoring
  - CloudFormation
    - Infrastructure as code
  - CloudTrail
    - Audit
  - Config
    - Compliance
  - Trusted Advisor
    - Best practices

#### Part 2
- Media Services
  - Kinesis
    - Data streaming
  - Elastic Transcoder
    - Media transcoding
- Machine Learning
  - SageMaker
    - ML as a service
  - Rekognition
    - Image and video analysis
  - Polly
    - Text to speech
- Analytics
  - Kinesis
    - analytics

- Security, Identity, & Compliance
  - IAM
    - Identity and Access Management
  - Cognito
    - User authentication
  - Inspector
    - Security assessment
  - AWS Organizations
    - Multi-account management
  - CloudHSM
    - Hardware security module
  - Directory Service
    - Active Directory
  - WAF & Shield
    - Web Application Firewall
    - DDoS protection

- AWS Cost Management
  - Cost Explorer
  - Budgets

- Mobile Services
  - Mobile Hub

- Application Integration
  - Simple Notification Service
  - Simple Queue Service

#### Part 3
- Overview of services 50+
#### Security and Compliance
- Shared Responsibility Model
  - AWS is responsible for security of the cloud
  - Customer is responsible for security in the cloud

#### Regions and Availability
- Regions
  - Geographical area
  - Multiple availability zones
- Availability Zones
  - Data centers (1-6)
  - Isolated from each other
  - Connected by high-speed network
