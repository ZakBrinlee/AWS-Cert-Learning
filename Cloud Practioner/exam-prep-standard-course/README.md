# [Exam Prep Standard Course: AWS Certified Cloud Practioner](https://explore.skillbuilder.aws/learn/course/16434/exam-prep-standard-course-aws-certified-cloud-practitioner-clf-c02-english)
Started: March 19, 2023
Completed: 

## Top Notes
- 

## Links
- [AWS Well-Architected Framework Whitepaper](https://docs.aws.amazon.com/wellarchitected/latest/framework/welcome.html)
- [Overview of Amazon Web Services Whitepaper](https://docs.aws.amazon.com/whitepapers/latest/aws-overview/introduction.html)
- [High availability and scalability on AWS](https://docs.aws.amazon.com/whitepapers/latest/real-time-communication-on-aws/high-availability-and-scalability-on-aws.html)
- [Migration and transfer](https://docs.aws.amazon.com/whitepapers/latest/aws-overview/migration-services.html)
- [IAM Identities (users, user groups, and roles)](https://docs.aws.amazon.com/IAM/latest/UserGuide/id.html)
- [What is IAM Identity Center?](https://docs.aws.amazon.com/singlesignon/latest/userguide/what-is.html)
- [What is IAM?](https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction.html)
- []()

## Notes
#### Intro Video
  - Prepare for the AWS Certified Cloud Practitioner exam steps
    - 1. Get to know the exam
      - Domain 1: Cloud Concepts
        - Knowing and understanding AWS services
        - Understanding the AWS global infrastructure and benefits of cloud computing
      - Domain 2: Security and Compliance
      - Domain 3: Cloud Technology and Services
      - Domain 4: Billing, Pricing, and Support
    - 2. Get to know the exam style questions
      - Official question set
    - 3. Learn about exam topics (Module 3)
    - 4. Review everything tested on the exam
      - Each domain
      - Exam style questions at end of each domain
    - Enhanced version 
      - Bonus questions at the end of each section
      - Hands on labs
    - 5. Determine your readiness
      - Practice exam
    - 6. Register for exam
    - 7. Take the exam


### Domain 1: Cloud Concepts
#### 1.1 Define the benefits of the AWS cloud
- What AWS is:
  - What is coud computing?
    - On demand self-service
    - access to the internet
    - resource pooling
    - rapid elasticity
    - resourece usage monitored and billed
- High availability
  - Means designing systems to be available 24/7, minimal downtime
  - System to response to failures
  - Reduce outages and stay online
- Fault tolerance
  - Means designing for zero downtime
  - System can continue to operate even if a component fails
  - Minimize and operate through failures
- Distaster recovery
  - Means designing for operating through a disater
  - System can recover from a disaster
  - Minimize downtime and data loss
- Elasticicity
  - Means designing for scalability
  - System can scale up and down based on demand
  - using automation to scale on demand with auto scaling
  - Minimize costs and maximize performance
    - Vertical scaling
      - Increase the size of the instance (t2.micro -> t2.medium -> t2.large)
    - Horizontal scaling
      - Increase the number of instances (t2.micro -> t2.micro 6x)

#### 1.2 Identify design priciples of AWS cloud
- AWS Well-Architected Framework
  - Design principles
    - Stop guessing your capacity needs
    - Test systems at production scale
    - Automate architecture
    - Allow for evolutionary changes
    - Use data to make changes
    - Improve through game days
    - Run test
  - 6 Pillars
    - Operational Excellence
      - Perform operations as code
      - Make frequent, small, resersible changes
      - Refine operations procedures frequently
      - Anticipate failure
      - Learn from all operational failures
    - Security
      - Implement a strong identity foundation
      - Maintain traceability
      - Apply security at all layers
      - Automate security best practices
      - Protect data in transit and at rest
      - Keep people away from data
      - Prepare for security events
    - Reliability
      - Test recovery procedures
      - Automatically recover from failure
      - Scale horizontally to increase aggregate workload availability
      - Stop guessing capacity
      - Manage change in automation
    - Performance Effency
      - Democratize advanced technologies
      - Go global in minutes
      - Use serverless architectures
      - Experiment more often
      - Consider Mechanical sympathy
    - Cost Optimization
      - Ability to run systems to deliver business value at the lowest price
    - Sustainability
      - Understand your impact
      - Establish sustainability goals
      - Maximize utilization
      - Anticipate and adopt new, more efficient hardware and software offerings
      - Use managed services
      - Reduce the downstream impact of your cloud workloads

#### 1.3 Understand the benefits and steategies for migration to the AWS Cloud
- AWS Cloud Adoption Framework
  - Grouped into 6 perspectives
    - Business
    - People
    - Governance
    - Platform
    - Security
    - Operations
  - Adoption Strategies
    - Project stage
      - Evaluate the business case for cloud adoption (does AWS meet buisness needs)
    - Foundation stage
      - Migration to AWS begins
    - Migration stage
      - Migrate workloads to AWS
      - Prepare a ccoe (Cloud Center of Excellence)
    - Reinvention stage
      - Assesment of the cloud environment
  - 7 Migration Strategies
    - Rehost
      - Lift and shift
      - Move to AWS without changes
    - Replatform
      - Lift, tinker, and shift
      - Move to AWS with changes
    - Repurchase
      - Drop and shop
      - Move to AWS and purchase new software
    - Refactore
      - Re-architecting
      - Move to AWS and re-architect
    - Retire
      - Drop and stop
      - Move to AWS and stop using
    - Retain
      - Keep and maintain
      - Keep on-premises
    - Relocate
  - 
#### 1.4 Understand concepts of cloud economics
- Ensure you know how using AWS services can save money
  - AWS Well-Architected Framework
    - framework is build to help you understand how to save money and run effiencly
  - TCO (Total Cost of Ownership)
    - Operational expenses
    - Capital expenses
    - Labor costs
    - Software licensing costs
  - Do you know which operations will reduce cost when moved to AWS?
  - Do you know how to establish benchmarking and testing to ensure cost savings?
  - Use data segmentation and reporting for audits. 
  - Dive deeper into sizing, security and compliance. 

#### Walkthrough Question 1
- Task statement 1.2
  - Q: Which AWS Cloud architecture design principle supports the distribution of workloads across multiple Availability Zones?
    - Keywords:
      - design principle
      - distribution of workloads across multiple Availability Zones
    - Choice Responses:
      - a: Implement automation
      - b: Design for agility
      - c: Design for failure
      - d: Implement elasticity
    - Evaluation Options:
      - a: Incorrect
        - Can use automation to deply resources, but the question is asking about distribution of workloads across multiple Availability Zones not automation.
      - b: Incorrect
        - Design for agility is not related to the number of availability zones.
      - c: Correct
        - Design for failure is the correct answer because it supports the distribution of workloads across multiple Availability Z ones.
      - d: Incorrect
        - Elasticity is not related to the number of availability zones.

### Domain 2: Security and Compliance
#### 2.1 Understand the AWS shared responsibility model
- See screenshot in parent folder
- Customer responsibily
  - Configuring firewalls and security groups
  - Managing IAM users and roles
  - Responsible for patching on EC2
- Managed services are usually AWS responsibility heavy
  - Database patching like RDS
#### 2.2 Understand Cloud security, governance, and compliance concepts
- Understand:
  - Compliance needs for locations and industries differ
  - AWS Compliance
  - AWS Artifact
  - Understand where to find compliance information
- One service may require a set of actions to be compliant, while another service may require a different set of actions to be compliant
- Different ways that compliance can be achieved at a higher level
  - Protect systems and higher information
  - Security at every layer
  - Integrate security services
  - Secure connections
- Security Services
  - GuardDuty
  - Macie
  - Cognito
  - WAF
  - Security Hub
  - Inspector
  - Secrets Manager
  - Shield + Shield Advanced
- Encryption
  - Data at rest
  - Data in transit
  - Need to understand encrypting data in transit and at rest
  - Identify who enables encryption for different services
- Log reporting and activity in account
  - AWS Compliance
  - AWS Artifact
  - Amazon CloudWatch
  - AWS CloudTrail
  - AWS Audit Manager
#### 2.3 Identify AWS access management capabilities
- Understand
  - Why do you need to control user access?
  - How to control access to AWS account
  - What is an AWS account
- AWS Root User Account
  - Know how to secure your account root user and tasks required
    - Change account settings
    - Restore IAM user permissions
    - Activate IAM access to Billing console
    - View Tax invoices
    - Close AWS account
    - Register as a seller
    - Configure S3 with MFA
    - Edit or delete S3 bucket policies
    - Signup for AWS GovCloud
- Know IAM
  - IAM users
  - IAM groups
  - IAM roles
    - temp creds
  - IAM policies
    - policy types
    - IAM policy simulator
  - IAM integration with other AWS services
#### 2.4 Identify components and resources for security
- Understand
  - Network Security
    - NACL
    - WAF
    - Security Groups
  - Security Services
    - WAF
    - Trusted Advisor
    - Inspector
    - MarketPlace
    - Knowledge Center


### Domain 3: Cloud Technology and Services
#### 3.1 Define methods of deploying and operating in the AWS Cloud
#### 3.2 Define the AWS Global Infrastructure
#### 3.3 Identify AWS Compute services
#### 3.4 Identify AWS database services
#### 3.5 Identify AWS network services
#### 3.6 Identify AWS storage
#### 3.7 Identify AWS artificial intelligence and machine learning services and analytics services
#### 3.8 Identify services from other in scope of AWS service categories


### Domain 4: Billing, Pricing, and Support
#### 4.1 Compare and contrast the various pricing models for AWS
#### 4.2 Understand resources for billing, budget, and cost management
#### 4.3 Identify AWS technical resources and AWS support options
