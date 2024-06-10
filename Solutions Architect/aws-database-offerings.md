# [AWS Database Offerings](https://explore.skillbuilder.aws/learn/course/61/aws-database-offerings;lp=1044)

Started: June 6th, 2024
Completed: June 6th, 2024

## Links
- [AWS Full Stack Template - GH](https://github.com/amazon-archives/aws-full-stack-template)

### What I need to know:
- ACID (Atomicity, Consistency, Isolation, and Durability)

## Database Offerings
### Cloud-Based Databases
#### Nature of Data
- Structured data
  - data that is organized in a way that is easily searchable
  - easy to analyze
  - difficult to change the structure
- Unstructured data
  - data that is not organized in a way that is easily searchable
  - files
- Semi-structured data
  - JSON files loaded into db engine
  - able to be analyzed

#### Relational Databases
- Data in stored in Tables
  - Entities
    - collection of data, in a table
  - Columns
    - attributes of the entity (Field)
  - Rows
    - individual records in the table (Record)

- Relationship between tables are build with keys
  - Primary Key
    - unique identifier for each row
  - Foreign Key
    - key that is used to link two tables together

#### Non-Relational Databases
- Semi-structured data
- Unstructured data
- OLTP web/mobile applications

- Database types
  - Key-Value
    - DynamoDB
    - Need to know the access patterns
  - Document
    - MongoDB
  - In-Memory
    - Redis
    - sub-millisecond latency
  - Graph
    - Neptune

- DynamoDB
  - ACID compliant
  - Point-in-time recovery
  - Global tables
  - millisecond latency
  - Table
    - partition key
      - unique identifier
      - location of data note
    - sort key
      - allows multiple items to be queried as a collection
    - Indexes (access data quickly)
      - local
        - uses the partition key with sort key
      - global
        - partition key and sort that can be different from the table

### Database Architectures
#### Overview
- Two common architectures
  - Server based
    - patch/update maintence
    - software updates
    - scaling
  - Serverless
    - apps hosted in the cloud by third part providers
    - Zero server management
    - pay for what you use
    - auto-scaling, high availability

- When to use which?
  - Serverless
    - small to medium sized applications
    - unpredictable traffic
    - short running tasks
  - Server based
    - large applications
    - predictable traffic
    - long running tasks/computations

#### Server Based Architecture
- Amazon RDS
  - Scaling
    - Vertical
      - increase the size of the instance
  - Engines
    - MySQL
    - PostgreSQL
    - MariaDB
    - Oracle
    - SQL Server
    - Aurora
  - Automation by AWS
    - configuration, management and maintenance
    - configure read replicas or set synchronous replication
    - automated backups and encryption
- Amazon EC2
  - customer responsible for deployment, configuration, and management
    - OS, patching, installs etc
  - Benefits
    - full control
    - supervise maintenance windows, ports, and instances per db
    - configurable to match on-premises db
    - encrypt EBS columes

- Scaling
  - usually with cost and complexity
  - depends on service used for the amount of control/automation available\

#### Serverless Architecture
- Fault tolerant
- high availability
- auto-scaling

- Amazon DynamoDB
  - fully managed
  - automatic scaling for capacity and performance
  - Supports store-models:
    - key-value
    - document
  - Benefits
    - supports ACID transactions
    - no admin overhead for patching, upgrades, scaling
    - Encryption by default
    - easy data replication across multiple regions
    - DAX for caching

- Amazon Aurora Serverless
  - on-demand, auto-scaling
  - MySQL and PostgreSQL compatible
  - Benefits
    - distributed, fault-tolerant, self-healing storage
    - six-way replication
    - pay per second
    - managed by RDS, no hardware provisioning, software patching, setup, configuration, or backups
  - Use Cases
    - Variable workloads
    - Unpredictable workloads
    - New apps
    - Development and testing
    - Multi-tenant apps

### Choosing the Right Database
#### Purpose-Built Databases
- Picking the best database to solve a specific problem
- Pick the database that best fits:
  - the workload
  - data model
  - and access patterns
