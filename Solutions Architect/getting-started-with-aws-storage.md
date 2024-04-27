# [Getting Started with AWS Storage](https://explore.skillbuilder.aws/learn/course/6233/getting-started-with-aws-storage)

Started: April 24, 2024
Completed: April 26, 2024

## Links
- [Amazing Application Storage Decision Checklist](https://explore.skillbuilder.aws/learn/course/6233/play/19883/bringing-aws-storage-services-all-together;lp=1044)


## Notes
### Core AWS Storage Services
- File Storage
  - The two most common storage protocols for file storage are Server Message Block (SMB) and Network File System (NFS).
  - The file system can be Windows Server, Linux, or a specialized operating system used on network attached storage (NAS) devices or clustered NAS systems.

#### Identifying the Right Storage Solution
- The optimal storage solution for a system varies based on the following:
  - Type of access method (block, file, or object)
  - Patterns of access (random or sequential)
  - Required throughput
  - Frequency of access (online, offline, archival)
  - Frequency of update (WORM, dynamic)
  - Availability and durability constraints

- Volume Types
  - SSD
    - SSD-backed storage for transactional workloads, such as databases, virtual desktops, and boot volumes
  - HDD
    - HDD-backed storage for throughput-intensive workloads, such as MapReduce, data warehousing, and log processing

#### Edge and Hybrid Storage Solutions
- Outposts
  - Supports
    - EBS
    - S3
  - fully managed service that extends AWS infrastructure, services, APIs, and tools to your premises
  - configurable to meet your specific requirements
  - installed by AWS
    - site must meet the facility, networking, and power requirements for your Outpost. Each configuration has unique power, cooling, and weight support requirements. 
    - It includes racks, servers, switches, and cabling that AWS owns and manages.
    - Each Outpost is an extension of an Availability Zone and its associated Region. 
  - Resources supported
    - Amazon EC2 instances and EBS volumes
    - Amazon ECS clusters
    - Amazon Elastic Kubernetes Service (Amazon EKS) nodes 
    - Amazon ElastiCache instances using Amazon ElastiCache for Redis or Amazon ElastiCache for Memcached
    - Amazon EMR clusters
    - Amazon RDS database instances
    - Amazon S3 buckets using Amazon S3 on AWS Outposts
      - 100 buckets per Outpost
      - 26tb, 48tb, or 96tb capacity can be added per Outpost
    - Application Load Balancers
    - AWS App Mesh Envoy proxy


### Transferring your data to the AWS cloud
#### Data Transfer + Migration Services
- AWS Transfer Family is designed to replace on-premises systems for file transfer workflows
- AWS DataSync synchronizes your data between a source data location or service and a destination location or service.
- AWS Snow Family provides offline data transfers using physical devices
- AWS Application Migration Service (AWS MGN), formerly CloudEndure Migration, provides a migration service between your servers and AWS services

#### AWS Transfer Family
- fully managed service to get files into and out of AWS storage services
  - S3
  - EFS
- supports
  - SFTP
  - FTPS
  - FTP

#### AWS DataSync
- Simplifies, automates and accelerates moving and replicating data between on-premises storage systems and AWS storage services
- manages the infrastructure for data transfer, automates data transfer tasks, and monitors the transfer process
- ability to schedule operations
- metadata is transferred with the data
- Costs
  - Data that is copied to or from AWS DataSync is charged at the standard AWS Data Transfer rate
  - costs are based on a flat per-gigabyte fee for the use of network acceleration technology, managed cloud infrastructure, data validation, and automation capabilities in DataSync

#### AWS Snow Family
- Snowcone
  - smallest device
  - rugged, secure, and portable, ideal for remote locations
- Snowball
  - 3 options
    - Edge Storage Optimized without compute
      - 80tb
      - no vCPUs or EBS storage
      - only used for transferring data to AWS
    - Edge Storage Optimized with compute
      - 80tb
      - 24vCPUs
    - Edge Compute Optimized
      - custom
      - ability to use for edge data collection and processing
- Snowmobile
  - Exabyte-scale data transfer service used to move extremely large amounts of data to AWS
  - 45-foot long ruggedized shipping container pulled by a semi-trailer truck
  - 100PB per Snowmobile

#### AWS Application Migration Service
- formerly CloudEndure Migration
- When to use?
  - lift-and-shift migrations
- Features
  - migrate databases and applications
  - windows/Linux

- How it works
  - Agent install
    - AWS Replication Agent is installed on the source machine
    - The agent captures data changes and sends them to replication servers
  - Continuous replication
    - Replication servers replicate the data to the target machine
  - Testing and Cut-over
    - Test the target resources
    - Cut-over to the target resources

### Protecting your data in the AWS cloud
#### Data Backup
- fully managed data protection service that makes it easy to centralize and automate across AWS services, in the cloud, and on premises
- Supports backup of multiple services
  - compute
  - storage
  - databases
- Apply backup policies plans to resources by tagging them

#### Native Service Snapshots
- creates backup copies of your data in your storage or db service.
- Point-in-time copies of your data
- Ability to match multiple service snapshots to create a consistent backup
- stored in S3
- Only changed data is stored between snapshots

#### CloudeEndure Disaster Recovery
- fully managed disaster recovery service that provides a simple, fast, reliable, and cost-effective solution for disaster recovery
- continuous replication of your source machines into a staging area in your target AWS account
- Recovery Point Objective (RPO) of seconds and Recovery Time Objective (RTO) of minutes
- billed hourly based on the number of machines you replicate
