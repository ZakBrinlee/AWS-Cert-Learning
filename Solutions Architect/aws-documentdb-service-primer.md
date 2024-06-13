# [Amazon DocumentDB Service Primer](https://explore.skillbuilder.aws/learn/course/61/play/142/amazon-documentdb-service-primer;lp=1046)

Started: June 12th, 2024
Completed: June 12th, 2024

## Links
- [Amazon DocumentDB](https://aws.amazon.com/documentdb/)
- [DocumentDB developer resources](https://docs.aws.amazon.com/documentdb/latest/developerguide/what-is.html)

### What I need to know:

## Notes
#### Service Introduction
- MongoDb compatible
- fully managed database service
- same application code, drivers, and tools that you use with MongoDB

- JSON documents are first class objects in the DB
- data is stored in a collection
  - collection is a group of documents
  - documents are a group of key-value pairs
- Can be used for content management
- Real-time operations

- Pricing
  - pay for what you use
  - on-demand instances (per hour/per partial second)
- Storage
  - auto-scales
  - per gb/month
- Backups
  - automated
  - point-in-time recovery
- IOPS
  - provisioned IOPS
  - per million requests increments
- Data transfered out
  - per gb/month

#### Service Technical Overview
- performant, scalable, and highly available

- Foundations
  - Cluster
    - one or more instances
    - one or more storage volumes
    - stores 6 copies across 3 AZs
  - Primary instance
  - Replica instances
  - Only runs in a VPC

- Security
  - IAM for access control
  - VPC for network isolation
  - Encryption at rest
    - cluster, indexes, logs, replicas, snapshots, etc
  - TLS for data in transit
  - KMS for encryption keys


#### Service Demonstration
- Steps to get started with DocumentDB cluster, loading and query data
  - Create a VPC
    - holds the resources for EC2 and DocumentDB
  - Create subnets
    - two private subnets (in different AZs)
    - one public subnet (EC2 instance)
  - Create security groups
    - one for EC2 instance
    - one for DocumentDB
  - Create an EC2 instance
    - compute for the db
  - Transport Layer Security (TLS) for data in transit
  - Create a subnet group
    - private subnet for database
