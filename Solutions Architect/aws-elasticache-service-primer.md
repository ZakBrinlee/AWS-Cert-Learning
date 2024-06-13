# [Amazon ElastiCache Service Primer](https://explore.skillbuilder.aws/learn/course/61/play/143/amazon-elasticache-service-primer;lp=1046)

Started: June 12th, 2024
Completed: June 12th, 2024

## Links
- [ElasticCache website](https://aws.amazon.com/elasticache/)
- [User Guides](https://docs.aws.amazon.com/AmazonElastiCache/latest/red-ug/WhatIs.html)

### What I need to know:

## Notes
#### Service Introduction
- Fully managed Redis and Memcached distributed memory cache
- deploy, run and scale popular open-source compatible in-memory data stores
- repository of frequently accessed data
- improves latency and throughput
- sits between EC2 and database
- auto-scales on demand
- centralized cache
- remote cache type

- Redis
  - session caching
  - message queue applications
  - leaderboards
  - full-page caching

- Memcached
  - small and static data
  - HTML/CSS files

- Pricing
  - on-demand nodes
    - per hour/per nodes
  - reserved nodes
    - 1 or 3 year terms
    - per hour/per nodes
  - each snapshot stored past 1 is charged per gb/month
  - data transfer out

#### Service Technical Overview
- sub-millisecond latency
- 3 common types of data caching
  - Built-in
  - Application
  - Remote
    - centralized in-memory repository
    - externally from dB in non-relational key-value store

- Common approached
  - lazy loading
    - reactive
    - only loads data when requested
  - write-through
    - proactive
    - writes data to cache when added to DB

- Security
  - IAM for access control
  - VPC for network isolation
  - Security groups for network access control
  - on-premis access via VPN or Direct Connect
  - Encryption at rest and transit

#### Service Demonstration
- Steps to get started with ElastiCache node and important settings/configurations
  - Create a VPC
    - holds the resources for EC2 and ElastiCache cluster
  - Create subnets
    - two private subnets (in different AZs)
    - one public subnet (EC2 instance)
  - Create security groups
    - one for EC2 instance SSH access
    - one for ElastiCache access from EC2
  - Create an EC2 instance
    - compute for the db
  - Install the Redis CLI
  - Create a subnet group
    - private subnet for database
