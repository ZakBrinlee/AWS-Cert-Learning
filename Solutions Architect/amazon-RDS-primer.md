# [Amazon RDS Service Primer](https://explore.skillbuilder.aws/learn/course/287/amazon-rds-service-primer)

Started: May 14th, 2024
Completed: May 14th, 2024

## Notes
### Amazon Relation Database Service (RDS)
#### Service Introduction
- Automates time-consuming tasks
  - hardware provisioning
  - OS & database setup
  - patching
  - backups

- Multi-AZ deployments
  - synchronous replication
  - automatic failover
  - automatic backups

- Database engines
  - MySQL
  - PostgreSQL
  - MariaDB
  - Oracle
  - SQL Server
  - Aurora

- Billing (3 parts)
  - Instance hosting the databases
    - On-Demand (hourly)
    - Reserved Instances (1-3 years)
  - Storage + I/O consumed
    - GB/month
    - I/O requests per million
  - Amount of data transferred
    - GB/month

#### Service Technical Overview
- DB engine manages/runs all DB tasks
- Instance class
  - CPU, memory, storage

- Considerations
  - Proximity to the internet
    - Restrict access to the DB by placing in a VPC (best practice)
  - Controlling access
    - Security groups
      - DB, VPC and EC2
    - IAM
  - Securing Communications
    - Data in transit
    - Uses SSL
  - Protecting data at rest
    - Data encryption

#### Service Demonstration
- Step 1: Choose Database
  - Configure Database settings
- Step 2: Create Database
- Step 3: Add data to the database
- Step 4: Query the data
