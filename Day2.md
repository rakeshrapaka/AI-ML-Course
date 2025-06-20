# 🐍 Day 2 – Python Basics for AI/ML (with Drone-Relevant Examples)

## 🎯 Learning Objectives

* Learn Python syntax and logic
* Work with variables, conditionals, loops, and functions
* Explore data manipulation with NumPy and Pandas
* Apply examples using drone telemetry and sensor data

---

## 📘 Why Python for AI/ML?

Python is the go-to language for AI due to its:

* Simplicity and readability
* Rich ecosystem of libraries
* Community support

> In drone and robotics systems, Python is used to automate flight patterns, analyze sensor data, and process camera streams.

---

## 🔤 Python Basics – Syntax & Logic

### ✅ Data Types

```python
integer_value = 10        # int
floating_value = 3.14     # float
text_value = "Drone"       # str
list_of_speeds = [12, 15, 9]  # list
is_flying = True          # bool
```

### ✅ Conditional Logic

```python
battery = 35
if battery < 20:
    print("Low battery – return to base")
else:
    print("Battery OK")
```

### ✅ Loops

```python
for speed in list_of_speeds:
    print(f"Speed: {speed} m/s")
```

### ✅ Functions

```python
def altitude_to_pressure(altitude):
    return 1013.25 * (1 - 2.25577e-5 * altitude) ** 5.2559

print(altitude_to_pressure(1200))
```

---

## 🔢 NumPy – Fast Numerical Computation

```python
import numpy as np

altitudes = np.array([100, 200, 300])
pressure = 1013.25 * (1 - 2.25577e-5 * altitudes) ** 5.2559
print(pressure)
```

> Use NumPy to compute altitude-pressure conversions for entire drone flights.

---

## 🧾 Pandas – Handle Structured Data

```python
import pandas as pd

data = {
    'timestamp': ['10:01', '10:02', '10:03'],
    'altitude': [100, 120, 140],
    'battery': [92, 88, 84]
}
df = pd.DataFrame(data)
print(df)

# Filter high altitude records
print(df[df['altitude'] > 110])
```

## 📂 Suggested Practice

* Create a function to flag low-battery warnings
* Use NumPy to compute average altitude
* Load `.csv` flight data into Pandas and explore

---

## 📌 Homework

* Simulate battery drain during flight using Python list & loop
* Filter drone logs with altitude > 100m using Pandas
* Use NumPy to calculate min, max, std of drone speed readings

Save your file as `yourname_day2_practice.py` and push it to your `/Day_02/` folder on GitHub.

---

Next up → **Day 3: Math for Machine Learning – Linear Algebra, Stats, Probability**
