# [AWS Certified Solutions Architect - Associate (SAA-C03) Cert Prep: 9 Services and Design Scenarios](https://www.linkedin.com/learning/aws-certified-solutions-architect-associate-saa-c03-cert-prep-9-services-and-design-scenarios)

Started: April 19, 2024
Completed: April 19, 2024

### What I need to know:
- ElastiCache -> know what it does, how to pick the right node type
- Understand the constraints of Developer Tools (languages?)
  - what they can do
  - when to use

## Notes
### Amazon Services
#### Media Content Delivery
- Elastic Transcoder
  - media transcoding
  - Jobs
    - do the transcoding
  - Pipelines
    - queues to manage jobs
  - Presets
    - settings for transcoding
  - Notifications
    - SNS used to notify of job status
- Transcoded files are placed back into the original bucket

- Amazon Translate
  - ML category
  - On-demand language translation
  - Encoder
    - reads source text
  - Decoder
    - outputs translated text

- Elemental MediaStore
  - Video origination and storage services
    - container
  - Considerations
    - live video streams optimal use this
    - Storage based video
      - not optimal
      - use S3 buckets

- Transcribe
  - Speech to text (audio/video)
    - generates closed caption files
  - based on machine learning

- Rekognition
  - Image and video analysis
    - people
    - speech
    - objects
  - Can be run against S3 buckets
    - enhanced search based on analysis results

#### Desktop and app streaming
- AWS WorkSpaces
  - virtual desktops
  - linux, windows 7, windows 10
  - Persistent storage
    - Virtual D:drive
    - auto backup
  - based on windows server virtualization

- AWS AppStream 2.0
  - Virtual apps in AWS
  - common use for custom-developed apps

#### ElastiCache
- Database in-memory caching
  - Two types
    - Memcached
      - simplest for implementation
    - Redis
      - HIPAA or PCI-DSS compliant
  - builds a cluster of caching servers

#### Security Services lab
- Key Management Services
  - Encryption keys
    - needs
      - name, tag (optional), key permissions, who can use it

- Cloud HSM
  - virtual hardware security module
  - cluster of HSMs

- Directory Services options
  - AD
  - Simple AD
    - linux samba AD compatible
  - AD Connector
    - connect to an existing / cognito
  - AWS Managed Microsoft AD (windows servers running AD)

#### Analytics engines
- CloudSearch
  - offline data to make searchable

- Elasticsearch
  - search engine
  - real-time data
  - Kibana
    - visualization tool
  - Logstash
    - data collection tool

- Data Pipeline
  - data related workflow
  - move, integrate, transform data

- AWS Glue
  - ETL
    - Extract Transform Load
    - do something to data and load it somewhere

- QuickSight (not an AWS tool external)
  - BI tool
  - data visualization

- Athena
  - SQL query tool
  - S3 data

#### Development operations (DevOps)
- CodeCommit
  - source code repository

- CodeBuild
  - build and test code
  - custom environments

- CodeDeploy
  - deploy code

- CodePipeline
  - monitor various stages of project
  - build, test, deploy etc stages

- CodeStar
  - project management tool
  - build a project?

- Cloud9
  - IDE cloud environment
  - terminal is linux based
  - actually an EC2 instance to run the IDE
  - suspends after 30 minutes of in-activity

- X-Ray
  - debugging tool within the cloud
  - traces requests

#### AWS Solutions
- Professional build solutions
  - created by industry professionals and solution architects
  - super detailed information for each solution
- Same as AWS Quick Starts
  - pre-built solutions

#### AWS Transit Gateway
- allows interconnection of all VPC
- connect on-prem with cloud
- Acts as the HUB in a spoke and hub model

#### AWS Backup
- centralized backup solution
- fully managed service
- ability to backup on-prem with Storage Gateway
- backup for many services
  - EBS, CloudFormation, etc

#### AWS Cost Explorer
- 24 hour wait window once enabled
- See all charges broken down by service, etc
- Budget management
  - set budgets
  - alerts when thresholds are met

