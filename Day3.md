# 🧮 Math for Machine Learning – Linear Algebra, Stats, and Probability

Welcome to Lesson 3! In this module, we’ll explore the **math foundation** that powers all Machine Learning models — especially useful when dealing with drone/robotics sensor data, flight predictions, or AI-based navigation.

---

## 🎯 Objectives

* Learn how math is used in AI/ML
* Understand the basics of:

  * Linear Algebra (vectors, matrices)
  * Statistics (mean, median, std dev)
  * Probability (likelihood, distributions)

---

## 🧠 Why Math in ML?

* Think of **ML models as formulas** that learn patterns from data.
* Math helps you understand **how** models work internally.
* Drones use math to interpret sensor inputs, predict positions, and balance movement.

---

## 🔢 1. Linear Algebra

### ✅ Key Concepts:

* **Scalar**: A single value (e.g., 30°C)
* **Vector**: A list of values (e.g., speeds at 5 timestamps)
* **Matrix**: A grid of numbers (e.g., camera pixels or telemetry log)

```python
import numpy as np

# Vector: drone's altitude at different times
altitudes = np.array([10, 15, 20, 25])

# Matrix: telemetry data (altitude, speed, battery)
data = np.array([
    [10, 5.2, 89],
    [15, 5.5, 85],
    [20, 5.3, 82]
])

print(data.shape)  # (3 rows x 3 columns)
```

---

## 📊 2. Statistics

### ✅ Key Measures:

* **Mean (Average)**: Central value
* **Median**: Middle value
* **Standard Deviation**: Spread of values

```python
import pandas as pd

battery_levels = pd.Series([92, 89, 84, 88, 87])
print("Mean:", battery_levels.mean())
print("Median:", battery_levels.median())
print("Std Dev:", battery_levels.std())
```

> Drones monitor average battery drain to forecast return time!

---

## 🎲 3. Probability

### ✅ Why It Matters:

* Helps in **classification** and **predictions**
* Used in **Bayesian networks** and **sensor fusion**

### 🔍 Example: Coin Flip Simulation

```python
import random

heads = 0
trials = 1000
for _ in range(trials):
    if random.choice(["H", "T"]) == "H":
        heads += 1

print(f"Probability of Heads ≈ {heads/trials:.2f}")
```

> Probabilities help drones deal with uncertain environments (e.g., GPS signal loss)

---

## ✨ Drone Tie-In

| Math Concept  | Drone Example                                  |
| ------------- | ---------------------------------------------- |
| Vector        | Speed, altitude, battery at a point            |
| Matrix        | Camera image or motion log                     |
| Mean, Std Dev | Analyzing flight data fluctuations             |
| Probability   | Estimating landing success in windy conditions |

---

## 🧠 Mind Map Summary

* **Linear Algebra**

  * Scalars, Vectors, Matrices
* **Statistics**

  * Mean, Median, Std Dev
* **Probability**

  * Chance, Randomness, Estimation
* **Drone Tie-Ins**

  * Telemetry, Sensor noise, Risk estimates

---

## 🎯 Homework

* Collect mock data: \[altitude, speed, battery]
* Use NumPy/Pandas to calculate mean, std dev
* Try simulating random GPS signal loss using `random.choice()`

📂 Save your work in `Lesson_03_Math_for_ML/` folder in your GitHub repo


## 🎥 Ready for Next?
* Feature Engineering & Data Cleaning** 
