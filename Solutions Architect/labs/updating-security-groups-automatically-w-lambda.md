# [Update Security Groups Automatically Using AWS Lambda](https://explore.skillbuilder.aws/learn/course/1105/play/25537/update-security-groups-automatically-using-aws-lambda;lp=1046)

Started: June 1, 2024
Completed: June 1, 2024

## Links
- [Documented Lab Blog](https://aws.amazon.com/blogs/security/how-to-automatically-update-your-security-groups-for-amazon-cloudfront-and-aws-waf-by-using-aws-lambda/)
- [AWS Security - Network Security - wp](https://d0.awsstatic.com/whitepapers/Security/Networking_Security_Whitepaper.pdf)

#### Lab Overview
- method to automatically update your Amazon Virtual Private Cloud (Amazon VPC) security groups to only allow access from Amazon CloudFront and AWS WAF
- Defining security group rules this way prevents malicious requests from bypassing AWS WAF security rules and accessing your Amazon Elastic Compute Cloud (Amazon EC2) instances directly

#### Lab Objectives
- Create Amazon VPC security groups
- Create an AWS Identity and Access Management (IAM) policy
- Create an AWS Lambda function
- Test a Lambda function with sample events
- Subscribe the Lambda function to an Amazon SNS topic

## Notes 
- **Additional information:** Amazon Web Services (AWS) publishes its current IP address ranges in JSON format. Each range is marked as regional or global

- **Question:** Why would you add two security groups for global rules?
  - **Answer:** The Amazon Cloudfront global IP space is currently more than 60 unique subnets. You can have 60 inbound and 60 outbound rules per security group (making a total of 120 rules). The AWS Lambda function will add the first 60 inbound rules to the first global security group and remaining to the second global security group.

- Tags are metadata associated with a resource, such as this security group. Tags consist of a key and a value.
  - You later create a Lambda function that targets security groups with these specific tags to update the security group rules.