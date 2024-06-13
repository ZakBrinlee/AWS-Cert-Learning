# [AWS Lambda Foundations](https://explore.skillbuilder.aws/learn/course/99/aws-lambda-foundations;lp=1046)

Started: June 13th, 2024
Completed: June 13th, 2024

## Links
- []()
- [Synchronous invocation](https://docs.aws.amazon.com/lambda/latest/dg/invocation-sync.html)
- [Lambda Event source mapping](https://docs.aws.amazon.com/lambda/latest/dg/invocation-eventsourcemapping.html)
- [Lambda execution environment](https://docs.aws.amazon.com/lambda/latest/dg/lambda-runtime-environment.html)
- [Scaling and concurrency in Lambda](https://docs.aws.amazon.com/lambda/latest/operatorguide/scaling-concurrency.html)
- [Using AWS Identity and Access Management Access Analyzer](https://docs.aws.amazon.com/IAM/latest/UserGuide/what-is-access-analyzer.html)
- [Managing permissions in AWS Lambda](https://docs.aws.amazon.com/lambda/latest/dg/lambda-permissions.html)
- [Giving Lambda functions access to resources in an Amazon VPC](https://docs.aws.amazon.com/lambda/latest/dg/configuration-vpc.html)
- [Connecting inbound interface VPC endpoints for Lambda](https://docs.aws.amazon.com/lambda/latest/dg/configuration-vpc-endpoints.html)
- [Best practices for working with AWS Lambda functions](https://docs.aws.amazon.com/lambda/latest/dg/best-practices.html)
- [Use Lambda environment variables to configure values in code](https://docs.aws.amazon.com/lambda/latest/dg/configuration-envvars.html)
- [Deploying serverless applications](https://docs.aws.amazon.com/serverless-application-model/latest/developerguide/serverless-deploying.html)
- [Lambda Operaters Guide](https://docs.aws.amazon.com/lambda/latest/operatorguide/intro.html)
- [AWS Lambda Power Tuning memory](https://serverlessrepo.aws.amazon.com/applications/arn:aws:serverlessrepo:us-east-1:451282441545:applications~aws-lambda-power-tuning)

### What I need to know:

## Notes
### AWS Lambda Foundations
- Course Objectives
  - Define Lambda and describe how it works
    - Describe the benefits of using Lambda and identify use cases
    - Examine Lambda function permissions and security 
    - Demonstrate best practices for writing Lambda functions
    - Deploy and test your serverless applications
    - Explore Lambda configuration considerations 
    - Monitor and troubleshoot Lambda functions

#### Introduction to Serverless
- Elminates the need to manually manager server infrastructure

- AWS Serverless platform
- Services tightly integrated with AWS Lambda for serverless applications
  - Compute
    - AWS Lambda
    - Lambda@Edge
  - Orchestration
    - AWS Step Functions
  - Storage
    - Amazon S3
  - Data Stores
    - Amazon DynamoDB
  - Event Bus
    - Amazon EventBridge
  - Interprocess Messaging
    - Amazon SNS
    - Amazon SQS
  - API Integration
    - Amazon API Gateway
    - AWS AppSync
  - Developer Tools
    - AWS Cloud Development Kit (CDK)
    - AWS Serverless Application Model (SAM)

- What is Lambda
  - compute service without the need to provision or manage servers
  - handles all the infrastructure management
  - initiates the function when triggered (event-driven)
  - built-in monitoring and logging

- Features
  - Bring your own code
  - Integrated with other AWS services
  - Flexible resource/concurrency models
  - Flexible permissions model
  - Availability and fault tolerance baked in
  - pay only for what you use

- Event Driven Architecture
  - Lambda functions are triggered by events
    - decouples services
    - initiate actions/communications by events
  - Primary mechanism for sharing info across services

- Producers - Routers - Consumers
  - Producers generate events
    - provides info to consumers
    - can be AWS services or custom apps
  - Routers route events to consumers
    - ingest, filter, and push events to consumers
  - Consumers process events
    - subscribe or recieve notification about events

- What is a Lambda Function??
  - Small piece of code that runs in response to events
  - Stateless
  - Actionable configuration for the function
    - Access permissions
    - triggering events
    - Code/dependencies/configurations

#### How AWS Lambda Works
- Understanding events
  - important to understand how each invocation model initializes functions, handles errors, and retries
  - Event are invoked in 3 ways
    
- Synchronous invocations
  - function is ran and waits for a response
  - when completed, lambda returns the response with result + additional data
  - No built-in retries
  - Synchronous AWS Services
    - API Gateway
    - Cognito
    - CloudFormation
    - Alexa
    - Lex
    - CloudFront

- Asynchronous invocations
  - events are queued and processed by Lambda
    - reqestor is not waiting for a response
    - suitable with the client does not need an immediate response
  - Asynch AWS Service integrations
    - Amazon SNS
    - S3
    - EventBridge
  - Destinations
    - send records of invocations to other services
    - configure destinations based on event failures or success

- Polling invocations
  - integrate with AWS streaming/queue services
  - Lambda watches the stream/queue for matching events
  - Polling AWS Service integrations
    - Kinesis
    - DynamoDB Streams
    - SQS
  - retry behavior varies by event source and config
  - Event Source Mapping
    - configuration of services as event triggers
    - Lambda reads events from these services:
      - Kinesis
      - DynamoDB
      - MQ
      - Managed Streaming for Apache Kafka
      - self-managed Apache Kafka
      - SQS

- Model error behavior
| Invocation Model 	| Error Behavior           	|
|------------------	|--------------------------	|
| Synchronous      	|        No retries        	|
| Asynchronous     	| Built in – retries twice 	|
| Polling          	|  Depends on event source 	|

- Execution Env
  - secure and isolated env
  - manages resources, lifecycle support
  - Lifecycle
    - **INIT phase**
      - creates or unfreezes the execution environment
      - runs the intialization code
      - Split into 3 subphases (ensures extensions+runtime are complete and ready before function code runs)
        - Extension init - starts all extensions
        - Runtime init - bootstraps the runtime
        - Function init - runs the functions static code
    - **Invoke phase**
      - invokes the function handler
      - after completion, Lambda prepares to handle another function invoke
    - **Shutdown phase**
      - shuts down the runtime
      - alerts the extensions to stop cleanly
      - removes the env
      - sends a shutdown event to the extensions informing of the shutdown

- Perf optimization
  - optimize options to individual functions to reduce latency and increase throughput
- Cold starts
  - when a function is invoked for the first time or after a long period of inactivity
  - all the phases are run, including the INIT phase so the env and downloads have to execute before the function code runs
- Warm starts
  - Lambda service retains environment
  - when a function is invoked and the execution environment is already running
  - the function code runs sooner since there is not a need to initialize the env

- Best Practice
  - minimize cold start times
  - critical to understand latency requirements and try to optimize your function for peak performance
  - **Provisioned concurrency**
    - prepares concurrent execution environments before invocs
- **Write functions to take advantage of warm starts**
  - Store and reference dependencies locally (in the `/tmp` directory ??)
  - Limit the re-initialization of variables
  - Add code to check for and reuse existing connections
  - Use the `tmp` space as transient cache
  - check that background processes have completed

#### AWS Lambda Function Permissions
- Two sides of permission scope for Lambda functions
  - Permission to invoke the function
    - IAM Resource Policy
  - Permission for the function to access other AWS services
    - IAM Execution Role Policy

- Lambda Security Sides (Left to Right)
  - Event Source -> Resource policy -> Lambda Function -> Execution role policy -> AWS Service

- Execution role
  - gives lambda the permissions to access other AWS services
    - actions it can take (eg. writing to a DynamoDB table)
  - IAM Access Analyzer
    - checks the policies for the execution role
    - identifies any issues with the permissions
    - reviews your AWS CloudTrail logs over the date range that you specify and generates a policy template with only the permissions that the function used during that time.
  - Trust policy that allows Lambda to `AssumeRole`

- Resource (aka function) policy
  - tells the Lambda service who can invoke the function
  - associated with the Event that triggers the function
  - allows source the `lambda:InvokeFunction` action

- AWS Serverless Application Model (AWS SAM)
  - helps to manage your policies
  - scopes the permissions of lambda functions to resources used by application
  
- Accessing resources in VPC
  - requires a VPC configuration
    - VPC subnet IDs
    - security group IDs
    - `AWSLambdaVPCAccessExecutionRole` managed policy
  - establish a priviate connection with AWS PrivateLink
    - interface VPC endpoint
    - allows private access of Lambda APIs withough needing an internet gateway, NAT device, or VPN connection
  - traffic between VPC and Lambda does not leave the AWS network

#### Authoring AWS Lambda Functions
- Best practices for writing Lambda code
- building functions based on nature of application

- AWs Lambda Programming model:
  - Use your own code and IDE
  - Supported languages
    - Node.js
    - Python
    - Ruby
    - Java
    - Go
    - C#
    - PowerShell

- Handler method (start)
  - method in code that processes events
  - runs when the function is invoked
  - takes in two objects
    - event - data passed to the function (required)
      - data/metadata needed to drive logic
    - context - runtime info about the function (optional)
      - info to interact with execution env
      - runtime info, logging, metrics, etc.
      - min info contained:
        - AWS request ID
        - Runtime - amount of time before function times out
        - Logging - log streams

- Design best practices
  - separate business logic from handler code
  - make functions modular
    - easier to test and maintain
  - treat functions as stateless
    - no need to store state between invocations
  - Only include what you need
    - reduce the size of the deployment package
    - only choose modules you need (not entire SDKs)
    - **Typescript** - consider bundling and tree shaking deps

- Best practices for code writing
  - Include logging statements
    - written to CloudWatch Logs
    - implement structured logging
  - Use return coding
    - return coding to exit the code
    - use the context-object to terminate and optionally return info to the caller
  - Provide env variables
    - store sensitive info in env variables
    - use the `AWS_SECRET
    - ease of configuration changes without direct code updates
  - Add secrete and reference data
    - Secretes Manager for sensitive data
  - Add recursive code
    - avoid a situation where a function calls itself
    - can lead to infinite loops
  - Gather metrics with CloudWatch
    - monitor function performance
    - use custom metrics to track function performance
    - EMF - Embedded Metric Format
  - Reuse execution context
    - take advantage of the execution context with warm starts
    - 1. Store dependencies locally
    - 2. Limit re-initialization of variables
    - 3. Check for and reuse existing connections
    - 4. Use the `/tmp` space as a transient cache
    - 5. Ensure background processes have completed

- Building Lambda Functions
  - Lambda console editor
    - best place to start for beginners
    - create, edit, and test functions
  - Deployment packages
    - function code consists of scripts or compiled programs w/deps
    - two types of deployment packages
      - ZIP archive
        - upload to S3
      - container image
        - pushed to ECR
  - Automate using tools
    - AWS SAM services
    - AWS CodeBuild
    - AWS CodePipeline
    - AWS CodeDeploy

- AWS SAM
  - provides shorthand syntax to define serverless applications
    - express functions, APIs, databases, and event source mappings
  - model application using YAML
  - expands into AWS CloudFormation syntax
  - extension of CloudFormation
- Pre-built SAM policies
  - predifined commonly used templates
- CLI
  - AWS SAM CLI for testing, you can do the following:
    - Invoke functions and run automated tests locally
    - Generate sample event source payloads
    - Run API Gateway locally
    - Debug code
    - Review Lambda function logs
    - Validate AWS SAM templates

- Serverless CI/CD pipeline
  - CodeBuild
    - packaging and testing before deployment
  - CodeDeploy
    - ensure safe deployments with version management

#### Configuring your Lambda Functions
- Three primary settings
  - memory
    - up to 10gb memory allocation
  - timeout
    - how long a function can run before being terminated
    - max of 15 minutes
  - concurrency

- Billing
  - based on the number of requests and the duration of the function
  - free tier
    - 1 million requests
    - 400,000 GB-seconds of compute time/month

- Concurrency and scaling
  - number of invocations that can run simultaneously
  - Types
    - Unreserved
      - not limited
    - Reserved
      - guarantees a max number of concurrent instances
    - Provisioned
      - pre-allocate concurrency
  - Why set limits?
    - limit costs
    - regulate the duration to process a batch of requests
    - match to downstream resource that cannot scale as quickly as Lambda

- CloudWatch metrics for Concurency
  - build graphs and dashboards to visualize concurrency
  - set alarms to monitor concurrency (use, performance and error rates)
  - Built-in metrics
    - ConcurrentExecutions
    - UnreservedConcurrentExecutions

- Testing concurrency
  - run perf test to simulate peak-levels
  - determine if backend can handle the speed of requests
  - does error handling work as expected?

#### Deploying and Testing Serverless Applications
- Similar to designing and building a house using details specs
  - blueprint/template of what is to be built
- CloudFormation template
  - defines the resources and dependencies of the application
  - blueprint of the Lambda function

- Deploying serverless applications
  - perform testing in the cloud
  - use AWS SAM to deploy
    - ensures env parity

- Versioning
  - versioning is automatic
  - each deployment creates a new version
  - can rollback to previous versions
- Publishing
  - publish a version to the Lambda service
  - makes a snapshot copy of $LATEST
- Aliases
  - pointers to a specific version
  - split code between alias versions for testing a portion of the traffic

- Integrate with CodeDeploy
  - automated rollout
  - traffic shifting methods
    - AllAtOnce
      - just what it sounds like
    - Canary
      - two increments
        - if first increments success, deploy second based on time specified
    - Linear
      - traffic is shifted in equal increments
  - Alarms
    - set alarms to monitor the deployment
    - rollback if alarms are triggered
  - Hooks
    - pre-traffic and post-traffic hooks
    - test functions
  - SAM can include CodeDeploy traffic shifting
    - `AutoPublishAlias` property
    - `DeploymentPreference` property
    - `Alarms` property
    - `Hooks` property

#### Monitoring and Troubleshooting
- Autotracks the following
  - Number of requests
  - Invocation duration per request
  - Number of requests that result in an error

- Lambda Insights
  - collects, aggregates, and summarizes system-level metrics
  - summarizes diagnostic information such as cold starts and Lambda worker shutdowns

- X-ray
  - Tuning performance
  - Identifying the call flow of Lambda functions and API calls
  - Tracing path and timing of an invocation to locate bottlenecks and failures
