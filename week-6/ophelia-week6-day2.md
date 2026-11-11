# Ophelia: Week 6, Day 2 
5 Step Strategy To Selecting, Training and Applying an LLM to a Commercial Problem

## 5 Step Strategy

1. Understand
2. Prepare
3. Select
4. Customize
5. Productionize

## 1. Understanding

### Activities -

1. Gather business requirements for the task
2. Identify performance criteria
   - Model and Business centric metrics
3. Understand the data: quantity, quality, format
4. Determine non-functionals:
   - Cost Constraints, Scalability, Latency
   - R & D / build budget and implementation timeline.

## 2. Preparation

### Activities

a. Research existing / non-LLM solution
   - Potential baseline Model.
b. Compare relevant LLMs.
   - The basics, including context length, price and [Tokens]
   - Benchmarks, Leaderboards, and Arenas &
   - Specialist scores for the task at hand
c. Curate data: clean, preprocess and split

## 3. Selection

### Activities

- Choose LLMs
- Experiment
- Train and validate with curated data.

## 4. Customization

Technique to optimize the performance of the models

1. Prompt
2. RAG
3. Agents
4. Fine-tune

- Prompt -> using prompts to bias the model to making model's output consistent with input
- RAG - Looking for ways to select relevant context, e.g. using vector Market similarity, Embedded model.
- Agents (Agentic AI) - Breaking Extension of prompt, doing LLMs calls into Multi calls and having one of the calls decide which to call and in what order
- Fine-tune - giving LLMs data to make it better at a task

- The first 3 are all Inference Time Techniques - levers, run time you used to train Models to get most out of them
- The last one is a Training Time Technique - The actual training of the Model
- Mostly, more time is spent on the Inference Time Section.

- RAG - Ideal for Generalisation. Generalise Models
- Fine tuning - Ideal for Models built purposely for one area of expertise

## 5. Productionize

### Activities

1. Determine API between model and platform(s).
2. Identify model hosting and deployment architecture.
3. Address scaling, monitoring, Security, compliance, observability.
4. Eval: measuring the Business - focused Metrics identified in Step 1
5. Continuously retrain and measure performance.
