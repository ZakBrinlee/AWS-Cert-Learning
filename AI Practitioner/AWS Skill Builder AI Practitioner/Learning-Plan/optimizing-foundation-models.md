# [Optimizing Foundation Models](https://skillbuilder.aws/learn/CDYTAJCKGY/optimizing-foundation-models/PVR1FRGN1T?parentId=SU2A1EJM1A)

Started: April 17th, 2026

Completed: April 17th, 2026


### Top notes:
- Two main optimization paths for foundation models:
    - **RAG**: inject enterprise knowledge at inference time (no weight updates).
    - **Fine-tuning**: update model behavior/weights for domain-specific performance.
- Choose **RAG** when data changes often, you need grounded answers from internal docs, and want lower retraining overhead.
    - Core pieces: enterprise data sources -> embeddings -> vector store -> retrieval + generation.
    - Common similarity methods: k-NN and cosine similarity.
    - AWS vector options: OpenSearch (provisioned/serverless), Amazon RDS/Aurora PostgreSQL with pgvector, and Amazon Kendra.
- Choose **fine-tuning** when consistent style/behavior and task-specific precision are required across repeated prompts.
    - Main methods: instruction tuning and RLHF.
    - Data prep priorities: highly relevant curated data, accurate labeling, governance/compliance, representativeness, and feedback loops.
- Agents add orchestration for multi-step workflows by connecting models to backend actions and feeding outcomes back into the system.
- Evaluate both RAG and fine-tuned systems with:
    - Human evaluation (quality, usefulness, contextual fit).
    - Benchmark datasets (objective model-to-model or version-to-version comparison).
    - Automated metrics: ROUGE (content overlap/recall), BLEU (translation precision + brevity), BERTScore (semantic similarity via embeddings).
- Business outcomes drive success criteria:
    - Support case: improve chatbot accuracy/relevance.
    - Retail case: improve conversion rate, average order value, and customer retention.


### Optimizing a FM with RAG
#### Business Case
- A telecom company is looking to improve customer support by incorporating a chat bot
    - lots of company data via chat logs, support tickets, recordings etc

#### RAG
- 
- Enterprise datasets
    - allows models ingest and use company data sources to acquire domain-specific knowledge
    - helps to deliver more accurate outputs
- Vector embeddings
    - process by which text, images, and audio are given numerical representation in a vector space
    - words that relate to each other will have closer embeddings after training
- Storing vectors
    - Vector databases: compactly store billions of high-dimensional vectors representing words and entities
    - Common algo to perform similarity search are `k-nearest neighbors` (k-NN) or cosine similarity
    - AWS Services offering vector DB options:
        - Amazon OpenSearch Service (provisioned)
        - Amazon OpenSearch Serverless
        - pgvector extension in Amazon Relational Database Service (Amazon RDS) for PostgreSQL
        - pgvector extension in Amazon Aurora PostgreSQL-Compatible Edition
        - Amazon Kendra

#### Agents
- Intermediary operations: facilitate communication between gen ai model and backend systems. 
- Actions launch: run a wide variety of tasks
- Feedback integration: collecting data on the outcomes of actions

#### Evaluate results
- Human evaluation -> involves real users interacting with the AI model to provide feedback based on their experience
    - quantitative examples
        - user exp
        - contextual appropriateness
        - creativity & flexibility
- Benchmark datasets -> predefined datasets and associated metrics that offer a consistent, objective means to measure model performances
    - essential for comparing performance across different models or different iterations of the same model

### Optimizing a FM with Fine-Tuning
#### Business Case
- A online fashion retailer, faces challenges with high cart abandonment rates and low repeat purchases
- Focus on the following metrics:
    - Conversion rate: Increase in successful purchases for each site visit
    - Average order value: Increase in the dollar amount spent for each transaction
    - Customer retention rate: Increase in the percentage of returning customers
- Solution - LLM with several functions
    - generate dynamic product descriptions
    - offer personalized shopping advice
    - improve automated interactions

#### Fine-Tuning
- Helps with
    - increase specificity
    - improve accuracy
    - reduce biases
    - boost efficiency
- Fine tuning approach
    - Instruction tuning
        - retraining the model on a new dataset that consists of prompts followed by the desired outputs
        - highly effective for interactive applications like virtual assistants and chatbots
    - Reinforcement learning from human feedback (RLHF)
        - Two parts
            - #1 - model is initially trained using supervised learning to predict human-like responses
            - #2 - further refined through a reinforcement learning process, where a reward model built from human feedback guides the model toward generating more preferable outputs
        - effective in aligning the model’s outputs with human values and preferences, thereby increasing its practical utility in sensitive applications
- Data prep
    - distinct from initial training for following reasons:
        - Specificity
        - High relevance
        - Quality over quantity
    - Key steps
        - Data curation -> ensure every piece of data is highly relevant
        - Labeling -> accuracy is paramount
        - Governance and compliance
        - Representativeness and bias checking
        - Feedback integration

#### Model Evaluation
- 3 common metrics
    - ROUGE -> Recall-Oriented Understudy for Gisting Evaluation
        - evaluations assess how much of the important information in the source texts is captured by the generated summaries
        - Count the number of overlapping units
            - words, N-grams, sentence fragments between gen output & reference texts
        - Two ways to use the metric
            - ROUGE-N
                - measures the overlap of n-grams between the generated text and the reference text
                - primarily assesses the fluency of the text and the extent to which it includes key ideas from the reference
            - ROUGE-L
                - uses the longest common subsequence between the gen text and the reference texts
                - good at evaluating the coherence and order of the narrative in the outputs
    - BLEU
        - Evaluate the quality of text that has been machine-translated from one natural language to another
        - measures the precision of N-grams in the machine-generated text that appears in the reference texts and applies a penalty for overly short translations (brevity penalty)
        - fundamentally a precision metric
    - BERTScore
        - uses the pretrained contextual embeddings from models like BERT to evaluate the quality of text-generation tasks
        - computes the cosine similarity between the contextual embeddings of words in the candidate and the reference texts
        - evaluates the semantic similarity rather than relying on exact lexical matches, it is capable of capturing meaning in a more nuanced manner
