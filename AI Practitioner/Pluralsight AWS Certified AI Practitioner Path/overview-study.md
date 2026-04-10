# AWS Certified AI Practitioner (AIF-C01) — Overview Study Guide

> Last updated: April 10, 2026
> All 5 course modules completed. This document consolidates key concepts, AWS services, and exam tips across all domains.

---

## Exam Domain Breakdown

| Domain | Topic | Weight (approx.) |
|--------|-------|-------------------|
| 1 | Fundamentals of AI and ML | ~20% |
| 2 | Fundamentals of Generative AI | ~24% |
| 3 | Applications of Foundation Models | ~28% |
| 4 | Guidelines for Responsible AI | ~14% |
| 5 | Security, Compliance, and Governance for AI Solutions | ~14% |

---

## Domain 1: Fundamentals of AI and ML

### Core Hierarchy
- **AI** → **ML** → **Deep Learning** → **Generative AI** (broad to narrow)
- **Foundation Models**: Large pre-trained models, fine-tuned for specific tasks (act as blueprints)
- **LLMs**: Foundation models specifically for understanding and generating language

### Data Types
- **Structured Data**: Tabular data, time series
- **Unstructured Data**: Text (emails, social media), images/videos without labels, audio files

### The ML Pipeline
1. **Generate Data**: Fetch → Clean (handle missing/duplicate data) → Prepare (feature engineering)
   - Feature selection, extraction, dimensionality reduction (PCA), categorical encoding
   - **Exploratory Data Analysis (EDA)**: Examine dataset before modeling — summarize features, identify patterns, compute correlation metrics to quantify variable relationships
2. **Train Model**: Tune parameters & hyperparameters
3. **Deploy & Monitor**

### Hyperparameters vs. Parameters
| | Hyperparameters | Parameters |
|-|-----------------|------------|
| Set when? | Before training | Learned during training |
| Examples | Learning rate, batch size, epochs | Weights and biases |
| Tuning | Grid search / random search | Auto-adjusted by algorithm |

### Learning Types
| Type | Key Characteristic |
|------|--------------------|
| Supervised | Labeled input data; Classification & Regression tasks |
| Unsupervised | No labels; clustering & anomaly detection |
| Semi-supervised | Mix of labeled and unlabeled data |
| Self-supervised | Model recognizes patterns from data itself (e.g., Gmail autocomplete) |
| Reinforcement | Feedback loop; model adapts from rewards/penalties |

### Model Fit
- **Underfitting (High Bias)**: Too simple, performs poorly on training AND test data
- **Overfitting (High Variance)**: Memorizes noise, performs well on training but poorly on unseen data
- **Balanced**: Low bias + low variance — generalizes well

### Evaluation Metrics
| Task | Metrics |
|------|---------|
| Classification | Accuracy, Precision, Recall, F1 Score |
| Regression | MAE, RMSE, R² |

### Key AWS AI/ML Services
| Service | Purpose |
|---------|---------|
| Amazon Rekognition | Image/video analysis, facial recognition, object detection; supports custom moderation adaptors and custom labels |
| Amazon Textract | Extract text/data from scanned documents and forms; real-time (sync) or async (batch) processing |
| Amazon Comprehend | NLP — sentiment analysis, entity recognition, language detection; supports custom classification and custom entity recognition |
| Amazon Translate | Real-time and batch language translation |
| Amazon Polly | Text-to-speech |
| Amazon Transcribe | Speech-to-text (ASR) |
| Amazon Lex | Chatbot builder (intents + slots); same tech as Alexa; integrates with Lambda and Comprehend |
| Amazon Forecast | Time-series predictions using historical data |
| Amazon Kendra | Intelligent NLP-based enterprise search |
| Amazon Personalize | Recommendation engine using pre-defined recipes |
| **Amazon SageMaker** | Fully managed end-to-end ML platform |

### SageMaker Key Features
- **Studio**: IDE for building models
- **Pipelines**: ML workflow versioning and step management
- **Autopilot**: AutoML — upload data + target variable
- **Data Wrangler**: Import → Clean → Feature Engineer → Visualize (EDA)
- **Feature Store**: Centralized hub for storing/retrieving ML features

