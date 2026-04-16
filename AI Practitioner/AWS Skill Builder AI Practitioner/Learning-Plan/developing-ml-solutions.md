# [Developing Machine Learning Solutions](https://skillbuilder.aws/learn/VSS1JQ8QWW/developing-machine-learning-solutions/HR1KN4V89V?parentId=SU2A1EJM1A)

Started: April 16th, 2026

Completed: April 16th, 2026

### Top notes:

### Developing ML Solutions
#### ML Development Lifecycle
- refers to the end-to-end process of developing, deploying, and maintaining machine learning models
- Phases
    - #1 - Business goal identification
    - #2 - ML Problem framing
    - #3 - Data processing
    - #4 - Model development
    - #5 - Model deployment
    - #6 - Model monitoring
    - #7 - Model retraining

#### Developing ML Solutions with AMZN SageMaker AI
- AMZN SageMaker AI for each phase of ML lifecycle
    - #1 - Business goal identification
    - #2 - ML Problem framing
        - SageMaker Feature Store -> create, share and manage features
    - #3 - Data processing
        - SageMaker AI -> training
        - SageMaker Data Wrangler
        - SageMaker Studio Classic -> built-in integration of EMR & AWS Glue
        - SageMaker Processing API -> run scripts and notebooks on datasets
    - #4 - Model development
        - SageMaker JumpStart
        - SageMaker Experiments
        - SageMaker Automatic Model Tuning
    - #5 - Model deployment
        - SageMaker AI
    - #6 - Model monitoring
        - SageMaker Model Monitor
    - #7 - Model retraining
    
#### Sources of ML Models
- SageMaker AI supported algorithms
    - Supervised learning -> classification &/or regression
    - Unsupervised learning -> clustering, dimension reduction, Topic modeling with pattern recognition, and anomaly detection
    - Image processing -> image classification, object detection, and computer vision, and time series
    - Text analysis -> natural language processing, document classification or summarization, topic modeling or classification, and language transcription or translation

#### ML Models Performance Evaluation
- Classification Metrics
    - Accuracy
    - Precision
    - Recall
    - F1
    - AUC-ROC
- Regression Metrics
    - Mean squared error
    - R squared

#### Model Deployment
- Deployment types
    - Self-hosted API
    - Managed API services
- SageMaker AI deployment options
    - Real-time
    - Batch transform
    - Async
    - Serverless

#### Fundamental Concepts of MLOps
- combines people, technology, and processes to deliver collaborative ML solutions
- extension of the DevOps principles and practices to the specific domain of machine learning systems
- Goals of MLOps
    - increase the pace of model development lifecycle through automation
    - improve quality metrics through testing and monitoring
    - Promote culture of collab between data scientists, engineers, and IT ops
    - provide transparency, explainability, audibility, and security
- Key Principles
    - Version control
    - Automation
    - CI/CD
    - Model Governance
