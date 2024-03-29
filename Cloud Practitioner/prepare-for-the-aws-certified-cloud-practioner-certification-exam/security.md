
## Intro
- Exam Security Domain
  - Define AWS shared responsibility model
  - Define AWS Cloud security and compliance concepts
  - Identify AWS access management capabilities
  - Identify resources for security support
- Changes from CLF-01 to CLF-02
  - Migration and business application have been added into the exam content
  - Increase in breadth, but not as much depth

### Security in the Cloud
- Security is a shared responsibility between AWS and the customer
  - AWS is responsible for the security of the cloud
    - Physical properties of the cloud hardware and software
    - Data encryption + patching servers
  - Customer is responsible for security in the cloud
- Principle of Least Privilege
  - Only give the minimum amount of access to a user to perform their job
  - Use IAM to create groups and roles
  - Use IAM to create policies
- Security Pillar of a Well-Architected Framework
  - Identity and Access Management
  - Detective Controls
  - Infrastructure Protection
  - Data Protection
  - Incident Response

### Security Services
- IAM (Identity and Access Management)
  - Create and manage AWS users and groups
  - Use IAM policies to define permissions
  - Use IAM roles to delegate permissions
- Web Application Firewall (WAF)
  - Protect web applications from attacks
  - Monitor web requests
  - Block requests that don't meet the rules
- AWS Shield
  - Protect web applications from DDoS attacks
  - Most often by making excessive requests to a server to make it unavailable or crash
  - AWS Shield Standard
    - Automatically included with AWS services
    - Route53, CloudFront helps with all known attacks
  - AWS Shield Advanced
    - Protect against more sophisticated attacks
    - 24/7 access to the DDoS response team
    - Cost money
  - Amazon Inspector
    - Analyze the behavior of your AWS resources
    - Identify potential security issues
  - AWS Trusted Advisor
    - Analyze your AWS environment and provide best practices
    - Best practices for security, performance, reliability, and cost optimization
  - Amazon GuardDuty
    - Threat detection service
    - Monitor for malicious activity
    - Monitor for unauthorized behavior
    - Monitor for resource vulnerabilities