---

## Domain 2: Fundamentals of Generative AI

### Core Concepts
- **Tokens**: Fundamental building blocks of data models
- **Context Window**: Max tokens a LLM can process at once
- **Chunking**: Divides input into manageable pieces
- **Embeddings**: Numerical representations of text, images, audio (used in recommendation systems)
- **Vectors**: Coordinates that indicate where a value is located; stored in **vector databases**

### GenAI Model Types
| Type | Description | Examples |
|------|-------------|---------|
| Foundation Models | Large pre-trained, fine-tunable | Amazon Titan, Claude |
| Transformer LLMs | Process input to generate human-readable output | GPT-4 |
| Multi-modal | Handle multiple input/output types | Amazon Titan Embeddings |
| Diffusion | High-quality image/video generation (forward: add noise; reverse: remove noise) | Art/video generation |

### Foundation Model Lifecycle
**Data Selection → Model Selection → Pre-training → Fine-tuning → Evaluation → Deployment → Feedback**

### Benefits vs. Risks
| Benefits | Risks |
|----------|-------|
| Adaptability | Hallucinations |
| Real-time responsiveness | Nondeterminism |
| Simplicity | Bias |
| | Limited interpretability |

### Model Selection Criteria
- **Technical**: Latency, throughput, constraints, compliance
- **Business**: Efficiency/accuracy, conversion rate, cross-domain performance, customer lifetime value

### AWS GenAI Services
| Service | Purpose |
|---------|---------|
| Amazon Bedrock | Managed access to multiple foundation models |
| SageMaker JumpStart | Pre-trained models + deployment (real-time, serverless, batch, async) |
| PartyRock | Rapid experimentation with models/apps |
| Amazon Q | Non-technical Q&A, dashboard generation, executive summaries |
| Amazon Q Developer | Code generation, automation, integration |

### Cost Tradeoffs
- Higher responsiveness/availability → higher cost
- Redundancy & performance → higher cost
- Provisioned throughput & custom models → higher cost

---

## Domain 3: Applications of Foundation Models

### Foundation Model Selection Factors
- **Modality** → type of data the model handles
- **Latency** → processing speed
- **Multi-lingual** → language support needs
- **Model size & complexity**
- **Customization** → fit to specific business needs
- **Input/output length** → short vs. long context

### Inference Parameters
| Parameter | Range | Effect |
|-----------|-------|--------|
| Temperature | 0.0–1.0 | Controls randomness; 0.0 = deterministic/focused, 1.0 = highly creative/random |
| Top-K | 0–500 | # of candidate tokens considered; lower = more predictable |
| Top-P | 0.0–1.0 | Cumulative probability cutoff; lower = safer outputs |

### Retrieval-Augmented Generation (RAG)
- Pairs a foundation model with an **external knowledge base**
- Cost-effective way to give models up-to-date/domain-specific knowledge without retraining
- Use cases: customer support, product documentation, research & analysis

### Customization Cost Ladder (Low → High Cost, Low → High Control)
1. **In-context learning** — low cost, flexible
2. **RAG** — cost-effective, uses external data
3. **Fine-tuning** — moderate cost, balances control and efficiency
4. **Pre-training** — highest cost, full control over model behavior

### Vector Storage on AWS
| Service | Best For |
|---------|----------|
| OpenSearch | Search engines, recommendation systems (combines vector + text search) |
| Aurora | E-commerce, real-time recommendations (scalable, RDS capabilities) |
| Neptune | Knowledge graphs, social networks (graph queries) |
| DocumentDB | Chatbots, personalization (schema-less storage) |
| RDS for PostgreSQL | Multi-media search, AI apps (pgvector extension) |

### Prompt Engineering Techniques
| Technique | Description |
|-----------|-------------|
| Zero-shot | Task given with no examples |
| Single-shot | One example provided with prompt |
| Few-shot | Multiple examples provided |
| Chain-of-thought | Model breaks problem into logical steps |
| Negative prompts | Tells the model what NOT to generate; reduces unwanted content |
| Prompt templates | Reusable structured templates |

