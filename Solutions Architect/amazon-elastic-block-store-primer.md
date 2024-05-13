# [Amazon Elastic Block Store (Amazon EBS) Primer](https://explore.skillbuilder.aws/learn/course/1644/play/55534/amazon-elastic-block-store-amazon-ebs-primer-101)

Started: May 12, 2024
Completed: May 12, 2024

## Links
- [Identity and Access Management for EC2](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/security-iam.html)
- [Amazon CloudWatch metrics for Amazon EBS](https://docs.aws.amazon.com/ebs/latest/userguide/using_cloudwatch_ebs.html)

### What I need to know:

## Notes
### Introduction to Block Storage
#### What is Block Storage?
- Raw storage that is divided into predefined continuous segments called blocks
- Can be stored on devices like HDDs, SSDs, or NVMes, or SANs

- File and Object storage are built on top of block storage

- basic architecture of block storage:
  - block storage
  - compute system
  - OS running the compute system

- Block storage management
  - Block size: OS formats the data into appropriate block sizes
  - Metadata: OS keeps track of the blocks and the information (resource type, permissions, create-time, modify-time, etc.)
  - Read-Write activity: OS uses metadata to control access, read, and write activity, caching activity, etc.
  - Locking control: OS manages data integrity when data is being modified, deleted or accessed by multiple users.

- Volumes
  - volume is a logical storage construct that can be created from a single drive or using multiple drives

- Performance
  - Block storage is designed for high-performance applications
  - Low latency and high IOPS

### Intro to Amazon EBS
#### EBS Overview
- Designed for mission-critical systems, Amazon EBS volumes are replicated within an Availability Zone
- EBS volumes are particularly well suited for use as the primary storage for file systems, databases, or any applications that require fine granular updates and access to raw, unformatted, block-level storage

- AWS Block storage portfolio
  - Instance storage
    - Temp block storage attached to host hardware
    - Data is lost when the instance is terminated
  - EBS storage
    - specific block storage to work with EC2 instances
    - data is persistent and can be detached and reattached to other instances
  - Snapshots
    - point in time backup of EBS volumes

#### Features and Benefits
- Performance for any workload
  - Different volume types to meet different performance needs
  - SSD for high performance apps and general purpose
  - HDD for throughput intensive workloads such as big data, analytics, and log processing
- Easy to use
  - Easy with management console, CLI, or SDK
- High reliability
  - EBS volumes are replicated within an Availability Zone
  - 99.999% availability
- Virtually unlimited storage
  - Configure storage based on your needs
  - Can use unlimited number of volumes
- Secure
  - Ability for advanced key management for encryption
  - Encryption options
- Cost Effective
  - Pay only for what you use
  - No upfront costs or long-term contracts
  - Price varies based on volume type, size, and usage
- High availability and High durability
  - EBS volumes are replicated within an Availability Zone
  - 99.999% availability

#### Use Cases
- Enterprise applications
- Relational databases
  - SAP HANA, Oracle, Microsoft SQL Server, MySQL, and PostgreSQL are widely deployed on Amazon EBS
- NoSQL databases
  - MongoDB, Cassandra, and Couchbase
  - DynamoDB is fully managed service that can use Amazon EBS
- Big data analytics
  - Amazon EMR, Hadoop, and Spark
- Relational databases
- NoSQL databases
  - MongoDB, Cassandra, Couchbase, and DynamoDB

### Types of EBS Storage
#### EBS Performance
- EBS volumes are designed for an AFR of 0.1 to 0.2 percent
- maximize availability and durability by creating snapshots frequently

- IOPS
  - Input/Output Operations Per Second
- Throughput
  - Amount of data that can be transferred in a given amount of time
- Burst balance
  - The amount of I/O that can be performed in a burst mode
  - Burst balance is a credit system that allows you to burst beyond the baseline performance of the volume
- Latency
  - The time it takes for a single I/O operation to complete
  - SSD - sub-1 millisecond to single digit milliseconds
  - HDD - double digit milliseconds

#### EBS Volume Types
- General Purpose SSD
  - gp2/gp3
  - ranges from a minimum of 100 IOPS at 33.33 GiB and below to a maximum of 16,000 IOPS at 5,334 GiB and above
- Provisioned IOPS SSD
  - io1/io2
- Throughput Optimized HDD
  - st1
- Cold HDD
  - sc1
- Magnetic

#### Choosing the Right EBS Volume Type
- Existing on-premises workload
  - Collect as much info as possible about your workload
  - Utilization, IOPS, throughput, latency, etc.
- New cloud workload
  - Create a test/dev environment to test the workload using different volume types
  - evaluate similar workloads
  - Use monitoring tools to evaluate performance on a regular basis

- Workload characteristics questions
  - Is the workload more IOPS or throughput intensive?
    - IOPS -> start with SSD
    - Throughput -> start with HDD
  - Does the workload requirements exceed max performance of a volume type?
    - Choose a different volume type
  - What is the latency requirement?
    - SSD for low latency
    - HDD for higher latency

#### EBS Snapshots
- Copies of data in EBS volume at a point in time
- Stored in S3
- Incremental snapshots
  - Only the blocks that have changed since the last snapshot are saved
- Encryption options

- Actions with snapshots
  - Create a snapshot
  - Copy a snapshot
  - Share a snapshot
  - Delete a snapshot
  - View snapshot details

- Amazon Data Lifecycle Manager
  - Automate the creation, retention, and deletion of snapshots
  - Resource tags are used to identify resources to be backed up

- Lifecycle policies
  - core settings
    - Policy type
      - Defines the type of resources the policy manages (Snapshots or AMIs)
    - Resource Type
    - Target tags - resources to be backed up
    - Schedules - frequency of backups
      - 1 mandatory schedule and 3 optional schedules
    - Retention - how long to keep backups

### Pricing
#### EBS Pricing
- Costs are calculated based on the provisioned amounts.
  - gigabyte (GB) per month for volumes
    - ((Provisioned GB volume size) * (Price per GB-month)) / (1 month)
  - IOPS per month for provisioned IOPS
    - (((Provisioned IOPS amount) - (Base IOPS amount)) * (Price per IOPS-month)) / (1 month)
  - MB/s per month for provisioned throughput
    - (((Provisioned MB/s throughput) - (Base MB/s throughput)) * (Price per MB/s-month)) / (1 month)

- Rate calculations per unit of time (1 month example)
  - Per-day = (Rate per unit-month) / (30 days per month)
  - Per-hour = (Rate per unit-month) / ((30 days per month) * (24 hours per day))
    - (Rate per unit-month) / (720 hours per month)
  - Per-minute = (Rate per unit-month) / ((30 days per month) * (24 hours per day) * (60 minutes per hour))
    - (Rate per unit-month) / (43,200 minutes per month)
  - Per-second = (Rate per unit-month) / ((30 days per month) * (24 hours per day) * (60 minutes per hour) * (60 seconds per minute))
    - (Rate per unit-month) / (2,592,000 seconds per month)

### EBS Architecture
#### Architecture
- Basic architecture
  - Single or multiple EBS volumes attached to an EC2 instance
  - EC2 instance and EBS reside in single AZ
  - Snapshots are stored in S3
  - Access is controlled through AWS IAM

- Advanced architecture - Multi-Attach
  - Multiple EBS volumes attached to an EC2 instance
    - Provisioned IOPS SSD volume types supported for Multi-Attach
  - EC2 instance and EBS reside in single AZ
  - Application or OS must manage the data consistency
  - Snapshots are stored in S3
  - Access is controlled through AWS IAM

- Advanced architecture - Striped volumes
  - Multiple EBS volumes attached to an EC2 instance
    - Striped redundant array of independent disks (RAID) 0
    - operates as a single volume
  - Snapshots are stored in S3
  - Access is controlled through AWS IAM

### Integration with Other AWS Services
#### Data Security
- Utilize IAM to control access to EBS volumes
- AWS Key Management Service (KMS) for encryption
  - Encryption happens on server hosting the EC2 instance
  - Data at rest inside the volume
  - All data moving between the EBS volume and the EC2 instance
  - All snapshots created from the EBS volume
  - All EBS volumes created from those snapshots

#### AWS Backup
- AWS Backup offers a more robust backup solution when compared to EBS Snapshots
- Operates as a separate service with additional features

- AWS Backup features
  - Policy-based backup solution - create backup policies based on specific business needs
  - Tag-based backup policies - create backup policies based on tags
  - Automated backup scheduling - set backup schedules
  - Automated retention management - set retention policies
  - Backup activity monitoring - monitor backup activity with dashboards
  - Lifecycle management - configure lifecycle policies that will automatically transition backups from warm storage to cold storage according to a schedule that you define
  - Backup access policies - set resource-based access policies on Backup Vaults
  - Cross-region backup - copy backups to another region for disaster recovery
  - Cross-account backup - copy backups to another account for disaster recovery

#### CloudEndure + AWS Application Migration
- CloudEndure Disaster Recovery minimizes downtime and data loss by providing fast, reliable recovery of physical, virtual, and cloud-based servers into AWS Cloud, including public Regions, AWS GovCloud (US), and AWS Outposts
  - replication of entire servers, including operating system, system state, databases, applications, and user data
  - low-cost staging area in the target AWS Region ready to launch in the event of a disaster

- AWS Application Migration Service (AWS MGN), formerly CloudEndure Migration, is a highly automated lift-and-shift (rehost) solution that simplifies, expedites, and reduces the cost of migrating applications to AWS Cloud, including public Regions, AWS GovCloud (US), and AWS Outposts
  - Continuous data replication

#### Amazon CloudWatch
- Data is available automatically in 1-minute periods at no charge
- Amazon EBS sends data points to CloudWatch for several metrics

- CloudWatch metrics
  - VolumeReadBytes
    - Provides information on the read operations in a specified period of time
  - VolumeWriteBytes
    - Provides information on the write operations in a specified period of time 
  - VolumeReadOps
    - The total number of read operations in a specified period of time
  - VolumeWriteOps
    - The total number of write operations in a specified period of time
  - VolumeTotalReadTime
    - total number of seconds spent by all read operations that completed in a specified period of time
    - Note: This metric is not supported with Multi-Attach enabled volumes
  - VolumeTotalWriteTime
    - total number of seconds spent by all write operations that completed in a specified period of time
    - Note: This metric is not supported with Multi-Attach enabled volumes
  - VolumeIdleTime
    - total number of seconds in a specified period of time when no read or write operations were submitted
    - Note: This metric is not supported with Multi-Attach enabled volumes
  - VolumeQueueLength
    - number of read and write operation requests waiting to be completed in a specified period of time
  - VolumeThroughputPercentage
    - The percentage of I/O operations per second (IOPS) delivered of the total IOPS provisioned for an Amazon EBS volume
    - Note: This metric is not supported with Multi-Attach enabled volumes
    - Used with Provisioned IOPS SSD volumes only
  - VolumeConsumedReadWriteOps
    - Used with Provisioned IOPS SSD volumes only
    - total amount of read and write operations (normalized to 256K capacity units) consumed in a specified period of time
  - BurstBalance
    - Used with General Purpose SSD (gp2), Throughput Optimized HDD (st1), and Cold HDD (sc1) volumes only 
    - Provides information about the percentage of I/O credits (for gp2) or throughput credits (for st1 and sc1) remaining in the burst bucket



