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

<!-- #region -->
# Machine Learning Zoomcamp


## 1.7 Introduction to NumPy


Plan:

* Creating arrays
* Multi-dimensional arrays
* Randomly generated arrays
* Element-wise operations
    * Comparison operations
    * Logical operations
* Summarizing operations
<!-- #endregion -->

```python jupyter={"is_executing": false}
import numpy as np
```

```python jupyter={"is_executing": false}
np
```

## Creating arrays


```python
np.zeros(10)
```

```python
np.ones(10)
```

```python
np.full(10, 2.5)
```

```python
a = np.array([1, 2, 3, 5, 7, 12])
a
```

```python
a[2] = 10
```

```python
a
```

```python
np.arange(3, 10)
```

```python
np.linspace(0, 100, 11)
```

## Multi-dimensional arrays


```python
np.zeros((5, 2))
```

```python jupyter={"is_executing": false}
n = np.array([
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
])
n
```

```python
n[0, 1] = 20
```

```python
n
```

```python
n[2] = [1, 1, 1]
```

```python
n
```

```python
n[:, 2] = [0, 1, 2]
```

```python
n
```

## Randomly generated arrays


```python
np.random.seed(2)
100 * np.random.rand(5, 2)
```

```python
np.random.seed(2)
np.random.randn(5, 2)
```

```python
np.random.seed(2)
np.random.randint(low=0, high=100, size=(5, 2))
```

## Element-wise operations


```python
a = np.arange(5)
a
```

```python
b = (10 + (a * 2)) ** 2 / 100
```

```python
b
```

```python
a / b + 10
```

## Comparison operations

```python
a
```

```python
a >= 2
```

```python
b
```

```python
a > b
```

```python
a[a > b]
```

## Summarizing operations

```python
a
```

```python
a.std()
```

```python
n.min()
```

### Next

Linear algebra refresher
