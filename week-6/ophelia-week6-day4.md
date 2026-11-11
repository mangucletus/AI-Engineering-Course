Ophelia: Week 6, Day 4 - The Four Steps of Training

The Four Steps of Training
Tweaking the parameters of a Model based on training data -- in a way that should generalize to unseen data.

1. Forward pass
Predict the output given inputs

2. Loss Calculation
How different was the prediction to the ground truth

3. Backward pass
How should we tweak parameters to do better next time (the "gradients")

4. Optimization
Update parameters a tiny step to do better next time

Hyper-parameters
You can specify additional Settings that aren't updated during training known as "Hyper-parameters" Like epoch and learning rate.

Code
from evaluation import test

tests = test.load_tests()

len(tests)

example = tests[0]
print(example.question)
print(example.category)
print(example.reference_answer)
print(example.keywords)

from collections import Counter
Count = Counter[str]([t.category for t in tests])
Count
Counter({'direct_fact': 70,
         'temporal': 20,
         'spanning': 20,
         'comparative': 10,
         'numerical': 10,
         'relationship': 10,
         'holistic': 10})
from evaluation.eval import evaluate_retrieval, evaluate_answer

evaluate_retrieval(example)

eval, answer, chunks = evaluate_answer(example)

eval

print(eval.feedback)
print(eval.accuracy)
print(eval.completeness)
print(eval.relevance)
