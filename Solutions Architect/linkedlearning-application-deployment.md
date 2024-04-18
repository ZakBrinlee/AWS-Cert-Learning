# [AWS Certified Solutions Architect - Associate (SAA-C03) Cert Prep: 7 Application Deployment](https://www.linkedin.com/learning/aws-certified-solutions-architect-associate-saa-c03-cert-prep-7-application-deployment)

Started: April 17, 2024
Completed: April 18, 2024

## Links
- [AWS Solutions Library](https://aws.amazon.com/solutions/#Browse_All_Solutions)
- [AWS Quick Starts](https://aws.amazon.com/quickstart/?solutions-all.sort-by=item.additionalFields.sortDate&solutions-all.sort-order=desc&awsf.filter-content-type=*all&awsf.filter-tech-category=*all&awsf.filter-industry=*all)
- [CloudFront use cases](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/IntroductionUseCases.html)

### What I need to know:
- Understand Kinesis Service and how it works to help manage data streams analytics in real-time
  - Kinesis Data Streams
  - Kinesis Firehose
  - Why would you use Kinesis Data Streams vs Firehose
    - why you want to narrow down data to just what is important to pass on
- Understand the constraints of SNS
- Understand what Simple Workflow Service is and how it works
  - when to use it
- Understand CloudWatch

## Notes
### Designing Cost-Optimized Compute
#### Application and Deployment services
- Implement app logic and code in the cloud
- code execution, data analytics

#### Additional Application services 
- AWS Amplify
  - front-end/back-end full stack deployment
  - auth, storage, apis, analytics etc
  - Angular, Vue, React and Next.js support
  - Includes visual UI design

- AppSync
  - GraphQL based solution for data integration
  - data sources: DynamoDB, Lambda, HTTP
  - acts as GraphQL proxy for data sources

- Device Farm
  - test apps on real devices
  - automated testing
    - appium, calabash and UI automator
  - manual testing options

#### Lambda
- Compute services that runs code in response to events
- No servers to manage
- Scales automatically
- Pay only for compute time, how long the function runs

- use process
  - upload code
  - launch code as Lambda function
  - AWS selects server
  - code is ran when event triggers

#### API Gateway
- API management service
  - create, publish, maintain, monitor and secure APIs
  - ability to interact with many targets
    - AWS services
    - other web services
    - data stored in AWS

- Serverless architecture
  - move data in/out without instances
  - process functions without servers
  - Two main services
    - API Gateway
    - Lambda

- CORS
  - can be enabled for API gateway
  - default is to only allow same-origin requests
    - internal domain requests only
- without enabled errors will be shown

#### Kinesis
- Analytic category
- Real-time data streaming process
  - multi-tier enabler
    - separate analytics from database
- very DevOps focused
- Conceptual importance for architects

- Operating modes/Services
  - Data Streams
  - FireHose
  - Data Analytics
  - Video Streams
    - Media

- Kinesis Benefits
  - architecture is fully managed
  - no custom code required
    - configure producers
      - apps that send the data to kinesis
    - configure consumers
      - apps that read the data from kinesis
    - focus is on the analytics

#### Kinesis Data Streams and Firehose
- Data Streams process
  - Input data is sent to Kinesis
  - Kinesis ingests and stores data streams for processing
  - Processing breaks down data into smaller parts (shards)
    - different services/tools to process
  - Sent to BI tools storage

- FireHose process
  - Input data is sent to Kinesis
  - Ingests, prepares and sends data continuously to chosen destination for storage
    - S3, Redshift, Elasticsearch
  -  Analyze streaming data with BI tools

- Video Streams process
  - Input data like CCTV, drones, etc
  - FH -> Ingests, prepares and sends data continuously to chosen destination for storage
    - S3, Redshift, Elasticsearch, Splunk
  - Output directly to media services processing (ML, AI, etc)

#### Kinesis Data Analytics
- analyze real-time data streams
- SQL based
- supports concurrent consumers
- Mid-stream data analytics
  - looking for specific things

- Process
  - input -> from FireHose or Data Streams
  - SQL -> query data
  - output -> to tools, S3, lambda, email something

#### Reference Architectures
- Well-architected frameworks provided by AWS
- AWS created architecture plans for specific scenarios
  - HIPAA, PCI, UK-OFFICIAL, etc

- Quick Start
  - automated reference deployments built by Amazon Web Services (AWS) solutions architects and AWS Partners

### Designing for Operational Excellence
#### CloudFront
- Networking and content delivery category
- CDN service
  - caches content at edge locations (regionally)
  - reduces latency
  - delivers content to users faster
  - can be used for static and dynamic content

- Implementation Considerations
  - Content source
    - S3
    - MediaPackage channel
    - HTTP server
  - Content access
    - Public
    - Restricted
  - Content constraints options
    - HTTPs required
    - Geo restrictions

- AWS Global Accelerator
  - TCP and UDP traffic
  - improves performance

#### Web Application Firewall
- Controls access to HTTP and HTTPs servers
  - based on requests
  - based on source IP
- Works with CloudFront and ELB

- Behaviors
  - Allow all requests
    - except those that match a rule
  - Block all requests
    - except those that match a rule
  - Monitor all requests
    - requests that match specific params

- Error handling
  - HTTP 403 error
    - forbidden / access denied
  - configurable default behavior
    - request matches no rules (allow|deny?)

#### Simple Queue Service (SQS)
- decouple applications
  - break apps into separate processing tasks
  - allows many small tasks to form a larger solution

- SQS messages
  - Outputs from other processes
  - Inputs to other processes
  - queued and processed async
    - non-linear
  - up to 256kb data per message

- SQS participants
  - Producers
    - create the message and put it into the queue
  - Consumers
    - pulls the message from the queue and processes it
  - messaging service
    - SQS

- Features
  - Redundant across multiple AZs
  - queued until processed
  - retention period
    - 1 minute to 14 days
  - auto scaling

- Types
  - Standard
    - default async type
    - doesn't guarantee sequential delivery
    - at least once delivery
  - FIFO
    - ordered delivery
    - exactly once delivery
    - supports fewer transactions per second

#### Simple Notification Service (SNS)
- "its like paging in the cloud"
- Pub-Sub messaging model

- Publishers
  - publishers push messages to topics
  - Topic examples: 
    - admin alerts, performance alerts, etc
  - Publisher examples:
    - CloudWatch, Cost explorer, etc

- Subscribers
  - clients receiving notifications
  - receive messages from topics
  - unaware of other subscribers or publishers

- Features
  - stored across AZs
  - Several delivery options
    - HTTP/HTTPS
    - Email
    - SMS
    - Lambda
    - SQS

- Limits
  - 256kb per message
  - special SMS constraints
    - 140 byte max per message
    - larger messages are split into multiple messages

#### Simple Workflow
- Defines sequences of tasks for a workflow
- Used in decoupled applications

- Workflow
  - activities
    - result in desired objective
  - Logic that controls the activities
    - starts with a Decider function to determine best workflow
  - Operates in a domain

- SWF activity task
  - one invocation of an activity
    - example: process an order
  - can be invoked multiple times
- SWF activity worker
  - process the activity task (application code)
  - can be run on EC2, Lambda, etc

#### Step Functions
- AWS recommends using Step Functions over SWF
- Similar to SWF in functionality
  - uses state machines
    - decider, activities, workers

### Designing for Elasticity and Scalability
#### OpsWorks
- Easy standardized deployment of instances, services and apps
- Configuration management service
  - Configure code based deployment
    - instance, service, app
  - Operate
    - app updates
    - infrastructure updates
  - Automated deployment

- OpsWorks Stacks
  - initial mode
  - a collection of layers
    - any AWS service + any runtime environment
- OpsWorks for Chef Automate
  - Cookbooks contain recipes
    - recipes are the same as layers
    - recipes are defined configurations
      - admin, AWS, third-party
- OpsWorks for Puppet
  - Master servers (puppet master)
    - pre-configured modules (layers)
    - pre-built layers
      - ruby, php, nodejs, java, RDS, MySQL, HA Proxy

- Use Cases
  - in cloud:
    - use Chef or Puppet
  - on-prem:
    - use Stacks

#### Cognito
- User identity and data synchronization service
  - SSO
- Google, Facebook, Amazon, etc
- Standards
  - OAuth 2.0
  - OpenID Connect
  - SAML 2.0
- Profile management
- Scales any amount of users
- Controls access to AWS resources
  - uses roles/users mapped to roles

#### Elastic MapReduce
- distributes processing across clusters
  - uses Hadoop framework
- Pulls from S3 buckets
- Uses EC2 instances
- User defines # of clusters

- Cluster nodes
  - Master node
    - manages the cluster
    - coordinates jobs across core and task nodes
  - Core nodes
    - run Hadoop tasks
    - store data
  - Task nodes
    - run Hadoop tasks
    - do not store data

- Very heavy large compute tasks to get done faster with parallel processing across many machines

#### CloudFormation
- Uses template to build resources
- Automated deployment

- templates
  - build stacks
- change sets
  - modify stacks

#### CloudFormation properties
- many properties are available and new properties are added regularly

#### CloudWatch
- Monitors the cloud + on-prem systems
- Collects and tracks metrics
- Dashboards available
- Logs of events
- Alarms
  - trigger actions

- Monitor your systems
  - receive notifications
  - take actions based on alarms

#### Trusted Advisor
- Scans AWS environment and provides recommendations
  - cost optimization
  - performance
  - security
  - fault tolerance

#### Organizations
- Collection of AWS accounts
- Centralized management of everything
- Free service

- Organizational units
  - groups of accounts
  - can have multiple levels
    - 5 levels deep
  - Think (IT, Accounting, Marketing, etc)
  - policies can be attached to OUs
