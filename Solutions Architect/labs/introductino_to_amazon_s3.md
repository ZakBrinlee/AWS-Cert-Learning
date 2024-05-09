# [Introduction to Amazon Simple Storage Service (S3)](https://explore.skillbuilder.aws/learn/course/7772/play/26009/introduction-to-amazon-simple-storage-service-s3)

Started: May 9th, 2024
Completed: May 9th, 2024

## Links
- [S3 Product Information Page](https://aws.amazon.com/s3/?nc2=h_m1)

#### Lab Overview
- This lab teaches you the basic feature functionality of Amazon S3 using the AWS Management Console.
- Amazon Simple Storage Service (Amazon S3) is an object storage service that offers industry-leading scalability, data availability, security, and performance. This means customers of all sizes and industries can use it to store and protect any amount of data for a range of use cases, such as websites, mobile applications, backup and restore, archive, enterprise applications, Internet of Things (IoT) devices, and big data analytics. Amazon S3 provides easy-to-use management features so you can organize your data and configure finely-tuned access controls to meet your specific business, organizational, and compliance requirements. Amazon S3 is designed for 99.999999999% (11 9’s) of durability and stores data for millions of applications for companies all around the world.

#### Lab Objectives
- After completing this lab, you will know how to:
  - Create a bucket in Amazon S3
  - Add an object to a bucket
  - Manage access permissions on an object and a bucket
  - Create a bucket policy
  - Use bucket versioning


## Notes 
- Amazon Resource Names (ARN)s uniquely identify AWS resources across all of AWS. Each section of the ARN is separated by a “:” and represents a specific piece of the path to the specified resource. The sections can vary slightly depending on the service being referenced, but generally follows this format:
  - arn:partition:service:region:account-id:resource

- Versioning is enabled for an entire bucket and all objects within the bucket. It cannot be enabled for individual objects.
- Amazon S3 always returns the latest version of an object if a version is not otherwise specified.
- In order to access a previous version of the object, you need to update your bucket policy to include the `“s3:GetObjectVersion”` permission.
- ```
{
  "Id": "Policy<some-numbers>",
  "Version": "<date>",
  "Statement": [
    {
      "Sid": "Stmt<some-numbers>",
      "Action": [
        "s3:GetObject",
        "s3:GetObjectVersion"
      ],
      "Effect": "Allow",
      "Resource": "arn:aws:s3:::<mybucketname>/*",
      "Principal": "*"
    }
  ]
}
```