### Operational Excellence with AWS
#### The operational excellence process
- Well-Architected Framework
  - Operational Excellence
    - 3 key topics
      - **prepare**
        - understand workloads + expected behaviors
          - considerations
            - operational priorities
            - design for operations
            - operational readiness
      - **operate**
        - monitor
          - env health
          - discover business/technical insights
        - respond
          - security, reliability, performance, cost
      - **evolve**
        - learn from experience
        - share learning
        - improve
        - scale

#### Widget Makers scenario
- Inventory Management
  - web base interface
  - sql
- User data
  - 230 user
  - 700mb
  - windows shares
- Order processing
  - SQL
  - web based < 100 users
- Payroll
  - SQL
  - time-clock connection
  - managers read/write
  - accounting read only
- Website
  - wordpress with custom plugins

#### Resilient design
- cannot require admins
- automation
  - recover, scaling, backups

- must test recovery procedures
  - needed to ensure they work
- auto recover from failure
- scaling
  - must be able to scale
- Monitor and use the metrics

#### Resilient design scenario
- all services
  - multiple AZ deployment

- Order Processing server
  - continue using MySQL
  - move into RDS for managed service solutions
- Inventory management
  - move to RDS
- Payroll
  - move to RDS
    - use REDIS for processing
- User Data
  - S3 bucket storage
    - use 3rd party tool to a map drive layers
- WebSite
  - ElasticLoad balanced deployment

#### Performant design
- Design principles
  - democratize advanced technologies
    - use what is already build
  - go global in minutes
    - deploy to be close to the user
  - use serverless architectures
    - no servers to manage
  - experiment more often
  - mechanical sympathy
    - think about the process and how it unfolds
    - do the best solution for the problem

- Autoscaling
  - key to performant design in the cloud
  - EC2 instances
    - logging of scale actions should be in place
  - Databases can scale quickly
    - monitor and scale as needed

#### Performant design scenario
- Inventory management
  - instance type optimized
  - enable SNS messaging
  - automate adding inventory with CloudWatch
- Payroll solution
  - instance type optimized
  - process only from read replica
- User Data
  - S3 buckets by department
  - configure alarms for exceeding 700Mb
- Website
  - use ELB volumes
  - instance type optimized

#### Secure design
- Principles
  - Implement a strong identity foundation
  - Enable traceability
    - use CloudTrail
    - monitor only the things you need
  - Apply security at all layers
  - Automate security best practices
  - Protect data in transit and at rest
  - Keep people away from data
  - Prepare for security events

- Security in the cloud
  - IAM
  - detective controls
  - infrastructure protection
  - data protection
  - incident response plan

#### Secure design scenario
- Order processing
  - IAM groups and policies to secure db
  - RDS secured to only specific people can access
- Inventory management
  - IAM groups and policies to secure db
- Payroll solution
  - IAM groups and policies to secure db
  - only accounting can access Read only replica
- User Data
  - AM groups and policies to secure db
  - encrypt data
  - use SSL for data transfer
  - only people of that department can access department bucket
- Website
  - Run server instance with appropriate roles
  - configure security group for network interfaces
  - configure security group for VPC

#### Cost optimization
- Principles
  - Adopt consumption models
  - measure overall efficiency
  - stop spending money on data-centers
  - analyze and attribute expenditure
  - use managed services to reduce cost of ownership

- Four Pillars
  - cost-effective resources
  - matching supply with demand
  - expenditure awareness
  - optimizing over time

#### Cost optimization scenario
- Order processing
  - used a managed database
- Inventory management
  - used a managed database
- Payroll solution
  - used a managed database
  - use the read replica as needed
- User Data
  - monitor use
- Website
  - use the right instance class
  - monitor access
    - address improper access

#### General best practices
- Design for failures
  - clustering
  - AZs
  - backups
  - alternate AWS account
  - CloudFormation templates

- Implement elasticity
  - scale but better with shrinking
  - Auto scaling
  - elastic load balancing
  - decoupled applications
  - run tasks in parallel

- Learn
  - AWS free tier account
  - Practice
    - build entire solutions
    - configure every option
    - tear down / start again
  - Try different solutions
