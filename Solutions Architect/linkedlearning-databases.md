# [AWS Certified Solutions Architect - Associate (SAA-C03) Cert Prep: 8 Databases](https://www.linkedin.com/learning/aws-certified-solutions-architect-associate-saa-c03-cert-prep-8-databases)

Started: April 18, 2024
Completed: April 18, 2024

### What I need to know:
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

## Notes
### AWS Database Design
#### Database Types
- Hosted services
  - relational & non-relational
- Custom instances
  - use your own license

- Hosted services
  - RDS
    - Aurora MySQL
    - Aurora PostgreSQL
    - Oracle
    - SQL Server
    - MariaDB
    - MySQL
    - PostgreSQL

- Custom Instances
  - Instance with OS running
    - AMI
  - install DB service
    - iso image

- Flat file vs Relational
  - flat file
    - single table
    - no relationships
    - no normalization
    - on line per record
  - relational
    - multiple tables
    - relationships
    - normalization

- No SQL
  - non-relational
  - schema-less

- Data Warehouse
  - large amounts of data usually from multiple sources
  - OLAP (Online Analytical Processing)
  - Redshift

#### Relational Databases
- terminology
  - Row
    - tuples
  - Column
    - attribute
    - properties
  - Table
    - relation
    - entities
    - objects
  - Views & Results
    - virtual table
    - query results

- Relationships
  - Primary key
    - unique identifier
  - Foreign key
    - links to primary key in another table
  - Join
    - combining data from two tables

- Normalization
  - process for evaluating and correcting structures
    - determines the best assignments of attributes to entities
  - Works through serious of normal forms
    - 1, 2, 3, 4 (optional), 5

#### Database hosting methods
- EC2 instances
  - launch, install db, open ports, connect to db
- Hosted services
  - launch, connect to db

#### High-availability solutions
- Clustering
  - multiple instance grouped together
  - replication
  - automatic failover
  - increased cost

- standby
  - multiple servers
  - one is active
  - no automatic failover
  - increases recoverability
  - one database replication

#### Scalability solutions
- Scaling instances
  - change the type/class

- Auto scaling
  - not supported in RDS

- Read replicas
  - read-only copies of the database
  - offloads read requests
  - multiple read replicas in different regions

#### Database security
- Encryption
  - data at rest
  - data in transit
  - key management
  - Must be enabled at creation

- RDS
  - supports encryption at rest

- Permissions
  - admin access should be based on IAM
  - data access should be based on capabilities
    - crud
    - DB admin

#### Aurora
- relational database
- OLTP optimized (writes/updates)
- MySQL compatible

- Scalable
  - starts at 10gb
  - scales in 10gb increments
  - compute resources scale with storage

- Availability
  - 6 copies of data across 3 AZs
  - write capability
    - continues with up to two copies list
  - read capability
    - continues with up to three copies lost

- Replicas
  - up to 15 replicas
    - automatic failover
  - up to 5 MySQL read replicas

#### Redshift
- OLAP databases
  - super fast read performance
- Data warehouse
- AWS managed
- columnar storage
  - excel style spreadsheets
- data compression
-  massive parallel processing
  - distributes queries across multiple nodes
- operates in 1 AZ
  - snapshots can restore to a new AZ

- Thresholds
  - Single node
    - 160gb
  - Multi-node
    - leader node
      - connections and queries
    - compute nodes
      - storage and processing
- Pricing
  - entry point .25$ per hour
  - $1k per TB per year
- Security
  - SSL encryption
  - AES 256 encryption at rest
  - Key management

#### DynamoDB
- NoSQL
- special features
  - millisecond latency
- stored on SSD
- Spread across 3 geographically distinct data centers

- Read consistency
  - eventually consistent
    - a few second delay
  - strongly consistent
    - milliseconds delay

- Pricing
  - .25$ per gb per month
  - throughput billed per 10 units hourly

#### Data security policies
- Compliance vs Policies
  - compliance (what)
    - external requirements
    - Government, industry, partner etc
  - policies (how)
    - data creation
    - data management
    - data destruction

- Privacy rules
  - Do what is required
  - Do what you promise
  - Report quickly and accurately

- Data security concerns
  - access is through the internet
  - data is concentrated in one place
  - data is stored on shared servers
  - Unknown data can be stored without careful control

### AWS Database Deployment
#### DynamoDB tables lab
- Table name - unique
  - Primary key
    - partition key: main index key
    - sort key (optional): secondary index key
- Tables are used, not DB
  - fully managed by AWS

#### MySQL lab
- RDS
  - MySQL is a free tier option
  - Aurora is not free
- Free tier has limited options

#### Configuration lab
- Any time you convert single to multi-AZ, you will have downtime
  - performance impact
- 

#### Backups lab
- configuration
  - Number of days to keep backups
    - 7 days (default)

#### Restore lab
- automated backups by RDS
  - Backups create a new instance
- ability to select the time to restore to
  - specific time/date

#### Snapshot lab
- Manual backups
  - using the dashboard
  - using CLI with a script

- Snapshots
  - unique name identifier
    - use month, day, year as a common best practice

#### Monitoring lab
- Utilize to develop solutions
  - CloudWatch
  - RDS dashboard
