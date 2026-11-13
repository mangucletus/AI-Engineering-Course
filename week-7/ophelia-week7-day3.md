Ophelia: Week 7, Day 3

## Five Important Hyper-parameters for QLoRA

### 1. Target Modules
Choose which modules to target, usually Targets the attention layers first and other as well.

### 2. r
Number of dimensions of the LoRA matrices

### 3. Alpha
Multiply LoRA A and LoRA B and Alpha tell you how much to scale before adding to the biggest module.

### 4. Quantization
Minimizing to 8 or 4 bits, saving more space for other things. - Makes the models poorer though.

### 5. Dropout
Randomly Probability that get wipe / zero out during the training. Usually, 10%.
It prevents your neural network from overfitting the data, improving Generalization.

## Five Important Hyper-parameters for Training

### 1. Epoch's
Passing data through in batches.

### 2. Batch size
How many batch are in one size batch

### 3. Learning Rate
How bigger step you take each time - Not point NOT Hot one

### 4. Gradient Accumulation
Forward pass, backward pass, take a baby step

### 5. Optimizer
-

## The 4 Steps of Training

Tweaking the parameters of a model based on training data, in a way that should generalize to unseen data

### 1. Forward pass
Predict the output given inputs

### 2. Loss
How different was the prediction to the ground truth

### 3. Backward pass
How should we tweak parameters to do better next time (the "gradients")

### 4. Optimization
Update parameters a tiny step to do better next time

The process of experimenting with these is called "hyper-parameter optimization"
