# AWS Certified AI Practitioner (AIF-C01) — Study Guide

> A high-level overview and structured study plan built from the AWS Skill Builder AI Practitioner Learning Plan.
> **Estimated total study time: 3–5 hours**

---

## Table of Contents

1. [Exam Overview](#1-exam-overview)
2. [Domain Breakdown & Weights](#2-domain-breakdown--weights)
3. [Recommended Study Schedule](#3-recommended-study-schedule)
4. [Domain 1 — Fundamentals of AI & ML (20%)](#4-domain-1--fundamentals-of-ai--ml-20)
5. [Domain 2 — Fundamentals of Generative AI (24%)](#5-domain-2--fundamentals-of-generative-ai-24)
6. [Domain 3 — Applications of Foundation Models (28%)](#6-domain-3--applications-of-foundation-models-28)
7. [Domain 4 — Responsible AI (14%)](#7-domain-4--responsible-ai-14)
8. [Domain 5 — Security, Compliance & Governance (14%)](#8-domain-5--security-compliance--governance-14)
9. [AWS Services Quick Reference](#9-aws-services-quick-reference)
10. [Key Terms & Concepts Cheat Sheet](#10-key-terms--concepts-cheat-sheet)
11. [Practice & Additional Resources](#11-practice--additional-resources)

---

## 1. Exam Overview

| Detail | Info |
|---|---|
| **Exam Code** | AIF-C01 |
| **Exam Level** | Foundational |
| **Cost** | $150 USD |
| **Duration** | 90 minutes |
| **Questions** | 85 total (65 scored + 20 unscored pilot) |
| **Passing Score** | ~720 / 1000 |
| **Format** | Multiple choice, multiple response, ordering, matching, case study |
| **Delivery** | Pearson VUE (testing center or online proctored) |

**Prerequisite:** No formal prerequisites, but 6+ months of exposure to AI/ML concepts on AWS is recommended.

### Official Resources
- [AWS Certified AI Practitioner Exam Page](https://aws.amazon.com/certification/certified-ai-practitioner/)
- [AIF-C01 Exam Guide (PDF)](https://d1.awsstatic.com/training-and-certification/docs-ai-practitioner/AWS-Certified-AI-Practitioner_Exam-Guide.pdf)
- [AWS Skill Builder — Exam Prep Hub](https://skillbuilder.aws/category/exam-prep/ai-practitioner-AIF-C01)
- [AWS Whitepaper: Overview of Amazon Web Services](https://docs.aws.amazon.com/whitepapers/latest/aws-overview/introduction.html)

---

## 2. Domain Breakdown & Weights

| Domain | Title | Exam Weight | Suggested Study Time |
|--------|-------|:-----------:|:--------------------:|
| **1** | Fundamentals of AI & ML | 20% | ~45 min |
| **2** | Fundamentals of Generative AI | 24% | ~60 min |
| **3** | Applications of Foundation Models | 28% | ~75 min |
| **4** | Responsible AI | 14% | ~40 min |
| **5** | Security, Compliance & Governance | 14% | ~40 min |
| | **Final Review** | — | ~30 min |
| | **Total** | **100%** | **~5 hours** |

> Domain 3 carries the most exam weight — allocate extra time to prompt engineering and foundation model optimization.

---

## 3. Recommended Study Schedule

### Session 1 — AI & ML Fundamentals (~45 min)
**Goal:** Build a solid foundation in core AI/ML terminology and AWS services.
- Read: [fundamentals-of-ml-and-ai.md](./fundamentals-of-ml-and-ai.md)
- Read: [developing-ml-solutions.md](./developing-ml-solutions.md)
- Focus on: Learning paradigms, deep learning, ML lifecycle phases, SageMaker AI service mapping, MLOps, and the AWS AI services map

### Session 2 — Generative AI Fundamentals (~60 min)
**Goal:** Understand what foundation models are and how the GenAI ecosystem works.
- Read: [exploring-ai-use-cases-and-applications.md](./exploring-ai-use-cases-and-applications.md)
- Read: [developing-gen-ai-solutions.md](./developing-gen-ai-solutions.md) *(first half — FM lifecycle & selection)*
- Focus on: FM lifecycle, model architectures (Transformer, Diffusion, Multimodal, GAN, VAE), GenAI capabilities, risks, industry use cases, and model provider/task mapping

### Session 3 — Foundation Model Applications (~75 min)
**Goal:** Master prompt engineering, RAG, fine-tuning, and evaluation.
- Read: [developing-gen-ai-solutions.md](./developing-gen-ai-solutions.md) *(second half — optimization & evaluation)*
- Read: [essentials-of-prompt-engineering.md](./essentials-of-prompt-engineering.md)
- Read: [optimizing-foundation-models.md](./optimizing-foundation-models.md)
- Focus on: Prompt elements, inference parameters, all prompt techniques, RAG architecture vs. fine-tuning, evaluation metrics (ROUGE/BLEU/BERTScore), and prompt security risks

### Session 4 — Responsible AI (~40 min)
**Goal:** Know the 8 dimensions of responsible AI and the AWS tools that support them.
- Read: [responsible-ai-practices.md](./responsible-ai-practices.md)
- Focus on: 8 core dimensions, bias vs. variance, transparency vs. explainability, AWS tools by category, and responsible dataset preparation

### Session 5 — Security, Compliance & Governance (~40 min)
**Goal:** Understand compliance frameworks, data governance, and AWS security services for AI workloads.
- Read: [security-compliance-governance-for-ai-solutions.md](./security-compliance-governance-for-ai-solutions.md)
- Focus on: Compliance frameworks (NIST/GDPR/HIPAA/PCI DSS), AWS governance services, layered security architecture, data governance strategies, and data/model lineage

### Final Review (~30 min)
- Review the [AWS Services Quick Reference](#9-aws-services-quick-reference) table
- Work through the [Key Terms & Concepts Cheat Sheet](#10-key-terms--concepts-cheat-sheet)
- Take a timed practice question set (links in [Section 11](#11-practice--additional-resources))

---

## 4. Domain 1 — Fundamentals of AI & ML (20%)

> Source notes: [fundamentals-of-ml-and-ai.md](./fundamentals-of-ml-and-ai.md) · [developing-ml-solutions.md](./developing-ml-solutions.md) · [exploring-ai-use-cases-and-applications.md](./exploring-ai-use-cases-and-applications.md)

### 4.1 Core ML Concepts

#### Data Types
| Type | Examples |
|------|---------|
| **Structured** | Tabular (spreadsheets, CSV, databases), time-series data |
| **Unstructured** | Text documents, images, video frames, audio |

#### Three Learning Paradigms
| Paradigm | Training Data | Subcategories | Example Use Cases |
|----------|--------------|---------------|-------------------|
| **Supervised** | Labeled | Classification (labels/categories), Regression (continuous values) | Fraud detection, demand forecasting, image classification |
| **Unsupervised** | Unlabeled | Clustering (grouping), Dimensionality reduction (compressing features) | Customer segmentation, data visualization, anomaly detection |
| **Reinforcement** | Reward/feedback signal | — | Game playing, process optimization, robotics |

#### When to Use ML
- When rules rely on too many overlapping factors and are difficult to code manually
- When the scale of the problem makes human-coded rules impractical
- When the system needs to learn and improve from data over time

#### Inference Types
| Type | Priority | Use Case |
|------|----------|---------|
| **Batch** | Accuracy / throughput | Processing large datasets overnight; non-time-sensitive decisions |
| **Real-time** | Low latency | Fraud detection, recommendation engines, chatbots |

### 4.2 Deep Learning

- Uses **artificial neural networks** — computational models that mimic the human brain
- Organized into layers: **Input layer → Hidden layer(s) → Output layer**
- Learns by adjusting connection weights (parameters) between nodes
- Primary domains: **Computer Vision** and **Natural Language Processing (NLP)**

### 4.3 ML Development Lifecycle (7 Phases)

```
#1 Business Goal Identification
      ↓
#2 ML Problem Framing
      ↓
#3 Data Processing
      ↓
#4 Model Development
      ↓
#5 Model Deployment
      ↓
#6 Model Monitoring
      ↓
#7 Model Retraining
```

#### SageMaker AI Service Mapping by Phase

| Phase | SageMaker AI Services |
|-------|----------------------|
| **#2 ML Problem Framing** | SageMaker Feature Store (create, share, manage features) |
| **#3 Data Processing** | SageMaker Data Wrangler, Studio Classic (EMR + Glue integration), Processing API |
| **#4 Model Development** | SageMaker JumpStart, SageMaker Experiments, Automatic Model Tuning |
| **#5 Model Deployment** | SageMaker AI (real-time, batch transform, async, serverless) |
| **#6 Model Monitoring** | SageMaker Model Monitor |

#### SageMaker Deployment Options
| Option | Best For |
|--------|---------|
| **Real-time** | Low-latency, synchronous predictions |
| **Batch Transform** | Large-scale batch inference jobs |
| **Async** | Large payload or long processing time requests |
| **Serverless** | Intermittent/sporadic traffic with no need to manage infrastructure |

### 4.4 Model Performance Metrics

#### Classification Metrics
| Metric | What It Measures |
|--------|-----------------|
| **Accuracy** | % of correct predictions overall |
| **Precision** | Of all positive predictions, how many were actually positive |
| **Recall** | Of all actual positives, how many did the model find |
| **F1 Score** | Harmonic mean of Precision and Recall (balance both) |
| **AUC-ROC** | Model's ability to distinguish between classes across all thresholds |

#### Regression Metrics
| Metric | What It Measures |
|--------|-----------------|
| **Mean Squared Error (MSE)** | Average of squared differences between predicted and actual values |
| **R² (R-squared)** | How well the model explains variance in the target variable (0–1) |

### 4.5 MLOps Fundamentals

**MLOps** extends DevOps principles to the ML domain. It combines people, technology, and processes to deliver collaborative ML solutions.

**Goals:**
- Accelerate model development lifecycle through automation
- Improve quality metrics through testing and monitoring
- Promote collaboration between data scientists, engineers, and IT Ops
- Provide transparency, explainability, auditability, and security

**Key Principles:**
- Version control
- Automation
- CI/CD pipelines
- Model governance

### 4.6 AWS AI/ML Services Reference (Domain 1)

| Service | Category | Key Function |
|---------|----------|-------------|
| Amazon Comprehend | Text & Documents | Uncovers insights and relationships in unstructured text |
| Amazon Translate | Text & Documents | Neural machine translation across languages |
| Amazon Textract | Text & Documents | Extracts text and data from documents |
| Amazon Rekognition | Vision | Image and video analysis; object/face/text detection |
| Amazon Kendra | Search | Intelligent ML-powered enterprise search |
| Amazon Lex | Chatbots | Conversational interfaces (voice + text) |
| Amazon Polly | Speech | Text-to-speech |
| Amazon Transcribe | Speech | Speech-to-text |
| Amazon Personalize | Recommendations | Real-time personalized recommendations |

### 4.7 Domain 1 Key Resources
- [Amazon SageMaker Developer Guide](https://docs.aws.amazon.com/sagemaker/latest/dg/whatis.html)
- [AWS Machine Learning Overview](https://aws.amazon.com/machine-learning/)
- [SageMaker Feature Store Docs](https://docs.aws.amazon.com/sagemaker/latest/dg/feature-store.html)
- [Amazon SageMaker Model Monitor](https://docs.aws.amazon.com/sagemaker/latest/dg/model-monitor.html)
- [AWS AI Services (Full List)](https://aws.amazon.com/machine-learning/ai-services/)

---

## 5. Domain 2 — Fundamentals of Generative AI (24%)

> Source notes: [fundamentals-of-ml-and-ai.md](./fundamentals-of-ml-and-ai.md) · [exploring-ai-use-cases-and-applications.md](./exploring-ai-use-cases-and-applications.md) · [developing-gen-ai-solutions.md](./developing-gen-ai-solutions.md)

### 5.1 Foundation Models

**Foundation models (FMs)** are large models pre-trained on internet-scale data that can perform many general tasks and be adapted for domain-specific use cases.

**Common Tasks a Single FM Can Perform:**
- Text generation & summarization
- Information extraction
- Image generation
- Chatbot / question answering
- Code explanation and generation

### 5.2 FM Lifecycle (6 Steps)

```
#1 Data Selection
      ↓
#2 Pre-training (internet-scale datasets)
      ↓
#3 Optimization (prompt engineering → RAG → fine-tuning)
      ↓
#4 Evaluation (metrics & benchmarks)
      ↓
#5 Deployment
      ↓
#6 Feedback & Continuous Improvement (monitor + retrain)
```

### 5.3 Generative Model Architectures

| Architecture | How It Works | Primary Use |
|-------------|-------------|------------|
| **Transformer** | Learns patterns and relationships between tokens (words, phrases, characters) | Text generation, NLP reasoning |
| **Diffusion** | Forward diffusion adds noise to data; reverse diffusion denoises to generate new content | Image generation |
| **Multimodal** | Processes and generates multiple data types simultaneously (text, image, audio) | Cross-modal understanding |
| **GAN** (Generative Adversarial Network) | Generator creates synthetic data; Discriminator tries to distinguish real vs. generated — zero-sum competition | Synthetic data, image synthesis |
| **VAE** (Variational Autoencoder) | Encoder compresses data to latent space; Decoder reconstructs/generates from that representation | Content generation, representation learning |

### 5.4 Optimization Path Tradeoffs

| Technique | Cost | Complexity | Weight Changes | Best When |
|-----------|:----:|:----------:|:--------------:|-----------|
| **Prompt Engineering** | Lowest | Low | No | Quick iteration; general task guidance |
| **RAG** | Medium | Medium | No | Data changes frequently; need grounded, doc-based answers |
| **Fine-tuning** | Highest | High | **Yes** | Consistent style/behavior; task-specific precision across many prompts |

> **Key exam distinction:** RAG injects context at inference time. Fine-tuning permanently updates model weights.

### 5.5 GenAI Capabilities vs. Risks

#### Capabilities
| Capability | Description |
|-----------|-------------|
| Adaptability | Flexible across many use cases without retraining |
| Responsiveness | Real-time content generation |
| Simplicity | Automates complex content creation workflows |
| Creativity | Combines and recombines elements to produce novel outputs |
| Personalization | Tailors content to individual preferences |
| Scalability | Generates large volumes of content quickly and cost-effectively |

#### Risks
| Risk | Description |
|------|-------------|
| Regulatory violations | Output may conflict with laws or industry regulations |
| Social risks | Reinforces stereotypes or causes societal harm |
| Data security & privacy | Training data may contain or expose sensitive information |
| Toxicity | Produces harmful, offensive, or dangerous content |
| Hallucinations | Generates plausible but factually incorrect information |
| Interpretability | Difficult to understand why a model produced a specific output |
| Nondeterminism | Same input may produce different outputs across runs |

### 5.6 Industry Use Cases

| Industry | Example Applications |
|---------|---------------------|
| **Media & Entertainment** | Content generation, virtual reality, news generation |
| **Retail** | Product review summaries, pricing optimization, virtual try-ons, store layout optimization |
| **Healthcare** | AWS HealthScribe (clinical documentation), personalized medicine, medical imaging |
| **Life Sciences** | Drug discovery, protein folding prediction, synthetic biology |
| **Financial Services** | Fraud detection, portfolio management, debt collection |
| **Manufacturing** | Predictive maintenance, process optimization, product design, material science |

### 5.7 FM Selection Criteria

When selecting a foundation model, evaluate:

- **Cost** — inference and hosting costs
- **Modality** — text, image, audio, multimodal
- **Latency** — response speed requirements
- **Multi-lingual support** — languages needed
- **Model size & complexity** — capability vs. compute tradeoffs
- **Customization** — fine-tuning and RAG support
- **Input/output length** — context window size
- **Responsibility considerations** — safety, alignment, bias
- **Deployment & integration** — API access, region availability, service quotas

### 5.8 Model Providers & Tasks (Amazon Bedrock)

| Provider | Model | Primary Tasks |
|---------|-------|--------------|
| Amazon | Titan | Text summarization, classification, Q&A, information extraction, embeddings |
| Anthropic | Claude | Content generation, translation, Q&A, summarization, code explanation |
| Meta | Llama | Q&A, chat, summarization, paraphrasing, sentiment analysis, text generation |
| Cohere | Command | Text generation, information extraction, Q&A, summarization |
| AI21 Labs | Jurassic-2 | Text generation, summarization, paraphrasing, chat |
| Stability AI | Stable Diffusion | Photorealistic image generation from text, image quality improvement |

### 5.9 AWS GenAI Services

| Service | What It Does |
|---------|-------------|
| **Amazon Bedrock** | Fully managed API layer for FMs from Amazon and leading AI providers. Serverless — no infrastructure to manage |
| **SageMaker JumpStart** | Pre-built solutions and FM access to quickly start with ML |
| **Amazon Q** | Enterprise generative AI assistant using your company's data and knowledge bases |
| **Amazon Q Developer** | ML-powered code recommendations for C#, Java, JavaScript, Python, TypeScript |

### 5.10 Domain 2 Key Resources
- [Amazon Bedrock User Guide](https://docs.aws.amazon.com/bedrock/latest/userguide/what-is-bedrock.html)
- [AWS Generative AI Overview](https://aws.amazon.com/generative-ai/)
- [Amazon Bedrock — Supported Foundation Models](https://docs.aws.amazon.com/bedrock/latest/userguide/models-supported.html)
- [Amazon Q Developer Docs](https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/what-is.html)
- [AWS Whitepaper: Introduction to Generative AI on AWS](https://docs.aws.amazon.com/whitepapers/latest/generative-ai-on-aws-technology-overview/generative-ai-on-aws-technology-overview.html)

---

## 6. Domain 3 — Applications of Foundation Models (28%)

> Source notes: [developing-gen-ai-solutions.md](./developing-gen-ai-solutions.md) · [essentials-of-prompt-engineering.md](./essentials-of-prompt-engineering.md) · [optimizing-foundation-models.md](./optimizing-foundation-models.md)

> **This is the highest-weighted domain (28%). Prioritize prompt engineering, RAG, fine-tuning, and evaluation.**

### 6.1 GenAI Application Lifecycle (5 Steps)

```
#1 Define Use Case
      ↓
#2 Select a Foundation Model
      ↓
#3 Improve Performance (prompt eng → RAG → fine-tuning)
      ↓
#4 Evaluate Results
      ↓
#5 Deploy the Application
```

#### Defining a Use Case
A well-defined use case should capture: **name, description, actors, preconditions, basic flow, alternate flows, postconditions, business rules, nonfunctional requirements, and assumptions.**

#### Deploying the Application — Key Considerations
- **Cost** — inference pricing and hosting overhead
- **Regions** — model availability varies by AWS region
- **Quotas** — service limits and rate limits
- **Security** — access control, encryption, data handling

### 6.2 Prompt Engineering

#### The 4 Elements of a Well-Crafted Prompt

| Element | Description |
|---------|-------------|
| **Instructions** | What the model should do — the task description |
| **Context** | Background information to guide the model's understanding |
| **Input Data** | The actual content or request to process |
| **Output Indicator** | The desired response format or type (e.g., bullet list, JSON, 200 words) |

> **Negative prompting** — tells the model what *not* to do; used to steer away from unwanted outputs.

#### 3 Inference Parameters That Control Output Behavior

| Parameter | Range | Lower Value | Higher Value |
|-----------|-------|-------------|--------------|
| **Temperature** | 0 – 1 | More focused, predictable, repetitive | More creative, diverse, unpredictable |
| **Top P** | 0 – 1 | Considers only top % of probability mass (focused) | Considers broader range (diverse) |
| **Top K** | Any integer | Limits to K most probable words (focused, coherent) | Considers more candidate words (diverse) |

> On the exam: **lower values = more focused/deterministic**, **higher values = more creative/diverse**. All three parameters work together to shape output randomness.

#### Prompt Best Practices
- Be clear and concise
- Include context when needed
- Specify the output format explicitly
- Break complex tasks into smaller, sequential steps
- Experiment iteratively — refine based on model output
- Use prompt templates for repeatable workflows
- Start prompts with a direct question or directive

#### Prompt Engineering Techniques

| Technique | Description | Best For |
|-----------|-------------|---------|
| **Zero-shot** | No examples provided — just the instruction | Simple tasks; larger/more capable models |
| **Few-shot** | Provide sample input/output pairs to guide the model | Tasks requiring a specific format or style |
| **Chain-of-Thought (CoT)** | Break complex reasoning into intermediate steps | Multi-step math, logic, or reasoning problems |
| **Self-consistency** | Sample multiple reasoning paths; take the most consistent answer | Improving reasoning accuracy |
| **Tree of Thoughts (ToT)** | Explore multiple reasoning branches in parallel | Complex, exploratory problems |
| **RAG** | Retrieval-Augmented Generation — inject external docs as context | Domain-specific Q&A without changing model weights |
| **ART** (Automatic Reasoning & Tool-use) | Automatically decomposes tasks and selects tools | Multi-step tool-calling workflows |
| **ReAct** | Interleaves reasoning and action — model thinks, then acts | Agents that interact with external systems |

### 6.3 RAG (Retrieval-Augmented Generation)

RAG pairs a **retrieval system** with a **generative language model** to inject domain-specific knowledge at inference time — without modifying model weights.

#### RAG Architecture Flow

```
Enterprise Data Sources (docs, databases, chat logs)
      ↓
Vector Embeddings (numerical representation of text/images/audio)
      ↓
Vector Store / Database (stored for similarity search)
      ↓
Retrieval (query → find relevant chunks via k-NN or cosine similarity)
      ↓
Generative Model (retrieved context + user query → grounded response)
```

#### Vector Similarity Methods
- **k-Nearest Neighbors (k-NN)** — finds the K most similar vectors to a query
- **Cosine Similarity** — measures the angle between two vectors (0 = unrelated, 1 = identical direction)

#### AWS Vector Store Options
| Service | Type |
|---------|------|
| Amazon OpenSearch Service (provisioned) | Vector database |
| Amazon OpenSearch Serverless | Vector database (no infrastructure management) |
| Amazon RDS for PostgreSQL + pgvector | Relational DB with vector extension |
| Amazon Aurora PostgreSQL-Compatible + pgvector | Relational DB with vector extension |
| Amazon Kendra | Managed intelligent search with semantic retrieval |

> **Related service:** [Amazon Bedrock Knowledge Bases](https://docs.aws.amazon.com/bedrock/latest/userguide/kb-how-it-works.html) — fully managed RAG pipeline in Bedrock.

### 6.4 Fine-Tuning

Fine-tuning is a supervised learning process that adds a smaller, curated dataset to a pre-trained FM to **modify its weights** for domain-specific behavior.

#### Fine-Tuning Use Cases
- Increase specificity for a target domain
- Improve accuracy on specialized tasks
- Reduce unwanted biases
- Enforce consistent tone/style across responses

#### Fine-Tuning Methods

| Method | How It Works | Best For |
|--------|-------------|---------|
| **Instruction Tuning** | Retrains the model on prompt → desired output pairs | Virtual assistants, chatbots requiring specific response patterns |
| **RLHF** (Reinforcement Learning from Human Feedback) | First trains on supervised data, then uses a human-feedback reward model to further refine outputs | Aligning model outputs with human values and preferences |

#### Fine-Tuning Data Requirements
| Requirement | Why It Matters |
|------------|---------------|
| **Specificity** | Data must closely match the target task |
| **High relevance** | Every data point should contribute meaningful signal |
| **Quality over quantity** | A small, accurate dataset outperforms a large, noisy one |
| **Accurate labeling** | Label errors compound during training and degrade performance |
| **Governance & compliance** | Data must meet security, privacy, and regulatory requirements |
| **Representativeness** | Data should cover the diversity of real-world inputs |
| **Feedback loops** | Ongoing data collection improves future fine-tuning rounds |

### 6.5 Agents

Bedrock Agents add **orchestration** to foundation models, enabling multi-step workflows.

**Key Functions:**
- **Intermediary operations** — facilitate communication between the GenAI model and backend systems
- **Actions** — run a wide variety of tasks (API calls, database lookups, code execution)
- **Feedback integration** — collect outcomes of actions and feed them back into the model's context

> See: [Amazon Bedrock Agents Docs](https://docs.aws.amazon.com/bedrock/latest/userguide/agents.html)

### 6.6 Evaluation Methods & Metrics

#### Evaluation Methods

| Method | Description |
|--------|-------------|
| **Human evaluation** | Users or domain experts interact with the model and assess quality, usefulness, and contextual appropriateness |
| **Benchmark datasets** | Curated, standardized collections used to compare model versions or different models objectively |
| **Automated metrics** | Scalable, quantitative measures of output quality |

#### Automated Evaluation Metrics

| Metric | Full Name | What It Measures | Best For |
|--------|-----------|-----------------|---------|
| **ROUGE** | Recall-Oriented Understudy for Gisting Evaluation | Overlap between generated and reference text (recall-focused) | Summarization quality |
| **BLEU** | Bilingual Evaluation Understudy | Precision of generated text vs. reference + brevity penalty | Translation quality |
| **BERTScore** | — | Semantic similarity using contextualized BERT embeddings (cosine similarity) | Meaning-level similarity; captures paraphrasing |

> Mnemonic: **ROUGE = Recall** (summarization), **BLEU = Precision + Brevity** (translation), **BERTScore = Semantic** (embeddings).

### 6.7 Prompt Security Risks

| Risk | Description |
|------|-------------|
| **Poisoning** | Malicious or biased data is injected into the training dataset to manipulate model behavior |
| **Hijacking / Prompt Injection** | Embedded instructions within a prompt override the model's intended behavior |
| **Exposure / Prompt Leaking** | Sensitive or confidential information is revealed during training or inference |
| **Jailbreaking** | Carefully crafted prompts bypass safety filters and constraints to gain unauthorized functionality |

> Related: [OWASP Top 10 for LLM Applications](https://owasp.org/www-project-top-10-for-large-language-model-applications/)

### 6.8 Domain 3 Key Resources
- [Amazon Bedrock — Prompt Management](https://docs.aws.amazon.com/bedrock/latest/userguide/prompt-management.html)
- [Amazon Bedrock — Knowledge Bases (RAG)](https://docs.aws.amazon.com/bedrock/latest/userguide/kb-how-it-works.html)
- [Amazon Bedrock — Agents](https://docs.aws.amazon.com/bedrock/latest/userguide/agents.html)
- [Amazon Bedrock — Fine-Tuning & Continued Pre-training](https://docs.aws.amazon.com/bedrock/latest/userguide/custom-models.html)
- [Amazon OpenSearch Service — Vector Engine](https://docs.aws.amazon.com/opensearch-service/latest/developerguide/knn.html)
- [Prompt Engineering Guide (external reference)](https://www.promptingguide.ai/)

---

## 7. Domain 4 — Responsible AI (14%)

> Source notes: [responsible-ai-practices.md](./responsible-ai-practices.md)

### 7.1 The 8 Core Dimensions of Responsible AI

| Dimension | Description |
|-----------|-------------|
| **Fairness** | Model treats all individuals and groups equitably; avoids discriminatory outcomes |
| **Explainability** | Ability to explain *why* the model made a specific decision |
| **Privacy & Security** | Protects sensitive data throughout training, inference, and deployment |
| **Veracity & Robustness** | Model produces accurate, consistent results and handles edge cases gracefully |
| **Transparency** | Visibility into *how* the model makes decisions (process-level) |
| **Governance** | Policies, oversight structures, and accountability mechanisms are in place |
| **Safety** | System avoids causing physical, psychological, or societal harm |
| **Controllability** | Humans can intervene to adjust or override model predictions and behavior |

> **Transparency vs. Explainability (exam distinction):**
> - **Transparency** = answers "*HOW* does the model make decisions?" (process-level visibility)
> - **Explainability** = answers "*WHY* did the model make this specific decision?" (output-level reasoning)

### 7.2 Bias vs. Variance

The #1 accuracy problem in AI/ML. The **ideal model** has **low bias AND low variance**.

| Problem | Technical Name | Root Cause | Effect |
|---------|---------------|-----------|--------|
| **High Bias** | Underfitting | Model is too simple; missing important features | Poor performance on both training and test data |
| **High Variance** | Overfitting | Model memorizes training data; too sensitive to noise | Great on training data, poor on new/unseen data |

#### Mitigations
| Technique | Addresses |
|-----------|---------|
| Cross-validation | Detect overfitting |
| Increase training data | Both bias and variance |
| Regularization (penalizes extreme weights) | High variance |
| Use simpler models | High variance |
| Dimensionality reduction | High variance (reduces noise features) |
| Early stopping | High variance (stops before overfitting) |

### 7.3 AWS Tools for Responsible AI

#### Model Evaluation
| Service | Function |
|---------|---------|
| **Amazon Bedrock** (Model Evaluation) | Compare and select FMs using automated metrics (accuracy, robustness, toxicity) or human review (friendliness, style, brand alignment) |
| **Amazon SageMaker Clarify** | Automated bias detection + explainability scores (identifies which features contributed most to a prediction) |

#### Data Quality & Balance
| Service | Function |
|---------|---------|
| **Amazon SageMaker Data Wrangler** | Detects data imbalances; supports random undersampling, random oversampling, and SMOTE for rebalancing |

#### Bias Detection
| Service | Function |
|---------|---------|
| **Amazon SageMaker Experiments** | Create, manage, analyze, and compare ML experiments to identify bias across runs |

#### Human Review & Feedback
| Service | Function |
|---------|---------|
| **Amazon Augmented AI (A2I)** | Builds human review workflows for ML predictions (human-in-the-loop) |
| **Amazon SageMaker Ground Truth** | Labeling service + direct human feedback for ranking, classifying, and guiding model outputs for RL |

#### Governance
| Service | Function |
|---------|---------|
| **Amazon SageMaker Role Manager** | Define minimum permissions (least-privilege) for ML personas quickly |
| **Amazon SageMaker Model Cards** | Capture and share model details: intended use, risk ratings, training details, evaluation results |
| **Amazon SageMaker Model Dashboard** | Centralized dashboard for monitoring all model behavior across the organization |

#### Safety & Content Filtering
| Service | Function |
|---------|---------|
| **Amazon Bedrock Guardrails** | Block undesirable topics, filter harmful content, redact PII, enforce consistent AI safety across FMs |

#### Transparency & Explainability
| Service | Function |
|---------|---------|
| **AWS AI Service Cards** | Transparent documentation on intended use cases, limitations, responsible AI design choices, and operational best practices for AWS AI services |
| **SageMaker Clarify** | Explains which features contributed most to model predictions (tabular, NLP, and computer vision) |
| **SageMaker Autopilot** | Provides insights into how ML models make predictions; feature relevance analysis |

### 7.4 Responsible Dataset Preparation

- Use **balanced, inclusive, and diverse** training data — adequate representation across all groups
- **Data curation process:**
  1. **Preprocessing** — clean, normalize, and select features; ensure accuracy and completeness
  2. **Data augmentation** — generate new instances for underrepresented groups
  3. **Regular auditing** — continuously check for biases and take corrective actions

### 7.5 Model Selection & Sustainability Considerations
When selecting a model for responsible deployment, also evaluate:
- **Value alignment** — does the model's behavior align with organizational and societal values?
- **Responsible reasoning** — does the model reason in ways that are safe and ethical?
- **Appropriate level of autonomy** — is the model's decision-making authority commensurate with risk?
- **Transparency and accountability** — can the model's outputs be explained and audited?

### 7.6 Human-Centered Design Principles for Explainable AI

| Principle | Description |
|-----------|-------------|
| **Design for amplified decision-making** | Supports human decision-makers in high-stakes situations — the AI augments, not replaces |
| **Design for unbiased decision-making** | Ensures decision processes and tools are free from systemic biases |
| **Design for human and AI learning** | Creates environments where both humans and AI systems can improve over time |

### 7.7 Domain 4 Key Resources
- [AWS Responsible Machine Learning](https://aws.amazon.com/machine-learning/responsible-machine-learning/)
- [Amazon SageMaker Clarify — Fairness & Explainability](https://docs.aws.amazon.com/sagemaker/latest/dg/clarify-fairness-and-explainability.html)
- [Amazon Bedrock Guardrails](https://docs.aws.amazon.com/bedrock/latest/userguide/guardrails.html)
- [Amazon Augmented AI (A2I)](https://docs.aws.amazon.com/augmented-ai/2019-11-07/APIReference/Welcome.html)
- [Amazon SageMaker Model Cards](https://docs.aws.amazon.com/sagemaker/latest/dg/model-cards.html)
- [AWS AI Service Cards](https://aws.amazon.com/machine-learning/responsible-machine-learning/ai-service-cards/)

---

## 8. Domain 5 — Security, Compliance & Governance (14%)

> Source notes: [security-compliance-governance-for-ai-solutions.md](./security-compliance-governance-for-ai-solutions.md)

### 8.1 Compliance Frameworks for AI Systems

AWS supports 143 security standards and compliance certifications. The key frameworks to know for the exam:

| Framework | Scope |
|-----------|-------|
| **NIST** | National Institute of Standards and Technology — US cybersecurity and AI risk management framework |
| **ENISA** | European Union Agency for Cybersecurity — EU cyber policy and AI security guidance |
| **ISO** | International security standards (e.g., ISO 27001) — recommended security management practices |
| **SOC** (Systems & Org Controls) | Third-party assessments of AWS compliance controls (SOC 1, 2, 3) |
| **HIPAA** | US healthcare data privacy and security law |
| **GDPR** | EU regulation protecting the personal data and privacy of EU citizens |
| **PCI DSS** | Payment Card Industry Data Security Standard — private payment information security |

#### Am I Operating in a Regulated Context?
Ask yourself:
- Do I need to **audit** this workload?
- Do I need to **archive** data for a defined period of time?
- Will model predictions constitute a **record** or special data item?
- Does source data contain **restricted classifications** under organizational governance?

### 8.2 AWS Services for Governance & Compliance

| Service | Function |
|---------|---------|
| **AWS Config** | Detailed view of AWS resource configuration; tracks changes over time |
| **Amazon Inspector** | Continuous vulnerability scanning for software vulnerabilities and unintended network exposure |
| **AWS Audit Manager** | Continually audits AWS usage to streamline compliance with regulations and industry standards |
| **AWS Artifact** | On-demand downloads of AWS security and compliance documents (ISO certifications, PCI reports, SOC reports) |
| **AWS CloudTrail** | Records all API calls and account activity for auditing and forensic investigation |
| **AWS Trusted Advisor** | Evaluates your environment using best-practice checks across cost, performance, resilience, security, and service limits |

### 8.3 AWS Security Services for AI Workloads

#### Core Security Services
| Service | Function |
|---------|---------|
| **AWS Security Hub** | Single dashboard aggregating all security findings; run automated security playbooks |
| **AWS KMS** | Encryption key management — encrypt data at rest and in transit |
| **Amazon GuardDuty** | Intelligent threat detection — analyzes logs to identify malicious activity |
| **AWS Shield Advanced** | DDoS protection + WAF integration for application-layer defense |

#### AI-Specific Security Services
| Service | Function |
|---------|---------|
| **Amazon Macie** | Automated sensitive data discovery at scale (PII, financial data) |
| **AWS IAM** | Fine-grained access management with least-privilege permissions |
| **AWS IAM Identity Center + IAM Access Analyzer** | Centralized access management and permission analysis across accounts |
| **SageMaker Role Manager** | Build and manage persona-based IAM roles for common ML workflows |
| **AWS Network Firewall** | Network-level traffic filtering, encryption, and decryption |
| **Amazon VPC** | Isolated virtual network for private, controlled resource deployment |
| **AWS PrivateLink** | Establishes private connectivity from your VPC to Amazon Bedrock (no public internet) |
| **Amazon Detective** | Intelligent threat investigation — visualizes security findings |
| **Amazon Inspector** | Vulnerability management and unintended network exposure detection |

### 8.4 Data Governance Strategies

#### Key Governance Strategies
- Data quality and integrity
- Data protection and privacy
- Data lifecycle management
- Responsible AI integration
- Governance structures and roles
- Data sharing and collaboration

#### Key Data Management Concepts

| Concept | Definition |
|---------|-----------|
| **Data lifecycle management** | Managing data from creation through disposal or archiving |
| **Data logging** | Systematic recording of data related to AI workload processing |
| **Data residency** | Physical location where data is stored and processed (important for GDPR compliance) |
| **Data monitoring** | Ongoing observation and analysis of data used in AI workloads |
| **Data retention** | Policies that define how long data must be kept |

### 8.5 Governance Implementation Approaches

| Approach | Description |
|---------|-------------|
| **Policies** | Develop clear guidelines covering AI principles, responsible AI considerations, and use boundaries |
| **Review cadence** | Regular reviews of performance, safety, and responsible AI implications |
| **Review strategies** | Comprehensive technical and non-technical assessments of AI solutions |
| **Transparency standards** | Commit to openness in development and deployment practices |
| **Team training** | Ensure all team members understand policies, guidelines, and best practices |

#### AI System Monitoring Aspects
- Performance metrics
- Infrastructure monitoring
- Bias & fairness checks
- Compliance & responsible AI validation

### 8.6 Data & Model Lineage

**Lineage** = documenting the origin, transformation, and movement of data and models through a system.

| Tool / Technique | Purpose |
|----------------|---------|
| **Data lineage** | Tracks data history — origin, transformations, and movement through systems |
| **Cataloging** | Systematic organization and documentation of datasets, models, and resources |
| **Model cards** | Standardized documentation of intended use, performance characteristics, limitations, and risk ratings |

### 8.7 Secure Data Engineering Best Practices

#### Assessing Data Quality
- **Completeness** — no critical fields missing
- **Accuracy** — data reflects real-world truth
- **Timeliness** — data is current and up-to-date
- **Consistency** — data is uniform across systems and formats

#### Privacy-Enhancing Technologies
- Data masking, obfuscation, and differential privacy
- Encryption, tokenization, and secure multi-party computation

#### Data Access Control
- Comprehensive data governance framework
- RBAC (role-based access control)
- Authentication + authorization mechanisms
- Monitor and log all data access activities
- Apply the **principle of least privilege**

#### Data Integrity
- Data validation and integrity checks at every pipeline stage
- Robust backup and recovery processes
- Maintain detailed data lineage and audit trails
- Regularly test and monitor data integrity controls

### 8.8 Domain 5 Key Resources
- [AWS Compliance Center](https://aws.amazon.com/compliance/)
- [AWS Config Developer Guide](https://docs.aws.amazon.com/config/latest/developerguide/WhatIsConfig.html)
- [AWS Audit Manager User Guide](https://docs.aws.amazon.com/audit-manager/latest/userguide/what-is.html)
- [AWS CloudTrail Docs](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-user-guide.html)
- [AWS KMS Developer Guide](https://docs.aws.amazon.com/kms/latest/developerguide/overview.html)
- [Amazon Macie Docs](https://docs.aws.amazon.com/macie/latest/user/what-is-macie.html)
- [AWS PrivateLink for Bedrock](https://docs.aws.amazon.com/bedrock/latest/userguide/usingVPC.html)
- [AWS Privacy Reference Architecture](https://docs.aws.amazon.com/prescriptive-guidance/latest/privacy-reference-architecture/introduction.html)

---

## 9. AWS Services Quick Reference

> Compact service → category → function reference for exam day review.

### AI/ML Platform Services

| Service | Category | Key Function |
|---------|----------|-------------|
| **Amazon Bedrock** | GenAI / FM Platform | Managed API for FMs; supports inference, fine-tuning, RAG, agents, and guardrails |
| **Amazon SageMaker AI** | ML Platform | End-to-end ML lifecycle — build, train, tune, deploy, monitor |
| **SageMaker JumpStart** | ML Platform | Pre-built ML solutions and FM access to quickly start building |
| **SageMaker Feature Store** | Data / Feature Management | Create, share, and manage ML features across teams |
| **SageMaker Data Wrangler** | Data Preparation | Data cleaning, transformation, imbalance detection, and SMOTE |
| **SageMaker Experiments** | Model Development | Track, compare, and analyze ML experiments; bias detection |
| **SageMaker Automatic Model Tuning** | Model Development | Hyperparameter optimization |
| **SageMaker Model Monitor** | Model Monitoring | Detect data drift, model quality issues, bias drift in production |
| **SageMaker Model Cards** | Governance | Document intended use, risk ratings, and training details |
| **SageMaker Model Dashboard** | Governance | Centralized view of all model performance and behavior |
| **SageMaker Role Manager** | Security / IAM | Persona-based least-privilege IAM roles for ML |
| **SageMaker Ground Truth** | Human Feedback | Data labeling + human-in-the-loop feedback |
| **SageMaker Clarify** | Responsible AI | Bias detection, explainability scores, fairness analysis |
| **SageMaker Autopilot** | AutoML | Automatic model creation with explainability insights |
| **Amazon Q** | GenAI Assistant | Enterprise AI assistant using your company data and systems |
| **Amazon Q Developer** | GenAI / Dev Tools | ML-powered code recommendations and software development assistance |

### Managed AI Services

| Service | Category | Key Function |
|---------|----------|-------------|
| **Amazon Comprehend** | NLP / Text | Insights and relationships in unstructured text; sentiment, entities, key phrases |
| **Amazon Translate** | NLP / Text | Neural machine translation across 75+ languages |
| **Amazon Textract** | Document Processing | Extracts text, tables, forms, and data from documents |
| **Amazon Rekognition** | Vision | Image and video analysis — object, face, text, scene detection |
| **Amazon Kendra** | Search | ML-powered intelligent enterprise search |
| **Amazon Lex** | Chatbot | Conversational interfaces using voice and text (ASR + NLU) |
| **Amazon Polly** | Speech | Text-to-speech synthesis |
| **Amazon Transcribe** | Speech | Automatic speech recognition (speech-to-text) |
| **Amazon Personalize** | Recommendations | Real-time personalized product and content recommendations |
| **Amazon Augmented AI (A2I)** | Human Review | Human-in-the-loop review workflows for ML predictions |
| **AWS HealthScribe** | Healthcare AI | Automatically generates clinical notes from patient-provider conversations |

### Security, Compliance & Governance Services

| Service | Category | Key Function |
|---------|----------|-------------|
| **AWS IAM** | Security | Fine-grained access management with least-privilege permissions |
| **AWS IAM Identity Center** | Security | Centralized access management across multiple AWS accounts |
| **IAM Access Analyzer** | Security | Analyzes resource policies to identify unintended access |
| **AWS KMS** | Security / Encryption | Managed encryption key creation and control |
| **Amazon VPC** | Networking | Isolated private virtual network |
| **AWS PrivateLink** | Networking | Private connectivity from VPC to AWS services (no public internet) |
| **AWS Network Firewall** | Networking | Network traffic filtering and protection |
| **Amazon GuardDuty** | Threat Detection | Intelligent threat detection from log analysis |
| **Amazon Macie** | Data Security | Automated sensitive/PII data discovery at scale |
| **Amazon Detective** | Threat Investigation | Visualizes and investigates security findings |
| **AWS Shield Advanced** | DDoS Protection | DDoS mitigation + WAF integration |
| **AWS Security Hub** | Security Management | Unified security findings dashboard + automated remediation |
| **AWS Config** | Compliance | Resource configuration tracking and compliance rules |
| **Amazon Inspector** | Vulnerability Mgmt | Continuous software vulnerability and network exposure scanning |
| **AWS Audit Manager** | Compliance | Continuous compliance evidence collection and audit reporting |
| **AWS Artifact** | Compliance | On-demand compliance document downloads (SOC, PCI, ISO) |
| **AWS CloudTrail** | Auditing | API call logging and account activity tracking |
| **AWS Trusted Advisor** | Best Practices | Best-practice checks across cost, performance, security, resilience |
| **Amazon Bedrock Guardrails** | AI Safety | Content filtering, topic blocking, PII redaction for FMs |

---

## 10. Key Terms & Concepts Cheat Sheet

### Learning Paradigms
| Paradigm | Training Data | Key Concept |
|----------|--------------|-------------|
| **Supervised** | Labeled | Learns labeled input→output mappings; predict on new inputs |
| **Unsupervised** | Unlabeled | Discovers patterns and structure without labels |
| **Reinforcement** | Reward signal | Agent improves behavior by maximizing cumulative reward |

### Model Architectures
| Architecture | Key Concept |
|-------------|-------------|
| **Transformer** | Processes sequences as tokens; learns attention-based relationships between words |
| **Diffusion** | Forward pass adds noise; reverse pass denoises to generate new content |
| **Multimodal** | Understands and generates across text, image, and audio simultaneously |
| **GAN** | Generator vs. Discriminator in adversarial competition — produces synthetic data |
| **VAE** | Encoder compresses to latent space; Decoder reconstructs/generates |

### Optimization Techniques
| Technique | Weight Changes | Cost | When to Use |
|-----------|:--------------:|:----:|-------------|
| **Prompt Engineering** | No | Lowest | Quick, iterative guidance; general task shaping |
| **RAG** | No | Medium | Frequently changing data; grounded, doc-based answers |
| **Fine-tuning** | **Yes** | Highest | Consistent specialized behavior; task-specific precision |

### Inference Parameters
| Parameter | Effect of Lower Value | Effect of Higher Value |
|-----------|----------------------|----------------------|
| **Temperature** | More focused, repetitive | More creative, diverse |
| **Top P** | Considers fewer token options (focused) | Considers more token options (diverse) |
| **Top K** | Limits to K most probable words | Considers more candidate words |

### Evaluation Metrics
| Metric | Focus | Best For |
|--------|-------|---------|
| **ROUGE** | Recall — how much of the reference text is captured | Summarization |
| **BLEU** | Precision + brevity — exact word matches | Translation |
| **BERTScore** | Semantic similarity via embeddings | Meaning-level comparison; paraphrasing |

### Bias vs. Variance
| Problem | Model Behavior | Solution |
|---------|---------------|---------|
| **High Bias (underfitting)** | Too simple; misses patterns in both training and test data | Add features, use more complex model, reduce regularization |
| **High Variance (overfitting)** | Memorizes training data; fails on new data | Add data, regularization, early stopping, simpler model, cross-validation |

### Transparency vs. Explainability
| Concept | Question It Answers | AWS Tool |
|---------|--------------------|---------| 
| **Transparency** | HOW does the model make decisions? | AWS AI Service Cards, SageMaker Model Cards |
| **Explainability** | WHY did it make this specific decision? | SageMaker Clarify, SageMaker Autopilot |

### 8 Dimensions of Responsible AI
> **F-E-P-V-T-G-S-C**: **F**airness, **E**xplainability, **P**rivacy & Security, **V**eracity & Robustness, **T**ransparency, **G**overnance, **S**afety, **C**ontrollability

### Prompt Security Risks
> **P-H-E-J**: **P**oisoning (training data), **H**ijacking/Injection (override intent), **E**xposure/Leaking (sensitive data), **J**ailbreaking (bypass safety filters)

### RAG Components
```
Data Sources → Embeddings → Vector Store → Retrieval (k-NN / cosine) → Generation
```

### GenAI Application Lifecycle
```
Define Use Case → Select FM → Improve Performance → Evaluate → Deploy
```

### ML Development Lifecycle
```
Business Goal → Problem Framing → Data Processing → Model Dev → Deploy → Monitor → Retrain
```

---

## 11. Practice & Additional Resources

### Official AWS Exam Prep

| Resource | Link |
|---------|------|
| AIF-C01 Exam Page | [aws.amazon.com/certification/certified-ai-practitioner](https://aws.amazon.com/certification/certified-ai-practitioner/) |
| Exam Guide (PDF) | [Download from AWS](https://d1.awsstatic.com/training-and-certification/docs-ai-practitioner/AWS-Certified-AI-Practitioner_Exam-Guide.pdf) |
| AWS Skill Builder Exam Prep Hub | [skillbuilder.aws — AIF-C01](https://skillbuilder.aws/category/exam-prep/ai-practitioner-AIF-C01) |
| Official Practice Question Set | [AWS Skill Builder](https://skillbuilder.aws) (search "AIF-C01 Practice Questions") |
| Official Practice Exam (paid) | Available via AWS Skill Builder subscription |

### AWS Skill Builder Learning Plan (Source Courses)

| Course | Link |
|--------|------|
| Fundamentals of Machine Learning and Artificial Intelligence | [View Course](https://skillbuilder.aws/learn/16ASDUHF86/fundamentals-of-machine-learning-and-artificial-intelligence/M7JZCTA94N) |
| Exploring AI Use Cases and Applications | [View Course](https://skillbuilder.aws/learn/A3U2U9VGMX/exploring-artificial-intelligence-use-cases-and-applications/M12JQTFKB5) |
| Responsible Artificial Intelligence Practices | [View Course](https://skillbuilder.aws/learn/1H631ZWCTP/responsible-artificial-intelligence-practices/BN51NEFJNG) |
| Developing Machine Learning Solutions | [View Course](https://skillbuilder.aws/learn/VSS1JQ8QWW/developing-machine-learning-solutions/HR1KN4V89V) |
| Developing Generative Artificial Intelligence Solutions | [View Course](https://skillbuilder.aws/learn/PWJCMNXWHT/developing-generative-artificial-intelligence-solutions/JFB95SXNPF) |
| Optimizing Foundation Models | [View Course](https://skillbuilder.aws/learn/CDYTAJCKGY/optimizing-foundation-models/PVR1FRGN1T) |
| Security, Compliance, and Governance for AI Solutions | [View Course](https://skillbuilder.aws/learn/YFACXFGBSJ/security-compliance-and-governance-for-ai-solutions/YZTVAG8P4Q) |
| Essentials of Prompt Engineering | [View Course](https://skillbuilder.aws/learn/XBNAVKA88J/essentials-of-prompt-engineering/9T9Q45EDTV) |

### Supplementary Study Resources

| Resource | Description |
|---------|-------------|
| [AWS Generative AI Whitepaper](https://docs.aws.amazon.com/whitepapers/latest/generative-ai-on-aws-technology-overview/generative-ai-on-aws-technology-overview.html) | Technical overview of generative AI on AWS |
| [AWS Well-Architected Framework — Machine Learning Lens](https://docs.aws.amazon.com/wellarchitected/latest/machine-learning-lens/welcome.html) | Best practices for ML workloads on AWS |
| [OWASP Top 10 for LLM Applications](https://owasp.org/www-project-top-10-for-large-language-model-applications/) | Security risks specific to LLM/GenAI applications |
| [Prompt Engineering Guide (promptingguide.ai)](https://www.promptingguide.ai/) | Comprehensive reference for all prompting techniques |
| [AWS re:Post — AI/ML Community](https://repost.aws/tags/TAV3BoQLBiQr6e-f06Pw2niA/machine-learning) | Community Q&A for AWS AI/ML topics |
| [AWS Blogs — Machine Learning](https://aws.amazon.com/blogs/machine-learning/) | Use case walkthroughs and feature announcements |

### Study Tips

1. **Focus on Domain 3 (28%)** — Prompt engineering, RAG, and fine-tuning are the highest-weighted areas. Know the techniques, tradeoffs, and evaluation metrics cold.
2. **Know your AWS services** — The exam frequently asks which service solves a specific problem. Use the [Quick Reference table](#9-aws-services-quick-reference) to drill service → function mapping.
3. **Understand the tradeoffs** — Prompt Engineering vs. RAG vs. Fine-tuning is a core exam decision-tree. Know when to use each.
4. **Memorize the dimensions** — The 8 dimensions of Responsible AI and the distinction between Transparency and Explainability appear frequently.
5. **Don't skip Domain 5** — Security and governance questions often have one clearly correct answer if you know which AWS service handles each compliance scenario.
6. **Use the practice question set** — After your study sessions, take the Official Practice Question Set on AWS Skill Builder to identify weak areas before the exam.

---

*Study guide built from the AWS Skill Builder AI Practitioner Learning Plan — April 2026.*
