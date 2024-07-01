# Prepare for the Solutions Architect Associate Exam

## [] [Specialized Courses]()
  - ### [] [AWS Well-Architected Labs](https://wellarchitectedlabs.com/)
  - ### [] [AWS Well-Architected Foundations](https://explore.skillbuilder.aws/learn/course/internal/view/elearning/108/aws-well-architected-badge)

## [X] [LinkedIn Learning Path - Prepare for the AWS Certified Solutions Architect](https://www.linkedin.com/learning/paths/prepare-for-the-aws-certified-solutions-architect-associate-saa-c03-certification)
  - ### [X] Cloud Services Overview
  - ### [X] Storage Design
  - ### [X] Virtual Private Cloud
  - ### [X] Compute Services
  - ### [X] Identity and Access Management
  - ### [X] Auto Scaling and Virtual Network Services
  - ### [X] Application Deployment
  - ### [X] Databases
  - ### [X] Services and Design Scenarios

## [] [AWS SkillBuilder Solutions Architect - Knowledge Badge Readiness Path - Courses](https://explore.skillbuilder.aws/learn/lp/1044/solutions-architect-knowledge-badge-readiness-path)
  - ### [X] AWS Technical Essentials
  - ### [X] Introduction to AWS Identity and Access Management (IAM)
  - ### [X] AWS Compute Services Overview
  - ### [X] Getting Started with AWS Storage
  - ### [X] Getting Started with Amazon Simple Storage Service (S3)
  - ### [X] Amazon Elastic Block Store (EBS) Primer
  - ### [X] AWS Database Offerings
  - ### [X] Amazon DynamoDB - Troubleshooting
  - ### [X] Amazon RDS Service Primer
  - ### [X] AWS Networking Basics
  - ### [X] Subnets, Gateways, and Route Tables Explained
  - ### [X] Configuring and Deploying VPCs with Multiple Subnets (includes Labs)
  - ### [X] Introduction to API Gateway
  - ### [X] AWS Network Connectivity Options
  - ### [X] Understanding AWS Networking Gateways
  - ### [X] Differences between Security Groups and NACLs
  - ### [X] AWS Network - Monitoring and Troubleshooting
  - ### [X] Getting Started with AWS CloudFormation
  - ### [X] AWS Well-Architected Considerations for Financial Services
  - ### [X] AWS Lambda Foundations
  - ### [X] Architecting Serverless Applications
  - ### [X] Scaling Serverless Architectures
  - ### [] Amazon Elastic Container Service (ECS) Primer
  - ### [X] Introduction to Database Migration
  - ### [] AWS Foundations: Cost Management
  - ### [] Amazon Simple Storage Service (S3) - Cost Optimization
  - ### [X] Deep Dive: Amazon Elastic Block Store (EBS) - Cost Optimization
  - ### [] AWS Storage Gateway Deep Dive: Volume Gateway
  - ### [] AWS Storage Gateway Deep Dive: Amazon S3 File Gateway
  - ### [X] Introduction to Step Functions
  - ### [] Migration Evaluator overview for Customers
  - ### [] AWS Backup Primer
  - ### [] Deep Dive with Security: AWS Identity and Access Management (IAM)
  - ### [] Securing and Protecting your Data in Amazon S3
  - ### [X] Protecting your Instance with Security Groups
  - ### [] Exam Prep Standard Course: AWS Certified Solutions Architect - Associate
  - ### [] Solutions Architect Knowledge Badge Assessment


## [] [AWS Skill Builder Solutions Architect - Knowledge Badge Readiness Path - Labs](https://explore.skillbuilder.aws/learn/lp/1044/solutions-architect-knowledge-badge-readiness-path)
  - ### [X] Introduction to AWS Identity and Access Management (IAM)
  - ### [X] Performing a Basic Audit of your AWS Environment
  - ### [X] Introduction to AWS Key Management Service (KMS)
  - ### [X] Introduction to Amazon S3
  - ### [X] Building your first Amazon Virtual Private Cloud (VPC)
  - ### [X] Introduction to Elastic Load Balancing
  - ### [] Comparing VPC Peering and Transit Gateway
  - ### [X] Configuring and Deploying Amazon VPC for a 3-tier Web App
  - ### [X] Launching and Managing a Web Application with CloudFormation
  - ### [X] Deploying your first AWS Lambda Container
  - ### [] UNDER MAINTENANCE - Lift and Shift an Application to Serverless on AWS
  - ### [X] Implementing Multi-Region Backup with Amazon S3 Cross-Region Replication
  - ### [] UNDER MAINTENANCE - Processing App Microservice Messages with Containers
  - ### [X] Auditing Your Security with AWS Trusted Advisor
  - ### [X] AWS Federated Authentication with AD FS
  - ### [X] Working with Amazon CloudFront for Dynamic Content Acceleration
  - ### [X] Update Security Groups Automatically Using AWS Lambda
  - ### [] Scale Your Security Vulnerability Testing with Amazon Inspector
  - ### [] Role Assumption Challenge
  - ### [] Filtering and blocking web incursions with AWS WAF
  - ### [] Using Data Encryption in AWS


## Top Notes
### Amazing links
- [Amazing Application Storage Decision Checklist](https://explore.skillbuilder.aws/learn/course/6233/play/19883/bringing-aws-storage-services-all-together;lp=1044)
- [Best Practices for Security, Identity, & Compliance](https://aws.amazon.com/architecture/security-identity-compliance/?cards-all.sort-by=item.additionalFields.sortDate&cards-all.sort-order=desc&awsf.content-type=*all&awsf.methodology=*all)


### What I need to know (direct from courses)
- EFS - Elastic File System
  - How it works within EC2 connections and how it is used
- ElastiCache -> know what it does, how to pick the right node type
- Understand the constraints of Developer Tools (languages?)
  - what they can do
  - when to use

- Application Deployment
  - Understand Kinesis Service and how it works to help manage data streams analytics in real-time
    - Kinesis Data Streams
    - Kinesis Firehose
    - Why would you use Kinesis Data Streams vs Firehose
      - why you want to narrow down data to just what is important to pass on
  - Understand the constraints of SNS
  - Understand what Simple Workflow Service is and how it works
    - when to use it
  - Understand CloudWatch

- Databases
  - Understanding Aurora, 
    - sizes, read replicas, etc.
  - Understand the following databases
    - DynamoDB
    - Redshift
    - Aurora
  - Understand the options available for RDS
    - what is available for free tier
    - how/when it is used
  - Understand where to manage a Database instance
    - RDS dashboard

- Auto-Scaling + Virtual network
  - Understand what is needed for Auto Scaling groups
    - how it can be setup / launched
    - permissions `ec2:runInstances`
  - Understand Elastic Load Balancing features/solutions
    - differences between Application vs Network load balancer
  - Understand what is running in the VPC and how to configure network rules
  - DNS routing policies
    - simple
      - same way it has always been performed, name to ip
    - weighted
      - split traffic based on weight
    - latency
      - based on lowest latency - fastest time
    - failover
      - primary and secondary
    - geolocation
      - based on location of requestor
    - multi-value answer
      - uses health checks to determine which to use

- VPCs
  - Understand the basics of 
    - VPCs
    - VPC peering
    - VPC security
    - NAT & NACL
  - Differences between Security Groups vs NACL
    - How are they used
    - where do they apply
    - what kind of rules do they used
    - how are they processed

- Storage Services
  - EBS Volume types
    - IOPS input/output
    - limits
    - usages
    - costs
    - size
  - S3 storage classes
    - costs
    - usages
    - retrieval times
    - limits 