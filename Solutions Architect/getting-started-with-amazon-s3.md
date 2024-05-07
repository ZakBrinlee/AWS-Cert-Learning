# [Getting Started with Amazon Simple Storage Service (Amazon S3)](https://explore.skillbuilder.aws/learn/course/161/getting-started-with-amazon-simple-storage-service-amazon-s3)

Started: May 6, 2024
Completed: May 6, 2024

## Links
- [Blocking public access to your Amazon S3 storage](https://docs.aws.amazon.com/AmazonS3/latest/userguide/access-control-block-public-access.html#access-control-block-public-access-policy-status)

### What I need to know:
- Bucket policy when to use
  - Use a bucket policy if:
    - You need to grant cross-account permissions to other AWS accounts or users in another account, without using IAM roles.
    - Your IAM policies reach the size limits for users, groups, roles. 
    - You prefer to keep access control policies in the Amazon S3 environment.
    - Although both bucket and user policies support granting permission for all Amazon S3 operations, the user policies are for managing permissions for users in your account.

- IAM policy when to use
  - Use an IAM policy if:
    - You need to control access to AWS services other than Amazon S3. IAM policies allow for easier centralized management all of your permissions.
    - You have numerous Amazon S3 buckets each with different permissions requirements. IAM policies will be easier to manage than having to define a large number of Amazon S3 bucket policies. This way you can focus on having fewer, more detailed IAM policies.
    - You prefer to keep access control policies in the IAM environment.

## Notes
### Amazon S3 Fundamentals
#### Storage Fundamentals
- Covers the 3 types of storage: block, file, and object

#### Amazon S3 Fundamentals
- Ability to organize objects to imitate a hierarchy by using key name prefixes and delimiters
  - Prefixes and delimiters allow you to group similar items to help visually organize and easily retrieve your data

- Limitations
  - Cannot be transferred between accounts
  - Unable to change bucket name once created
  - Unable to nest buckets

- Tagging
  - key-value pairs and apply to a whole bucket or to individual objects to help with identification, searches, and data classification
  - Benefits
    - Object tags enable fine-grained access control of permissions. For example, you could grant an IAM user permission to read-only objects with specific tags.
    - Object tags enable fine-grained object lifecycle management in which you can specify a tag-based filter, in addition to a key name prefix, in a lifecycle rule.
    - When using Amazon S3 analytics, you can configure filters to group objects together for analysis by object tags, key name prefix, or both prefix and tags.
    - You can also customize Amazon CloudWatch metrics to display information by specific tag filters. The next lesson provides more details.

- Bucket Tags
  - Use tags to understand the cost of your storage and to manage your storage costs
  - Tag-set
    - A collection of tags for a bucket
- Object Tags
  - ability to categorize and query your storage
  - 10 tags per object

- Replication
  - Cross region + Same region capabilities

#### Interfacing with Amazon S3
- 3 Ways to interact with S3
  - Console
  - CLI
  - SDK

- Buckets can be used as virtually hosted domains
  - `http://bucket-name.s3-website-region.amazonaws.com`
    - virtual-hosted–style URL, the bucket name is part of the domain name in the URL, which makes the URL easier to read, and more end-user friendly

- DNS request step-by-step:
  - The client wants to view the dolphins.jpg object stored on Amazon S3. The client makes a DNS request to get the address of s3.amazonaws.com. 
  - The client receives one or more IP addresses for facilities that can process the request. In this example, the IP address is for Facility B.
  - The client makes a request to Amazon S3 Facility B.
  - Facility B returns a copy of the dolphin.jpg object to the client.

### Data Management and Security
#### Amazon S3 Data Management
- Strongly consistent read-after-write
- Versioning
  - Versioning-enabled buckets enable you to recover objects from accidental deletion or overwrite
    - If you delete an object, instead of removing it permanently, Amazon S3 inserts a delete marker, which becomes the current object version. You can always restore the previous version
    - If you overwrite an object, it results in a new object version in the bucket. You can always restore the previous version

- Command Line Usage
  - High-level commands
    - simplify managing objects and buckets
  - Low-level commands
    - provide more granular control over objects

- Multi-Part Uploads
  - Upload large objects in parts
  - Benefits
    - Improved throughput
    - Quick recovery from network issues
    - Pause and resume uploads
    - Begin an upload before you know the final object size

#### Cloud Data Migration Services
- level of online connectivity is a major factor in data migration

- Online transfer services
  - AWS DataSync
    - Synchronize data between on-premises storage and AWS storage services
    - Automate data transfer tasks up to 10 times faster than open-source tools
  - AWS Transfer family
    - Fully managed service to get files into and out of AWS storage services
    - integrates with existing authentication systems + dns routing
  - S3 Transfer Acceleration
    - Speeds up transfers to and from S3 by using the CloudFront network
  - Amazon Kinesis Data Firehose
    - Load data streams into S3
  - Amazon Kinetic Data Streams
    - Collect and process large streams of data records in real-time
  - Amazon Partner Network
    - 3rd party connectors

- Offline transfer services
  - AWS Snowcone
    - smallest device
    - 8tb of storage
  - AWS Snowball
    - 50tb or 80tb of storage
    - Two options
      - Edge Storage Optimized
      - Edge Compute Optimized
  - AWS Snowmobile
    - Exabyte-scale data transfer service
    - 100PB per Snowmobile

- Hybrid cloud services
  - AWS Direct Connect
    - Dedicated network connection between on-premises and AWS
    - Higher throughput and secure data transfer
  - AWS Storage Gateway
    - Hybrid cloud storage service that enables on-premises applications to use AWS storage services

#### Securing Data Access
- Principle of Least Privilege
  - Only grant the permissions required to perform a task

- Security Mechanisms
  - IAM
    - IAM is used to create users and manage their respective access to resources, including buckets and objects.
  - Bucket Policies
    - Bucket policies are used to configure permissions for all or a subset of objects using tags and prefixes.
  - Access Control Lists
    - Define who can access objects and what they can do with them
  - Pre-Signed URLs
    - Pre-Signed URLs are used to grant time-limited access to others with temporary URLs.

- Block Public Access feature
  - Prevents public access to buckets and objects
  - Can be enabled at the account or bucket level
  - 5 settings
    - Block all public access
    - Block public access granted through new ACLs
      - prevents you from creating any new ACL, either for a bucket or object, which grants public access permissions
      - After you enable this option, you should then review your ACLs to evaluate any existing public access permissions and assess whether or not those permissions should stay the same
    - Block public access granted through any ACLs
      - ignores any existing ACLs that grant public permission on buckets and objects
    - Block public access granted through new public bucket policies
      - prevents you from creating any new bucket policies, previous ones are still in effect
    - Block public and cross-account access granted through any public bucket policies
      - prevents you from creating any new bucket policies that grant public or cross-account access
      - existing policies are still in effect

- Query string authentication
  - use query parameters to provide request information, including the authentication information
  - referred to as a presigned URL
  - grant time-limited access to objects in your bucket

#### Encrypting Data
- Server-Side Encryption
  - SSE-S3
    - Amazon S3 manages the keys
  - SSE-KMS
    - AWS Key Management Service (KMS) manages the keys
  - SSE-C
    - You/customer manage the keys

#### Amazon S3 Service Integration
- Data lakes
  - Store and analyze large amounts of data
  - Use S3 as a data lake
  - 11 9's of durability

- S3 data lake features
  - Decoupling storage from compute
    - use EC2 instances to analyze data stored in S3
  - Centralized data architecture
    - store data in a single location
  - Integration with clusterless and serverless AWS services
    - Amazon Athena, Amazon Redshift Spectrum, Amazon Rekognition, and AWS Glue to query and process data
    - AWS Lambda to run code without provisioning or managing servers
  - Standardized APIs
    - RESTful APIs

- Data Cataloging
  - AWS Glue
    - Catalogs data, generates ETL code, and runs ETL jobs
  - AWS Lake Formation
    - Simplifies the process of building, securing, and managing data lakes

- In-place data querying
  - Amazon Athena
    - Query data in S3 using standard SQL
  - Amazon Redshift Spectrum
    - Query data in S3 using Redshift
  - Amazon FSx for Lustre and Amazon S3 data lakes
    - Amazon FSx for Lustre can use Amazon S3 as a raw data repository as well as a repository for processed data