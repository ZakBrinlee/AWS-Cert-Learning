# [AWS Certified AI Practitioner (AIF-C01): Applications of Foundation Models](https://app.pluralsight.com/ilx/video-courses/aws-certified-ai-practitioner-foundation-models-application/course-overview)

Started: April 8th, 2026
Completed: April 9th, 2026

## Top Notes
- 
  - 

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
    - Top-k -> 0 to 500 -> # of most likely canidates to consider for the next token
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
- 

### Evaluating Foundation Model Performance
- 
