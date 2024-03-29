# [AWS Technical Essentials](https://explore.skillbuilder.aws/learn/course/internal/view/elearning/1851/aws-technical-essentials)

Started: March 23rd, 2024
Completed: March 29th, 2024

## Top Notes
- Course builds an application to understand the concepts
  - Employee directory that stores images and information about fictional employees

### Links
- [Elastic Load Balancer features](https://aws.amazon.com/elasticloadbalancing/features/#Product_comparisons)
- [How AWS WAF works](https://docs.aws.amazon.com/waf/latest/developerguide/how-aws-waf-works.html)

### Project Application
- AWS Services
  - Networking
  - Compute
    - EC2 instance
      - Assigned a IAM role: `AmazonS3FullAccess`
  - Storage
  - Databases
  - Monitoring
  - Load Balancing
  - Scaling
  - Security
- Notes

### Introduction to AWS
- 3 cloud deployment models
  - Cloud
  - Hybrid cloud
  - On-premises
- Availability Zones
  - 3+ data centers
  - Isolated from each other
  - Connected by high-speed, low-latency networks
- Region
  - Considerations
    - Compliance
      - May require data/resources in a certain way (restricted to geographic location)
    - Latency
      - Global customers would require resources in multiple regions
    - Pricing
      - Varies from region to region
    - Service availability
      - Not every service is available in every region
- Edge Locations
  - Content delivery network (CDN)
  - Caches content at locations closer to users
  - Reduces latency
- AWS Global Infrastructure
  - 400+ edge locations
- Protecting Root User
  - Enable MFA
- IAM Roles
  - No static login credentials
  - IAM roles are assumed programmatically
  - Temporary credentials for configurable amount of time
  - credentials expire and rotated
- 
### AWS Compute
- Virtual Machines
- Containers
- Serverless
#### Getting Started with Amazon EC2
- web service that provides secure, resizable compute capacity in the cloud. 
- With this service, you can provision virtual servers called EC2 instances. 
- Instance family types
  - General purpose
  - Compute optimized
  - Memory optimized
  - Accelerated computing
  - Storage optimized
#### Amazon EC2 Instance Lifecycle
- Launch
  - Pending
    - Running
      - Stopping
        - Stopped
      - Shutting down
        - Terminated
    - Rebooting
#### Container Services
- Container Orchestration
  - Starting, stopping, restarting, monitoring and more for a cluster of EC2 instances
- Services
  - Amazon Elastic Container Service (ECS)
    - end-to-end container orchestration service that helps you spin up new containers
  - Amazon Elastic Kubernetes Service (EKS)
    - managed service that you can use to run Kubernetes on AWS without needing to install, operate, and maintain your own Kubernetes control plane or nodes.
- VM vs Container
  - Containers share the OS of the host machine
  - VM container their own OS
- Container
  - More lightweight than a VM
#### Intro to Serverless
- Unable to see or access the underline infrastructure of the server/compute
  - AWS Lambda
    - Run code without provisioning or managing servers
    - Pay only for the compute time you consume
    - Scales automatically
    - Supports multiple languages
    - Event-driven
    - Serverless applications
      - No server management
      - Flexible scaling
      - High availability
      - No idle capacity
      - Pay for value
- Convenience over control
#### Serverless with AWS Fargate
- AWS Fargate
  - Serverless compute engine for containers
  - Run containers without having to manage the underlying infrastructure
  - Define app content, networking, storage, and scaling requirements
#### Serverless with AWS Lambda
- Code ran when triggered
  - Triggers are events
- Run time of under 15 minutes
- 7 Lambda Concepts
  - Function
    - resource that you can invoke to run your code in Lambda
  - Trigger
    - describe when a Lambda function should run
      - Almost anything can trigger a lambda function
  - Event
    - JSON document that contains data for a Lambda function to process
    - Gets passed to the function as an argument
  - Application Environment
    - Set of configuration values that your Lambda function can use
    - manages the processes and resources that are required to run the function
  - Deployment Package
    - A .zip file archive – This contains your function code and its dependencies. Lambda provides the operating system and runtime for your function
    - A container image – This is compatible with the Open Container Initiative (OCI) specification. You add your function code and dependencies to the image. You must also include the operating system and a Lambda runtime.
  - Runtime
    - The programming language that you choose to write your Lambda function
      - Runtime options: Node.js, Python, Ruby, Java, Go, .NET Core, and custom runtime
  - Lambda function handler
    - The method in your code that processes events
      - Runs when the function is invoked
      - Receives event data and context information
      - Returns a response to the caller

### AWS Networking
- Networking is how you connect computers around the world and allow them to communicate with one another.
#### Amazon VPC
- Virtual Private Cloud
  - Boundary between your network and the internet
  - Isolate your applications/resources from everything else
  - Control over IP address range, subnets, route tables, and network gateways

#### Amazon VPC Routing
- Main Route Table
  - set of rules, called routes, that are used to determine where network traffic is directed
#### Amazon VPC Security
- Network Access Control Lists
  - Firewall at the subnet level
  - Allows traffic in and out by default
    - Inbound and outbound rules must be created if you want two way from an IP
  - Stateless
  - Rules are evaluated in order
- Security Groups
  - Blocks all inbound traffic by default
  - Allows all outbound traffic by default
  - Stateful
  - Will remember the inbound rule and allow the response
  - Rules are evaluated in order

### Databases on AWS
- Hosting on EC2
  - Customer still responsible for
    - App optimization
    - Scaling
    - High Availability
    - Database backups
    - DB s/w patches
    - DB s/w installs
- Managed DB
  - Customer responsible
    - App optimization

#### Amazon RDS
- Relational Database Service
  - Managed service that makes it easy to set up, operate, and scale a relational database in the cloud
  - Supports multiple database engines
    - MySQL
    - PostgreSQL
    - MariaDB
    - Oracle
    - SQL Server
    - Amazon Aurora
      - ability to scale to petabytes
  - 

- DB instances are placed in a private subnet in 1AZ
  - Ability to configure data replication in multiple AZs
  - Automated backups

#### Amazon DynamoDB
- Serverless database
- NoSQL
- fully encrypted at rest
- Purpose built for applications that need consistent, single-digit millisecond latency at any scale
- All your data is stored on SSDs and is automatically replicated across multiple Availability Zones in a Region, providing built-in high availability and data durability.
- Create database tables that can store and retrieve any amount of data and serve any level of request traffic. 
- Scale up or scale down your tables' throughput capacity without downtime or performance degradation. 
- Monitor resource usage and performance metrics using the AWS Management Console

### Monitoring, Load Balancing, and Scaling
#### Monitoring
- Metrics that are monitored over time are called "statistics"
- CloudWatch
  - a way to collect and analyze data about the operational health and usage of your resources
- Many benefits from monitoring
  - Respond proactively to issues
  - Improve performance and reliability
  - Recognize security threats and events
  - Make data-driven decisions
  - Create cost-effective solutions

#### Amazon CloudWatch
- Monitor
  - Collect and track metrics
  - Collect and monitor log files
  - Set alarms

- Possibilities of CW
  - Detect anomalous behavior in your environments.
  - Set alarms to alert you when something is not right.
  - Visualize logs and metrics with the AWS Management Console.
  - Take automated actions like scaling.
  - Troubleshoot issues.
  - Discover insights to keep your applications healthy.

- CloudWatch Alarms
  - 3 states an alarm can be in
    - ALARM
    - OK
    - INSUFFICIENT_DATA

- CloudWatch Logs
  - Monitor, store, and access log files from EC2 instances, CloudTrail, and other sources
  - Ability to query log data

#### Traffic Routing with Elastic Load Balancing
- Load Balancers
  - Distributes tasks across a set of resources
  - Even though ELB auto scales, you still need to ensure the app layer can scale with it
- Types of Load Balancers
  - **Application Load Balancer**
    - Layer 7
    - HTTP/HTTPS
      - Need to configure 3 components
        - Listener
        - Target Group
          - Type of backend resources
        - Rule
          - Defines how the requests are routed
          - can be path based routing
    - User Authorization
    - Rich Metrics and logging
    - Redirects
    - Fixed Responses
  - **Network Load Balancer**
    - Layer 4
    - TCP/UDP/TLS
    - TCP and User Datagram Protocol (UDP) connection based
    - Source IP preservation
    - Low latency
    - routing connections from a target in the target group based on IP protocol data
  - **Gateway Load Balancer**
    - Layer 3 and 4
    - IP
    - Health checks
    - GLB endpoints
    - Higher availability for third-party virtual appliances
    - helps you to deploy, scale, and manage your third-party appliances, such as firewalls, intrusion detection and prevention systems, and deep packet inspection systems.

- Key Features
  - **Hybrid Mode**
    - Because ELB can load balance to IP addresses, it can work in a hybrid mode, which means it also load balances to on-premises servers.
  - **High Availability**
    - ELB is highly available. The only option you must ensure is that the load balancer's targets are deployed across multiple Availability Zones.
  - **Scalability**
    - In terms of scalability, ELB automatically scales to meet the demand of the incoming traffic. It handles the incoming traffic and sends it to your backend application.
  - Health Checks
    - ELB performs health checks on the targets to ensure that only healthy targets receive traffic.

#### Amazon EC2 Auto Scaling
- Key Features
  - Auto scaling (duh)
  - Scheduled scaling
  - Fleet management
  - Predictive scaling
  - Purchase options

- ELB with EC2 auto scaling
  - Configuring EC2 auto scaling
    - 3 main components
      - Launch template or configuration
        - which resources should be auto scaled?
      - Scaling groups
        - Where should the resources be deployed?
      - Scaling policies
        - When should the resources be added or removed?

- Launch templates and configurations
  - 3 ways to create a launch template
    - Use an existing instance where all setting are already defined
    - Create one from an already existing template or previous version of a launch template
    - Create a template from scratch
      - Params needing defined
        - AMI ID
        - Instance type
        - Key pair
        - Security group
        - storage
        - resource tags

- Scaling policy types
  - Simple scaling
    - Use a cloudwatch alarm to trigger the scaling, very simple and straightforward
  - Step scaling
    - responds to additional alarms even when a scaling activity is already in progress
  - Target tracking scaling
    - If your application scales based on average CPU utilization, average network utilization (in or out), or request count, then this scaling policy type is the one to use.
