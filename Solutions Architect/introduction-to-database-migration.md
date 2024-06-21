# [Introduction to Database Migration](https://explore.skillbuilder.aws/learn/course/65/play/151/introduction-to-database-migration;lp=1046)

Started: June 20th, 2024
Completed: June 20th, 2024

## Links
- [AWS Database Migration Service](https://aws.amazon.com/dms/)
- [AWS Schema Conversion Tool](https://aws.amazon.com/dms/schema-conversion-tool/)

## Notes
### Schema Migration
#### Introduction to Database Migration
- Reasons to migrate a database
  - moving data from legacy engines to modern engines
  - moving data from one platform to another
  - frequently copy data from one database to another
- Benefits
  - simple to use AWS DMS
  - minimal downtime
  - supports most popular databases
  - low cost
  - fast and easy to setup
  - reliable
- Tools to help 
  - AWS Schema Conversion Tool (SCT)
  - AWS Database Migration Service (DMS)

- AWS Database Migration Service (DMS)
  - Server in the cloud with replication software
  - Create source and target connections
  - DMS creates tables, primary keys, indexes, and foreign keys, triggers, etc
- AWS Schema Conversion Tool (SCT)
  - Converts database schema

- Common migration steps
  - 1. Envisioning and assessment
  - 2. Converting database schemas
  - 3. Converting applications and remediation
  - 4. Converting scripts
  - 5. Integrating with third-party apps
  - 6. Migrating data
  - 7. Functionally testing entire system
  - 8. Testing performance
  - 9. Integrating and deploying
  - 10. Training and transferring knowledge
  - 11. Documenting and controlling versions
  - 12. Planning for support in post-production

#### Envisioning and assessing migration (AWS SCT)
- Step 1 of migration
- Envisioning and accessing migration
- Understand the scope of the migration
  - db schema
  - data volumes
  - data types
  - resources
  - stakeholders
- Evaluate known risks
- Create a business case
  - identify SMEs
  - responsible stakeholders
  - plan capacity

- AWS SCT
  - catalogs the physical and logical components of the system
  - able to provide detailed reports on one+ popular open-source databases
  - Complexity scale
    - 1. Simple/gray - < 1 hour work
    - 2. Medium/orange - 1-4 hours work
    - 3. Complex/red - 4+ hours work
  - Detailed reports of complexity of migration
    - conversion issues
    - manual conversion steps with checklist

#### Converting database schemas 
- convert db objects to target db
  - tables, indexes, constraints, foreign keys, triggers, and stored procedures
  - Does not include actual data migration
- converts source-object definitions to target engine format
- type of alerts provided when converting
  - simple, medium, complex
  - anything not supported by target engine

- Database Migration Playbooks
  - series of guides focused on best practices for creating successful blueprints for migration
  - 5 current playbooks
    - Msft SQL Server to Aurora MySQL
    - Msft SQL Server to Aurora PostgreSQL
    - Oracle to Aurora PostgreSQL

#### Converting Applications
- Porting application code to new database
- often the most challenging part of migration
  - requires understanding of application code
  - may require changes to code
  - may require changes to queries
- AWS SCT can help with this
  - modernize your SQL code to work with new dB
  - extract SQL statements embedded in code
  - track where SQL statements are used
    - convert to SQL that will work with target dB
    - rebuild application program to work with converted code

#### Converting scripts
- Looks at batch scripts used for extract, transform, and load (ETL)
  - db maintenance, disaster recovery, etc
- benefits
  - convert Oracle, msft, and teradata scripts to work run on PostgreSQL dbs

#### Integrating with third-party apps
- validate that third-party apps work with new dB
- access is restored and secured
- may involve updating connections to new dB

### Data Migration
#### Migrating data
- May require translating data types if source and target dBs are different
- challenging if dealing with large data volumes and need to keep sync
- Reasons to use
  - db modernization
    - move legacy engines to modern engines
    - moving platforms
    - replication

- What is AWS DMS
  - server in the cloud with replication software
  - works if either source or target is in AWS
  - ability to select which schemas or tables to migrate
  - ability to monitor progress
  - can validate relational migrations

- How is data moved
- three ways to move data
  - full load
    - initial load of all data
  - ongoing replication (CDC)
    - change data capture
    - captures changes to data
  - full load + ongoing
    - initial load and then captures changes

#### Functionally testing entire system
- ensure that all applications interacting with the database perform as before, from a functional perspective
  - examples
    - data is being written to the correct tables
    - orders are being processed correctly through the system
    - inventory is being updated correctly

#### Tuning performance
- Performance tuning sometimes occurs in parallel with functional testing
- applications are meeting the specified performance requirements

- when issue arises
  - each system level is checked for bottlenecks
  - from user interface to database
  - SQL statements prepared by app
  - database engine and associated layers

#### Integrating and deploying
- processing of moving the new system into production
- typically with a planned series of steps
  - what systems cut over and when

- maintain a roll-back plan and options

### Training and Support
#### Training and transferring knowledge
- critical aspect in deploying any new system
- until the entire team understand the system, consider adding training to team members
- Document and changes from the migration
  - what was changed
  - how it was changed

#### Documenting and controlling versions
- document all changes
- document how the new system operates

- script all steps to utilize infrastructure as code
- treat all artifacts as code
- version control all artifacts

#### Planning for support in post-production
- AWS allows you to automate backups and other support tasks
- Ensure that automated tasks are occasionally checked
- personal trained to support tasks that are not automated