### Prompt Security Risks
- **Prompt injection/hijacking** — attacker manipulates prompt to produce unintended output
- **Data poisoning** — maliciously inserting false/harmful training data
- **Exposure** — model reveals sensitive information
- **Jailbreaking** — clever prompts that bypass safety constraints

### Fine-tuning Methods
- **Continuous pre-training** — keep an existing model up to date with new data (distinct from initial pre-training)
- **Instruction tuning** — provide guidelines/directives
- **Domain adaptation** — general → specific field
- **Transfer learning** — fine-tune pre-trained model for a new task

### Fine-tuning Data Requirements
- Data curation, governance, representativeness, labeling quality
- **RLHF (Reinforcement Learning from Human Feedback)** — reward model trained with human feedback

### Evaluation Metrics for Foundation Models
| Metric | What It Measures |
|--------|-----------------|
| ROUGE | Recall/overlap between generated and reference text (summarization) |
| BLEU | Translation quality (bilingual evaluation) |
| BERTScore | Semantic similarity via embeddings |

### Business Objective Alignment for FM Evaluation
- **Productivity** — efficiency gains from AI integration
- **User engagement** — how well the model drives interaction
- **Task accuracy** — reliability of the AI at achieving intended tasks

### Bedrock Agents
- Orchestrate multi-step tasks: **Data Retrieval → Analysis → Response Generation**
- Features: RAG, dynamic code generation, memory retention, action schemas, prompt engineering

---

## Domain 4: Guidelines for Responsible AI

### Core Principles
- **Ethical, Transparent, and Trustworthy**
- **Transparency** = HOW a model reaches its decision (access to training data, algorithms)
- **Explainability** = WHY the model made a specific decision

### Bias vs. Variance (Responsible AI Context)
- **High Bias** → underfitting → poor performance overall
- **High Variance** → overfitting → fails on unseen data
- **Subgroup analysis** → ensures the model is accurate and fair across all groups

### Types of Bias
| Type | Description |
|------|-------------|
| Measurement bias | Faulty/inaccurate data captured |
| Sampling bias | Training data not representative of the full population |
| Confirmation bias | Ignoring data that contradicts a preexisting belief |
| Observer bias | Labeler's subjective opinions infect labeled data |

### GenAI-Specific Risks
- **Hallucinations** — misleading, plausible-sounding false outputs
- **Prompt misuse / Model exposure** — model reveals confidential/operational information
- **IP infringement** — generated content may violate intellectual property

### Human-Centered Design for Explainable AI
- Design for **amplified decision-making** (high-pressure situations)
- Design for **unbiased decision-making** (transparent processes + bias mitigation training)
- Design for **human and AI learning** (cognitive apprenticeship, personalization, user-centered design)

### AWS Tools for Responsible AI
| Tool | Purpose |
|------|---------|
| **SageMaker Clarify** | Detects bias in data & predictions; visualizes distribution across groups; explains model decisions |
| **SageMaker Ground Truth** | Automated data labeling with human + machine assistance; GT Plus for expert tasks |
| **SageMaker Model Cards** | Documents model purpose, risk ratings, limitations, ethics, performance metrics |
| **SageMaker Model Monitor** | Post-deployment monitoring for data drift, bias, and performance declines |
| **Amazon A2I (Augmented AI)** | Human review triggered randomly or by confidence score (employees, 3rd party, Mechanical Turk) |
| **Bedrock Guardrails** | Filters/blocks harmful inputs and outputs from foundation models |

### Bedrock Guardrails — What It Blocks
- Harmful content categories
- Prompt attacks
- Denied topics
- Profanity
- PII (Personally Identifiable Information)
- PHI (Protected Health Information)

---

## Domain 5: Security, Compliance, and Governance for AI Solutions

### Identity & Access Security
- **IAM Policies**: Identity-based, fine-grained, AI resource access control
- **IAM Roles**: Role-based access control (RBAC)
- **Attribute-Based Access Control (ABAC)**: Boolean/dynamic granular control
- Always apply the **Principle of Least Privilege**

