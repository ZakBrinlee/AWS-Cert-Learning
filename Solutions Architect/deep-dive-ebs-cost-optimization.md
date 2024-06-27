# [Deep Dive: Amazon Elastic Block Store (Amazon EBS) Cost Optimization](https://explore.skillbuilder.aws/learn/course/10143/deep-dive-amazon-elastic-block-store-amazon-ebs-cost-optimization;lp=1046)

Started: June 26, 2024
Completed: June 26, 2024

## Links
- [EBS direct APIs](https://docs.aws.amazon.com/ebs/latest/APIReference/Welcome.html)
- [Amazon EBS volume types](https://aws.amazon.com/ebs/volume-types/)

### What I need to know:
- For workloads under 16,000 IOPS and under 1,000 MB/s, gp3 volumes offer a significant cost savings compared to older gp2 volumes, and compared to the high IOPS performance io1 and io2 volumes types

## Notes
### Intro to Cost Optimization
#### AWS Well-Architected Cost Optimization Pillar
- Optimized workload:
  - fully uses all resources
  - achieves outcome at lowest cost
  - meets functional requirements

- Describes how to architect workloads to maximize value at the lowest cost
- continuous process of refinement and improvement over time
- Helps to achieve Five goals
  - practice cloud financial management
  - understand and control where money is being spent
  - choose the most cost-effective resources
  - manage demand and supply
  - optimize over time

- 5 Design principles
  - Implement cloud financial management best practices
    - build capabilities through knowledge building, programs, resources, and processes to become cost efficient
  - Adopt a consumption model
    - pay for what you use
    - increase or decrease usage based on demand/requirements
  - Measure overall efficiency
    - measure output and cost
    - use metrics to make decisions and gains in optimization and lower costs
  - Stop spending money on undifferentiated heavy lifting
    - AWS manages infrastructure so you can focus on your business
  - Analyze and attribute expenditure
    - identify costs and attribute them to the right resources

#### Common Amazon EBS Cost Optimization Opportunities
- Charged for EBS volumes as long as they are provisioned (even if not used)
- Common areas for optimization
  - Delete inactive or unattached EBS volumes when appropriate
  - Avoid provisioning EBS volumes larger than required
  - Avoid over-sizing provisioned performance options
  - Use newer volume types when appropriate
  - Use lower-cost volume types when appropriate

- EBS Snapshot saving opportunities
  - Delete snapshots that are no longer needed
  - Use EBS Snapshots Archive to create archival snapshots
    - archive snapshots are stored at a lower cost
  - Use AWS Backup to create backup copies of your data to maintain archival data copies rather than keeping additional snapshots

### EBS Pricing
#### Pricing Considerations
- EBS Pricing
  - Charged for provisioned storage size
  - Charged for IOPS provisioned
  - Snapshots based on storage consumed

- methodology
  - EBS volume pricing varies per AWS Region.
  - EBS volume pricing varies by EBS volume type.
  - EBS volumes are priced per GB-month for the provisioned capacity.
  - Provisioned IOPS performance is priced per IOPS-month.
  - Provisioned throughput is priced per megabytes per second per month (MB/s-month).

- Instance stores vs EBS Volumes
  - Instance stores are temporary storage
    - lower cost but data is lost when instance is stopped or terminated
  - Features
    - EC2 instance store volumes offer sub-millisecond latency to your EC2 instances.
    - EBS Snapshots and AWS Backup are not available for instance store volumes.
    - Instance store volumes are deleted when the EC2 instance is stopped or terminated

- considerations when choosing EBS volumes
  - What is the minimum actual storage space or volume size needed for the data?
  - What is the performance profile requirement for IOPS?
  - What is the performance profile requirement for throughput?
  - What are the latency requirements?
  - What are the data durability requirements?

#### EBS Pricing Review
- Pay for capacity and performance provisioned
- Quotes based on:
  - Per GB per month for storage
  - IOPS per month for provisioned IOPS
  - MB/s per month for provisioned throughput
  
- SSD Volumes
  - With Elastic Volumes, volume sizes can only be increased within the same volumes. To decrease a volume size, you must copy the EBS volume data to a new, smaller EBS volume

#### EBS Volume Type Pricing Comparisons
- Components and size requirements
  - gp2
    - you increase the provisioned volume capacity to increase sustained IOPS and throughput performance
  - gp3
    - you provision your volume capacity and can provision IOPS and throughput separately
  - io1
    - you provision both your volume capacity and IOPS separately
  - io2
    - you provision both your volume capacity and IOPS separately.

#### EBS Snapshot Billing Review
- Price based on the amount of data stored in the snapshot vault
- Snapshots are incremental backups
  - only store the data that has changed since the last snapshot

- EBS Archival Snapshots
  - 1/4 the cost of standard snapshots
  - retrieval costs added
    - flat fee per GB retrieved

### Volume Cost Optimization Tool
#### Using AWS Computer Optimizer for EBS Volumes
- must be **opted in** to use AWS Compute Optimizer
- monitor them and verify that your volumes are providing optimal performance and cost effectiveness using AWS Compute Optimizer
- analyzes the configuration and utilization metrics of your AWS resources
- generates optimization recommendations to reduce the cost and improve the performance of your workloads

- visualization and analysis of the usage patterns can help make decisions on when to move or resize the running resources and still meet performance and capacity requirements

- Recommendations for:
  - EC2 instances
  - EC2 Auto Scaling groups
  - EBs volumes
  - Lambda functions