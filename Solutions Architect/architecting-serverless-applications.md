# [Architecting Serverless Applications](https://explore.skillbuilder.aws/learn/course/12716/architecting-serverless-applications;lp=1046)

Started: June 17th, 2024
Completed: June 17th, 2024

## Links
- [Amazon's Builders' Library](https://aws.amazon.com/builders-library/?cards-body.sort-by=item.additionalFields.sortDate&cards-body.sort-order=desc&awsf.filter-content-category=*all&awsf.filter-content-type=*all&awsf.filter-content-level=*all)
- [Serverless Patterns](https://serverlessland.com/patterns)
- [Serverless Application Repository](https://aws.amazon.com/serverless/serverlessrepo/)

### What I need to know:
- The key to thinking serverless is thinking in terms of patterns and applications, rather than in terms of individual functions or resources

- Other recommended courses:
  - [Getting into the Serverless Mindset]()
  - [Introduction to Serverless Development]()

## Notes
### Serverless Application Architectures
#### Migrating to Serverless
- Top questions to consider
  - How do you implement computing infrastructure?
  - How do you approach application development and deployment?

- 3 migration patterns when migrating legacy applications to serverless
  - Leapfrog
    - Straight from legacy to serverless - leapfrogging over hybrid
  - Organic
    - Lift and shift to serverless
      - Apps are left as is, but the infrastructure is moved to serverless
  - Strangler
    - incrementally replace parts of the legacy app with serverless components
    - Over time, the legacy app is replaced by a serverless app

- Considerations
  - What does the app DO and how is it ORGANIZED?
  - How can the data be broken apart by command query responsibility segregation (CQRS)?
    - What belonds on the control plane and what belongs on the data plane?
  - How does the applications SCALE and what COMPONENTS DRIVE the CAPACITY you need?
  - Do you have schedule-based tasks?
  - Do you have workers listening to a queue?
  - Where can you refactor or enhance functionality without impacting the current implementation?

#### Choosing Compute Services and Data Stores
- Lambda & Fargate
  - Lambda
    - 15 minute or less runtimes
    - unpredictable workloads
    - smaller applications
    - real-time data processing
  - Fargate
    - Great for lifting and shifting existing containerized applications to serverless
    - longer running processes or larger deployments
    - predictable and consistent workloads

- Matching data stores
  - NOSQL
    - S3
      - claim-check pattern
      - flexible object storage
    - DynamoDB
      - key/value store
    - Elasticache for Redis
      - in-memory caching 
    - Quantum Ledger Database (QLDB)
      - immutable, cryptographically verifiable ledger
  - Relationional
    - Aurora Serverless
      - on-demand, auto-scaling
    - Auroa
      - MySQL and PostgreSQL compatible
      - parallelized transactional data
    - RDS
      - MySQL, PostgreSQL, MariaDB, Oracle, SQL Server
      - managed relational databases

- Separate and model data stores into transactional (instead of query needs)
- Use concepts from CQRS to separate data stores

- S3
  - data lakes
  - claim-check pattern
  - filter data retrieved by Lambda
- DynamoDB
  - key/value store
  - partition key and sort key
  - capture changes with DynamoDB Streams
- ElastiCache for Redis
  - in-memory caching
- Quantum Ledger Database (QLDB)
  - immutable, cryptographically verifiable ledger
- Aurora
  - MySQL and PostgreSQL compatible
- Aurora Serverless
  - on-demand, auto-scaling
- RDS
  - MySQL, PostgreSQL, MariaDB, Oracle, SQL Server
  - managed relational databases

#### Application Architecture Patterns
- Automation
  - Use AWS Step Functions to automate workflows

- Serverless web/mobile app
  - incorporate async connections

- challenges
  - real-time data experiences
  - access data offline/low-speed connections
  - sync data across devices
  - multiple connection
  - support transacational and query data

- AWS Appsync
  - single endpoint
  - GraphQL

- Best practices
  - dont reinvent the wheel
  - dont port your code
    - apply event-drivent thinking
  - stay current
  - prefer idempotent, stateless functions
  - Keep events inside AWS services for as long as possible
  - Verify the limits of all services of app