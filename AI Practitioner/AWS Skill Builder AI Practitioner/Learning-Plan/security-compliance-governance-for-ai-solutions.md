# [Security, Compliance, and Governance for AI Solutions](https://skillbuilder.aws/learn/YFACXFGBSJ/security-compliance-and-governance-for-ai-solutions/YZTVAG8P4Q?parentId=SU2A1EJM1A)

Started: April 21, 2026

Completed: April 21, 2026

### Top notes:
- Regulated AI workloads require controls for auditability, retention, privacy, and least-privilege access.
- Core compliance frameworks to know: NIST, ENISA, ISO, SOC, HIPAA, GDPR, and PCI DSS.
- Key AWS governance/compliance services: AWS Config, Amazon Inspector, AWS Audit Manager, AWS Artifact, AWS CloudTrail, and AWS Trusted Advisor.
- Secure AI with layered defenses: IAM, KMS encryption, VPC/PrivateLink isolation, and GuardDuty/Detective/Security Hub monitoring.
- Strong data governance depends on lifecycle management, data quality/integrity, privacy protections, and clear retention/residency policies.
- Data and model lineage (source documentation, cataloging, model cards) is essential for traceability, risk management, and responsible AI.

## Notes
### Applying Governance & Compliance for AI Systems
#### Compliance Standards for AI Systems
- AWS supports 143 security standards and compliance certifications.
- NIST
- European Union Agency for Cybersecurity (ENISA) 
    - contributes to the EU’s cyber policy
- ISO
    - security standard that outlines recommended security management practices and comprehensive security controls
- AWS System and Organization Controls (SOC) 
    - Reports are independent assessments conducted by third parties that show how AWS has implemented and 
    maintained key compliance controls and objectives
- HIPPA
- General Data Protection Regulation (GDPR)
    - European Union's GDPR safeguards the fundamental right of EU citizens to privacy and the protection of their personal information
- PCI DSS
    - private information security standard that is managed by the PCI Security Standards Council

- Regulated is a common term used to indicate that a workload might need special consideration, because of some form of compliance that must be achieved
- You are operating in a regulated context when you must comply with regulatory frameworks such as HIPAA, GDPR, PCI DSS, and others.
- Questions to ask to determine if you need to comply to a regulatory framework such as:
    - Do you need to audit this workload?
    - Do you need to archive this data for a period of time?
    - Will the predictions created by my model constitute a record or other special data item?
    - Do any of the systems you get the data from contain data classifications that are restricted by your organization’s governance, but not a regulatory framework?

#### AWS Services for Governance and Compliance
- AWS Config
    - detailed view of the configuration of AWS resources in account
- AMZN Inspector
    - vulnerability management service that continuously scans your AWS workloads for software vulnerabilities and unintended network exposure
- AWS Audit Manager
    - continually audit your AWS usage to streamline how you manage risk and compliance with regulations and industry standards.
- AWS Artifact
    - on-demand downloads of AWS security and compliance documents, such as AWS ISO certifications, PCI reports, and SOC Reports
- AWS CloudTrail
- AWS Trusted Advisor
    - continuously evaluates your AWS environment using best practice checks across the categories of cost optimization, performance, resilience, security, operational excellence, and service limits
    - provides recommendation actions

#### Data Governance Strategies
- Key data governance strategies
    - Data quality and integrity
    - Data protection and privacy
    - Data lifecycle management
    - Responsible AI
    - Governance structures and roles
    - Data sharing and collaboration
- Key data management concepts
    - Data lifecycles -> management of data throughout its entire lifespan, from creation to eventual disposal or archiving
    - Data logging -> systematic recording of data related to the processing of an AI workload
    - Data residency -> physical location where data is stored and processed
    - Data monitoring -> involves the ongoing observation and analysis of data used in AI workloads
    - Data analysis -> used to understand the characteristics, patterns, and relationships within the data used for AI workloads
    - Data retention -> policies define how long data should be kept for AI workloads

#### Approaches for Implementing Governance Strats
- important to establish and follow governance strategies to ensure responsible development and deployment
- Key approaches:
    - Policies -> Develop clear and comprehensive policies that outline the organization's approach to generative AI, including principles, guidelines, and responsible AI considerations
    - Review cadence -> Implement a regular review process to assess the performance, safety, and responsible AI implications of the generative AI solutions
    - Review strategies -> Develop comprehensive review strategies that cover both technical and non-technical aspects of the generative AI solutions
    - Transparency standards -> Commit to maintaining high standards of transparency in the development and deployment of generative AI solutions
    - Team training requirements -> Ensure that all team members involved in the development and deployment of generative AI solutions are adequately trained on relevant policies, guidelines, and best practices

- Monitoring an AI System
    - Key aspects
        - Performance metrics
        - Infrastructure monitoring
        - Bias & fairness
        - Compliance & responsible AI

### Securing AI Systems
#### Security and Privacy Considerations for AI Systems
- Threat detection
- Vulnerability management
- Infrastructure protection
- Prompt injection
- Data encryption

#### AWS Services & Features for Securing AI Systems
- Four foundational AWS security services
    - Security Hub
        - single dashboard w/ all security findings + create&run automated playbooks
    - AWS KMS
        - Encrypts data
    - GuardDuty
        - threat detections
    - AWS Shield Advanced
        - protects again DDoS events + WAF
- AI related security services
    - AMZN Macie
        - automated sensitive data discovery at scale
    - AWS Identity and Access Management (IAM)
        - access management with fine-grained permissions
    - AWS IAM Identity Center and IAM Access Analyzer
        - apply privileges to resources
    - SageMaker Role Manager
        - build and manage persona-based IAM roles for common ML needs
    - AWS Network Firewall 
        - everything network, encrypt + decrypt
    - Amazon Virtual Private Cloud (Amazon VPC)
        - isolated virtual network
    - AWS PrivateLink
        - establish private connectivity from your Amazon VPC to Amazon Bedrock
    - Amazon GuardDuty &&
    - Amazon Inspector &&
    - Amazon Detective
        - intelligent threat detection
    - AWS Security Hub &&
    - AWS Config &&
    - AWS Audit Manager &&
    - AWS Artifact
        - automated incident response and compliance
    - AWS Shield Advanced and AWS Firewall Manager
        - WAF style protection

#### Understanding Data & Model Lineage
- Source citation and documenting data origins are essential tasks that contribute to securing your AI systems
- Tools & techniques
    - Data lineage
        - technique used to track the history of data, including its origin, transformation, and movement through different systems
    - Cataloging
        - systematic organization and documentation of the datasets, models, and other resources used in the development of a generative AI system
    - Model cards
        - standardized format for documenting the key details about an ML model, including its intended use, performance characteristics, and potential limitations

#### Best Practices for Secure Data Engineering
- essential for ensuring the safety and reliability of AI and generative AI systems
- Assessing Data Quality
    - Completeness
    - Accuracy
    - Timeliness
    - Consistency
- Implementing Privacy-Enhancing Technologies
    - data masking, obfuscation or differential privacy mechanisms
    - use encryption, tokenization or secure multi-party computation to protect data
- Data Access Control
    - comprehensive data governance framework
    - RBAC controls
    - authentication + authorization mechanisms
    - monitor and log all data access activities
    - principle of least privilege
- Data Integrity
    - data validation + integrity check at various stages of pipeline
    - robust data backup + recovery
    - transaction management and atomicity principles
    - maintain detailed data lineage and audit trails
    - monitor and test data integrity controls regularly

- AWS Privacy Reference Architecture
    - set of guidelines to assist in the design and implementation of privacy-supporting controls within AWS services
