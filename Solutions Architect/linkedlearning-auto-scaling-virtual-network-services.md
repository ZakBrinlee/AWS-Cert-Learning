# [AWS Certified Solutions Architect - Associate (SAA-C03) Cert Prep: 6 Auto Scaling and Virtual Network Services](https://www.linkedin.com/learning/aws-certified-solutions-architect-associate-saa-c03-cert-prep-6-auto-scaling-and-virtual-network-services)

Started: April 17, 2024
Completed: April 17, 2024

## Links
- [Create an Auto Scaling group using a launch template](https://docs.aws.amazon.com/autoscaling/ec2/userguide/create-asg-launch-template.html)
- [Auto Scaling group](https://docs.aws.amazon.com/autoscaling/ec2/userguide/auto-scaling-groups.html)
- [Elastic Load Balancing features](https://aws.amazon.com/elasticloadbalancing/features/)

### What I need to know:
- Understand what is needed for Auto Scaling groups
  - how it can be setup / launched
  - permissions `ec2:runInstances`
- Understand Elastic Load Balancing features/solutions
  - differences between Application vs Network load balancer
- Understand what is running in the VPC and how to configure network rules
- DNS routing policies
  - simple
    - same way it has always been performed, name to ip
  - weighted
    - split traffic based on weight
  - latency
    - based on lowest latency - fastest time
  - failover
    - primary and secondary
  - geolocation
    - based on location of requestor
  - multi-value answer
    - uses health checks to determine which to use

## Notes
### Auto Scaling Solutions
#### Overview
- Auto Scaling is a service that allows you to scale your EC2 instances up or down based on demand.
  - Monitors applications
  - adjusts capacity (up/down)
  - manages costs

- What can be auto-scaled?
  - EC2 groups
  - Aurora DB Clusters
  - DynamoDB tables
  - DynamoDB global secondary indexes
  - ECS services
  - Spot fleet requests

- Costs
  - free to use
  - services it triggers/uses can incur costs

#### Auto Scaling Groups
- Group
  - collection of EC2 instances with similar characteristics
  - can be scaled based on criteria specified
  - unhealthy instances are replaced automatically
- Considerations
  - time to launch/configure a new instance
  - metrics to scale on
    - CPU utilization
    - network traffic
    - memory
  - What AZ should it span
  - Scale to increase or decrease capacity
  - specify min # of instances to be running

- Scaling out
  - adding more instances
  - more performance/redundancy
- Scaling in
  - removing instances
  - save cost

#### Termination Policies
- Default steps when terminating (policy)
  - Select AZ with most instances
    - has at least one without termination protection
  - Select the instance with the oldest launch configuration
    - if multiple, select nearest to a billing hour
    - if multiple, select at random

- Custom termination policies options
  - oldest instance
  - newest instance
  - oldest launch configuration
  - closest to next billing hour
  - default

#### Configuration Lab
- When creating instance, you can choose to launch them in a AS group
- Launch Configuration is required with an AS group
- Launch Configuration
  - AMI
  - Instance type
  - Key pair
  - Security group
  - User data
  - Block device mapping
  - IAM role

#### Launch Methods
- Launch Templates
- Launch Configurations
- Using existing EC2 instance
  - create AMI
  - use AMI to launch group
- Amazon EC2 Launch Wizard

#### Load balancer concepts
- Definition
  - sits between requester and a endpoint that will service the requests
  - distributes incoming traffic across multiple endpoints to respond to the requests

- Categories
  - Sender initiated
    - sender locates best target
  - Receiver initiated (load balancer)
    - receiver locates best target

- Static load balancing
  - multi-tier app
    - specific actions are assigned to a specific resource
    - actions always processed on assigned target
    - no scalability

- Dynamic load balancing
  - actions are assigned to a resource based on current load
  - scalability is provided
  - Used by ELB

- Algorithms
  - Round Robin
  - Randomized
  - Centrally managed
  - Threshold-based

#### Elastic Load Balancing 
- Benefits
  - highly available
  - secure
  - flexible
  - monitor and auditing
  - elastic
  - hybrid -> can implement multiple types of LB within one env

- Types
  - Classic Load Balancer
    - good for old apps
    - only recommended for legacy use
  - Application Load Balancer
    - always recommended for NEW apps
    - good for HTTP/HTTPS
    - layer 7
    - web/app servers
  - Network Load Balancer
    - always recommended for NEW apps
    - good for TCP
    - layer 4

- Supported services
  - ec2
  - ecs
  - auto scaling
  - CloudWatch
  - Route 53

### Virtual Network Services
#### DNS
- Overview
  - Domain Name System
    - translates domain names to IP addresses
  - RFCs 1034 and 1035
    - 1034 understand structure
    - 1035 understand operation

- Components / resolution process
  - Requestor (mobile device, web browser, server, etc)
    - root DNS server
      - top level domain server
        - authoritative DNS server
          - local DNS server
            - resolver (actual server/source of the IP address)

- Hosting DNS
  - provides name resolution
    - caching
    - recursion
  - stores DNS database
    - aliasing
  - provides zone transfers
    - offloads resolution processing

- DNS resolution
  - request of ip address of host name
    - forward lookup
  - request of host name of ip address
    - reverse lookup

- DNS records (most common)
  - a or aaaa
    - hostname > ipv4 or ipv6
  - ns
    - domain > hostname
  - mx
    - mail record
  - cname
    - alias for real name (canonical name)

#### Configuring DNS Lab
- IAM account alias
  - DNS alias must be unique globally
- EC2
  - can use public ipv4 address
  - alias that routes to the public DNS address

#### Configuring Route 53 Lab
- Can setup health checks
  - can be used to determine if a resource is healthy
  - can be used to determine if a resource is unhealthy

#### Configuring ACLs and NACLs Lab
- ACLs
  - considered legacy approach for S3
    - recommends using policies instead
- NACLs
  - inbound/outbound rules into a VPC

#### Flow Logs
- Capture the information about the traffic that is flowing in and out of the VPC
  - logs stuff like source, destination, port, etc

- Be prepared for flow logs
  - S3 bucket

- Services for flow logs
  - VPC
  - Subnet
  - Network interface