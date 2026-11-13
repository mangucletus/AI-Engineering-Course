Ophelia: Week 7, Day 1 - High Level Explanation of LoRA

## High Level Explanation of LoRA

Step 1: Freeze the weights - we will not optimize them
Step 2: Select some layers to target, called "Target Modules"
Step 3: Create new "adaptor" matrices with lower dimensions, fewer parameters
Step 4: Apply these adaptors to the Target Modules to adjust them - and these get trained.

## 3 Essentials Hyperparameters

### 1. r - The rank, or how many dimensions in the low-rank matrices.
Rule of Thumb: Start with 8, then double to 16, then 32, until diminishing returns.

### 2. Alpha - A scaling factor that multiplies the lower rank matrices
Rule of Thumb: Twice the value of r

### 3. Target Modules - Which layers of the neural network are adapted.
Rule of Thumb: Start by targeting the attention heads

## Size of Weights in MB

- 13,000 - Llama 3.2 3B
- 3600 - Quantized to 8 bit
- 2200 - Quantized to 4 bits
- 8 + 3 - QLoRA with r = 32
    - The LoRA weighs in 32 bit
