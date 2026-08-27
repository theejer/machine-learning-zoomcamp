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

## 1.8 Linear algebra refresher — Practice

Work through each exercise before checking the solution notebook: `08-linear-algebra.ipynb` (same folder).

Plan:

* Vector operations
* Multiplication
    * Vector-vector multiplication
    * Matrix-vector multiplication
    * Matrix-matrix multiplication
* Identity matrix
* Inverse

```python
# Import numpy

```

## Vector operations

1. Create `u = np.array([2, 4, 5, 6])`.
2. Compute `2 * u` — what operation does this correspond to mathematically?
3. Create `v = np.array([1, 0, 0, 2])`.
4. Compute `u + v`.
5. Compute `u * v` (element-wise). Note this is *not* the dot product — keep that distinction in mind for the next section.

```python
# 1-5. vector operations
u = None
v = None

```

## Multiplication

### Vector-vector multiplication

1. Write your own `vector_vector_multiplication(u, v)` function using a `for` loop (don't use `.dot()` inside it).
   It should assert the shapes match, then return the dot product as a float.
2. Test it on `u` and `v` above.
3. Confirm your result matches `u.dot(v)`.

```python
def vector_vector_multiplication(u, v):
    # TODO: assert shapes match, loop over elements, accumulate the sum
    pass

```

```python
# test against u.dot(v)

```

<!-- #region -->
### Matrix-vector multiplication

1. Create the matrix:

```python
U = np.array([
    [2, 4, 5, 6],
    [1, 2, 1, 2],
    [3, 1, 2, 1],
])
```

2. Check `U.shape` and reason about which dimension must match `v`'s length.
3. Write `matrix_vector_multiplication(U, v)` that reuses your `vector_vector_multiplication` function — loop over the rows of `U`, computing one dot product per row.
4. Test it against `U.dot(v)`.
<!-- #endregion -->

```python
U = None

```

```python
def matrix_vector_multiplication(U, v):
    # TODO: assert shapes match, loop over rows, reuse vector_vector_multiplication
    pass

```

```python
# test against U.dot(v)

```

<!-- #region -->
### Matrix-matrix multiplication

1. Create the matrix:

```python
V = np.array([
    [1, 1, 2],
    [0, 0.5, 1],
    [0, 2, 1],
    [2, 1, 0],
])
```

2. Write `matrix_matrix_multiplication(U, V)` that reuses `matrix_vector_multiplication` — loop over the columns of `V`, treating each column as a vector to multiply against `U`.
3. Test it against `U.dot(V)`.
<!-- #endregion -->

```python
V = None

```

```python
def matrix_matrix_multiplication(U, V):
    # TODO: assert shapes match, loop over columns of V, reuse matrix_vector_multiplication
    pass

```

```python
# test against U.dot(V)

```

## Identity matrix

1. Create a 3x3 identity matrix `I` with `np.eye`.
2. Multiply `V.dot(I)` and confirm it returns `V` unchanged. Explain in your own words why that must be true.

```python
# identity matrix check

```

## Inverse

1. Take the first three rows of `V` (call it `Vs`) so it's square.
2. Compute its inverse with `np.linalg.inv`.
3. Multiply the inverse by `Vs` and confirm you get (approximately) the identity matrix.
4. Bonus: what would happen if you tried to invert a non-square matrix, or a square matrix that isn't invertible? You don't need to run it — just reason about it, then verify with a quick experiment if you like.

```python
# Vs, Vs_inv, and the identity check

```

### Next

Intro to Pandas — practice in `09-pandas-practice.ipynb`.
