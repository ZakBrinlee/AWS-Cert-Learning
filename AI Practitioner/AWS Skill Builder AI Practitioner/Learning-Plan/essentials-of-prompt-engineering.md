# [Essentials of Prompt Engineering](https://skillbuilder.aws/learn/XBNAVKA88J/essentials-of-prompt-engineering/9T9Q45EDTV?parentId=SU2A1EJM1A)

Started: April 22, 2026
Completed: April 22, 2026

### Top notes:
- A well-crafted prompt has 4 elements: **Instructions** (what to do), **Context** (background info), **Input Data** (the actual request), and **Output Indicator** (desired format/type). Use **negative prompting** to steer the model away from unwanted outputs.
- **3 key inference parameters** to tune output behavior:
  - **Temperature** (0–1): lower = focused/predictable, higher = creative/diverse.
  - **Top P** (0–1): limits token choices to a cumulative probability threshold — lower = more focused.
  - **Top K** (any integer): limits token choices to the K most probable words — lower = more focused.
- **Prompting best practices**: be clear and concise, include context, specify output format, break up complex tasks, experiment, and use prompt templates.
- **Core prompting techniques**:
  - **Zero-shot**: no examples — works best with larger/more capable models.
  - **Few-shot**: provide sample input/output pairs to guide the model.
  - **Chain-of-thought**: break multi-step or complex reasoning into intermediate steps.
- **Prompt security risks** to know:
  - **Poisoning**: malicious data injected into training data.
  - **Hijacking / Prompt injection**: embedded instructions that override intended behavior.
  - **Exposure / Prompt leaking**: sensitive info revealed during training or inference.
  - **Jailbreaking**: crafted prompts that bypass safety filters and constraints.

## Notes
### Prompt Basics
#### Understanding Prompts
- Elements of a prompt
    - Instructions
        - task description or instruction for how the model should perform
    - Context
        - external information to guide the model
    - Input data
        - input for which you want a response
    - Output indicator
        - output type or format
- Negative prompting
    - used to guide the model away from generating types of content or behaviors.
    - provide the model with examples of what not to do/generate

#### Modifying Prompts
- you can often configure inference parameters to limit or influence the model response
- Most common categories of inference parameters
    - Randomness & Diversity (most common)
        - influence the variation in generated responses by limiting the outputs to more likely outcomes or by changing the shape of the probability distribution of outputs
        - Temperature
            - controls the randomness or creativity of the model's output
            - Temp is set between 0 and 1
                - higher -> more diverse and unpredictable
                    - eg. 1.0 - more diverse, creative, and unpredictable but may be less coherent/relevant
                - lower -> more focused and predictable
                    - eg. 0.2 - output are more conservative, repetitive, and focused on the most likely responses
        - Top P
            - controls the diversity of the text by limiting the # of words the model can choose from based on their probabilities
            - Top P is set between 0 and 1
                - lower -> model will only consider words that make up the top %P of the total probability distribution. 
                    - eg. 0.25 - more focused and coherent.
                - higher -> will consider a broad range of possible words for the next word in the sequence
                    - eg. 0.99 - more diverse and creative output  
        - Top K
            - limits the number of words to the most probable words, regardless of their % probabilities
            - any range/limit of numbers (100, 30, 500, etc)
                - Low top k (eg - 10)
                    - model will only consider the 10 most probable words for the next word in the sequence
                    - more focused and coherent
                - High top k (eg - 500)
                    - model will consider the 500 most probable words for the next word in sequence, regardless of individual probabilities
                    - more diverse and creative output
    - Length
        - refers to the settings that control the maximum length of the generated output and stop sequences that signal end of gen process
        - Maximum length
            - max # of tokens the model can generate during inference process
                - helps to prevent excessive or infinite output generation
        - Stop sequences
            - special tokens or sequences of tokens that signal the model to stop generating further output.
            - can be predefined or dynamically generated

- Prompting Best Practices
    - Be clear & concise
    - Include context if needed
    - Use directives for the appropriate response type
    - Consider the output in the prompt
    - Start prompts with an interrogation
    - Provide an example response
    - Break up complex tasks
    - Experiment and be creative
    - Use prompt templates

#### Prompt Engineering Techniques
- Zero-shot
    - user presents a task to gen model w/o providing examples or explicit training for specific task
    - larger and more capable the FM, the higher the likelihood of obtaining effective results from zero-shot prompts
- Few-shot
    - providing contextual examples to guide the understanding and expected output for specific task
    - supplement the prompt with sample inputs and corresponding desired outputs.
- Chain-of-thought
    - divides intricate reasoning tasks into smaller - intermediary steps
    - recommended with the task requires multi steps or series of logical reasoning

### Risks
#### Prompt Misuses and Risks
- Poisoning, Hijacking & Prompt injection
    - Poisoning
        - intentional intro of malicious or biased data into training dataset
    - Hijacking & Prompt Injection
        - influencing the outputs of gen models by embedding specific instructions within the prompts
- Exposure and prompt leaking
    - Exposure
        - exposing sensitive or confidential info during training or inference.
    - Prompt leaking
        - unintentional disclosure or leakage of prompts or inputs used within a model
- Jailbreaking
    - practice of modifying or circumventing the constraints & safety measure implemented in a gen model/assistant to gain unauthorized access or functionality
    - involves crafting carefully constructed prompts/input sequences that try to bypass or exploit vulnerabilities in a system's filtering mechanisms/constraints
