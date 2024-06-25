# [Launching and Managing a Web Application with AWS CloudFormation](https://explore.skillbuilder.aws/learn/course/406/play/25505/launching-and-managing-a-web-application-with-aws-cloudformation;lp=1046)

Started: June 25, 2024
Completed: June 25, 2024

## Links
- [CF Template anatomy](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/template-anatomy.html#concept-template-description)
- [Bootstrapping Applications via AWS CloudFormation](https://s3.amazonaws.com/cloudformation-examples/BoostrappingApplicationsWithAWSCloudFormation.pdf)

#### Lab Overview
- provision and update a web application with a number of supporting AWS products and services, including Auto Scaling groups, Amazon Elastic Compute Cloud (EC2) instances, and Elastic Load Balancing
- No charge for using AWS CloudFormation, but you are charged for the AWS resources that are created
- CF provides an easy way to create and manage a collection of related AWS resources, provisioning and updating them in an orderly and predictable fashion
- CF Templates
  - JSON or YAML
  - define the resources
  - associated dependencies
  - runtime parameters
  - apply version control to AWS infrastructure
- CF stacks
  - collection of resources
- Six Top Level objects in a template
  - AWSTemplateFormatVersion
  - Description
  - Parameters
  - Mappings
  - Resources (required)
  - Outputs
- 
#### Lab Objectives
- Create an Amazon Simple Storage Service (S3) bucket using AWS CloudFormation
- Provision a simple PHP web application using an Amazon Linux AMI
- Apply an AWS CloudFormation template to an existing application
- Modify an existing application using AWS CloudFormation
- Add IAM roles and Elastic Load Balancing to the application using AWS CloudFormation

## Notes 
- Users have the ability to modify settings for an existing stack
  - eg. change the instance type of an EC2 instance
  - eg. change the env
- YAML Resource Type format:
  - `AWS::ProductIdentifier::ResourceType` -> `AWS::S3::Bucket`
- `Resource` declarations use a `Properties` attribute to specify the information used to create a resource
- Sample template for single S3 bucket resource
```
AWSTemplateFormatVersion: 2010-09-09
Description: Basic S3 Bucket CloudFormation template
Resources:
  S3BucketForWebsiteContent: // Resource name
    Type: AWS::S3::Bucket // Resource type
    Properties:
      PublicAccessBlockConfiguration:
        BlockPublicAcls: false
        BlockPublicPolicy: false
        IgnorePublicAcls: false
        RestrictPublicBuckets: false
Outputs:
  BucketName:
    Value: !Ref S3BucketForWebsiteContent
    Description: Name of the newly created Amazon S3 Distribution

```

- `Outputs` section is used to return values from the stack in response to `cfn-describe-stacks` command
  - Can include info based on:
    - literals
    - resources
    - parameters
    - pseudo parameters
    - intrinsic functions

- Formation Settings\
  - `Preserve successfully provisioned resources`
    - allows the successfully created resource to remain and rolls back the unsuccessful resource. You can use this to troubleshoot resources like EC2 instances and so on.

- Retention policy for resources
  - Often data in stored in S3 buckets, and you may want to retain the data even if the stack is deleted
  - Use `DeletionPolicy` attribute to specify the behavior of the resource when the stack is deleted
    - `DeletionPolicy: Retain` -> resource is retained when the stack is deleted

- Instance updates
  - CF tries to optimize change by updating the existing instance rather than replacing it
    - maintains the Instance ID
  - Public IP addresses are not preserved and will change with instance updates
  - CF updates the elastic IP address of the instance

- `Roles` property to assign an IAM role to a resource
  - `Roles: - some-role-name-id`

- Example part of CF template to add ELB to an existing stack
```
 ElasticLoadBalancer:
    Type: AWS::ElasticLoadBalancing::LoadBalancer
    Properties:
      Subnets:
        - !Ref VPCPublicSubnetId
      SecurityGroups:
        - !Ref WebServerSecurityGroup
      Listeners:
        - LoadBalancerPort: 80
          InstancePort: 80
          Protocol: HTTP
      HealthCheck:
        Target: HTTP:80/
        HealthyThreshold: 3
        UnhealthyThreshold: 5
        Interval: 30
        Timeout: 5
```
- Considerations when making changes
  - Changes to alarm thresholds will render the alarm inactive during the update
  - changes to instance types will require a stop/start of the instance
  - Immutable resources will be replaced not changed