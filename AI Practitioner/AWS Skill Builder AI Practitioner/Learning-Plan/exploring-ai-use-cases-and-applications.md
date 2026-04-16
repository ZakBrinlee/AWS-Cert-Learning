# [Exploring Artificial Intelligence Use Cases and Applications](https://skillbuilder.aws/learn/A3U2U9VGMX/exploring-artificial-intelligence-use-cases-and-applications/M12JQTFKB5?parentId=SU2A1EJM1A)

Started: April 14th, 2026

Completed: April 14th, 2026

### Top Notes:
- AI delivers value across industries (media, retail, healthcare, life sciences, finance, manufacturing) by improving decisions, personalization, and operational efficiency.
- Core AI application patterns to recognize: computer vision, NLP, intelligent document processing, and fraud detection.
- Use ML when rule-based systems become too complex or do not scale well.
  - Supervised learning: classification (labels/categories) and regression (continuous values).
  - Unsupervised learning: clustering (grouping similar items) and dimensionality reduction (compressing features while preserving signal).
  - Reinforcement learning: improves decisions through iterative feedback/reward.
- Generative AI strengths: adaptability, real-time responsiveness, automation/simplicity, creativity, personalization, and high content scalability.
- Generative AI risks to monitor: regulatory and social risk, data privacy/security issues, toxicity, hallucinations, interpretability limits, and nondeterministic outputs.
- Model selection should balance: model type, performance requirements, capabilities, constraints, and compliance needs.
  - Know common model providers/examples and fit-to-task (text generation, summarization, Q&A, embeddings, and image generation).
- Business success is measured with outcome metrics, not just model quality.
  - Key metrics: user satisfaction, conversion rate, ARPU, cross-domain performance, and efficiency.

## Notes

### AI
#### Examples of real-world use cases
- Media & Entertainment
    - content generation
    - virtual reality
    - new generation
- Retail
    - product review summaries
    - pricing optimization
    - virtual try-ons
    - store layout optimizations
- Healthcare
    - AWS HealthScribe
        - empowers building clinical applications that auto generate clinical codes by analyzing conversations
    - Personalize medicine
        - generate treatment plans based on patient specific genetic makeup, lifestyle, and disease progression
    - improve medical imaging
- Life sciences
    - drug discovery
    - protein folding prediction
    - synthetic biology
- Financial services
    - fraud detection mechanisms
    - portfolio management
    - debt collection
- Manufacturing
    - predictive maintenance
    - process optimization
    - product design
    - material science

#### Examples of AI applications
- Computer Vision
    - image classification
    - object detection
    - image segmentation
- Natural Language Processing
    - text classification
    - sentiment analysis
    - machine translation
    - language generation
- Intelligent document processing
    - extract info
    - generate summaries
    - provide actionable insights
- Fraud detection
    - identifying + preventing fraudulent activities
    - unauthorized behavior with a system, process or transaction

### ML
#### Machine Learning
- Appropriate solutions for AI+ML
    - when rules rely on too many factors, have overlaps, or need to be finely tuned, it becomes difficult for humans to code them accurately
    - Scale of the project is challenging

#### Techniques and Use Cases
- Supervised Learning
    - Two subcategories
        - Classification -> assign labels or categories to new data
            - eg. fraud detection, customer retention, image classification
        - Regression -> predicting continuous or numerical values based on 1+ input variable -> model relationship between dependent var and 1(+) independent vars
            - eg. weather forecasting, market forecasting, population growth prediction
- Unsupervised learning
    - Two subcategories
        - Clustering -> groups data into different clusters
            - eg. customer segmentation, targeted marketing, recommended systems
        - Dimensionality reduction -> reduce the number of features/dimensions in a data set while preserving most import info/patterns
            - eg. big data viz, meaningful compression, feature elicitation
- Reinforcement learning
    - improves its model by mining feedback from previous iterations

### Generative AI
#### Capabilities
- Adaptability -> multi-use cases
- Responsiveness -> real-time generation
- Simplicity -> automate content creation processes
- Creativity and exploration -> generate novel ideas, designs, or solutions by combining and recombining elements in unique ways
- Data efficiency -> ability to learn from small amounts of data and generate new samples consistent with training data
- Personalization -> ability to create personalized content tailored to individual prefs or characteristics
- Scalability -> generate large amounts of content quickly

#### Challenges
- some challenges include regulatory violations, social risks, privacy concerns, toxicity, hallucination, and interpretability
- Regulatory violations
- Social risks
- Data security & privacy concerns
- Toxicity
- Hallucinations
- Interpretability
- Nondeterminism

#### Factors to consider when selecting
- key factors to consider when selecting an appropriate generative AI model
    - Model types
    - Performance requirements
    - Capabilities
    - Constraints
    - Compliance
- Models Types - options
    - AI21 labs - Jurassic-2 models
        - tasks: text gen, summarization, paraphrasing, chat
    - Amazon Titan
        - tasks: text summarization, classification, open-ended Q&A, info extrac, embeddings
    - Anthropic - Claude
        - tasks: content gen, txt translation, question answering, text sum, code expl & gen
    - Stability AI - Stable Diffusion
        - tasks: gen photo realistic images from txt, improve quality of gen images
    - Cohere - Command
        - tasks: text gen, info extract, q&a, sum
    - Meta - Llama
        - tasks: q&a, chat, sum, paraph, sentiment analy, text gen

#### Business Metrics
- quantifying the performance, effectiveness, and return on investment (ROI) of AI applications through relevant business metrics, organizations can gain valuable insights into the value delivered
- Business metrics (non-exhaustive)
    - 1 - User satisfaction
    - 2 - Avg revenue per user (ARPU)
    - 3 - Cross-domain performance
    - 4 - Conversion rate
    - 5 - Efficiency
