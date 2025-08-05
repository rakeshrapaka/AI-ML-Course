 # Day 6: Deep Learning Fundamentals
## Concepts
- Difference between Neural Networks and Deep Neural Networks.
- Why Deep Learning works.
- Vanishing Gradient problem & how ReLU helps.
- Intro to TensorFlow & PyTorch.

## Analogy
Shallow networks: one chef cooks the whole meal. Deep networks: multiple chefs handle parts.

## Practical Exercise
- Build a simple DNN with 2 hidden layers using Keras.
- Train on MNIST dataset.

## Example Code
```python
import tensorflow as tf
from tensorflow.keras.models import Sequential
from tensorflow.keras.layers import Dense, Flatten
from tensorflow.keras.datasets import mnist

(x_train, y_train), (x_test, y_test) = mnist.load_data()
x_train, x_test = x_train / 255.0, x_test / 255.0

model = Sequential([
    Flatten(input_shape=(28,28)),
    Dense(128, activation='relu'),
    Dense(64, activation='relu'),
    Dense(10, activation='softmax')
])

model.compile(optimizer='adam', loss='sparse_categorical_crossentropy', metrics=['accuracy'])
model.fit(x_train, y_train, epochs=5, validation_data=(x_test, y_test))
print("Accuracy:", model.evaluate(x_test, y_test)[1])
```
