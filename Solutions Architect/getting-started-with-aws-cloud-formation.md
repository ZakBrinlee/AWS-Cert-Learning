# [Getting Started with AWS CloudFormation](https://explore.skillbuilder.aws/learn/course/3627/play/12382/getting-started-with-aws-cloudformation)

Started: May 30th, 2024
Completed: May 30th, 2024

## Links
- [CloudFormation User Guide](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/Welcome.html)

## Notes
#### CloudFormation Basics
- Infrastructure as Code (IaC)
- CloudFormation is a service that helps you model and set up your Amazon Web Services resources so that you can spend less time managing those resources and more time focusing on your applications that run in AWS.
- Benefits
  - Model a collection of aws and non-aws resources
  - Provision and update them in an orderly and predictable fashion
  - Manage the resources throughout their lifecycles
- Defined resources in a structured file format called a template.
  - JSON or YAML

- Additional benefits
  - Automate best practices
    - apply DevOps and GitOps best practices
  - Scale infrastructure globally
    - manage multiple environments
    - share templates across teams/organizations
  - Integrate with other AWS services
    - use CloudFormation with other AWS services
      - IAM, AWS Config, AWS Service Catalog, etc.
  - Manage third-party and private resources
    - model, provision and manage third-party resources
  - Extend CloudFormation with the community
    - use open-source tools and frameworks
    - share templates with the community

- Ways to use CloudFormation
  - Single Developers
    - avoid costs by rapidly provisioning and tearing down resources
    - Great for testing out new ideas
  - Enterprise Teams
    - enforce best practices and governance
    - share templates across teams
  - Disaster Recovery
    - quickly re-create resources in another region
    - enabling disaster recovery and business continuity

- Tips
  - When creating a stack, it is a best practice to create an integration pipeline
  - Careful of resource lifecycles differences and how it affects your stack

#### Using CloudFormation
- Basic Technical concepts
  - Resources
    - the building blocks of your CloudFormation template
    - represent the different components/AWS services of your stack
  - Templates
    - JSON or YAML files that define the resources in your stack
    - Includes resources and how they depend on each other
  - Stack
    - a collection of resources that you manage as a single unit
  - StackSet
    - named set of stacks that use the same template, but applied to different regions or accounts
    - Ability to create, update, or delete stacks across multiple accounts and regions with a single operation
