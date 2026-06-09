# Day 02 - NumPy Arrays, Shapes, and Indexing

## Overview

Today I started learning NumPy, the core numerical computing library used throughout Machine Learning, Deep Learning, Data Science, and AI applications. The focus was understanding NumPy arrays, their shapes, dimensions, and indexing techniques.

---

## What I Learned

### 1. NumPy Arrays (`ndarray`)

NumPy provides the `ndarray` (N-dimensional array) data structure, which stores data more efficiently than Python lists.

Example:

```python
import numpy as np

arr = np.array([1, 2, 3, 4, 5])
```

Benefits:

* Faster computations
* Less memory usage
* Vectorized operations
* Foundation for ML libraries such as TensorFlow and PyTorch

---

### 2. Creating Arrays

#### Zeros Array

```python
np.zeros((3,3))
```

Creates a 3×3 matrix filled with zeros.

#### Ones Array

```python
np.ones((2,4))
```

Creates a 2×4 matrix filled with ones.

#### Arange

```python
np.arange(0,10,2)
```

Output:

```python
[0 2 4 6 8]
```

#### Linspace

```python
np.linspace(0,1,5)
```

Output:

```python
[0.   0.25 0.50 0.75 1.00]
```

---

### 3. Understanding Shape

The shape tells us the dimensions of an array.

Example:

```python
arr = np.array([[1,2,3],
                [4,5,6]])

print(arr.shape)
```

Output:

```python
(2,3)
```

Meaning:

* 2 rows
* 3 columns

---

### 4. Reshaping Arrays

Changing the dimensions without changing the data.

```python
arr = np.arange(12)

arr.reshape(3,4)
```

Output:

```python
[[ 0  1  2  3]
 [ 4  5  6  7]
 [ 8  9 10 11]]
```

Important:

```python
rows × columns = total elements
```

---

### 5. Array Indexing

#### 1D Indexing

```python
arr = np.array([10,20,30,40])

arr[0]
```

Output:

```python
10
```

---

### 6. 2D Indexing

```python
arr = np.array([
    [1,2,3],
    [4,5,6]
])

arr[1,2]
```

Output:

```python
6
```

Meaning:

```python
[row, column]
```

---

### 7. Array Slicing

Extracting a portion of an array.

```python
arr[1:4]
```

Returns elements from index 1 to 3.

---

### 8. Matrix Slicing

Example:

```python
a = np.arange(16).reshape(4,4)
```

Matrix:

```python
[[ 0  1  2  3]
 [ 4  5  6  7]
 [ 8  9 10 11]
 [12 13 14 15]]
```

Slice:

```python
a[1:3,0:2]
```

Output:

```python
[[4 5]
 [8 9]]
```

Explanation:

```text
Rows: 1 and 2
Columns: 0 and 1
```

This extracts a 2×2 submatrix.

---

## Mini Project: Matrix Operations

### Goal

Create a 5×5 matrix of random numbers and perform basic feature-scaling operations.

### Steps

1. Generate random matrix.
2. Find maximum value of each row.
3. Normalize every column.
4. Print results.

### Code

```python
import numpy as np

matrix = np.random.randint(1,100,(5,5))

print("Original Matrix:")
print(matrix)

row_max = np.max(matrix, axis=1)

print("\nMaximum value of each row:")
print(row_max)

col_min = np.min(matrix, axis=0)
col_max = np.max(matrix, axis=0)

normalized = (matrix - col_min) / (col_max - col_min)

print("\nNormalized Matrix:")
print(normalized)
```

### Why This Matters

Feature scaling is an important preprocessing step in Machine Learning because it helps models train faster and prevents features with large values from dominating others.

---

## Key Takeaways

* NumPy arrays are the foundation of scientific computing in Python.
* Shape determines dimensions of data.
* Reshape changes structure without changing data.
* Indexing and slicing allow efficient data extraction.
* Matrix operations are significantly easier than with Python lists.
* Feature scaling is a practical application of NumPy and an essential ML preprocessing technique.

---

## Challenges Faced

* Understanding row vs column indexing.
* Visualizing how slicing works in two dimensions.
* Remembering that slicing excludes the ending index.

---

## Tomorrow's Focus

* NumPy mathematical operations
* Broadcasting
* Array statistics
* Aggregation functions
* Random module
* Boolean masking
* Vectorized computation

---

## Files Created

* day02_numpy_arrays.ipynb
* day02_notes.md

## Commit Message

```bash
git add .
git commit -m "Day 02: Learned NumPy arrays, shapes, indexing and matrix operations"
git push origin main
```
