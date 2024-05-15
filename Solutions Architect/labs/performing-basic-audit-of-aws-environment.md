# [Performing a Basic Audit of your AWS Environment](https://explore.skillbuilder.aws/learn/course/885/performing-a-basic-audit-of-your-aws-environment)

Started: May 14th, 2024
Completed: May 14th, 2024

## Links
- [Testing IAM policies with the IAM policy simulator](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_testing-policies.html)

#### Lab Overview
- This lab leads you through the steps to perform basic audits of core AWS resources. You will use the AWS Management Console to understand how to audit the use of multiple AWS services, Amazon EC2, Amazon VPC, Amazon IAM, Amazon Security Groups, AWS CloudTrail and AWS CloudWatch. This lab will help you understand how you can extend your existing auditing objectives related to organizational Governance, Asset Configuration, Logical Access Controls, Operating Systems, Databases and Applications security configurations within AWS. The skills learned will help provide visibility; testability and automated audit evidence gather capabilities.

#### Lab Objectives
- Review user permissions in AWS IAM
- Capture audit evidence using AWS IAM Policy Simulator
- Review Inbound and Outbound networking rules for Amazon EC2 Security Groups
- Review Amazon VPC configurations, subnets, and Network ACLs
- Review Amazon CloudWatch performance metrics
- Review raw Amazon CloudTrail logs within Amazon S3

## Notes 
- **Security Groups**: Act as a firewall for associated Amazon EC2 instances, controlling both inbound and outbound traffic at the instance level.
- **Network Access Control Lists (ACLs)**: Act as a firewall for associated subnets, controlling both inbound and outbound traffic at the subnet level.

- The following are basic characteristics of **security groups**:
  - You can specify allow rules, but not deny rules.
  - You can specify separate rules for inbound and outbound traffic.
  - By default, no inbound traffic is allowed until you add inbound rules to the security group.
  - By default, all outbound traffic is allowed until you add outbound rules to the group. Then, you specify the outbound traffic that is allowed.
  - Responses to allowed inbound traffic are allowed to flow outbound regardless of outbound rules and vice versa, as security groups are therefore stateful.
  - Instances associated with a security group can’t talk to each other unless you add rules allowing it.
    - **Exception**: The default security group has these rules by default.
  - After you launch an instance, you can change which security groups the instance is associated with.

- You can specify a number of different sources in security group rules, such as anywhere, a custom IP address or CIDR, My IP (the IP address of your current workstation), or specific security groups. The rules you choose to implement are a critical step towards running instances and services within Amazon EC2.