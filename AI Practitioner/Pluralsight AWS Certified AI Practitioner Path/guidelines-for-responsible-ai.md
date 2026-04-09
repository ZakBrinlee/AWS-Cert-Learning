# [AWS Certified AI Practitioner (AIF-C01): Guidelines for Responsible AI](https://app.pluralsight.com/ilx/video-courses/aws-certified-ai-practitioner-responsible-ai-guidelines/course-overview)

Started: April 9th, 2026

Completed: April 9th, 2026

## Top Notes
- Responsible AI must be **ethical, transparent, and trustworthy** — transparency = *how* a model decides; explainability = *why* it made a specific decision.
- **Bias vs. Variance**: High bias → underfitting (poor on all data); High variance → overfitting (great on training, poor on unseen). Goal is **balanced** (low bias + low variance). Use **subgroup analysis** to ensure fairness across groups.
- **4 types of bias to know**: Measurement (faulty data), Sampling (non-representative data), Confirmation (ignoring contradicting data), Observer (labeler's subjective opinions).
- **GenAI-specific risks**: Hallucinations (false but plausible outputs), Prompt misuse/model exposure (leaking confidential info), and IP infringement.
- **AWS tools for responsible AI**:
  - **SageMaker Clarify** — detects bias in data & predictions, explains model decisions with visualizations.
  - **SageMaker Ground Truth** — human + machine-assisted data labeling; GT Plus for complex/expert tasks.
  - **SageMaker Model Cards** — documents model purpose, risk ratings, limitations, ethics, and performance.
  - **SageMaker Model Monitor** — post-deployment monitoring for data drift, bias, and performance declines.
  - **Amazon A2I (Augmented AI)** — triggers human review (random or by confidence score) via employees, 3rd party, or Mechanical Turk.
  - **Bedrock Guardrails** — filters/blocks unsafe or non-compliant inputs and outputs from foundation models.

### Responsible AI Systems
- Ensuring that the ML algorithms are ETHICAL, TRANSPARENT, and TRUSTWORTHY
  - Transparent
    - ability to see HOW a ML model makes decisions. Access to training data, algorithms, and training processes.
  - Explainability
    - WHY a model is making a specific decision

- Bias and Variance
  - Model fit -> can make accurate predictions on new, unseen data consistently
  - High Bias -> leads to underfitting
    - Model doesn't learn enough from training set and performs poorly on the training & test data
  - High Variance -> leads to overfitting
    - model learns the data too well, including noise. Performs well on training set, but poorly on unseen data
  - Balanced -> low bias and variance
  - Subgroup analysis -> helps ensure the model is accurate and fair for all groups

- Types of Bias
  - Measurement bias -> capturing faulty data
  - Sampling bias -> training data is not representative as a whole
  - Confirmation bias -> ignoring any data that contridicts sole belief
  - Observer bias -> labeler of data has their own subjective opinions or preferences

- Transparency and Explainability
  - Transparency -> how the model reached its determination
    - decision trees -> structure is easy to visualize and understand
    - Neural networks -> hard to understand the logic (challenging to explain)
  - Explainability -> why the model made a specific decision

- Risk of GenAI Models
  - Hallucinations -> misleading claims that might sound true
  - Prompt Misuses -> model gives to much detail about how it works
    - Model exposure -> shares confidential information
  - Intellectual Property
    - IP infringement claims

- Human-centered Design for Explainable AI
  - design for amplified decision-making
    - meant for high pressure situations
  - design for unbiased decision-making
    - processes and tools that are transparent and fair
    - train decision makes to recognize and mitigate biases
  - Design for human and AI learning
    - learning envs that work well for both humans and AI
      - cognitive apprenticeship
      - personalization
      - user-centered design

### Building Responsible AI with AWS Tools
- Explainability of Model Decisions with SageMaker Clarify
  - Detecting bias in data
    - identify underrepresented or overrepresented groups
  - Detecting bias in predictions
    - if any group is unfairly disadvantaged
    - visualizes distribution of predictions across groups
  - explains how MLs are making predictions with visualization

- Automating Data Labeling with SageMaker Ground Truth
  - simplifies and speeds up the process of labeling data
  - Mix of techniques
    - human labelers
    - machine assistance -> provides humans with suggestions
  - automated labeling
  - GT Plus -> brings in experts for more complicated data

- AI Governance
  - Amazon SageMaker Model Cards -> helps to document the model
    - Model purpose
    - Risk ratings (low, med, high, unknowns)
    - Limitations
    - Ethical considerations
    - Performance metrics
  - SageMaker Model Monitor -> helps to monitor performance post deployment
    - Compares real user data with trained model data 
    - Alerts if the data is different than what was trained (data drift)
    - Alerts for biased
    - Alerts for performance declines
  - Open Source & Transparency
    - Open source models
    - Open data licensing

- Boosting ML Accuracy with Amazon A2I
  - Amazon Augmented AI (A2I) -> evaluation of accuracy with AI but with human interactions
    - Triggers human review
      - Random
      - Confidence score
    - 3 Review processes
      - employees
      - 3rd party
      - AWS mechanical Turk    

- Using Guardrails in Amazon Bedrock for Fairness and Safety
  - evaluates the input/output of foundation models
  - Helps to filter content
  - Can also block user input
    - Harmful categories
    - Prompt attacks
    - Denied Topics
    - Profanity
    - PII
