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

## 🧠 From Data to Model: The Learning Process**

### 🎯 Objectives:

* Understand how data is used to train models
* Learn about features, labels, training & testing
* See what happens “under the hood” during training

---

### 🍽️ Analogy: Learning to Make Masala Dosa

Imagine you want to teach someone (or a robot!) to make perfect masala dosa.

#### 1. **Features** = Ingredients and heat levels

> Eg: flour type, batter fermentation time, pan heat, oil amount
> **In ML**: features are the inputs

#### 2. **Label** = What makes a dosa “perfect”

> Golden color? Crispiness? Thickness?
> **In ML**: label is the output we’re predicting

#### 3. **Training** = Trying with different combos of features and checking the result

> "If batter is 12 hrs fermented and pan is medium hot → dosa is perfect"
> This builds a **model**: a recipe that connects inputs to output.

---

## 🧪 Simple Table Example

| Batter Hours | Pan Temp (°C) | Is Dosa Perfect? (Label) |
| ------------ | ------------- | ------------------------ |
| 8            | 180           | No                       |
| 12           | 200           | Yes                      |
| 10           | 190           | Yes                      |
| 6            | 150           | No                       |

The model finds patterns:

* If batter ≥ 10 hours and pan ≥ 190°C → likely perfect!

---

### 🎓 Key Concepts

| Term             | Meaning                                                     |
| ---------------- | ----------------------------------------------------------- |
| **Training**     | Teaching the model from known data                          |
| **Testing**      | Checking how well it performs on *unseen* data              |
| **Overfitting**  | Like memorizing recipe *too perfectly*, fails on new batter |
| **Underfitting** | Learns too little, can't even make decent dosa              |

---

### 🧪 Exercise: Identify the Parts

You’re teaching a robot to predict house price.

| Feature                 | Label |
| ----------------------- | ----- |
| Number of rooms         | ?     |
| Size of house (sq ft)   | ?     |
| Distance to city center | ?     |
| Price                   | ?     |

<details><summary>✅ Solution</summary>

* Features = rooms, size, distance
* Label = price

</details>

---

### 🧠 Bonus Analogy: Studying for Exams

* **Training Set** = Your practice problems
* **Testing Set** = The actual exam
* **Overfitting** = Memorizing practice answers
* **Good Model** = Understands the concepts and applies them to any exam

---

## 💡 Practical Activity

Try this mini-lab in a spreadsheet:

1. Create columns: `Study Hours`, `Sleep Hours`, `Score (Label)`
2. Fill with sample data:

   ```
   Study: 2, Sleep: 6 → Score: 60
   Study: 5, Sleep: 7 → Score: 85
   Study: 1, Sleep: 4 → Score: 40
   ```
3. Plot `Study vs Score` – see the trend!
4. Predict what happens if Study = 4, Sleep = 6?

<details><summary>✅ Expected Answer</summary>
Likely Score ≈ 75–80 based on trend
</details>

---

## 📌 Summary Cheat Sheet

| What?                | In Real Life                       | In ML              |
| -------------------- | ---------------------------------- | ------------------ |
| Inputs               | Ingredients                        | Features           |
| Expected Output      | Dosa quality                       | Label              |
| Learning Process     | Trying recipes and judging results | Training           |
| Final Recipe         | "Best dosa rule"                   | Trained Model      |
| Applying to new case | Making dosa for guests             | Testing/Prediction |

---

## 🎥 Ready for Next?

* Visualizing **Decision Trees**
* Try a real-world mini ML experiment (no code)
* Understand model accuracy and bias
* Feature Engineering & Data Cleaning** 
