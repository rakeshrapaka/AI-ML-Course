 # Day 4: Perceptron Learning & Activation Functions

## Concepts
- What is a Perceptron? (Building block of neural networks)
- Single-layer vs Multi-layer Perceptron (MLP)
- Role of activation functions: Sigmoid, Tanh, ReLU
- Linear vs Non-linear decision boundaries
- Why we need activation functions to model complex patterns

## Analogy
Think of a perceptron as a simple switch: it turns on or off based on input. Activation functions add 'personality' to this switch, making it respond smoothly or sharply.

## Practical Exercise
- Implement a simple perceptron for binary classification.
- Try different activation functions and visualize their output.

## Example Code: Simple Perceptron
```python
import numpy as np

# Step activation
def step(x): return np.where(x >= 0, 1, 0)

# Dataset: AND logic gate
X = np.array([[0,0],[0,1],[1,0],[1,1]])
y = np.array([0,0,0,1])

# Initialize weights
W = np.random.randn(2)
b = 0
lr = 0.1

# Training
for epoch in range(10):
    for i in range(len(X)):
        z = np.dot(X[i], W) + b
        pred = step(z)
        error = y[i] - pred
        W += lr * error * X[i]
        b += lr * error

print("Trained Weights:", W, "Bias:", b)
for x in X:
    print(f"Input: {x} -> Prediction: {step(np.dot(x, W) + b)}")
```

## To-Do
- Modify dataset to OR, XOR and test perceptron performance.
- Plot activation functions (sigmoid, tanh, relu) using matplotlib.
