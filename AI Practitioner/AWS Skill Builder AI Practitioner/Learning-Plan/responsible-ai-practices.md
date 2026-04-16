# [Responsible Artificial Intelligence Practices
](https://skillbuilder.aws/learn/1H631ZWCTP/responsible-artificial-intelligence-practices/BN51NEFJNG?parentId=SU2A1EJM1A)

Started: April 15, 2026

Completed: April 16, 2026

### Top notes:
- Responsible AI ensures AI systems are transparent, trustworthy, and accountable — requiring leadership oversight, expert teams, and built-in guidelines from the start.
- **Bias vs. Variance** (core accuracy problem): Low bias + low variance = ideal model. High bias → underfitting (model too simple). High variance → overfitting (model memorizes training data, fails on new data).
  - Mitigations: cross-validation, more data, regularization, simpler models, dimensionality reduction, early stopping.
- **8 core dimensions of Responsible AI**: Fairness, Explainability, Privacy & Security, Veracity & Robustness, Transparency, Governance, Safety, Controllability.
- **Transparency vs. Explainability**: Transparency = *how* the model makes decisions; Explainability = *why* it made a specific decision.
- Key AWS tools by category:
  - **Model evaluation**: Bedrock (automated + human review), SageMaker Clarify (bias detection, explainability scores).
  - **Data quality**: SageMaker Data Wrangler (detect imbalances; undersampling, oversampling, SMOTE).
  - **Bias detection**: SageMaker Experiments.
  - **Human review**: Amazon A2I (human-in-the-loop ML prediction review) + SageMaker Ground Truth (labeling + direct human feedback).
  - **Governance**: SageMaker Role Manager (least-privilege), Model Cards (intended use/risk ratings), Model Dashboard (central model monitoring).
  - **Safety/content filtering**: Bedrock Guardrails (block topics, filter harmful content, redact PII).
- Responsible dataset prep requires balanced, inclusive, and diverse data — with data curation steps: preprocessing, augmentation, and regular auditing.
- Model selection must also factor in **sustainability**: value alignment, responsible reasoning, appropriate autonomy, and transparency.

### Intro to responsible AI
- Companies should be proactive about the following in their system:
    - It is fully transparent and accountable, with monitoring and oversight mechanisms in place.
    - It is managed by a leadership team accountable for responsible AI strategies.
    - It is developed by teams with expertise in responsible AI principles and practices.
    - It is built following responsible AI guidelines.

#### Challenges in Traditional AI & Gen AI
- #1 problems developers face in AI applications is ACCURACY.
- IDEAL model has low bias and low variance
- Bias
    - means that the model is missing important features of the datasets.  (data is too basic)
    - Measured by the difference between expected predicts and the true values we are trying to predict.
        - Narrow difference means LOW BIAS
        - Wide difference means HIGH BIAS -> Underfitted -> model is not capturing enough diff in the features of the data
- Variance
    - sensitivity to fluctuations or noise in the training data. 
    - HIGH VARIANCE -> model is familiar with training data that it can make predictions with HIGH accuracy
        - capturing all the features of the data
        - new data to the model will make the accuracy drop since it is unfamiliar with new/diff features
        - OVERFITTING -> unable to generalize to unseen examples
- Ways to overcome bias and variance errors
    - Cross Validation -> should be used to detect overfitting
    - Increase data
    - Regularization -> method that penalizes extreme weight values
    - Simpler models
    - Dimension Reduction -> unsupervised machine learning algorithm that attempts to reduce the dimensionality (number of features) within a dataset
    - Stop training early

#### Core Dimensions of Responsible AI
- Fairness
- Explainability
- Privacy & Security
- Veracity & robustness
- Transparency
- Governance
- Safety
- Controllability

### Developing Responsible AI Systems
#### AMZN Services & Tools for Responsible AI
- FM Model evaluation
    - AMZN Bedrock
        - evaluate, compare and select best FM for use case with a few clicks
        - TWO evaluation offerings
            - automated: predefined metrics such as accuracy, robustness, and toxicity
            - human: subjective or custom metrics such as friendliness, style, and alignment to brand voice
                - in-house employees or AWS-managed team as reviewers
    - AMZN SageMaker AI Clarify
        - Automatically evaluate metrics such as accuracy, robustness, and toxicity
        - helps identify potential bias
    - AMZN SageMAker Data Wrangler
        - detect data imbalances
        - 3 balancing operators
            - random undersampling
            - random oversampling
            - Synthetic Minority Oversampling Technique (SMOTE) for rebalancing data
- Guardrails
    - helps control the interaction between users and FMs by filtering undesirable and harmful content, redacting personally identifiable information (PII), and enhancing content safety and privacy
    - Consistent level of AI safety
    - Block undesirable topics
    - Filter harmful content
    - Redact PII to protect user privacy

- Bias Detection
    - AMZN SageMaker AI Experiments
        - create, manage, analyze, and compare your machine learning experiments
    - AMZN SageMAker Data Wrangler
        - detect data imbalances
- Model prediction explanation
    - Amazon Augmented AI (Amazon A2I)
        - service that helps build the workflows required for human review of ML predictions
- Governance improvement
    - AMZN SageMaker Role Manager
        - define min permissions quickly
    - AMZN SageMaker Model Cards
        - capture, retrieve and share essential model info. -> intended uses, risk ratings, and training details
    - AMZN SageMaker Model Dashboard
        - dashboard for all model behavior

#### Responsible Considerations to Select a Model
- Model selection has strategic implications for how the AI system will perform
- evaluate models for accuracy, robustness, toxicity, or nuanced content that requires human judgement
    - Model evaluation on AMZN BedRock or SageMaker AI Clarify
- Sustainability concerns
    - socially, environmentally and economically sustainable
        - Value alignment
        - Responsible reasoning skills
        - Appropriate level of autonomy
        - Transparency and Accountability

#### Responsible Prep for Datasets
- Balanced datasets
    - represent all groups of people or data topics
        - adequate # of examples or instances of each group
    - inclusively and diversity help to ensure fairness and unbiased models
- Data curation
    - process of labeling, organizing and preprocessing data
    - Main steps of data curation
        - Data preprocessing
            - ensure accuracy, completeness, and unbiased
            - techniques: cleaning, normalization, feature selection
        - Data augmentation
            - generate new instances of underrepresented groups
        - Regular auditing
            - Check for biases and take corrective actions if necessary

### Transparent and Explainable AI Models
#### Transparent & Explainable Models
- Transparency answers the question HOW a model makes decisions
- Explainability answers the question WHY the model made the decision it did
- AWS Tools for transparency
    - AWS AI Service Cards
        - transparent documentation on Amazon services that help you build your AI services
        - form of responsible AI documentation that provides customers with a single place to find information on the intended use cases and limitations, responsible AI design choices, and the deployment and operation best practices for our AI services
    - AMZN SageMaker Model Cards
        - catalog and provide documentation on models that you create or develop yourself
        - details include information such as the intended use and risk rating of a model, training details and metrics, evaluation results and observations, and additional callouts such as considerations, recommendations, and custom information
- AWS Tools for explainability
    - SageMaker AI Clarify
        - integrated with SageMaker AI Experiments to provide scores detailing which features contributed the most to your model prediction on a particular input for tabular, NLP, and computer vision models
    - SageMaker Autopilot
        - help provide insights into how ML models make predictions
        - determines the contribution of individual features or inputs to the model's output and provides insights into the relevance of different features

#### Model Trade-Offs
- Interpretability: is the degree to which a human can understand the cause of a decision
- Explainability: how to take an ML model and explain the behavior in human terms
- Model Safety: ability of an AI system to avoid causing harm in its interactions with the world
- Model control: where you can influence the model's predictions and behavior by changing aspects of the training data

#### Principles of Human-Centered design for Explainable AI
- Key principles
    - Design for amplified decision making
        - supports decision-makers in high-stakes situations
    - Design for unbiased decision making
        - aim to ensure that the design of decision-making processes, systems, and tools is free from biases that can influence the outcomes
    - Design for human and AI learning
        - process that aims to create learning environments and tools that are beneficial and effective for both humans and AI
- AMZN SageMaker Ground Truth
    - most comprehensive set of human-in-the-loop capabilities for incorporating human feedback across the ML lifecycle to improve model accuracy and relevancy
    - give direct feedback and guidance on output that a model has generated by ranking, classifying, or doing both for its responses for RL outcomes
