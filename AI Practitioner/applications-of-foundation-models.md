# [AWS Certified AI Practitioner (AIF-C01): Applications of Foundation Models](https://app.pluralsight.com/ilx/video-courses/aws-certified-ai-practitioner-foundation-models-application/course-overview)

Started: April 8th, 2026
Completed: April 9th, 2026

## Top Notes
- **Foundation model selection** depends on modality, latency, multi-lingual needs, model size/complexity, customization, and input/output length — match the model to the task.
- **Inference parameters** control output behavior: **Top-K** limits the candidate token pool (count), **Top-P** limits it by cumulative probability — lower values = safer/predictable, higher = creative/varied.
- **RAG (Retrieval-Augmented Generation)** pairs a foundation model with an external knowledge base — cost-effective way to give models up-to-date or domain-specific knowledge without full retraining.
- **Customization cost ladder** (low → high cost, low → high control): In-context learning → RAG → Fine-tuning → Pre-training.
- **Prompt engineering techniques** to know: Zero-shot, Single-shot, Few-shot, Chain-of-thought, Prompt templates. Security risks include prompt injection/hijacking, data poisoning, and jailbreaking.
- **Fine-tuning approaches**: Instruction tuning, domain adaptation, transfer learning. Data quality matters — curation, governance, representativeness, labeling, and RLHF all shape results.
- **Evaluation metrics**: ROUGE (recall/overlap of generated vs. reference text), BLEU (translation quality), BERTScore (semantic similarity via embeddings). Also align against business objectives (productivity, user engagement, task accuracy).
- **AWS tooling**: Bedrock Agents orchestrate multi-step tasks (RAG + dynamic code gen + memory retention); vector storage options include OpenSearch, Aurora, Neptune, DocumentDB, and RDS (pgvector).

### Design Considerations for Foundation Model Applications
- Selecting Foundation Models
  - Modality -> type of data a model is trained to handle
  - Latency -> how quickly a model processes requests
  - Multi-lingual -> multiple language support
  - Model Size & Complexity
  - Customization -> better fit specific business needs
  - Input & Output Length -> short or long

- Inference Parameters
  - Affects how a foundation model generates it's responses
  - Top-P & Top-K sampling
    - Top-k -> 0 to 500 -> # of most likely candidates to consider for the next token
      - lower = less options, more likely outputs
      - higher = more options, less likely outputs
    - Top-P -> 0.0 to 1.0
      - lower = less options, more likely outputs
      - higher = more options, less likely outputs

- Retrieval-augmented Generation (RAG)
  - technique where a foundation model is paired with an external knowledge source
  - Knowledge base -> external source of data
  - Business Applications
    - Customer support
    - Production documentations
    - Research and analysis

- Vector Storage Solution on AWS
  - Embeddings capture the semantic meaning of inputs
  - AWS services for storing embeddings
    - OpenSearch -> search engines, recommendation systems -> combines vector and text search
    - Aurora -> e-commerce, real-time recommendations -> scalable, rds capabilities
    - Neptune -> knowledge graphs, social networks -> graph queries for embedding data
    - DocumentDB -> chatbots, personalization -> schema-less storage for varied embeddings
    - RDS for PostgreSQL -> multi-media search, AI applications -> PGVector extension for similarity searches

- Cost Tradeoffs for Customization
  - pre-training
    - high costs, full control over model behavior
  - fine-tuning
    - moderate cost, balances control and efficiency
  - in-context learning
    - low cost, great for flexibility
  - RAG
    - cost effective, uses external data for specialized tasks

- Agents for Multi-step tasks
  - Data Retrieval -> Analysis -> Response generation
  - Agents for Bedrock
    - Use RAG
    - Dynamic code generation
    - Orchestrate tasks
    - Memory retention
    - Action schema
    - Prompt engineering

### Prompt Engineering Techniques
- Context -> provides relevant background information
- Instruction -> clear direction for output
- Negative Prompts -> reduction of 
- Model latent space ->

- Techniques
  - Zero-shot -> giving the model a task without examples
  - Single-shot -> provide an example with the prompt
  - Few-shot -> provides more than one example with the prompt
  - Chain-of-thought -> asking the model to break down the problem into smaller logical steps
  - Prompt-templates -> designed template to help translate prompts to output

- Benefits & Best Practices
- Response Quality Improvement
  - Specific prompts -> lead to high-quality outputs
  - Discovery -> uncovers new insights and discoveries
  - Experimentation -> refine your prompts
  - Guardrails -> ensure safe and relevant answers
  - Using Multiple comments -> improve depth and structure

- Risks and Limitations of Prompt Engineering
  - Exposure -> exposes sensitive data
  - Poisoning -> maliciously inserting false/harmful data when training
  - Hijacking -> attacker manipulates a prompt to generate unintended output
  - Jailbreaking -> clever prompts to bypass a model's safety constraints

### Training and Fine-tuning Foundation Models
- Pre-training
  - general learning from massive data sets
- Fine-tuning
  - training the model for a specific use case
- Continuous pre-training
  - Keeping the model up to date with new data

- Methods for Fine-tuning
  - Instruction tuning -> provide a set of guidelines/directives
  - Adapting models for specific domains -> general purpose to a specific purpose/field
  - Transfer learning -> fine-tune a pre-trained model for a new task

- Prepare data to fine-tune
  - Data Curation -> organize and select high quality data
  - Data Governance -> uphold ethical standards & policy, process, practices
  - Data size -> impact richness
  - Data representativeness -> data that represents best to avoid bias
  - Data Labeling -> adding tags/categories for helping with different patterns
  - Reinforcement Learning from Human Feedback -> reward model is trained with human feedback

### Evaluating Foundation Model Performance
- Evaluating approaches
  - Human eval -> people assess the model output
  - Benchmark dataset -> test against industry standards (pre-defined tasks)

- Performance metrics
  - ROUGE -> Recall-oriented Understudy for Gisting Evaluation -> recall
    - measures overlap between generated and reference text
  - BLEU -> Bilingual evaluation understudy -> bilingual
    - focuses on the quality of the text
  - BERTScore -> bond
    - measures quality of text generated by embeddings
    - bonding of related words

- Business Objective Alignment
  - Productivity
  - User engagement
  - Task Engineering
