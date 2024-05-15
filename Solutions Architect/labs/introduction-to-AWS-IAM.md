# [Introduction to AWS Identity and Access Management (IAM)](https://explore.skillbuilder.aws/learn/course/880/play/25639/introduction-to-aws-identity-and-access-management-iam)

Started: May 14th, 2024
Completed: May 14th, 2024

#### Lab Overview
- AWS Identity and Access Management (IAM) is a web service that enables Amazon Web Services (AWS) customers to manage users and user permissions in AWS. With IAM, you can centrally manage users, security credentials such as access keys, and permissions that control which AWS resources users can access.

- This lab shows you how to manage access and permissions to your AWS services using AWS Identity and Access Management (IAM). Practice the steps to add users to groups, manage passwords, log in with IAM-created users, and see the effects of IAM policies on access to specific services.

#### Lab Objectives
- After completing this lab, you will know how to:
  - Exploring pre-created **IAM Users and Groups**
  - Inspecting **IAM policies** as applied to the pre-created groups
  - Following a **real-world scenario**, adding users to groups with specific capabilities enabled
  - Locating and using the **IAM sign-in URL**
  - **Experimenting** with the effects of policies on service access


## Notes 
- Features and uses of IAM
  - Manage IAM Users and their access: You can create Users and assign them individual security credentials (access keys, passwords, and multi-factor authentication devices). You can manage permissions to control which operations a User can perform.
  - Manage IAM Roles and their permissions: An IAM Role is similar to a User, in that it is an AWS identity with permission policies that determine what the identity can and cannot do in AWS. However, instead of being uniquely associated with one person, a Role is intended to be assumable by anyone who needs it.
  - Manage federated users and their permissions: You can enable identity federation to allow existing users in your enterprise to access the AWS Management Console, to call AWS APIs and to access resources, without the need to create an IAM User for each identity.

- Basic structure of the statements in an IAM Policy is:
  - **Effect** says whether to Allow or Deny the permissions.
  - **Action** specifies the API calls that can be made against an AWS Service (eg cloudwatch:ListMetrics).
  - **Resource** defines the scope of entities covered by the policy rule (eg a specific Amazon S3 bucket or Amazon EC2 instance, or * which means any resource).

- **Inline Policy**, which is a policy assigned to just one User or Group
  - Inline Policies are typically used to apply permissions for one-off situations

- User Security Credentials Tab details
  - **Access Keys**: Keys can be active or inactive and only administrators have the ability to inactivate or delete keys. If a user with limited permissions tried to deactivate or delete an access key, they would receive a message similar to the following:
    - We encountered the following errors while processing your request: User:arn:aws:iam::111122223333:user/user-1_01 is not authorized to perform: iam:UpdateAccessKey on resource: user user-1_01
  - **Signing Certificates**: Can be signed certificates, X.509 Certificate and/or third party tools (e.g. OpenSSL).
  - **Console password**: Users with access to the AWS Management Console require a password. Passwords can be generated and/or changed by administrators within the IAM dashboard. Passwords can be auto-generated or custom-generated based on organization preferences.
  - **Assigned MFA (Multi-Factor Authentication) Device**: Multi-Factor Authentication is a simple best practice that adds an extra layer of protection on top of your username and password.
  - **Virtual**: Use your existing smartphone, tablet, or computer running any application that supports the open TOTP standard.
  - **Hardware Keyfob**: Tamper-evident hardware keyfob device provided by Gemalto, a 3rd-party provider.
  - **Hardware Display Card**: Tamper-evident hardware display card device provided by Gemalto, a 3rd-party provider.