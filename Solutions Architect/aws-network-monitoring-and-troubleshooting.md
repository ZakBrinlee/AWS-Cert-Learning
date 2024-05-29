# [AWS Network – Monitoring and Troubleshooting](https://explore.skillbuilder.aws/learn/course/8187/aws-network-monitoring-and-troubleshooting)

Started: May 28th, 2024
Completed: May 29th, 2024

## Notes
### MODULE 1: OVERVIEW OF NETWORK MONITORING AND TROUBLESHOOTING
#### Module 1 Introduction
- As part of the network strategy, make sure you use the best tools for monitoring and troubleshooting incidents or threats
- Network monitoring helps engineers reduce the mean time to repair and recover and solve real-time network performance issues
- Amazon CloudWatch to not only monitor our environment, but also automatically troubleshoot and remediate incidents in real time

#### Develop Secure, Reliable, and High Performing Networks
- What is Network Monitoring?
  - process that monitors for fault and performance of all networking components
  - maintain and optimize the availability, performance, and security of network infrastructure

- Proactive Monitoring
  - monitor network performance and security
  - determine the monitoring interval. What makes sense for the device and data?
  - Choose the right protocol for monitoring that does not impact the network performance
  - set proactive thresholds

- Network Monitoring Topics
  - Network performance monitoring
    - Observing network performance metrics
  - Network security monitoring
  - Capacity monitoring
    - monitor users on network to ensure that the network is not overloaded
    - QoS policy
  - Application performance optimization
    - monitor application performance issues

- Network Monitoring Alerts
  - Announce not only when a problem has occurred or a threshold is being approached.
  - Contain information to identify the device and the threshold/s that was breached to trigger the alert

#### Monitoring for Troubleshooting
- Troubleshooting your network refers to the process of identifying problems using a precise and repeatable process
- Identify the problem, determine the cause, and resolve the issue in a timely manner

- 5 phases of the AWS Reliability Pillar
  - Generate
    - generate data through monitoring, gathering metrics, and establishing thresholds
  - Aggregate
    - creation of a complete view from multiple data sources
  - Alert
    - leveraging real-time processing and alarms to notify when thresholds are breached
  - Storage
    - Data management and retention policies
  - Analyze
    - Utilize dashboards, reports, insights, and help keep env current and optimized

- Utilize Amazon CloudWatch
  - active monitoring
  - passive monitoring
  - Trigger actions through
    - Amazon Kinesis
    - Amazon SQS
    - Amazon Lambda

- Ensure expected performance
  - Record performance related metrics
  - Analyze metrics when events or incidents occur
  - Establish KPIs to measure workload performance
  - Use monitoring to generate alarm-based notifications
  - Review metrics at regular intervals
  - Monitor and alarm proactively

- Metrics to monitor
  - Bandwidth capacity
  - Throughput
  - Latency
  - Packet loss
  - Retransmission
  - Availability
  - Connectivity
  - Network/Server response time
  - CloudWatch metrics

#### How Security Applies
- Security information monitoring
- Security event monitoring
- process of collecting and analyzing information to detect suspicious behavior or unauthorized system changes on your network
  - Implement metrics to define which type of behavior will initiate an alert and what action to take.
  - Protect your network and environment from hackers, malware, disgruntled employees, careless employees, outdated devices and operating systems.
  - Set up continuous security monitoring to act and automate the monitoring of vulnerabilities, cyber threats, and your organization's risk-management decisions.
  - Implement real-time visibility in your environment to alert on compromises of security, misconfigurations, and vulnerabilities. 

- Four kinds of security controls
  - Directive
    - policies, standards, and guidelines
  - Detective
    - identify and characterize an incident in progress and provide assistance during investigations and audits
  - Preventative
    - prevent an incident from occurring
  - Responsive
    - limit the extent of any damage caused by the incident

- 3 Main security areas
  - Networks
  - Devices
  - Users

- Anomaly Detection
  - Detecting unusual behavior

- Network anomalies
  - deviate from what is normal, standard, or expected network behavior. Detection of anomalies in network behavior demands the continuous monitoring of a network for unexpected trends or events
- Application performance anomalies
  - observe application function, collect data on all problems, including supporting infrastructure and application dependencies
