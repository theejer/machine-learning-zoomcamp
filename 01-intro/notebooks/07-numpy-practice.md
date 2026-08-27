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

## 1.7 Introduction to NumPy — Practice

Work through each exercise from memory before running it. If you get stuck, peek at the corresponding
section in the solution notebook: `07-numpy.ipynb` (same folder).

Plan:

* Creating arrays
* Multi-dimensional arrays
* Randomly generated arrays
* Element-wise operations
    * Comparison operations
    * Logical operations
* Summarizing operations

```python jupyter={"is_executing": false}
# Import numpy under its usual alias
import numpy as np
```

## Creating arrays

1. Create an array of 10 zeros.
2. Create an array of 10 ones.
3. Create an array of 10 elements, all equal to `2.5`, using a single function call (not multiplication).
4. Create the array `[1, 2, 3, 5, 7, 12]` from a Python list, then overwrite the element at index 2 with `10`.
5. Create an array with integers from 3 up to (but not including) 10 using a range-style function.
6. Create an array of 11 evenly spaced numbers between 0 and 100 (inclusive).

```python jupyter={"is_executing": false}
# 1. array of 10 zeros
np.zeros(10)

```

```python
# 2. array of 10 ones
np.ones(10)
```

```python jupyter={"is_executing": false}
# 3. array of 10 elements all equal to 2.5
np.full(10, 2.5)
```

```python jupyter={"is_executing": false}
# 4. create array, then set index 2 to 10
a = None
a = np.arange(3,11, 2)
a[2:]
```

```python jupyter={"is_executing": false}
# 5. integers from 3 up to (not including) 10
np.arange(3,10)
```

```python jupyter={"is_executing": false}
# 6. 11 evenly spaced numbers between 0 and 100

np.linspace(0, 100, 11)
```

## Multi-dimensional arrays

1. Create a 5x2 array of zeros.
2. Create the 3x3 array `[[1,2,3],[4,5,6],[7,8,9]]`.
3. Set the element at row 0, column 1 to `20`.
4. Replace the entire row at index 2 with `[1, 1, 1]`.
5. Replace the entire column at index 2 with `[0, 1, 2]`.
6. Print the final array and check it matches what you expected.

```python jupyter={"is_executing": false}
# 1. 5x2 array of zeros
np.zeros((5, 2))
```

```python jupyter={"is_executing": false}
# 2. build n
n = None
n = np.array([
	np.arange(1,4),
	np.linspace(4,6,3),
	np.arange(7,10)
])
n
```

```python jupyter={"is_executing": false}
# 3. n[0, 1] = 20
n[0,1] = 20
n
```

```python jupyter={"is_executing": false}
# 4. replace row 2 with [1, 1, 1]
n[2,:] = [1,1,1]
n
```

```python jupyter={"is_executing": false}
# 5. replace column 2 with [0, 1, 2]
n[:, 2] = [0,1,2]
```

```python jupyter={"is_executing": false}
# 6. print n
n
```

## Randomly generated arrays

1. Seed the random generator with `2`, then generate a 5x2 array of random numbers in `[0, 100)` using `np.random.rand`.
2. Re-seed with `2`, then generate a 5x2 array of standard-normal samples with `np.random.randn`.
3. Re-seed with `2`, then generate a 5x2 array of random integers between 0 and 100 (exclusive) with `np.random.randint`.
4. Without re-running the seed, what happens if you call `np.random.rand(5, 2)` again? Try it and think about why.

```python jupyter={"is_executing": false}
# 1. seeded rand, scaled to [0, 100)
n = np.random.rand(5, 2)
n * 100
```

```python jupyter={"is_executing": false}
# 2. seeded randn
n = np.random.randn(5, 2)
n * 100
```

```python jupyter={"is_executing": false}
# 3. seeded randint
n = np.random.randint(low=0, high=10000, size=(5,2))
n
```

```python
# 4. call rand again without reseeding - observe/explain

```

## Element-wise operations

1. Create `a = np.arange(5)`.
2. Compute `b = (10 + (a * 2)) ** 2 / 100`.
3. Compute `a / b + 10`.

### Comparison operations

4. Compute the boolean array `a >= 2`.
5. Compute the boolean array `a > b`.
6. Use boolean indexing to select only the elements of `a` where `a > b`.

### Logical operations

7. Using `a` and `b` from above, build a boolean mask that is `True` where `a > 1` **and** `b < 3`, and use it to filter `a`. (Hint: `&`, or `np.logical_and`.)
8. Build a mask that is `True` where `a == 0` **or** `a == 4`, and use it to filter `a`.

```python
# 1-3. a, b, a / b + 10
a = None
b = None

```

```python
# 4-6. comparisons and boolean indexing

```

```python
# 7. AND mask

```

```python
# 8. OR mask

```

## Summarizing operations

Using `a` from before:

1. Compute the standard deviation of `a`.
2. Compute the mean and sum of `a`.
3. Using `n` from the multi-dimensional section, compute its minimum and maximum.
4. Bonus: compute the min of `n` along each axis separately (`axis=0` and `axis=1`) and explain the difference in your own words.

```python
# 1-2. std, mean, sum of a

```

```python
# 3. min/max of n

```

```python
# 4. bonus: axis=0 vs axis=1

```

### Next

Linear algebra refresher — practice in `08-linear-algebra-practice.ipynb`.
