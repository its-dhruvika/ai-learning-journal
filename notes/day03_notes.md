# Day 03 - NumPy Operations, Broadcasting, and Linear Algebra

## Overview

Today I explored vectorized operations, broadcasting, and basic linear algebra in NumPy. These concepts are fundamental to Machine Learning because they enable fast computations on large datasets without using explicit Python loops.

---

## What I Learned

### 1. Vectorized Operations

NumPy performs operations on entire arrays at once instead of processing elements one by one with loops.

Example:

```python
import numpy as np

a = np.array([1, 2, 3])
b = np.array([4, 5, 6])

print(a + b)
print(a * b)
```

Output:

```python
[5 7 9]
[ 4 10 18]
```

Benefits of vectorization:

* Cleaner code
* Faster execution
* Lower memory overhead
* Essential for machine learning workflows

---

### 2. Broadcasting

Broadcasting allows NumPy to perform operations on arrays with different shapes by automatically expanding dimensions when they are compatible.

Broadcasting rules:

1. Compare shapes from right to left.
2. Dimensions are compatible if they are equal or one of them is 1.
3. If dimensions are compatible, NumPy stretches the dimension with size 1.

Example:

```python
a = np.array([[1], [2], [3]])     # Shape: (3,1)

b = np.array([[10, 20, 30, 40]]) # Shape: (1,4)

result = a + b
```

Shapes:

```text
(3,1)
(1,4)
------
(3,4)
```

Result:

```python
[[11 21 31 41]
 [12 22 32 42]
 [13 23 33 43]]
```

### Broadcasting in My Own Words

Broadcasting is NumPy's ability to automatically expand smaller arrays to match larger arrays during calculations without actually copying the data.

---

### 3. Aggregation Functions

NumPy can perform calculations across entire arrays or specific axes.

```python
matrix = np.array([
    [1, 2, 3],
    [4, 5, 6]
])
```

#### Sum

```python
matrix.sum()
```

Output:

```python
21
```

#### Mean

```python
matrix.mean()
```

Output:

```python
3.5
```

#### Standard Deviation

```python
matrix.std()
```

---

### Understanding Axes

For a 2D array:

* `axis=0` → operate down columns
* `axis=1` → operate across rows

Example:

```python
matrix.sum(axis=0)
```

Output:

```python
[5 7 9]
```

Example:

```python
matrix.sum(axis=1)
```

Output:

```python
[ 6 15]
```

---

### 4. Matrix Multiplication

Matrix multiplication combines rows from the first matrix with columns from the second matrix.

```python
a = np.array([
    [1, 2],
    [3, 4]
])

b = np.array([
    [5, 6],
    [7, 8]
])

result = np.dot(a, b)
```

Output:

```python
[[19 22]
 [43 50]]
```

Alternative syntax:

```python
result = a @ b
```

---

## Mini Project: Image Processing with NumPy

### Goal

Manipulate an image using NumPy arrays.

### Steps Performed

1. Loaded an image using Matplotlib.
2. Observed that the image is stored as a NumPy array with shape `(height, width, 3)`.
3. Flipped the image horizontally.
4. Converted the image to grayscale.
5. Saved the processed image.

### Code

```python
import matplotlib.pyplot as plt
import numpy as np

image = plt.imread("sample.jpg")

flipped = image[:, ::-1]

grayscale = image.mean(axis=2)

plt.imsave("grayscale.jpg", grayscale, cmap="gray")
```

### Key Insight

Images are simply multidimensional NumPy arrays:

* Height → number of rows
* Width → number of columns
* RGB channels → color information

Shape example:

```text
(480, 640, 3)
```

---

## Three Things That Confused Me

1. Understanding broadcasting rules when arrays have multiple dimensions.
2. Remembering the difference between `axis=0` and `axis=1`.
3. Distinguishing element-wise multiplication from matrix multiplication.

---

## Three Things That Clicked

1. NumPy operations are much faster because they avoid Python loops.
2. Broadcasting works by comparing dimensions from right to left.
3. Images can be manipulated using simple array operations.

---

## Key Takeaways

* Vectorized operations replace explicit loops.
* Broadcasting enables calculations between compatible shapes.
* Aggregation functions simplify data analysis.
* `axis=0` represents columns and `axis=1` represents rows.
* Matrix multiplication is fundamental to neural networks.
* Images are multidimensional NumPy arrays.
