# [Configuring and Deploying VPCs with Multiple Subnets](https://explore.skillbuilder.aws/learn/course/499/configuring-and-deploying-vpcs-with-multiple-subnets;lp=1044)

Started: May 31st, 2024
Completed: May 31st, 2024

## Notes
### Amazon VPC Deployment
#### Intro
- Identify what an Amazon Virtual Private Cloud (Amazon VPC) is
- Describe the difference between a default Amazon VPC and a custom Amazon VPC
- Demo: Deploying a simple Amazon VPC through the AWS Management Console
- Demo: Deploying a simple Amazon VPC through the AWS Command Line Interface (AWS CLI)

#### Virtual Private Cloud (VPC)
- VPCs are virtual networks, associated to a single AWS Region, and is a service that defines a boundary around the AWS services and resources that customers choose to deploy and how those services and resources communicate with each other and external networks such as the internet

- Two Types of VPCs:
  - Default
    - Each default Amazon VPC creates a public subnet within each Availability Zone within the supported Region. 
    - Each public subnet is configured with a default route for all inbound and outbound traffic that routes IP traffic to the general internet. 
    - AWS sets up the configuration that allows all traffic, so there is no privacy and isolation by default.
    - Only one default Amazon VPC per Region is permitted.
    - Each default comes with one Amazon VPC Classless Inter-Domain Routing (CIDR) range, which is a given range of IP addresses.
  - Custom
    - Unlike a default Amazon VPC, each component of a custom Amazon VPC must be explicitly defined when you create it; nothing is allowed in or out without explicit configuration. 
    - Some decisions, such as the IPv4 and IPv6 support and the CIDR block for the Amazon VPC, cannot be modified later. 
    - Other features of an Amazon VPC, such as subnets, routing, and VPC endpoints, can be modified as needed.

- Ways to secure connection between VPC and on-premises network:
  - AWS Direct Connect
  - AWS Site-to-Site Virtual Private Network (VPN)
  - AWS Client VPN

#### Deploying a Basic Amazon VPC
- Considerations + Steps
  - VPC can't live in more than one Region
    - Choose region based on requirements
  - Subnet is restricted to a single Availability Zone
  - Launch AWS resources in the same Subnet
  - Connect an Internet Gateway to the VPC if public access is needed
  - Configure Route Tables to direct traffic

### Securing and Configuring High Availability
- Describe AWS Identity and Access Management (IAM)
- Identify network access control lists (network ACLs)
- Identify security groups
- Compare and contrast stateless and stateful controls
- Identify Elastic Load Balancing and the different types

#### IAM
- IAM lets you control who can configure and manage your Amazon VPCs
- IAM users 
  - represent people and also applications that need access to an AWS account. 
- IAM groups 
  - are groups of related users, for example, your development team, sysadmins, storage engineers, and the finance team.
- IAM roles 
  - are used by AWS services. IAM roles can also be used to grant external access to your AWS account along with access to resources and services in the AWS account. For example, an Amazon Elastic Compute Cloud (Amazon EC2) instance inside your AWS account requires programmable access to Amazon CloudWatch, Amazon Simple Storage Service (Amazon S3), and the like.  
- IAM policies 
  - are used to allow or deny access to AWS services. IAM policies must be attached to an IAM user, an IAM group, or an IAM role. AWS provides preconfigured policies, AWS Managed Policies, that can be assigned as necessary. Customers can also create custom inline policies that allow or deny unique combinations of permissions that best suit the customer's AWS environment. On their own, policies just sit there, to take action they must be attached to a user, a group, or a role.  

#### Security Features
- Two main features
  - Network Access Control Lists (NACLs)
    - filter traffic at the subnet level
    - only manages traffic crossing the subnet boundary
    - stateless
  - Security Groups
    - Attached to AWS resources (elastic network interfaces: ENIs)
    - Can reference other security groups
    - stateful

- Security Best Practices
  - Use multiple Availability Zones deployments for high availability
  - Use Amazon CloudWatch to monitor VPC components
  - Use VPC Flow Logs to monitor network traffic
  - Chaining security groups together to create a layered security model
    - Allow port 22 [Secure Shell (SSH)] access to every tier for administration.
    - Only allow your web servers to have port 80 (HTTP) or port 443 (HTTPS) open to the internet.
    - Your application servers would only allow traffic that originated from the web server security group.
    - Your database servers would only allow traffic that originated from the application server security group.

#### Adding High Availability
- Elastic Load Balancers (ELBs)
  - automatically distributes incoming application traffic across multiple targets, such as Amazon EC2 instances, containers, IP addresses, AWS Lambda functions, and virtual appliances

- Classic Load Balancer
- Application Load Balancer
- Network Load Balancer
- Gateway Load Balancer

- To increase the availability of your Amazon VPC based applications, make sure to use these strategies:
  - Use a second subnet, either for more capacity or as a backup option.
  - Deploy your second subnet to a second Availability Zone to maximize availability.
  - One route table can be associated with multiple subnets but a subnet can only have one route table.
  - Manage traffic between resources using Elastic Load Balancing.
  - Use Elastic Load Balancing to detect unhealthy resources and automatically fail over to healthy ones in your other subnet(s).

### Multi-Tier Architecture
#### Production-Ready: Multi-Tier Architecture for an Amazon VPC
- AWS Cloud Adoption Framework (AWS CAF) key capabilities:
  - **AWS Identity and Access Management (IAM)**: Define, enforce, and audit user permissions across AWS services, actions, and resources.
  - **Detective control**: Improve your security posture, reduce the risk profile of your environment, and gain the visibility you need to spot issues before they impact your business.
  - **Infrastructure security**: Reduce the surface area of the infrastructure you manage and increase the privacy and control of your overall infrastructure on AWS.
  - **Data protection**: Implement appropriate safeguards that help protect data in transit and at rest by using natively integrated encrypted services.
  - **Incident response**: Define and launch a response to security incidents as a guide for security planning.

- Design considerations for different tier architecture
  - Single-tier
    - Doesn't use any private data
    - Can be unavailable for extended periods if something fails (also consider Single-AZ deployments)
    - Will only ever be used by you
  - N-tier
    - Subnets and Amazon VPCs don't cost money, they just cost IP addresses.
    - Each subnet you create has to reserve five IP addresses for AWS, the first four and the last.
    - You can't resize a CIDR block after it's been created, so any IP addresses you reserve in that CIDR block are potentially stuck there until you delete that subnet. 
    - Storing resources in separate subnets increases the layers of security between them, but too many subnets can risk your Amazon VPC running out of IP addresses.