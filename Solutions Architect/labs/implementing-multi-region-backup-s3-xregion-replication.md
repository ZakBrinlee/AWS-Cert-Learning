# [Implementing Multi-Region Backup with Amazon S3 Cross-Region Replication](https://explore.skillbuilder.aws/learn/course/918/implementing-multi-region-backup-with-amazon-s3-cross-region-replication;lp=1046)

Started: June 1, 2024
Completed: June 1, 2024

## Links
- [S3 Cross-Region Replication](https://docs.aws.amazon.com/AmazonS3/latest/userguide/replication.html)
- [How S3 Versioning works](https://docs.aws.amazon.com/AmazonS3/latest/userguide/versioning-workflows.html)
- [Replicating delete markers between buckets](https://docs.aws.amazon.com/AmazonS3/latest/userguide/delete-marker-replication.html)

#### Lab Overview
- create source and destination buckets
- enable versioning
- create various replication policies

#### Lab Objectives
- Create source and destination S3 buckets with versioning enabled
- Create a Cross-Region Replication policy
- Enable replication for an entire bucket, encrypted files, a specific folder, or a specific tag
- Identify the conditions necessary for replicating objects
- Delete replicated files and understand how deletions are replicated

## Notes 
- S3 supports Cross-Region Replication (CRR) for automatic, asynchronous copying of objects across buckets in different AWS Regions.
- Helps with
  - Comply with compliance requirements
  - Minimize latency
  - Increase operational efficiency
  - Maintain object copies under different ownership

- Replication rules are used to determine which objects in a bucket are replicated (options)
  - replicate an entire bucket
  - a specific folder within a bucket
  - any objects with a specified tag
- Same or different region can be used for source and destination buckets


- **WARNING:** Objects that already exist in the bucket before replication is enabled will **NOT** be replicated
  - Use S3 Batch replication to replicate existing objects
- **WARNING:** Much like versioning, objects with tags must be uploaded to the source bucket **after** the replication policy using tags has been created and enabled. Objects that are uploaded and tagged prior to the policy being created will **not** replicate

- Example IAM policy for bucket replication
```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": [
                "s3:GetReplicationConfiguration",
                "s3:ListBucket"
            ],
            "Resource": [
                "arn:aws:s3:::source-bucket-57538018"
            ]
        },
        {
            "Effect": "Allow",
            "Action": [
                "s3:GetObjectVersionForReplication",
                "s3:GetObjectVersionAcl",
                "s3:GetObjectVersionTagging"
            ],
            "Resource": [
                "arn:aws:s3:::source-bucket-57538018/*"
            ]
        },
        {
            "Effect": "Allow",
            "Action": [
                "s3:ReplicateObject",
                "s3:ReplicateDelete",
                "s3:ReplicateTags"
            ],
            "Resource": "arn:aws:s3:::destination-bucket-57538018/*"
        }
    ]
}
```

- **Note:** If you have a business requirement to replicate deleted objects, you can modify your replication rule to enable **Delete marker replication**.