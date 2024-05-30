# [Introduction to AWS Step Functions](https://explore.skillbuilder.aws/learn/course/8819/play/28737/introduction-to-aws-step-functions-version-20;lp=1046)

Started: May 30th, 2024
Completed: May 30th, 2024

### Course summary:
- AWS Step Functions is a serverless orchestration service. You can use it to combine AWS Lambda functions and other AWS services to build business-critical applications. With AWS Step Functions, you can build visual workflows that help you rapidly translate business requirements into applications. Through Step Functions' graphical console, you see your application's workflow as a series of event-driven steps. 
- Step Functions is based on state machines and tasks. A state machine is a workflow. A task is a state in a workflow that represents a single unit of work performed by another AWS service. Each step in a workflow is a state.
Step Functions manages state, checkpoints, and restarts for you, and it provides built-in capabilities to automatically deal with errors and exceptions. Step Functions provides the scalability, reliability, and availability needed to successfully manage your data processing workflows. You can manage millions of concurrent executions with Step Functions because it scales horizontally and provides fault-tolerant workflows.
- Step Functions uses IAM to control access to others services and resources. To maintain security, you must grant Step Functions access to those resources by using an IAM role. It is always a best practice to include only the permissions that are necessary in your IAM policies.
- Step Functions provides several ways to manage your microservice workflows. For long-running workflows, you can use Standard Workflows. For short-duration, high-volume workflows that require an immediate response, synchronous Express Workflows are ideal. For short-duration workflows that do not require an immediate response, Step Functions provides asynchronous Express Workflows.

## Notes
#### Introduction to Serverless
- Eliminates the need to manage servers

- General features of serverless
  - capacity provisioning
  - automatic scaling
  - built-in high availability
  - pay-for-use billing

- AWS Serverless Platform
  - Compute
    - AWS Lambda
  - Orchestration
    - AWS Step Functions
  - Data Stores
    - Amazon DynamoDB
    - Amazon S3
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

#### What is AWS Step Functions?
- Serverless orchestration for modern apps
- Maintains app state

- State
  - based on state machines and tasks.
    - State Machine: a workflow that defines the steps to be executed
    - Task: a single step/task within a state machine
      - Each step in a workflow is a state

- Individual states can make decisions based on their input, perform actions, and pass output to other states

- States can provide a variety of functions in your state machine: 
  - Perform some work in your state machine.
  - Make a choice between branches of activity.
  - Stop an activity with a failure or success.
  - Simply pass its input to its output or inject some fixed data.
  - Provide a delay for a certain amount of time or until a specified time or date.
  - Begin parallel branches of activity.
  - Dynamically iterate steps.

- Different types of states
  - Task
    - represents a single unit of work performed by a state machine
    - performs work by using an activity or AWS Lamnda function, or other API services
  - Choice
    - Adds branching logic to a state machine
  - Parallel
    - create parallel branches of activity in your state machine
  - Wait
    - delays the state machine from continuing for a specified time
  - Success
    - stops an execution successfully
  - Fail
    - stops the activity of the state machine and marks it as a failure
  - Pass
    - passes its input to its output without performing work
      - useful when constructing and debugging state machines
  - Map
    - run a set of steps for each element of an input array

#### Why use AWS Step Functions?
- Helps to subdivide complex applications into smaller, more manageable series of steps
- define and manage workflow of an application independently from the business logic

- Features
  - Auto scaling
  - High availability
  - Pay-per-use pricing
    - billing is metered by state transitions
  - Security and Compliance
    - integrated with IAM

- Orchestration Features
  - built in service primitives
  - AWS service integrations
  - built in error handling
  - full history of each run
  - visual monitoring
  - high volume orchestration

#### Amazon States Language
- JSON-based language used to define state machines
- Create a workflow (collection of states)
  - Do work (tasks states)
  - Determine which states to transition to next (choice states)
  - Stop the workflow with a success or failure (terminal states)
  - etc

- Transitions
  - link states together
  - System begins with "StartAt" state
  - Non-terminal states require a "Next" field to indicate the next state (except for choice states)
  - process continues until a terminal state is reached (success or failure) or a runtime error occurs

- Step functions use JSON path expressions
  - receives JSON as input
- Fields to filter and control the flow of data
  - InputPath
  - ResultPath
  - OutputPath
  - Parameters
  - ResultSelector

- Intrinsic functions
  - States.Format
    - takes 1+ arguments
  - States.StringToJson
    - converts a string to JSON
  - States.JsonToString
    - converts JSON to a string
  - States.Array
    - creates an array in JSON format

#### AWS Step Functions Workflow Studio
- Low code visual workflow editor
- States browser
  - actions panel with list of AWS APIs
  - Flow panel with list of flow states
- Canvas panel
  - drag and drop states to create a workflow
- Inspector panel
  - view and edit state properties
- Info panel
  - view info about selected APIs

#### AWS Step Functions Security
- IAM has 3 existing policies
  - AWSStepFunctionsFullAccess
    - full access to Step Functions
  - AWSStepFunctionsReadOnlyAccess
    - read-only access to Step Functions
  - AWSStepFunctionsConsoleFullAccess
    - full access to Step Functions console

#### Standard and Express Workflows
- Standard Workflows are ideal for long-running, durable, and auditable workflows. 
- Express Workflows are ideal for high-volume, event-processing workloads such as IoT data ingestion, streaming data processing and transformation, and mobile application backends.
  - There are two types of Express Workflows, asynchronous and synchronous. You learn more about the different types of Express Workflows later in this topic.

- Express workflows has two types
  - Asynchronous
    - ideal for high-volume, event-processing workloads
  - Synchronous
    - ideal for mobile application backends

#### AWS Step Functions Use Cases
- Data processing
  - ETL
  - Data validation
  - Data transformation
  - Data enrichment
- IT Automation
  - Patch management
  - Backup and restore
  - Disaster recovery
  - Incident response
- E-commerce
  - order processing
  - inventory management
- Web Applications
  - user registration
