 # Day 5: Neural Networks Basics
## Concepts
- What is a Neural Network?
- Neurons, Layers (Input, Hidden, Output), Weights, and Activation Functions.
- Common activations: Sigmoid, ReLU, Tanh.
- Forward Propagation (data flow) and Backpropagation (learning process).

## Analogy
A neural network is like a team of decision-makers: each neuron makes a small decision and passes it to the next layer.

## Practical Exercise
- Implement a single-layer perceptron in Python (NumPy).
- Experiment with Tanh and ReLU activation.

## Example Code
```python
import numpy as np

def relu(x): return np.maximum(0, x)
def tanh(x): return np.tanh(x)

X = np.array([[0,0],[0,1],[1,0],[1,1]])
y = np.array([[0],[1],[1],[0]])

W = np.random.randn(2,1)
b = np.zeros((1,))
lr = 0.1
for epoch in range(1000):
    z = np.dot(X, W) + b
    a = tanh(z)
    grad_w = np.dot(X.T, (2*(a - y)*(1 - a**2))) / len(X)
    W -= lr * grad_w
    b -= lr * np.mean(2*(a - y)*(1 - a**2))

print("Predictions:", np.round(tanh(np.dot(X, W) + b)))
```
