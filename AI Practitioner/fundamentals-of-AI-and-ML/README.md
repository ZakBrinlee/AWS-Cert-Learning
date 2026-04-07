# [AWS Certified AI Practitioner (AIF-C01): Fundamentals of AI and ML](https://app.pluralsight.com/ilx/video-courses/aws-certified-ai-practitioner-ai-ml-fundamentals/course-overview)

Started: April 7th, 2026
Completed: April 7th, 2026

## Top Notes
- 
  - 

### Intro basic AI and ML Concepts
- AI Model -> data driven -> adaptable -> less transparent (than traditional)
- AI meaning -> overarching term for enabling computers to mimic human intelligence
- ML meaning -> Enabling computers to learn on their own using data
- Deep Learning -> using neural networks to learn without intervention
- Natural Language Processing -> Helps computers understand human language
- Generative AI -> Generating new content to expand on the input data (training data)

#### How Do Machines Learn
- Proving ML algorithm with data/labels which will recognize patterns
- Models go through a 'training' state to learn and reach an 'intelligent' state
- Foundation Models
  - large general purpose pre-training models known as foundation models
  - They act as a *blueprint* that can be adapted for various tasks by training on smaller task-specific datasets view *fine tuning*
  - generally cost millions of dollars to create
- Large Language Models
  - foundation model for understanding and generating language
  - use DL to analyze and predict word sequences
  - can process complex language patterns and nuances
- Training Data
  - Input variables (images)
  - target variables (correct label)
  - Goals: should be able to predict the output
  - Predictions: score of 0-1 for how close it recognizes a prediction
- Model Fit
  - How well it has been trained and can predict
  - Patterns (3)
    - Underfitting - model doesn't learn enough from training set and performs poorly on both training and test data - Distracted Dan
    - Overfitting - model learns data to well including noise. It does well on training set but poorly on unseen data - Photocopier Phil
    - Balanced - learns the right amount without being over complex to overfitting
  - Fairness and Bias
    - based on training data not being inclusive for the audience
    - Training Data, Historical, Algorithmic

#### Different ways machines learn
- Supervised Learning
  - providing the training data with labels for the input data
  - Tasks types
    - Classification
      - multiclass
      - binary
    - Regression
      - uses continuous values
- Unsupervised Learning
  - Doesn't rely on labels
  - The model will identify categories
    - clustering based on similar features
    - anomaly detection
- Semi-Supervised learning
  - partially label the data
  - learns from labeled and unlabeled data
- Self-supervised learning
  - Involves using the data to recognize patterns / features
  - Think of gmail auto-complete
- Reinforcement Learning
  - algorithm receives feedback and adapts accordingly
  - Think of e-commerce upsells based on your iterations

#### Types of Data in AI Models
- Structured Data
  - Tabular
  - Time series
- Unstructured Data
  - Text (email, social media posts)
  - Images and videos without labels
  - Audio files

#### Exam tips:
- Need to remember 4 definitions
  - Artificial Intelligence
  - Machine Learning
  - Deep Learning
  - Generative AI
- Natural Language Processing basic
- Models go through a training stage -> should be able to predict outcomes
- Different types of Learning for machines
- Types of training Data
- Model Fit patterns
- Machine Learning Models

### The Machine Learning Pipeline
- Generating Data
  - Fetch -> gather data from sources
  - Clean -> ensure data is accurate and useable
    - missing values
    - inconsistent data
    - duplicates
  - Prepare -> feature engineering
    - formats the data in a format that is easier for a ML model to learn from
    - feature selection
      - select the most relevant features
    - feature extraction
    - dimensionality reduction
      - PCA -> principle component analysis
    - categorical encoding
    - handling scale
- Training the Model
  - Train and tune model
    - goal of enabling the model to predict outputs on new, unseen data
    - parameters
      - weights and biases
        - weights determine the importance of each feature
        - biases provie extra adjustment to fine-tune the model
    - hyperparameters
      - learning rate -> how quickly or slowly the model updates its weights and biases during training
      - batch size -> # of training examples before updating weights
      - number of epochs - to few can lead to underfitting
  - Evaluate model
    - Classification Models
      - True | Positive
      - Imbalanced datasets
    - Evaluation Metrics
      - Accuracy -> measures the $ of correct predictions
      - Precision -> measures the number of predicted positives
      - Recall (sensitivity) -> Measures the proportion of actual positives that were correctly identified by the model
      - F1 score -> measure the harmonic mean of precision and recall
- Deploying the model
  - Deploy to prod
  - Monitor/collect data/evaluate
  
#### Exam Tips
- The ml process
  - Generating Data
    - Exploratory Data Analysis (EDA) -> process of examining and understanding a dataset before diving into modeling
      - Summarizing Features
      - Visualizing the Data
      - Formulating Questions
      - Correlation Metrics -> allows you to quantify relationships between variables
    - Feature engineering -> process of transforming the raw data into meaningful features
      - Feature selection
      - Feature extraction
      - Dimensionality reduction
      - Scaling
      - Categorical encoding
  - Training the Model
  - Deploying the model
