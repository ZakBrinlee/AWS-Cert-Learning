# [AWS Certified Solutions Architect - Associate (SAA-C03) Cert Prep: 5 Identity and Access Management](https://www.linkedin.com/learning/aws-certified-solutions-architect-associate-saa-c03-cert-prep-5-identity-and-access-management)

Started: April 16, 2024
Completed: April 16, 2024

## Links
- []()

### What I need to know:

## Notes
### Identity and Access Management
#### Overview
- Resources
  - aws services
  - things on which actions can be taken
- Principles
  - anyone/thing that can interact with AWS
  - Users
  - Groups
  - Roles
- Policies
  - JSON documents
  - define permissions

#### Principles
- Also called `entities`
  - entities can perform action
    - people, group etc
    - person, or service with permissions:
      - AWS management console
      - aws api/cli

- User credentials
  - consists of name, password and up to two access keys
    - access keys used for API or CLI
  - Easy to assign policy to groups and assign users to groups

- Groups
  - collection of IAM users
  - permissions should be management at group level
- Role
  - identity that is granted permissions
  - works with federated users
    - federated users are mapped to a role

#### Root User
- Account created when you sign up for AWS
  - the account owner
  - has full access to all resources
  - Best practice
    - create an IAM user and use that instead of root user

#### Authentication
- validation of credentials
- creds provide identity
- Auth of persons or process

- Auth into AWS
  - User name and password
    - console access
  - Access key ID and secret access key
    - also known as user-keys
    - programmatic access
    - API/CLI

#### Authorization policies
- Policies
  - Rules to determine actions/access that is allowed
  - JSON documents
  
- Identity-based policies
  - Used with users, groups, or roles
- Resource-based policies
  - used for cross-account access

- Policy Processing
  - All requests are denied by default
  - Explicit allow overrides implicit deny
  - permission boundaries can override explicit allows
  - Explicit denies override explicit allows

- Actions or operations
  - requires the request to be authenticated
  - processed against a resource
- Includes CRUD
  - Create (launch)
  - Read (view)
  - Update (edit)
  - Delete (terminate)

#### Multi-factor authentication
- Best practice to use MFA
- Requires two forms of authentication
  - Something you know
  - Something you have
  - Something you are
  - Something you receive

#### Key rotation
- Key
  - Access key ID
  - Secret Access key
- key rotation only applies to user keys
- Best practice to rotate keys regularly
- Key update process
  - Create second access key
  - Update application to use new key
  - deactivate old key
  - Test new key
  - delete old key

#### Multiple permissions
- policies are cumulative
- boundaries
  - does not provide permissions
  - constrains permissions a user can receive
  - limit a user to specific services

#### AWS Compliance Program
- Provides documentation on how AWS meets compliance requirements
- split by region

#### AWS Security Hub
- Not a free service
- provides a comprehensive view of security alerts and compliance status
- Helps with the way you manage your security
- Automated compliance checks

#### Shared responsibility model
- This is probably the most repeated concept in AWS
- AWS security
  - Physical
  - Network
  - Hypervisor
  - Managed Services (DynamoDB, RDS)
- Customer security
  - Guest OS
  - Applications
  - User Data

#### Data security control
- AWS provides
  - Data storage
  - creation
  - backup
  - recovery
  - retention
- Customer provides
  - Data classification
  - encryption
  - access control
  - monitoring
  - auditing

- Data governance includes
  - ingestion
  - transformation
  - classification
    - identified
    - determine the type and how to protect
    - protect
    - Levels
      - public, internal, sensitive, restricted
  - utilization
  - retention
  - removal

- Encryption
  - PII should be encrypted
  - Organizational trade secrets
  - customer information
  - product information

#### Federated directory services
- A system of trust between two parties
- AWS supports standardized protocols
  - SAML 2.0
  - OpenID Connect (OIDC)
  - OAuth 2.0
- Examples
  - google, facebook, apple, etc

