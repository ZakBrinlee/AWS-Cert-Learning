# [Amazon Neptune Service Primer](https://explore.skillbuilder.aws/learn/course/amazon-neptune-service-primer;lp=1046)

Started: June 11th, 2024
Completed: June 11th, 2024

## Links
- [Amazon Neptune](https://aws.amazon.com/neptune/)
- [Getting Started Guide](https://docs.aws.amazon.com/neptune/latest/userguide/intro.html)
- [Loading data into Neptune](https://docs.aws.amazon.com/neptune/latest/userguide/bulk-load.html)

### What I need to know:

## Notes
### Amazon Neptune Service Primer
#### Service Introduction
- Fully managed graph database service
  - Non-relational database
  - ACID compliant
  - Apache TinkerPop
  - RDS SPARQL

- Use cases
  - social networking
  - recommendation engines
  - fraud detection

- Billing
  - Pay for DB instance hours
  - Pay for storage
  - Request to Database
  - Data transfer out of the database

#### Service Technical Overview
- Utilized Database instances
  - primary database
  - read replicas (up to 15)
  - cluster volume
    - copies of the data across multiple AZs

- Neptune endpoints
  - cluster endpoint
    - connects to current primary instance
  - reader endpoint
    - one of the read replicas
  - instance endpoint
    - specific DB instance

- Security of data
  - IAM for access control
  - HTTPS encrypted client connections for DB access
    - AES-256 encryption at rest
    - KMS for encryption keys

- Example use case
  - Real-time streaming architecture
    - Collect
      - Kinesis Data Streams from multiple sources
    - Process
      - AWS Lambda gathers stream into a batch, then sent to Neptune for storage
    - Store
      - Neptune stores the data

#### Service Demonstration
- Steps to get started with Neptune cluster, loading and verifying data in database
  - Create a VPC
  - Create the subnets
    - Two private subnets (in different AZs)
    - One public subnet (EC2 instance)
  - Create an Amazon EC2 instance
  - Create Security Groups
    - Neptune SG (SSH access to EC2 Neptune project)
    - EC2 SG (Access from EC2)
  - Create IAM role
    - Neptune access to S3 for loading data