- Hyperparameters vs Parameters
  - Hyperparameters
    - Definition: Settings that you choose before training a model
    - Setting Time: before training begins
    - Purpose: Control the learning process and model behavior
    - Examples: learning rate, batch size, # of epochs
    - Tuning method: Optimized through techniques, such as grid search or random search
  - Parameters
    - Definition: Values that the model learns during training
    - Setting time: Updated and adjusted during training
    - Purpose: directly impact model predictions
    - Examples: Weights and biases in neural networks
    - Tuning method: auto adjusted through training algorithms
- Classification vs Regression evaluation metrics
  - Classification Models:
    - Accuracy -> # of times the model got it right out of all predictions made
    - Precision -> # of items the model predicated as positive were actually positive
    - Recall -> # of actual positive items were correctly identified by the model
    - F1 Score -> single number that combines precision and recall to give a balanced view of model's performance
  - Regression Models:
    - Find the difference between predicted values and actual values
      - Mean Absolute Error (MAE)
      - Root Mean Squared Error (RSME)
    - Determine how well a model can predict based on info
      - R Squared

### AWS Managed AI/ML Services and Applications
- Key Services
  - Vision
  - Language
  - Speech
  - Chatbot
  - Forecasting
  - Search
  - Recommendations

- Amazon Rekognition
  - Helps computers "see" and make sense of images/videos using ML
  - Use cases:
    - tracking people
    - analyzing faces
    - facial emotions
    - detection -> objects, scenes, text, brands, activities and inappropriate content
  - Custom moderation adaptor -> use a data set you provide with specialized training/recognition
    - custom labels -> identify specifics

- Amazon Textract
  - Extracting text
    - scanned forms
    - images
    - tables and grids
  - pull out key details
  - Data processing options
    - Real-time analysis
      - single doc sync quickly
    - Async analysis
      - long form content / batches

- Amazon Comprehend
  -  natural language processing -> interpret and understand human language
  - Discover insights into text with built-in classification
    - Spam detection
    - sentiment analysis
  - Entity recognition
  - language detection
  - Two key way of breaking down text
    - Tokenization
      - split sentences into individual words for phrases
    - Parts of Speech (PoS)
      - figures out what role each word plays in a sentence
  - Custom classification -> train based off your data/labels
  - Custom entity recognition

- Amazon Translate
  - translates that maintains tone and fluency
  - localize applications
  - multilingual sentiment analysis
  - real time or large collection (5mb)

- Amazon Polly
  - Text to speech using deep learning
  - Modes
    - real-time mode -> instant audio output
    - batch mode
  - customizations
    - languages
    - voices
    - speech synthesis markup language\
      - pronunciation
      - Adding special emphasis to parts of text
    - lexicons

- Amazon Transcribe
  - Speech to Text
    - real-time via microphone
    - batch uploading
  - Automatic Speech Recognition
    - identifies multi-lingual audio
  - improve accuracy using custom vocab
    - also with custom language models

- Amazon Lex
  - same tech that power Amazon Alexa
  - auto converts speech to text to build chat bots
  - Essence of Bot Conversation
    - intents -> 
    - slots -> details to fulfill the intent
  - Key integrations
    - AWS Lambda
    - Amazon Connect
    - Amazon Comprehend

- Amazon Forecast
  - use historical data to predict trends
    - future sales -> inventory levels -> demand for products
  - needs a labelled training dataset
  - Amazon S3 -> amazon Forecast

- Amazon Kendra
  - Powerful search service
  - NLP
  - extract answers from large data sets
  - search using conversational language
  - contextual relevance

- Amazon Personalize
  - provides recommendations
  - uses recipes -> pre-defined algorithms to build+train models
    - Examples:
      - USER_PERSONALIZATION
      - PERSONALIZED_RANKING
      - PERSONALIZED_ACTIONS
      - POPULAR_ITEMS
      - RELATED_ITEMS
      - USER_SEGMENTATION

### Unpacking Amazon SageMaker
- Fully managed service
- prepare, build, train, tune and deploy ML models from scratch
- supervised, unsupervised, reinforcement, and deep-learning
- Uses SageMaker Studio - IDE for building models
- SageMaker Pipelines
  - ML Workflows
    - version and tracking
    - manage steps for each part of the process
- AutoML (Autopilot)
  - Upload data + specify target variable

- Data Wrangler
  - Transforms data into clean manageable data
  - Part of the SageMaker studio
  - Can use SQL to manipulate data
  - Import -> Clean -> Feature Engineer -> Visualize (EDA)

- SageMaker Feature Store
  - centralized hub for storing and retrieving ML Features
  - reduces redundancy of features and save time