### Encryption & Data Security Services
| Service | Purpose |
|---------|---------|
| **AWS KMS** | Encryption at rest and in transit (Customer, AWS Managed, or AWS Owned keys) |
| **Amazon Macie** | Finds sensitive data in S3 |
| **AWS PrivateLink** | Private network connectivity |

### Data Governance Concepts
- **Data Origins** — how and where data was collected, cleaned, transformed
- **Data Source Citation** — references to data sources
- **Data Lineage** — full history and origin tracking
- **Data Cataloging** — organizes datasets, models with licenses, sources, and metadata

### AI System Security Threats (OWASP-style for AI)
1. Prompt injection
2. Insecure output handling
3. Training data poisoning
4. Model denial of service

### Threat Detection & Investigation Services
| Service | Role |
|---------|------|
| **GuardDuty** | Threat detection (data poisoning, misuse, misconfiguration) |
| **Inspector** | Vulnerability scanning and findings |
| **Detective** | Security incident investigation and response |
| **WAF** | Web Application Firewall — blocks common web attacks |
| **AWS Shield** | DDoS attack protection |
| **Amazon Cognito** | Identity management with adaptive protections |

### Compliance Standards to Know
- **PCI-DSS** — payment card industry
- **NIST** — cybersecurity framework
- **HIPAA** — health information privacy (protects PHI — Protected Health Information)
- **GDPR** — EU data protection regulation
- **ISO** — international standards
- **SOC** — internal controls reporting
- **AWS Artifact** — access to compliance docs, reports, and certifications

### GRC Services (Governance, Risk, Compliance)
| Service | Purpose |
|---------|---------|
| **AWS Config** | Detailed resource configuration + change tracking |
| **AWS Inspector** | Vulnerability management (scans, assessments, findings) |
| **AWS Detective** | Security incident investigation |
| **AWS Audit Manager** | Gathers audit evidence for GRC; tracks control effectiveness |
| **AWS Artifact** | Compliance docs, certs, and reports |
| **AWS Trusted Advisor** | Continuously evaluates against architecture pillars; recommends fixes |
| **AWS GuardDuty** | Monitoring and alerting for threats |
| **AWS CloudTrail** | Records all AWS account activity |
| **Amazon CloudWatch** | Logs, metrics, performance monitoring |

### Data Lifecycle (Governance)
**Collect → Process → Store → Consume → Archive → Dispose**

- **S3 Object Lock** — WORM (Write Once Read Many) data immutability
- **CloudWatch + CloudTrail** — logging, monitoring AI input/output behavior, security events, responsible AI usage

### Governance Frameworks
- **Governance Protocols**: Policies → Reviews (technical + non-technical) → Intervention plans
- **Application type**: Public consumer vs. Enterprise
- **Model type**: Pre-trained, Fine-tuned, Self-trained

---

## AWS Services Quick Reference (Full Exam Cheatsheet)

### AI/ML Core
| Service | One-liner |
|---------|-----------|
| SageMaker | End-to-end ML platform (Studio, Pipelines, Autopilot, Data Wrangler, Feature Store) |
| Rekognition | Computer vision (images, video, faces, objects) |
| Textract | Document text/data extraction |
| Comprehend | NLP (sentiment, entities, classification) |
| Translate | Language translation |
| Polly | Text-to-speech |
| Transcribe | Speech-to-text |
| Lex | Chatbot builder (intents + slots) |
| Forecast | Time-series demand forecasting |
| Kendra | Enterprise NLP search |
| Personalize | Real-time recommendations |

### Generative AI
| Service | One-liner |
|---------|-----------|
| Amazon Bedrock | Managed multi-FM access + Agents + Guardrails |
| SageMaker JumpStart | Pre-trained model hub + deployment options |
| PartyRock | No-code GenAI experimentation |
| Amazon Q | Business assistant (reports, summaries, Q&A) |
| Amazon Q Developer | Developer coding assistant |

### Responsible AI
| Service | One-liner |
|---------|-----------|
| SageMaker Clarify | Bias detection + model explainability |
| SageMaker Ground Truth | Data labeling (human + machine) |
| SageMaker Model Cards | Model documentation and risk rating |
| SageMaker Model Monitor | Post-deployment drift + bias monitoring |
| Amazon A2I | Human-in-the-loop review workflows |
| Bedrock Guardrails | Filter/block unsafe FM inputs and outputs |

