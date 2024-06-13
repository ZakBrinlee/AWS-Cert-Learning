# [Amazon Quantum Ledger Service Primer](https://explore.skillbuilder.aws/learn/course/61/play/144/amazon-quantum-ledger-database-qldb-service-primer;lp=1046)

Started: June 12th, 2024
Completed: June 12th, 2024

## Links
- [Quantum Ledger Database](https://aws.amazon.com/qldb/)
- [Developer resources](https://aws.amazon.com/qldb/resources/)

### What I need to know:

## Notes
#### Service Introduction
- fully managed ledger database
  - transparent, immutable, cryptographically verifiable transaction log
  - tracks each and every application data change
  - maintains complete and verifiable history of changes over time
  - system of record
  - supports PartiQL query language

 - Immutable & Transparent
   - journal of accurate and sequenced changes
   - cannot be deleted or modified
   - will then store data into tables
 - Cryptographically verifiable
   - hash functions to create a secure output file of changes (Digest)
     - Digest
       - proof of data change history
     - secure chain of changes (digest chain)
       - proof of data integrity
 - Serverless
   - no servers to manage
   - scales automatically
   - Create ledger, define tables, and run queries

- Uses
  - Finance
    - keeps track of financial transactions
  - Insurance
    - keeps track of claims
  - Manufacturing
    - keeps track of supply chain
  - Retail
    - keeps track of inventory
  - Healthcare
    - keeps track of patient records
  - etc

- Pricing
  - Storage per GB/month
    - history
    - indexes
    - tables
  - IOs per million
    - data in/data out our of QLDB

#### Service Technical Overview
- Supports
  - ACID transactions
  - SQL like query language
  - automatic scaling

- Foundation
  - deployed in multiple AZs
  - fully recoverable from failures
  - strongly durable
  - a write action is only acklowledged after it is durably stored in multiple AZs

- Ledger
  - a collection of tables
  - a journal of all changes to tables (immutable)
- Tables
  - a collection of documents revisions
    - includes the record of a deletion
  - ION Form
- Journal
  - sequence of changes to tables
  - Blocks that are chained together

- PartiQL
  - provides SQL query access across multiple data sources
  - queriable views of journal data

- 3 ways to view data
  - User View
    - current state of the data
  - Commited
    - all changes to the data
    - User view + system data
  - History
    - runs a history function on the query
    - all changes based on the commited view

- Security
  - IAM for access (identity based policies)
  - Monitoring
    - CloudWatch (alarms, events, logs)
