# [AWS Technical Essentials](https://explore.skillbuilder.aws/learn/course/internal/view/elearning/1851/aws-technical-essentials)

Started: March 23rd, 2024

## Top Notes
- Course builds an application to understand the concepts
  - Employee directory that stores images and information about fictional employees
- 


## Links
- []()

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
  - No static login creds
  - IAM roles are assumed programmatically
  - Temporary credentials for configurable amount of time
  - Creds expire and rotated
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
  - Starting, stopping, restarting, monitoring and more for a cluser of EC2 instances
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
      - Runtime options: Node.js, Python, Ruby, Java, Go, .NET Core, and custom runtimes
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

### AWS Databases on AWS
### Monitoring, Load Balancing, and Scaling
### What's New
