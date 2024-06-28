# []()

Started: June 28, 2024
Completed: June 28, 2024

## Links
- [AWS Lambda Runtime Interface Emulator](https://docs.aws.amazon.com/lambda/latest/dg/welcome.html)
- []()

#### Lab Overview
- package and deploy Lambda functions as container images of up to 10 GB in size
- functions deployed as container images benefit from the same operational simplicity, automatic scaling, high availability, and native integrations with many services

- In this lab, you will deploy a sample application to AWS Lambda utilizing a container image. You will make use of AWS Cloud9 as your cloud-based integrated development environment (IDE), where you will create the sample application, test it locally, upload the container image to Amazon Elastic Container Registry (Amazon ECR), and finally deploy it to AWS Lambda using the AWS Serverless Application Model (SAM).

#### Lab Objectives
- Create and test a Lambda function locally in your Cloud9 development environment using the Lambda Runtime Interface Emulator
- Upload your Lambda container image to the Amazon Elastic Container Registry (Amazon ECR)
- Modify and re-upload the container used in your Lambda function
- Invoke your Lambda function via an Amazon API Gateway endpoint

## Notes 
- AWS Serverless Application Model (AWS SAM) is an open-source framework that you can use to build serverless applications on AWS
- AWS SAM CLI (Command Line Interface) comes preinstalled on Cloud9 instances
- `sam init` command initializes a new serverless application project
- SAM templates are extensions of CloudFormation templates
  - Two values required when working with container images
    - `PackageType` : `Image|Zip` - specifies the type of deployment package
    - `Metadata` - helps SAM manage the container images
- **AWS base images for Lambda** include a component called the **AWS Lambda Runtime Interface Emulator (RIE)**
  - AWS Lambda RIE is a proxy for the Lambda Runtime API that allows you to locally test the Lambda function packaged as a container image
- Repo URI: `654834219284.dkr.ecr.us-east-1.amazonaws.com/getletter`

- The AWS SAM CLI provides an easy method of building and deploying our application, which includes tagging and pushing our container to the specified repository.

- the `sam deploy` process, SAM is deploying a new CloudFormation Stack, using the template initialized earlier.
- Once your function has been changed, you will need to re-build, re-tag, and re-deploy your updated container image

- Example of deploying a SAM application

```
sam deploy \
	--stack-name getletter \
	--s3-bucket <S3Bucket> \
	--capabilities CAPABILITY_NAMED_IAM CAPABILITY_AUTO_EXPAND \
	--image-repository <repositoryUri>
```