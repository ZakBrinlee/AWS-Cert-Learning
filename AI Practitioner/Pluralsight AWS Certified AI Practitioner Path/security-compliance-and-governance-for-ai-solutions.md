# [AWS Certified AI Practitioner (AIF-C01): Security, Compliance, and Governance for AI Solutions](https://app.pluralsight.com/ilx/video-courses/aws-certified-ai-practitioner-ai-solutions-security-compliance-governance/course-overview)

Started: April 9th, 2026

Completed: April 9th, 2026

## Top Notes
- AI security starts with **identity, access, and encryption**: use IAM policies/roles, attribute-based access control when needed, and always apply the **Principle of Least Privilege**.
- Key AWS security services to know:
  - **KMS** for encryption at rest and in transit, **Macie** for sensitive data discovery in S3, and **PrivateLink** for private network connectivity.
- **Data governance depends on traceability**: know **data origins**, **source citation**, **lineage**, and **cataloging** so data quality, integrity, and compliance can be validated.
- Common AI security threats include **prompt injection**, **insecure output handling**, **training data poisoning**, and **model denial of service**.
  - Supporting AWS protections: **GuardDuty** (threat detection), **Inspector** (vulnerability findings), **Detective** (investigation), **WAF** (web protection), **Shield** (DDoS), and **Cognito** (identity/adaptive protection).
- Compliance/GRC is about **accountability, transparency, and continuous monitoring**.
  - Core standards/services: **PCI-DSS, NIST, HIPAA, GDPR, ISO, SOC**, plus **AWS Artifact** for compliance reports and documentation.
- AWS governance services to remember:
  - **AWS Config** (resource configuration + change tracking), **Audit Manager** (collects audit evidence), **CloudTrail** (activity history), **Trusted Advisor** (best-practice checks), plus GuardDuty/Inspector/Detective for ongoing risk visibility.
- Strong data governance follows the **data lifecycle**: collect → process → store → consume → archive → dispose.
  - Use **S3 Object Lock** for WORM immutability and **CloudWatch/CloudTrail** for logging, monitoring, and AI system oversight.
- Governance frameworks should define **policies, review processes, and intervention plans**, and should vary based on both **application type** (public consumer vs enterprise) and **model type** (pre-trained, fine-tuned, self-trained).

### Securing AI Systems
- IAM Roles & Policies
  - IAM Policies
    - identity based
    - fine grained
    - AI resource access
  - IAM Roles
    - RBAC - role based access control
  - Attribute access control
    - Boolean based values
    - dynamic & granular
  - Utilize "Principle of Least Privilege"

- Services and Features for Securing AI System
  - Encryption -> KMS - Key Management Service -> at Rest and In-transit
    - Customer Managed Key
    - AWS Managed Keys
    - AWS Owned keys 
  - Macie -> used to secure data in S3
    - finding sensitive data
  - AWS Private Link -> private network connection

- Data History
  - Data Origins
    - How, where the data was collected
    - cleaned info
    - transformation info
  - Data Source Citation
  - Data Lineage
    - history, origin, everything tracking
  - Data Cataloging
    - organizes and documents components, datasets, models with licenses, sources and metadata
  
- Secure Data Engineering
  - Data quality and integrity are 
    - we ensure this by looking at the history
  - Data Access Controls
    - IAM
    - Encryption
    - Network Controls
    - Monitor
  - Compliance
    - PII
    - PHI
    - Privacy Enhancement

- AI System Security Risk and Threats
  - Amazon GuardDuty -> Threat Detection
    - training data poisoning
    - misuse
    - misconfiguration
  - Amazon Inspector
    - identify vulnerabilities
  - Amazon Detective
    - incident response/detection

- Application and Infra Security for AI Systems
  - 10 ten security risks
    - Prompt Injection
    - Insecure output handling
    - Training data poisoning
    - model denial of service
  - AWS Services to support security
    - WAF (Web Application Firewall)
    - AWS Shield -> DDoS attacks
    - AWS Cognito -> identity and access management -> adaptive protections

### Governance and Compliance for AI Systems
- Regulatory Compliance Standards for AI Systems
  - GRC -> Governance Risk Compliance
  - AWS Config
    - provide details on configuration to resources
  - Amazon Inspector
    - scan & assessments of risks
  - Compliance -> rooted in accountability and transparency
    - PCI-DSS
    - NIST
    - HIPPA
    - GDRC
    - ISO
    - SOC -> internal controls
  - AWS Artifact -> provides docs, reports, etc for compliance

- AWS Services for GRC
  - AWS Config
    - provides detailed info about resources
    - track changes
  - AWS Inspector -> scans, assessments, process findings
    - vulnerability management
  - AWS Detective
    - aids in the investigation of security incidents
  - AWS Audit manager
    - audit usage for GRC
    - gathers evidence for auditing control effectiveness
  - AWS Audit Manager
    - tracks changes
  - AWS Artifact
    - access to security and compliance docs, certs, and reports
  - AWS Trusted Advisor
    - continuously evals against architecture pillars
    - recommends remediation changes
  - AWS GuardDuty
    - monitoring and alerting
  - AWS Cloudtrail -> record all activity

- Data Governance Strategies
  - Data Lifecycle
    - collect -> process -> store -> consumption -> archive -> disposal
  - S3 Object locking
    - WORM data immutability
  - Logging and monitoring
    - CloudWatch & CloudTrail
      - input/output behavior
      - perf metrics
      - security events
      - infrastructure
      - responsible AI usage

- Governance Protocols
  - Policies
    - align with overall org missions, goals, processes etc
  - Reviews
    - technical reviews
    - non-tech reviews
    - testing
  - Review intervention
    - have a plan in place for how to function when an issue is found

- Governance Frameworks
  - Application
    - Public Consumer
    - Enterprise
  - Model
    - pre-trained
    - fine-tuned
    - self-trained
  
