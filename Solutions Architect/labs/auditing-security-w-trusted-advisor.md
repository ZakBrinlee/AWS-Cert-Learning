# [Auditing Your Security with AWS Trusted Advisor](https://explore.skillbuilder.aws/learn/course/887/auditing-your-security-with-aws-trusted-advisor;lp=1046)

Started: June 1, 2024
Completed: June 1, 2024

## Links
- [Best Practices for Security, Identity, & Compliance](https://aws.amazon.com/architecture/security-identity-compliance/?cards-all.sort-by=item.additionalFields.sortDate&cards-all.sort-order=desc&awsf.content-type=*all&awsf.methodology=*all)
- [Trusted Advisor](https://aws.amazon.com/premiumsupport/technology/trusted-advisor/)

#### Lab Overview
- demonstrates the steps to audit your AWS resources with Trusted Advisor to ensure your configuration complies with basic security best practices
- working with security groups
- multi-factor authentication (MFA)
- AWS Identity and Access Management

#### Lab Objectives
- Use Trusted Advisor to perform a basic audit of your AWS resources
- Modify Amazon Elastic Compute Cloud (Amazon EC2) Security Groups to meet best practices
- Configure Multi-factor Authentication (MFA) (Optional, requiring installation of software on a mobile device)

## Notes 
- AWS provided controls to protect your resources
  - IAM
  - VPCs
  - Security Groups
  - Network Access Control Lists (NACLs)
  - certificates

- AWS Trusted Advisor provides best practices in five categories:
  - Cost optimization
  - Security
  - Fault tolerance
  - Performance improvement
  - Service limits

- Main resources to audit:
  - EC2
  - ELB
  - EBS
  - S3
  - EC2 auto scaling
  - IAM
  - RDS
  - Route 53
  - etc

- Basic Support + Developer plans access to these security checks:
  - Security Groups - Specific Ports Unrestricted
    - flagging security groups that allow unrestricted access to specific ports
  - IAM Use
  - MFA on Root Account
  - EBS Public Snapshots
  - RDS Public Snapshots

- Checks summary levels:
  - (Red) Critical – Action recommended
  - (Orange) Investigation recommended
  - (Green) No issues or concerns found
