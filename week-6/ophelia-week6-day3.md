 Ophelia: Week 6, Day 3 - Baseline Model & Traditional ML

## The Importance of a Baseline

- Start cheap and simple
- Gives a benchmark to improve on
- An LLM might not be the right solution

## Machine Learning

- A branch of AI where Algorithms learn from data to make predictions without being explicitly programmed.
- These days, ML is most often used in the context of traditional ML, Pre-Deep learning & LLMs
- It's still crucial to understand core ML principles to be an LLM practitioner.
- Generalizing - The ability to perform well on new, unseen data by capturing underlying patterns
- Overfitting - When a model mimics the training data too closely, leading to poor performance on unseen data.
- The goal of Machine Learning is to GENERALIZE - to make accurate predictions on unseen data.

### Some algorithms include:

1. Random Forest
2. Linear Regression

## Model Predictions Terminology

- "y-Hat" is the terminology used for Model predictions
- The y is what the Model says the Price should be and
- The "Hat" is the actual / true price of the item (ground truth).
- Every dot represent one of the test parts.
Random ForestRandom Forest is a type of Model called "ensemble": meaning, it can combine many smaller models algorithms to make better predictions.
Decision TreeDecision Tree: Bunch of "If" statements combined together to make prediction
XGBoost is an ensemble Model that combines multiple Decision Trees
XGBoost builds one tree after another, and with each next tree correcting errors of the previous / prior trees using "gradient descent"
It is faster than Random Forest and better at generalizing.
```python
return model.predict()(0) - to predict new unseen values
