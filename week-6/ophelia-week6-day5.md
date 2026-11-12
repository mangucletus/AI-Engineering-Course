Ophelia: Week 6, Day 5 - Fine-Tuning for Frontier Models

## To Fine Tuning with OpenAI

1. Create training Dataset in Jsonl format and upload to OpenAI
2. Run training - training loss and validation loss should increase
3. Evaluate results, tweak and repeat

## Types of Fine Tuning

### 1. Supervised Fine-Tuning (SFT)

Supervised fine-tuning (SFT) lets you train an OpenAI model with examples for your specific use case. The result is a customised model that more reliably produces your desired style and content.

Best for classification, Nuanced Translation, Generating content in a specific format
- Correcting instruction following failures

Use with:
- gpt-4.1-2025-04-14
- gpt-4.1-mini-2025-04-14
- gpt-4.1-nano-2025-04-14

### 2. Direct Preference Optimization (DPO)

Direct Preference Optimization (DPO) allows you to fine-tune models based on prompts and pairs of responses. This approach enables the model to learn from more subjective human preference. Optimizing for output that are more likely to be favored.

DPO is currently only supported for text inputs and output.

Best for:
1. Summarizing text, focusing on the right things
2. Generating chat messages with the right tone and style

Use with: Same models as Supervised fine-tuning.

### 3. Reinforcement Fine-Tuning (RFT)

Reinforcement fine-tuning (RFT) - adapts an OpenAI reasoning model with a feedback signal you define. Like supervised fine tuning, it tailors the model to your task. The difference is that instead of training on fixed "correct" answers, it relies on a programmable grader that scores every candidate response.

Best for complex domain-specific task that require advanced reasoning
- Medical diagnoses based on history and diagnostic guidelines
- Determining relevant passages for legal case law

Use with: o4-mini-2025-04-16, Reasoning Models only

## Data Size

OpenAI recommends fine-tuning with a small population of 50-100 examples.

## Steps in Fine Tuning

1. Prepare data for fine tuning in JSONL (JSON Lines) format and upload to OpenAI
2. Fine-tuning starts

## Key Objectives of Fine-Tuning for Frontier Models.

1. Setting Style or tone in a way that can't be achieved with prompting
2. Improving the reliability of producing a type of output
3. Correcting failures to follow complex prompts.
4. Handling edge cases
5. Performing a new skill or task that's hard to articulate in a prompt

* Problem like ours doesn't benefit significantly from Fine-Tuning
- The problem and style of output can be clearly specified in a prompt
- The model can take advantage of its enormous world knowledge from its pre-training; providing a few extra prices doesn't materially help.

Failed experiments is part of the nature of Data Science!
