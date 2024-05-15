# [Introduction to AWS Key Management Service](https://explore.skillbuilder.aws/learn/course/897/play/25667/introduction-to-aws-key-management-service)

Started: May 14th, 2024
Completed: May 14th, 2024

## Links
- [How to Use the REST API to Encrypt S3 Objects by Using AWS KMS](https://aws.amazon.com/blogs/security/how-to-use-the-rest-api-to-encrypt-s3-objects-by-using-aws-kms/)

#### Lab Overview
- This lab provides a basic understanding and hands-on experience of AWS Key Management Service. It will demonstrate the basic steps required to get started with Key Management Service, creating keys, assigning management and usage permissions for the keys, encrypting data and monitoring the access and usage of keys. For the lab to function as written, please DO NOT change the auto assigned region.

#### Lab Objectives
- Create an Encryption Key
- Create an S3 bucket with CloudTrail logging functions
- Encrypt data stored in a S3 bucket using an encryption key
- Monitor encryption key usage using CloudTrail
- Manage encryption keys for users and roles

## Notes 
- AWS Key Management Service is also integrated with AWS CloudTrail to provide you with logs of all key usage to help meet your regulatory and compliance needs
- CloudTrail provides event history of your AWS account activity, including actions taken through the AWS Management Console, AWS SDKs, command line tools, and other AWS services

- Amazon S3 and AWS KMS perform the following actions when you request that your data be decrypted.
  - Amazon S3 sends the encrypted data key to AWS KMS
  - AWS KMS decrypts the key by using the appropriate master key and sends the plaintext key back to Amazon S3
  - Amazon S3 decrypts the ciphertext and removes the plaintext data key from memory as soon as possible

- If you are uploading or accessing objects encrypted by SSE-KMS, you need to use AWS Signature Version 4 for added security. Signature Version 4 is the process to add authentication information to AWS requests. When you use the AWS Command Line Interface (AWS CLI) or one of the AWS SDKs to make requests to AWS, these tools automatically sign the requests for you with the access key that you specify when you configure the tools. When you use these tools, you don’t need to learn how to sign requests yourself. For more information on this process read this blog post: [blog post](https://aws.amazon.com/blogs/security/how-to-use-the-rest-api-to-encrypt-s3-objects-by-using-aws-kms/)