---
jupyter:
  jupytext:
    formats: ipynb,md
    text_representation:
      extension: .md
      format_name: markdown
      format_version: '1.3'
      jupytext_version: 1.19.5
  kernelspec:
    display_name: Python 3 (ipykernel)
    language: python
    name: python3
---

# Machine Learning Zoomcamp

## 1.8 Linear algebra refresher


Plan:

* Vector operations
* Multiplication
    * Vector-vector multiplication
    * Matrix-vector multiplication
    * Matrix-matrix multiplication
* Identity matrix
* Inverse

```python
import numpy as np
```

## Vector operations

```python
u = np.array([2, 4, 5, 6])
```

```python
2 * u
```

```python
v = np.array([1, 0, 0, 2])
```

```python
u + v
```

```python
u * v
```

## Multiplication

```python
v.shape[0]
```

```python
def vector_vector_multiplication(u, v):
    assert u.shape[0] == v.shape[0]
    
    n = u.shape[0]
    
    result = 0.0

    for i in range(n):
        result = result + u[i] * v[i]
    
    return result
```

```python
vector_vector_multiplication(u, v)
```

```python
u.dot(v)
```

```python
U = np.array([
    [2, 4, 5, 6],
    [1, 2, 1, 2],
    [3, 1, 2, 1],
])
```

```python
U.shape
```

```python
def matrix_vector_multiplication(U, v):
    assert U.shape[1] == v.shape[0]
    
    num_rows = U.shape[0]
    
    result = np.zeros(num_rows)
    
    for i in range(num_rows):
        result[i] = vector_vector_multiplication(U[i], v)
    
    return result
```

```python
matrix_vector_multiplication(U, v)
```

```python
U.dot(v)
```

```python
V = np.array([
    [1, 1, 2],
    [0, 0.5, 1], 
    [0, 2, 1],
    [2, 1, 0],
])
```

```python
def matrix_matrix_multiplication(U, V):
    assert U.shape[1] == V.shape[0]
    
    num_rows = U.shape[0]
    num_cols = V.shape[1]
    
    result = np.zeros((num_rows, num_cols))
    
    for i in range(num_cols):
        vi = V[:, i]
        Uvi = matrix_vector_multiplication(U, vi)
        result[:, i] = Uvi
    
    return result
```

```python
matrix_matrix_multiplication(U, V)
```

```python
U.dot(V)
```

## Identity matrix

```python
I = np.eye(3)
```

```python
V
```

```python
V.dot(I)
```

## Inverse

```python
Vs = V[[0, 1, 2]]
Vs
```

```python
Vs_inv = np.linalg.inv(Vs)
Vs_inv
```

```python
Vs_inv.dot(Vs)
```

### Next 

Intro to Pandas

```python

```
