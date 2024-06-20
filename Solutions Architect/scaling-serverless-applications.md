# [Scaling Serverless Applications](https://explore.skillbuilder.aws/learn/course/12713/scaling-serverless-architectures;lp=1046)

Started: June 19th, 2024
Completed: June 19th, 2024

## Links
- [Using Lambda with Amazon SQS](https://docs.aws.amazon.com/lambda/latest/dg/with-sqs.html)
- [Tutorial - Use SQS as an event source for Lambda](https://aws.amazon.com/serverless/use-sqs-as-an-event-source-for-lambda-tutorial/)
- [Lambda Power Tuning tool](https://github.com/alexcasalboni/aws-lambda-power-tuning)
- [VPC Networking for Lambda](https://docs.aws.amazon.com/lambda/latest/dg/foundation-networking.html)
- [Query your Database from Serverless Application](https://aws.amazon.com/blogs/database/query-your-aws-database-from-your-serverless-application/)

### What I need to know:
- "Build today with tomorrow in mind"

## Notes 
### Scaling Serverless Architectures
#### Intro
- Architect serverless solutions for reliable scaling helps to avoid the following:
  - introduction of additional complexity
  - degradation of performance
  - reduced security

- Some course coverage:
  - Comparing AWS Lambda based architectures with traditional cloud architectures
  - Applying best practices to optimize the speed with which Lambda functions run
  - Comparing storage options for persisting resource and application state
  - Applying serverless testing strategies as they relate to mocking, unit tests, function design, effectively testing to scale, and integration testing
  - Exploring options for expenditure awareness within your serverless applications

#### Thinking Serverless at Scale
- General cloud architecture themes:
  - build
  - measure
  - learn
  - repeat

- Microservices approach
  - multiple and loosely coupled services
  - reduces complexity of the individual services
  - introduces complexity at scale related to number of services

- Scaling Best Practices
  - Separate your application and database
  - Take advantage of AWS Global infrastructure
  - Identify and avoid heavy lifting
  - Monitor for percentile
  - Refactor as you go

- Key scaling considerations
  - Evaluate trade offs
  - Be aware of service limited end-2-end
  - Balance performance requirements, cost and impact
  - build in monitoring and iterate based on data

- Concurrency
  - number of lambda invocation that can execute at the same time
  - if exceeded, lambda will throttle the invocations
  - Impacts
    - invocation model
    - service limits
  - Async and sync invocations
    - `concurrency = request rate * average duration`
    - EG: ` 25 requests per second * 10 seconds = 250 concurrent invocations`
      - if the concurrency limit is < 250 the requests will be throttled
  - Async events
    - 2 retry attempts per throttled/limit event
  - Sync events
    - 0 retries

#### Scaling Considerations for Serverless Services
- Key to understand the capabilities and limitations of the services you are using
  - timeouts
  - retry behavior
  - throughput
  - Payload size

- **API Gateway** considerations:
  - Helps to manage access patterns
    - edge optimized endpoints with CloudFront distribution
    - optional caching reduces load on backend
    - API keys and usage plans limit requests by client
  - Analyzing the access patterns
    - Who will be using the API?
    - Where will they be using it?
    - How often will they be using it?
    - Do you need to throttle for downstream services?
  - Lambda authorizers
    - invocations count towards the concurrency limit

- **Amazon SQS** considerations:
  - When used as a Lambda event source, the Lambda service will poll the SQS queue for messages
  - SQS configuration settings
    - Batch size
    - Visibility timeout
      - set to 6x the function timeout
    - max receive count
    - redrive policy
  - Lambda Concurrency should be set to 5 minimum to account for the 5 pollers
    - max concurrency is 1000

- **Lambda** considerations:
  - Concurrency limits
    - prevents runaway Lambda invocations
    - reserved concurrency on a function
  - Managing concurrency
    - test all scenarios where different functions are used
  - Burst behavior
    - Lambda will burst to 3000 concurrent invocations
    - account concurrency limit: 5000
  - Memory allocation
    - Memory allocation impacts CPU and network performance
    - affects the duration of function
  - AWS Lambda Power Tuning
    - tool to help optimize memory allocation
  - Environment Reuse
    - Warm start
    - Best practices
      - Store and reference dependencies locally
        - When retrieving data from a database, store values outside of the handler function
        - Limit the re-initialization of variables
        - Check and reuse connections
        - use /tmp directory for temporary files/cache
        - Check the background process have completed before returning a response/exits

- **Database** considerations:
  - DynamoDb
    - Auto scaling
      - scales read and write capacity based on demand
    - On-demand until you know your workload

- **Step Functions & SNS** considerations:
  - Step Functions
    - orchestrate long running workflows/tasks
    - Utilize wait states to avoid unnecessary polling
    - Utilize callbacks to avoid long running tasks
    - Use timeouts to avoid stuck executions
      - `TimeoutSeconds` in the state machine definition
    - Be mindful of payload limits between steps
    - Know the limits
  - SNS
    - initiate parallel processing tasks and nested applications
    - Use Event Fork Pipelines to model SNS fan-outs
    - Understand the retry behavior with Lambda subscriber
    - Pay attention to number of filter policies

- **Kinesis Data Streams** considerations:
  - Customize failure handling
    - bisect on function error
    - max record age in seconds
    - max retry attempts
    - destination on failure
  - 1/mbps per shard
  - Enhanced fan-out
    - allows multiple consumers to read from the same shard
    - increases throughput
      - 2MBps per shard

#### Testing for Peak Load
- Validate assumptions and decisions
  - Load test with realistic data
  - test each integration point
  - Test with real access patterns
- Load testing tips
  - watch for service limits
  - use all monitoring tools
  - avoid mocking services you don't control
  - use auto-scaling or on-demand mode with testing DynamoDB
  - Dive deep into workload to design the tests