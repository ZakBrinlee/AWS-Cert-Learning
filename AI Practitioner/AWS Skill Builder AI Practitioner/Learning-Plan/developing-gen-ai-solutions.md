# [Developing Generative Artificial Intelligence Solutions](https://skillbuilder.aws/learn/PWJCMNXWHT/developing-generative-artificial-intelligence-solutions/JFB95SXNPF?parentId=SU2A1EJM1A)

Started: April 17th, 2026

Completed: April 17th, 2026

### Top notes:
- The GenAI app lifecycle has 5 steps: **Define use case → Select FM → Improve performance → Evaluate → Deploy**.
- A well-defined use case captures: name, description, actors, preconditions, basic/alt flows, postconditions, business rules, and nonfunctional requirements.
- FM selection criteria: cost, modality, latency, multi-lingual support, model size/complexity, customization, input/output length, responsibility considerations, and deployment/integration needs.
- **Prompt engineering** is the first and lowest-cost performance lever — design, augment, tune, ensemble, and mine prompts to guide model behavior.
  - Techniques to know: Zero-shot, Few-shot, Chain-of-thought (CoT), Self-consistency, Tree of Thoughts (ToT), RAG, ART, ReAct.
  - **RAG** pairs a retrieval system with a generative model to inject domain-specific context without modifying model weights.
- **Evaluation methods**: human review (subjective quality), benchmark datasets (standardized comparison), and automated metrics.
  - Metrics: **ROUGE** (recall-based overlap for summarization), **BLEU** (precision + brevity for translation), **BERTScore** (semantic similarity via contextualized embeddings).
- Deployment considerations: cost, region availability, service quotas, and security.

#### Gen AI Lifecycle
- #1 - Define a use case
- #2 - Select a FM
- #3 - Improve Perf
- #4 - Evaluate results
- #5 - Deploy app

#### Defining A Use Case
- Defining the problem to be solved -> gathering relevant reqs -> aligning stakeholder expectations
- teams must carefully analyze the problem space, consult with subject matter experts, and translate business needs into technical specifications that can guide the development process
- Business Use Case: a structured narrative that describes how a system or process should behave from the perspective of an actor or stakeholder.
    - Parts of use case:
        - Use case name
        - brief description
        - actors
        - preconditions
        - Basic flow (main success scenario)
        - Alt flows (extensions)
        - Postcondition
        - business rules
        - nonfunctional requirements
        - assumptions
        - notes / additional info

#### Selecting a FM
- pre-trained model selection criteria
    - Cost
    - Modality
    - Latency
    - Multi-lingual support
    - Model size
    - Model complexity
    - customization
    - input/output length
    - responsibility considerations
    - deployment and integration

#### Improving Performance of FM
- Prompt engineering -> process of carefully crafting the input prompts or instructions given to the model to generate desired outputs or behaviors
    - Key Aspects:
        - Design: Crafting clear, unambiguous, and context-rich prompts that effectively communicate the desired task or output to the model
        - Augmentation: Incorporating additional information or constraints into the prompts, such as examples, demonstrations, or task-specific instructions, to guide the model's generation process
        - Tuning: Iteratively refining and adjusting the prompts based on the model's outputs and performance, often through human evaluation or automated metrics
        - Ensembling: Combining multiple prompts or generation strategies to improve the overall quality and robustness of the outputs
        - Mining: Exploring and identifying effective prompts through techniques like prompt searching, prompt generation, or prompt retrieval from large prompt libraries
    - Prompt techniques
        - Zero-shot prompting
        - Few-shot prompting
        - Chain-of-thought (CoT) prompting
        - Self-consistency
        - Tree of thoughts (ToT)
        - Retrieval Augmented Generation (RAG)
        - Automatic Reasoning and Tool-use (ART)
        - ReAct prompting
    - RAG
        - Two main components
            - Retrieval System
            - Generative language model

#### Evaluating an FM
- Types of Eval methods
    - Human -> humans interact with the foundation model and assess its performance based on specific criteria
    - Benchmark datasets -> curated collections of data designed specifically for evaluating the performance of language models or other AI systems
    - Automated metrics -> provide a quick and scalable way to evaluate foundation model performance
- Eval metrics
    - ROUGE -> Recall Oriented Understudy for Gisting Evaluation
        - measures the quality of a generated summary or translation by comparing it to one or more reference summaries or translations
    - BLEU -> Bilingual Evaluation Understudy
        - measures the similarity between a generated text and one or more reference translations, considering both precision and brevity
    - BERTScore -> evaluates the semantic similarity between a generated text and one or more reference texts
        - uses pre-trained Bidirectional Encoder Representations from Transformers (BERT) models to compute contextualized embeddings for the input texts, and then calculates the cosine similarity between them

#### Deploying the Application
- Key consideration factors
    - Cost
    - Regions
    - Quotas
    - Security