- Federated directory services
  - Groups and Users can be linked
  - entire directory can be linked
  - extra auth info can be provided

- IAM Identity Center / AWS Single Sign-On
  - connects existing directories to AWS
  - requires use of AWS Organizations
  - MAy connect with MSFT Active directory
    - AWS-Managed AD
    - Self-managed AD (needs AD connector)

### IAM Best Practices
#### User accounts
- Ability to generate access keys for programmatic access by user
- Ability to generate console password

#### Password policies
- Default password policies
  - min 8 character
  - max 128 characters
  - 3 of 4 character types required
    - uppercase, lowercase, number, special character
  - cannot be the same as account name/email

- Best practices
  - Change password regularly
  - Unique password
  - avoid easily guessed

#### Credential rotation
- AWS provides the ability to set password rotation policies
- ability to track pw history and restrict reuse

#### Principle of least privilege
- Grant only the access needed
- Summaries
  - Policy Summary
    - services
  - Service Summary
    - actions
  - Action Summary
    - resources

#### IAM Roles
- Creating a naming convention
- used for CLI and programs

#### Amazon STS
- Security Token Service
  - Short-term
    - minutes to hours
  - dynamic
- Global service by default
  - can be restricted to a region

- Assume Role action/api
  - assume temp credentials

#### Policy conditions
- ability to set granular conditions
- can be used to restrict access based on
  - IP address
  - time of day
  - MFA
  - VPC
  - User agent
  - etc

#### CloudTrail
- Logs for everything
  - governance
  - compliance
  - auditing

- Event history
  - Management console
  - AWS SDK
  - Command line
  - Other AWS services

- process
  - account activity occurs 
    - -> log file created 
      - -> log file delivered to S3 bucket

#### AWS Control Tower
- Setup/govern multiple accounts
- Provides a dashboard
- Guardrails can be set
  - preventive guardrails
    - stops x from happening
  - detective guardrails
    - notifies when x happens
- Account factory
  - template for accounts

- Requires AWS Organizations
- Home Region
  - where the control tower is set up

- Setup steps
  - Review pricing and select regions
  - Configure org units
  - configure shared accounts
  - configure CloudTrail and encryption
  - Review and set up landing zone

#### Service control policies
- Manage permissions in organizations
  - centralized control of accounts/capabilities
  - enforce guardrails
- Requires all org features to be enabled

- SCPs inheritance
  - deny statement apply to all lower levels
  - allow statements apply to all lower levels unless overridden
  - An implicitly deny is the default
- SCP strategies
  - Deny list strategy
    - deny all, then allow specific
  - Allow list strategy
    - remove default SCP
    - apply allow scps at appropriate lower levels

- Primary rule
  - Implicit deny can be overridden; explicit deny cannot

#### Key security services
- AWS Shield
  - DDoS protection
  - Two versions
    - Standard & Advanced
  - protection at layers 3, 4, 7
- Web Application Firewall (WAF)
  - Protects web apps
  - Rules can be set
  - Web Access Control Lists (Web ACLs)
  - Can be used with CloudFront
- Secrets Manager
  - allows for apps to retrieve creds through API
    - no stored creds
    - rotation of creds

#### Additional security services
- Amazon Cognito
  - authentication, authorization, user management
    - web/mobile apps
  - User pools
    - directory of user profiles
  - Identity Pool
    - provide access to AWS resources
    - through user pools
    - through direct social identity provider logon
    - user profiles only saved when integrated with user pools

- Amazon GuardDuty
  - threat detection service
- guard duty terms
  - Account
  - Detector
    - associate of discoveries and findings
  - Data Source
    - what is monitored
  - Finding
    - potential security issue
  - Scan Options
    - malware protection feature
  - Suppression Rules
    - ignore findings based on rules
  - Trusted IP List

- Amazon Macie
  - data privacy
  - monitoring, protection of sensitive data
  - monitors S3 buckets for PII
  - can use regex-based rules for identification
