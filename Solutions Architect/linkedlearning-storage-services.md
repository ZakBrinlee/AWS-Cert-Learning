# [AWS Certified Solutions Architect - Associate (SAA-C03) Cert Prep: 2 Storage Design](https://www.linkedin.com/learning/aws-certified-solutions-architect-associate-saa-c03-cert-prep-2-storage-design)

Started: April 9, 2024
Completed: April 10, 2024

## Links
- [Amazon EBS volume types](https://docs.aws.amazon.com/ebs/latest/userguide/ebs-volume-types.html)
- [Amazon S3 Storage Classes](https://aws.amazon.com/s3/storage-classes/)

### What I need to know:
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

## Notes
### Amazon S3
#### S3 Storage Class
- Simple Storage Service
- Object-based storage
  - any type of data
- Distributed across at least 3 availability zones
  - except 1A class
- Supports encryption and auto data classification

- Getting data into S3
  - AWS SDK (APIs)
  - Direct Connect
  - Storage Gateway
  - Kinesis Firehose
  - Transfer Acceleration
    - Based on CloudFront edge locations with optimized network path
  - Snow Family

#### S3 Terminology
- Buckets
  - Containers for objects
  - Unique name
  - Region-specific
  - 100 buckets per account
- Objects
  - think of it like a file but really it is anything
  - Each object has a key
- Keys
  - Unique identifier for an object
  - Full path to the object
- Object URLs
  - `https://s3.amazonaws.com/bucketname/keyname`
  - way to access objects by network
- Eventual Consistency
  - S3 is eventually consistent
- Great for static website hosting

Common Operations
- Creating and deleting buckets
- CRUD objects
- managing object properties

- REST Interface is the S3 API
  - maps http methods to CRUD operations
  - create uses PUT or POST
  - read uses GET
  - update uses POST or PUT
  - delete uses DELETE

#### S3 Advanced features
- Prefixes and delimiters
  - folder structure like naming convention
- Storage classes
  - Ways that S3 can store data
  - Standard, infrequent access, one zone infrequent access, intelligent tiering, glacier, glacier deep archive, reduced redundancy storage
- Object lifecycle management
  - Automate moving objects between storage classes
- Encryption
  - at rest, in transit
- Versioning
  - keep multiple versions of an object
- Multi-Factor authentication delete
  - requires a second factor to delete an object
- Multi-part upload
  - upload large objects in parts
- Range GETs
  - get a specific range of bytes from an object
- Cross-region replication
  - replicate objects to another region
- Logging
  - log all requests to a bucket

### Additional AWS Storage Services
#### Glacier
- Archival data
- Low cost
- Retrieval times are slow, super slow
- Region is defined by user
- Encryption is default
- Vaults
  - Archives go into vaults
- Vault locks
- Data retrieval
  - up to 5% retrieval per month, no charge
  - Ability to configure limit costs
  - expedited, standard, bulk retrieval options
    - expedited is 3-5 minutes
    - standard is 3-5 hours
    - bulk is 5-12 hours

#### Setting up a Glacier vault lab
- Manually put items into Glacier requires creating a vault
- Can create 1000 vaults per region
- Configure with many options
  - SNS topic for notifications
  - Permissions are policy based
  - Data retrieval settings
    - Can select Free Tier only

#### S3 and Tape Gateway
- Tape Gateway
  - Integrates with many other resources
    - EC2, S3 Glacier deep archive

- Storage Gateway
  - File Gateway
    - object storage for S3
  - Volume Gateway
    - block storage for EC2 (EBS snapshots), stored in S3
  - Tape Gateway
    - virtual tape library, stored in S3
    - Ability to select host platform

#### S3 Enhanced features
-  Smart tiering
  - Automatically moves objects between storage classes
  - Move object from x to y after z days
- Object locking
  - write once, read many
    - "WORM"
- Batch processing
  - process objects in batches
  - Based on a manifest of all the objects in the bucket
    - List of actions that can be taken

#### Elastic Block Store (EBS)
- Durable instance storage
  - persists beyond instance termination
  - Block storage
    - Can be shared between resources

- Volume Types
  - Magnetic
    - lowest cost
    - lowest performance/slowest
  - SSD
    - General purpose
    - Provisioned IOPS
      - 10,000 or more
      - provisioned input/output operations per second
- EBS-optimized instances
  - instances that are optimized for EBS
  - dedicated network connection to EBS


- Protecting EBS data
  - Snapshots
    - point-in-time backup of a volume
  - Volume recovery
    - attaching volumes from one to another
  - Encryption

#### Creating EBS volume lab
- EBS is not found in the Management Console services list
  - Part of EC2 so to locate it, go to EC2
- Magnetic volumes is the only one that is on the free-tier
- Can select the availability zone/needs to be in the same AZ as the instance

#### Elastic File System (EFS)
- Elastic File System
  - shareable
    - Multiple instances can access at the same time
    - think LAN-like system
    - NFSv4 access
  - can be used by EC2
    - Not supported on Windows instances
  - Multiple GB per second Input throughput

#### EFS and PrivateLink
- PrivateLink
  - endpoints (public) to EFS resources
  - elastic network interface (ENI)
- allows for secure connection between VPCs, services, and applications in AWS

#### Intro to Amazon FSx
- Windows and Lustre
- Fully managed file system
- Integrated with AWS services
  - Cloudwatch example: store log files in FSx
- Windows
  - Windows file server
  - SMB protocol
  - Active Directory integration

#### Hands on with FSx
- File system name is option, (recommended for ease of management)
- Ability to be deployed to 1 or more AZ
- Windows auth through AD can be self-managed or AWS managed

#### Integrating on-prem storage
- Storage Gateway
  - Run a VM image, (storage gateway) locally to create a gateway
  - 3 types of storage types:
    - File Gateway
      - file based
      - files into S3
    - Volume Gateway
      - SCSI protocol
      - block level
    - Tape Gateway
      - virtual tape concept
      - backup and archive

- Hosting options
  - EC2 on AWS
  - On-premises in your own instance

#### Storage access security lab
- Utilize "Policy Generator" to create a policy for buckets

#### Storage performance
- EBS Volume types
  - SSD vs Magnetic
- S3 storage classes
  - durability and availability differences