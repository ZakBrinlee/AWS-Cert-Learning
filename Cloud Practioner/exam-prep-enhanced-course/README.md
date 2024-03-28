# [Exam Prep Enhanced Course: AWS Certified Cloud Practitioner](https://explore.skillbuilder.aws/learn/course/16485/exam-prep-enhanced-course-aws-certified-cloud-practitioner-clf-c02-english)

Started: March 27rd, 2024

## Top Notes

## Labs
- Exercise 1: Exploring AWS Lambda and Amazon EventBridge
  - In this lab exercise, you will create an AWS Lambda function that will monitor an Amazon Elastic Compute Cloud (Amazon EC2) instance. You will then create an Amazon EventBridge rule that invokes the Lambda function when an EC2 instance is launched. Finally, you will launch an EC2 instance to confirm that your Lambda function is invoked when the instance state changes to running.

## Links
- []()

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
  - Fault Tolernace
    - means designing systems that can continue to operate in the event of a failure
    - Designing for ZERO downtime
  - Disater Recovery
    - Designing for systems to OPERATE THROUGH a disaster

- Scaling
  - Vertical Scaling
    - Increase the **size** of the instance
  - Horizontal Scaling
    - Increase the **number** of instances

#### Identify design principles of the AWS Cloud
- Design Priciples
  - Stop Guessing capacity
  - Test systems at production scale
  - Automate architecture
  - Allow for evolutionary changes
  - Use data to make changes
  - Improve through game days
  - Run test

- Architecture Framework Core Pillars
  - **Operational Excellence** (design priciples)
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
    - Environment impacts with energy consumption and effeciency
      - Understand your impact
      - Establish sustainability goals
      - Maximaize utilization
      - Anticipate and adopt new, more efficient hardware and software offerings
      - Use managed services
      - Reduce the downstream impact of your cloud workloads

#### Understand the benefits of the strategies for migration to the AWS Cloud
- AWS Cloud Adoption Framework
  - Identifies specific organizational capabilities for optimal cloud adoption
  - Can reduce the business risk through increase reliability and security

- Cloud Adoption Stragies
  - 7Rs to Cloud Migration
    - Retire
      - decommisioning or shutting down a system
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
- Undertstand
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
    - Unmanaged
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
  - AWS seperates services by the network zone they are in
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
- 
- 

#### Identify AWS database resources
- 
- 

#### Identify AWS network resources
- 
- 

#### Identify AWS storage resources
- 
- 

#### Identify AWS artificial intelligence and machine learning services and analytics services
- 
- 

#### Identify services from other in-scope AWS service categories
- 
- 

### Billing, Pricing, and Support

#### Introduction to Billing, Pricing, and Support
- 
- 

#### Compare AWS pricing models
- 
- 

#### Understand resources for billing, budget, and cost management
- 
- 

- 
#### Identify AWS technical resources and AWS Support options
- 