### Security & Compliance
| Service | One-liner |
|---------|-----------|
| AWS KMS | Encryption key management |
| Amazon Macie | Sensitive data discovery in S3 |
| AWS PrivateLink | Private network connectivity |
| GuardDuty | Continuous threat detection |
| Inspector | Vulnerability assessments |
| Detective | Security incident investigation |
| WAF | Web application protection |
| Shield | DDoS protection |
| Cognito | Identity with adaptive protection |
| AWS Config | Resource config tracking |
| Audit Manager | Audit evidence collection |
| CloudTrail | API/activity history logging |
| Trusted Advisor | Best-practice recommendations |
| AWS Artifact | Compliance docs and reports |
| CloudWatch | Logs, metrics, monitoring |

---

## Study Plan

### Phase 1 — Concept Reinforcement (Days 1–2)
- [ ] Re-read Top Notes from all 5 domain files
- [ ] Quiz yourself on all evaluation metrics (classify vs. regression; ROUGE vs. BLEU vs. BERTScore)
- [ ] Drill the customization cost ladder: In-context → RAG → Fine-tuning → Pre-training
- [ ] Memorize the 4 AI security threats and their AWS service mitigations
- [ ] Review all model fit types (underfitting / overfitting / balanced) and how bias types cause them

### Phase 2 — AWS Service Mapping (Days 3–4)
- [ ] Cover the AWS Services Quick Reference above without looking
- [ ] For each SageMaker sub-feature, know when to use each one vs. the others
- [ ] For each vector storage option, know the use case (OpenSearch vs. Aurora vs. Neptune vs. DocumentDB vs. RDS)
- [ ] Know when to use Guardrails vs. A2I vs. Model Monitor vs. Clarify
- [ ] Distinguish GuardDuty / Inspector / Detective / Config / Audit Manager / Trusted Advisor roles

### Phase 3 — Practice Questions (Days 5–6)
- [ ] Review the official **AWS AIF-C01 Exam Guide** for task statements that may reveal gaps
- [ ] Complete AWS official sample questions for AIF-C01
- [ ] Focus on scenario-based questions (e.g., "Which service would you use to...?")
- [ ] Review any missed answers and tie back to the domain notes
- [ ] Practice distinguishing between similar services (Kendra vs. Comprehend, Lex vs. Comprehend, etc.)

### Phase 4 — Final Review (Day 7)
- [ ] Review all "Top Notes" sections from each domain file
- [ ] Quick pass over the AWS Services Quick Reference cheatsheet
- [ ] Light review of governance frameworks, compliance standards, and data lifecycle
- [ ] Rest — no new material

---

## Key Distinctions to Remember for the Exam

| Concept | Key Differentiator |
|---------|-------------------|
| Transparency vs. Explainability | Transparency = HOW the model decides; Explainability = WHY it made a specific decision |
| Temperature vs. Top-K vs. Top-P | Temperature = randomness level; Top-K = count of candidates; Top-P = cumulative probability threshold |
| RAG vs. Fine-tuning | RAG = external data at inference time (no retraining); Fine-tuning = retrains the model on specific data |
| Hyperparameters vs. Parameters | Hyperparameters = set before training; Parameters = learned during training |
| GuardDuty vs. Inspector vs. Detective | GuardDuty = detect threats; Inspector = find vulnerabilities; Detective = investigate incidents |
| CloudTrail vs. CloudWatch | CloudTrail = API/activity history; CloudWatch = metrics/logs/performance monitoring |
| SageMaker Clarify vs. Model Monitor | Clarify = bias detection + explainability (pre & post); Monitor = ongoing post-deployment drift alerts |
| A2I vs. Ground Truth | A2I = human review of model outputs; Ground Truth = human labeling of training data |
| ROUGE vs. BLEU vs. BERTScore | ROUGE = recall/overlap (summarization); BLEU = precision (translation); BERTScore = semantic similarity |