- Web application security anomalies
  - anomalous or suspicious web application behavior that impacts security such as cross-site scripting attacks or DDoS attacks

- Examples of normal and abnormal behavior include:
  - Online retail: Needs to predict which sales, discounts, events, or new products result in boosts in sales. The boost will increase demand on their web servers.
  - IT security team: Needs to prevent hacking and detect abnormal login patterns along with user behaviors.
  - Cloud provider: Needs to track traffic and services to assess changes to infrastructure.

#### Fundamentals of Tools and Services
- proactively address any issues, for each metric identify the
  - Target
  - Measurement approach
  - Priority
  - Build alarms and notifications

- Using the Performance Efficiency Pillar of the AWS Well-Architected Framework ensures that the resources are performing as expected

- Tools for monitoring and troubleshooting
  - Amazon CloudWatch
  - VPC Flow Logs
    - Capture information about the IP traffic going to and from network interfaces in your VPC
  - Traffic Mirroring
    - copy network traffic from an elastic network interface of Amazon EC2 instances
      - content inspection
      - threat monitoring
      - troubleshooting
  - VPC Reachability Analyzer
    - diagnostic tool that helps you analyze and troubleshoot reachability between two resources in your VPC
  - AWS Transit Gateway Network Manager
    - centrally manage your networks built around transit gateways
  - AWS CloudTrail
    - management events
    - data events

- Network monitoring tools
  - Commercial off-the-shelf (COTS) tools
  - Open-source tools

- Benching tools
  - Help to understand how your network is performing
  - Throughput and bandwidth are measured by benching tools
    - Bandwidth is the maximum amount of data that can go through a given medium.
    - Throughput is the amount of data that actually goes through that medium.
  - Tools
    - iPerf / iPerf3
      - active measurements of the maximum achievable bandwidth on IP networks
    - ExtraHop
      - monitoring solution for security, network performance, and the cloud
      - detailed metrics on average bandwidth utilization, average throughput, and more
    - Netperf
      - CLI tool similar to iPerf that measures throughput and benchmarking speeds

#### Module 1 Summary
- What monitoring is and how monitoring can improve network performance
- Why monitoring is important for troubleshooting and what metrics can help
- Why monitoring is fundamental for network security
- What tools and services are available for monitoring and troubleshooting your network

### MODULE 2: MONITORING YOUR NETWORK WITH AMAZON CLOUDWATCH
#### Monitoring Your Network with Amazon CloudWatch – Part 1
- Metrics provide data in two ways:
  - Indicate a point within a range (for example, percentage of total capacity).
  - Provide a quantitative measurement [such as total packets per second(PPS)].

- Monitoring plan
- Ask the following questions
  - What are your goals for monitoring?
  - What resources will you monitor?
  - How often will you monitor these resources?
  - What monitoring tools will you use?
  - Who will perform the monitoring tasks?
  - Who should be notified when something goes wrong?

- Steps needed for monitoring your environment
  - Create monitoring plan and goals
    - What is your account strategy?
    - What is your end goal?
  - Define metrics
    - What resources will you monitor?
    - What metrics can track the progress of your goals?
  - Establish baseline
    - After baseline is established ask the following questions
      - How often will you monitor these resources?
  - Monitor using Amazon CloudWatch
  - Using alarms and notifications
    - Who should be notified when something goes wrong?

#### Monitoring Your Network with Amazon CloudWatch – Part 2
- CloudWatch uses **namespaces**
- namespace contains data and each different namespace holds different data
- Examples
  - Network Manager: AWS/NetworkManager
  - Transit Gateway: AWS/TransitGateway
  - CloudWatch agent: CWAgent
  - EC2: AWS/EC2
- Using the metric's namespace, data points, and dimensions, you can get granular with tracking your metrics

#### AWS Systems Manager Agent
- Software that can be installed on EC2 instances, on-premises servers, or virtual machines
- Makes it possible for Systems Manager to update, manage, and configure these resources
  - View and controls infrastructure on AWS
  - view operational data from multiple AWS services and automate operational tasks across your AWS resources
  - maintain security and compliance by scanning your managed instances and reporting on (or taking corrective action on) any policy violations

