# [Amazon Redshift Service Primer](https://explore.skillbuilder.aws/learn/course/61/play/141/amazon-redshift-service-primer;lp=1046)

Started: June 12th, 2024
Completed: June 12th, 2024

## Links
- [Amazon Redshift](https://aws.amazon.com/redshift/)
- []()

### What I need to know:

## Notes
### Amazon Redshift
#### Service Introduction
- Scalable data warehouse
  - Uses the following to provide fast performance
    - Machine learning
    - massively parallel query execution
    - columnar storage
      - data is indexed in the same way that queries are executed
    - high-performance disk

- Redshift Spectrum
  - Allows you to run queries against exabytes of data in S3
  - No need to load or transform the data
  - Pay for the queries you run

- Pricing
  - Cluster node types (per hour)
    - On-demand
    - Concurrency scaling pricing (per second that exceeds the daily free limit)
    - Reserved instance pricing
    - Redsift Spectrum pricing (per TB scanned)

#### Service Technical Overview
- Fully managed
- petabyte-scale data warehouse

- The warehouse
  - Nodes
    - a collection of computing resources
    - organized into a group called a cluster
    - each cluster runs an Amazon Redshift engine and contains one or more databases

- Cluster
  - Leader node
    - distributes queries to the compute nodes
  - Compute nodes
    - store data and perform queries and computations
    - partition jobs into Slices
  - Slices
    - partitions of the compute nodes
    - each slice is a unit of parallel processing
    - each slice is assigned a portion of the data
    - each slice processes a portion of the query

- Uses SQL endpoint to connect to the cluster
- Configured to run inside a VPC
- Securing communications
  - HTTPS connections
  - SSL
- Protecting data
  - Encryption at rest
  - KMS for encryption keys
  - aes-256 encryption

#### Service Demonstration
- Getting started with first Redshift cluster
  - Create a VPC
    - holds EC2 instance and Redshift database
  - Create the subnets
  - Create an S3 bucket
  - Create an S3 endpoint
    - Keep the endpoint private and within the VPC
  - Create an IAM role
    - copy data to/from S3
  - Create the security Groups
    - EC2 access for Redshift
    - Access to Redshift from EC2
  - Create the subnet group
    - private subnet for Redshift cluster
