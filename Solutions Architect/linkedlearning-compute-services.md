# [AWS Certified Solutions Architect - Associate (SAA-C03) Cert Prep: 4 Compute Services](https://www.linkedin.com/learning/aws-certified-solutions-architect-associate-saa-c03-cert-prep-4-compute-services)

Started: April 14, 2024
Completed: April 14, 2024

## Links
- [Amazon EBS-optimized instances](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-optimized.html)
- [AWS Compute Optimizer](https://aws.amazon.com/compute-optimizer/)
- [AWS ECS with Fargate](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/getting-started-fargate.html)
- [Getting started with ECS](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/getting-started.html)
- 
### What I need to know:
- Differences between Security Groups vs NACL
  - How are they used
  - where do they apply
  - what kind of rules do they used
  - how are they processed

## Notes
### Compute Services Design
#### EC2 Overview
- Virtual Machine in the cloud
- Can be used for a variety of workloads
- Pay as you go, what you use
- Integrates with other AWS services
- Ability to configure and launch in minutes

- Benefits
  - time to market
  - scalability
  - reliability
  - security
  - Control
  - Services integration
  - cost efficiency

- Deployment steps
  - Choose AMI
  - Configure network and security
  - Choose instance type
  - Choose the AZ
  - Add storage
  - Start the instance

#### EC2 Instance Types
- Types
  - General purpose
    - M5, M4, and M3 classes
    - T2 class
      - burst performance option
    - Balance of compute, memory, and networking resources
    - not extremely busy
  - Compute Optimized
    - C5, C4, and C3 classes
    - High performance processors
      - media coding
      - batch jobs
      - many concurrent users
      - gaming servers
  - Memory Optimized
    - X1e, X1, R4, and R3 classes
    - High memory capacity
      - in-memory databases
      - real-time processing of big data
      - processing large data sets into RAM
  - Storage Optimized
    - H1, I3, and D2 classes
    - High sequential read and write access to large data sets
      - data warehousing
      - relational databases
      - network file systems
  - Advanced Computing
    - P3, P2, F1, and G3 classes
    - special hardware components
    - Graphics processing units
      - 3D rendering
      - FPGA

#### EC2 Pricing
- Pricing Categories
  - On-demand
    - pay for what you use (minutes/hours/storage/network-transfer)
    - no upfront costs
    - no long-term commitments
  - Reserved
    - reserved capacity
      - in hours
    - 1, 2 or 3 year terms
    - significant discounts
  - Spot
    - bid on unused capacity
    - up to 90% off on-demand prices

- Reserved payment types
  - All upfront
  - Partial upfront
  - No upfront

#### EBS and EC2
- EC2 instances has storage by default for the OS, etc

- EBS
  - Requires an EBS-optimized instance
  - Persistent block storage
    - just like a hard drive
    - changes are saved

#### AWS Compute Optimizer
- Identifies optimal EC2 resources
  - looks at resource config
  - looks at utilization data
  - requires CloudWatch enabled
  - minimum 30 consecutive hours of data
    - Except with Lambda Function data (n functions within 14 days)
- Integrates with CostExplorer

- Recommends
  - instance types
  - auto scaling groups
  - EBS
  - Lambda functions

### Compute Services Implementation
#### Launching EC2 lab
- Ability to launch multiple instances
  - auto scaling group from the start
- Ability to have termination protection. Multi-step to terminate
- enable bursting

#### Configuring EC2 linux lab
- PEM key file for connection
- Use Putty for Windows
  - convert PEM to PPK
  - use PuttyGen

#### Setting up EC2 windows lab
- Windows is more disk intensive than linux
- After launching, be sure to connect with Remote Desktop (RDP)
- Requires RPD config file from AWS to access windows instance

#### Shared tenancy
- multiple customers shared the same hardware (time/space)
- default instance

- Pros
  - Cheaper
  - simple deployment
- Cons
  - lower performance
  - less control

#### Dedicated hosts
- physical machines
  - runs the virtual machines
- Used by a single customer
- explicitly configured
- no free tier

- Pros
  - licensing management
  - more detailed reporting
  - compliance management
  - determine placement on restarts
- Cons
  - more expensive

- BYOL
  - Bring Your Own License
  - use your current window licenses
  - less expensive for ec2 instance

#### Dedicated instances
- Runs on physical machine
  - single instance on the machine
  - May be moved, on restart

- Pros
  - hardware dedicated to single customer
  - performance advantages
- Cons
  - less accurate license management

#### AMI Virtualization
- Amazon Machine Image
  - blueprint of server configuration
  - OS, software, settings, firewall, etc
  - can be public or private

- All instances are created from an AMI
- Amazon Marketplace has AMI free and for a fee

- Who can launch an AMI?
  - Public: anyone
  - Explicit: specified (whitelist of users)
  - Implicit: Owner
  - Default: implicit

- Hardware Virtual Machines
  - HVM
  - AMI fully virtualize the hardware
  - requires hardware-assisted virtualization

- ParaVirtual
  - runs on host without support for virtualization
  - less performant

- Instance Root Volume
  - contains the boot sector
    - starts the boot loader
      - boot loader launches the OS

- Instance store-backed AMI
  - stored in S3
  - always terminating
  - 
- EBS backed AMI
  - support for stop action
  - recovery on failure

### Compute Services Management
#### Instance management
- Bootstrapping
  - provides code to run on instance at launch
    - install scripts, etc
- VM Import/Export
  - import existing VM into EC2

- Instance metadata
  - security groups
  - ID
  - type
  - AMI base

- Instance management
  - change instance type
  - change security groups
  - activate terminate protection
    - has to be manually turned off in management console before instance can be terminated

#### Working with security groups
- Similar to a firewall for instances
- Limit of 5 per instance
- instances receive the default SG

- group examples
  - web server access
  - database access

- Security Group
  - instance level
  - supports allows rules only
  - is Stateful: return traffic auto allowed
  - All rules evaluated before deciding
  - applied only to instances defined
- NACL
  - Subnet level
  - supports allow and deny rules
  - is Stateless: return traffic must be explicitly allowed with a rule
  - Rules are processed in order
  - applies to all instances in subnet

- Security Group Constraints
  - only allow rules are permitted
  - no inbound traffic is allowed w/o request
  - defaulted to allow all outbound traffic
- 
#### Working with security groups lab
- Closed to open security system
  - closed by default
    - must open ports to allow traffic

#### Advanced EC2 management
- Resource Optimization Recommendations
  - support blog
  - recommendations on optimization changes
- Traffic Mirroring
  - copy network traffic to a destination
    - send all EC2 traffic to somewhere else
  - used for monitoring, security, and troubleshooting
    - content inspection
    - threat monitoring

#### AWS Batch
- Collection of process to run

- AWS Batch
  - under compute services
  - managed EC2 environment
  - spot or on-demand
- Batch Jobs
  - script of commands/jobs
  - unit of work
  - automate anything CLI essentially 

#### Elastic Container Services (ECS)
- Deploying application in instances
  - uses Docker Container
- What is a container
  - lightweight, standalone, executable package
  - includes everything needed to run
    - code, runtime, libraries, etc
  - portable across different platforms
    - Java Runtime is similar

- Features
  - No VM builds are required
  - Uses Amazon Fargate to auto build environments
  - Ability to use EC2 instances for advanced control
- Container Usage
  - web server
  - app server
  - message queue server
  - etc
  - concept of microservices support
- ability to scale different docker containers independently in the same instance

#### Elastic Beanstalk environment
- deploy, monitor
- for creating an entire infrastructure
- creates all the services and resources for the environment
  - security groups, ENIs, etc
