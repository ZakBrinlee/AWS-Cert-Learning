# [Amazon DynamoDB - Troubleshooting](https://explore.skillbuilder.aws/learn/course/12617/amazon-dynamodb-troubleshooting)

Started: May 17th, 2024
Completed: May 17th, 2024

## Links
- []()
- []()

### What I need to know:

## Notes
### Introduction
#### Overview of DynamoDB
- NoSQL database service
- Fully managed

- Benefits
  - millisecond latency
  - multi-region replication
  - data encryption
  - integration with other AWS services

- Concepts + Terminology
  - Tables
    - A collection of data
  - Items
    - A single data record
    - group of attributes that are uniquely identifiable
    - (rows, records, or tuples)
  - Attributes
    - A single data element on an item
    - (columns, fields, or properties)
  - Primary Key
    - Unique identifier for each item in a table
    - Two types
      - Partition key
        - (hash key)
      - Partition key and sort key
        - key for which the data is sorted
  - Secondary Indexes
    - Allow for querying on non-primary key attributes
  - Streams
    - Capture changes to items in a table
  - Read capacity units (RCUs)
    - Read throughput for a table
    - 1 strongly consistent read per second
    - 2 eventually consistent reads per second
      - up to 4 KB in size
  - Write capacity units (WCUs)
    - Write throughput for a table
    - 1 write per second
      - up to 1 KB in size
  - Throttling
    - limits on the number of reads and writes per second
  - Read/Write capacity mode
    - On-demand
    - Provisioned

#### Gathering Info with AWS Management Console
- Dashboard shows details of each table
- Detailed view of each table is possible
- Monitoring tab shows metrics taken by CloudWatch

#### Using the CLI to Gather Info
- CLI common commands
  - list-tables
  - describe-table
  - get-item
  - describe-limits
```
aws dynamodb list-tables // list all tables in the region
aws dynamodb describe-table --table-name <table-name> // get details of a table
aws dynamodb get-item // get an item from a table with given primary key
aws dynamodb describe-limits // get limits for the account - returns the current provisioned-capacity quotas
``` 
- CloudWatch monitoring
  - Captures events
    - user activity
    - ip address, etc.

#### Monitoring DynamoDB
- You should collect monitoring data from all parts of your AWS solution to help troubleshoot a multipoint failure if one occurs
  - What are your monitoring goals?
  - What resources will you monitor?
  - How often will you monitor these resources?
  - What monitoring tools will you use?
  - Who will perform the monitoring tasks?
  - Who should be notified when something goes wrong?

- Available metrics
  - account metrics
  - table metrics
  - table operation metrics
  - global secondary index metrics


### Troubleshooting
#### Determining the Problem
- 1. Identify the problem
  - Look for characteristics of the problem
    - What errors are in the console or log files?
    - Are customers getting error messages?
    - What messages or codes are the users getting
- 2. Gather information
  - Look at the logs, metrics, etc
- 3. Analyze the information
  - Look for patterns
- 4. Review documentation
  - Look for known issues
- 5. Try known solutions
  - apply solutions to the problem

#### Troubleshooting DynamoDB Tables that are Throttled
- Throttling could be caused by either DynamoDB or the applications that read or write into your DynamoDB table
  - common issues
    - Your DynamoDB table has adequate provisioned capacity, but most of the requests are being throttled.
    - You activated AWS Application Auto Scaling for DynamoDB, but your DynamoDB table is being throttled.
    - Your DynamoDB table is in on-demand capacity mode, but the table is being throttled.
    - You have a hot partition in your table.
  - metrics associated with throttling
    - ThrottledRequests
    - ReadThrottleEvents
    - WriteThrottleEvents
    - ThrottledPutRecordCount
    - OnlineIndexThrottleEvents

- Common causes of table throttling?
  - Traffic is more than double the previous peak
    - 30 minute period
  - Traffic exceeds the per-partition throughput limit
    - 3000 RCUs or 1000 WCUs

#### Troubleshooting Observed Latency in DynamoDB
- analyzing the CloudWatch metric **SuccessfulRequestLatency**, it's a best practice to check the average latency
- Monitor the SuccessfulRequestLatency metric to determine whether requests are still throttled or latency is below an acceptable threshold.

- Strategies to reduce latency
  - Reduce the request timeout settings
  - Reduce distance between client and DynamoDB endpoint
    - look at global tables
  - Use caching
    - DynamoDB Accelerator (DAX)
  - Send constant traffic or reuse connections
  - Use eventually consistent reads

### Getting Help
#### Resources
- AWS Knowledge Center
- Amazon DynamoDB Developer Guide
- Official AWS YouTube channel
- Official AWS Twitch channel
- AWS CLI Command Reference 
- API Reference
- DynamoDB workshops

- Peer engagement
  - AWS re:Post 

#### Support 
- What data is needed prior to contacting support?
  - 1. A clear description of the problem you are experiencing
  - 2. Expected outcome: What behavior will you see when the problem is resolved?
  - 3. Steps to reproduce the problem, if applicable and feasible
  - 4. Your account number
  - 5. Helpful information for AWS Support, such as:
    - Time frame of problematic behavior (for example, every morning at 8 AM)
    - AWS Region
    - Table name(s)
    - AWS SDK used
  - 6. Any error messages produced, including output captured (if using AWS CLI tools) or console screenshots (if using the AWS Management Console) and logs produced by any tools such as CloudTrail, access logs, Amazon VPC flow logs (if relevant), and request tracing
  - 7. Context about the issue: Additional details, such as what kind of application is running on the targets and what backend databases they must access, to help the engineer quickly test the solution, troubleshoot, and determine possible causes
  - 8. Any attempted troubleshooting steps already taken and their results