#### Amazon CloudWatch Dashboards, Logs, and Queries
- Dashboard examples
  - Single dashboard that pulls data from multiple Regions to create a global view.
  - Multiple dashboards, each one focusing on providing a distinct view of your network.
  - Cross-account, cross-Region dashboards to summarize your data from multiple AWS accounts and Regions.

- Custom dashboard features
  - Metrics explorer widgets to your dashboard helps you to troubleshoot your network more efficiently.
  - Alarm widget to display the status a single alarm or multiple alarms.
  - Animated dashboard that replays CloudWatch metric data that was captured over time.

- CloudWatch Query - supports
  - One or more query commands separated by Unix-style pipe characters (|).
  - Six query commands, along with many supporting functions and operations (including regular expressions, arithmetic operations, comparison operations, numeric functions, datetime functions, string functions, and generic functions).
  - Comments. 
  - Ignoring lines in a query that start with the # character. 
  - Fields that start with the @ symbol are generated by CloudWatch Logs Insights. For more information about the fields that CloudWatch Logs discovers automatically and generates: Supported logs and discovered fields.

#### Amazon CloudWatch Alarms
- CloudWatch alarms add scalability and automatic recovery to your AWS environment and more
  - **metric alarm** watches a single CloudWatch metric or the result of a math expression based on CloudWatch metrics.
  - **composite alarm** includes a rule expression that takes into account the alarm states of other alarms that you have created

- each alarm you create, you can specify CloudWatch to treat missing data points as: 
  - **notBreaching** – Missing data points are treated as good and within the threshold.
  - **breaching** – Missing data points are treated as bad and breaching the threshold.
  - **ignore** – The current alarm state is maintained.
  - **missing** – If all data points in the alarm evaluation range are missing, the alarm transitions to INSUFFICIENT_DATA.

### MODULE 3: TRAFFIC VISIBILITY AND ANALYSIS
#### VPC Flow Logs
- A service that provides visibility in your Amazon VPC by capturing information about the internet protocol (IP) traffic going to and from network interfaces
  - centralized source to monitor different network aspects and to provide a history of network traffic flows within entire Amazon VPCs, subnets, or specific elastic network interfaces (ENIs)
- Useful with the following tasks
  - Diagnosing overly restrictive security group rules.
  - Monitoring the traffic that is reaching your instance.
  - Determining the direction of the traffic to and from the network interfaces.

#### VPC Traffic Mirroring
- Copies each IP packet, sent or received, by an elastic network interface (ENI) on an Amazon EC2 instance to a traffic mirror target. A traffic mirror target is an out-of-band security appliance, monitoring appliance, or Network Load balancer.
- Captures and inspects network traffic at scale and provides data for troubleshooting and intrusion detection, along with other types of threat monitoring and content inspection. 

#### Open-Source Tools and Traffic Mirroring
- Zeek - open-source network security monitoring tool
- Suricata - open-source intrusion detection and prevention system
- Wireshark - open-source network protocol analyzer

### MODULE 4: NETWORK MAPPING
#### VPC Reachability Analyzer
- aids in troubleshooting network issues by verifying connectivity using automated reasoning
- Only used for endpoints within the same VPC
- Reachability Analyzer analyzes all possible paths through your network without having to send any traffic on the wire

- Ability to run a reachability analysis between:
  - VPN gateways
  - Network interfaces
  - Internet gateways
  - VPC endpoints
  - VPC peering connections
  - Transit gateways

- help your network design by: 
  - Troubleshooting connectivity issues caused by network misconfiguration.
  - Verifying that your network configuration matches your intended connectivity.
  - Automating the verification of your connectivity intent as your network configuration changes.
  - Determining whether a destination resource in your Amazon VPC is reachable from a source resource. 

#### AWS Transit Gateway Network Manager
- helps to centrally manage your networks that are built around transit gateways
- With Network Manager, you set up a global view of your private network by registering your transit gateways and on premises resources

- Concepts
  - Global Network
    - A global network is a collection of transit gateways that are associated with a single AWS account
  - Device
    - A device is a physical or virtual appliance that connects to a transit gateway
  - Connection
    - A connection is a logical connection between a device and a transit gateway
  - Site
    - A site is a physical location that contains devices
  - Link
    - A link is a physical connection between a device/site and a transit gateway

