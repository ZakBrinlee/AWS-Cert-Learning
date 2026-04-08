# [AWS Certified AI Practitioner (AIF-C01): Fundamentals of Generative AI](https://app.pluralsight.com/ilx/video-courses/aws-certified-ai-practitioner-generative-ai-fundamentals/course-overview)

Started: April 8th, 2026

Completed: April 8th, 2026

## Top Notes
- Generative AI creates new content from learned patterns; key building blocks are **tokens**, **context windows**, **chunking**, **embeddings**, and **vectors** (often stored in vector databases).
- Model families to know:
  - **Foundation models** (large pre-trained, then fine-tuned), **transformer LLMs** (language generation), **multimodal models** (multiple input/output types), and **diffusion models** (high-quality image/video generation via noise-add/remove process).
- Prompt engineering is essential: better prompts produce better outputs; structure, context, and constraints directly affect quality.
- Foundation model lifecycle: **Data Selection → Model Selection → Pre-training → Fine-tuning → Evaluation → Deployment → Feedback**.
- Benefits vs risks:
  - Benefits: adaptability, responsiveness, simplicity.
  - Risks: hallucinations, nondeterminism, bias, and limited interpretability.
- Model selection should balance technical + business criteria:
  - Technical: latency, throughput, constraints, compliance.
  - Business: efficiency, accuracy, conversion/revenue impact, cross-domain performance, customer lifetime value.
- AWS Generative AI stack:
  - **Amazon Bedrock** (managed access to multiple FMs)
  - **SageMaker JumpStart** (pretrained models + deployment options)
  - **PartyRock** (rapid experimentation)
  - **Amazon Q / Q Developer** (business and coding assistance).
- Cost tradeoffs to remember: higher responsiveness/availability, redundancy/performance, and provisioned throughput/customization generally increase cost.


### Generative AI Concepts
- Generate new content based on data it is trained with
- Tokens
  - fundamental building blocks of a data model
- Context window
  - number of tokens a LLM can take in when generating text
- Chunking
  - divides input into chunks
- Embeddings
  - representations of values or objects like text, images, and audio
  - Often used in recommendation systems
- Vectors
  - numerical values (coordinates) that indicate where a value or object is located
  - Stored in a vector database
- Transformer based LLMs
  - process input data using neural networks to generate a human-understandable output
  - transforms input to a desired output
  - handles large data sets
  - Examples: GPT4
- Generative AI Models
  - Foundation:
    - large scale pre-trained -> can be fine tuned
    - Examples: Amazon Titan, Claude
  - Multi-modal
    - extension of foundation -> can handle multiple input types and outputs
    - Examples: Amazon Titan Embeddings
  - Diffusion:
    - generative high quality images
    - Two phases:
      - Forward process -> adds noise
      - Reverse process -> remove noise
    - Examples: art generation, video generation, upscaling images
- Prompt Engineering
  - process of designing inputs, or prompts, to guide generative AI models to produce a desired output
- Foundation Model Lifecycle
  - Data Selection -> relevant, high quality, diverse data
  - Model Selection -> select the suitable model based on the problem requirement
  - Pre-training -> train based on data
  - Fine-tuning -> train foundation model on smaller specialized data for the problem
  - Evaluation -> ensure it meets performance standards
  - Deployment -> refined model is put into production
  - Feedback -> real world usage is collected and refined the model

### Use Cases for Generative AI
- Image and video generation
- Chatbots and language translation
- Code generation and summarization
- Recommendation engines and search optimization
- Advantages of generative AI
  - Adaptability
  - Responsiveness - real time output
  - Simplicity
- Limitations and Challenges
  - Hallucinations
  - Lack of Interpretability
  - Nondeterminism
  - Bias 
- Model Selection Factors
  - Model Types
    - Foundation
    - Transformer
    - Diffusion
    - Multi-modal
  - Performance Requirements
    - Latency
    - Throughput
    - Constraints
    - Compliance
- Business Metrics and Value
  - Efficiency and accuracy
    - How well the model uses resources
    - how reliability the AI achieves the tasks
  - Conversion Rate and Revenue
    - % of users who take a desired action or campaign
    - average amount of money per user
  - Cross-domain performance
    - ability to perform well across various tasks
  - Customer lifetime value
    - long term value impact on customer retention

### Generative AI in AWS
- SageMaker Jumpstart
  - built-in algorithms
  - pre-trained models
  - customized solutions
  - supports different inference types
    - real time
    - serverless
    - batch transform
    - async
- Bedrock
  - solid foundation
  - ability to use multiple models
- PartyRock
  - experiment with models/apps
- Amazon Q
  - non-technical question answers
  - dashboard generation
  - exec summaries
  - data stories
- Q Developer
  - CODE GEN
  - automation
  - integration

- Advantages or AWS Generative AI Services
  - accessibility
  - efficiency
  - cost-effectiveness
  - speed to market
  - built-in security
  - safety
  - compliance

- Cost tradeoffs of AWS Generative AI Services
  - responsiveness & availability
  - redundancy & performance
  - provisioned throughput & custom models 
