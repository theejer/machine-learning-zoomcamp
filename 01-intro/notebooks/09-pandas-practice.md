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

## 1.9 Introduction to Pandas — Practice

Work through each exercise before checking the solution notebook: `09-pandas.ipynb` (same folder).

Plan:

* Data Frames
* Series
* Index
* Accessing elements
* Element-wise operations
* Filtering
* String operations
* Summarizing operations
* Missing values
* Grouping
* Getting the NumPy arrays

```python
# Import numpy and pandas

```

<!-- #region -->
## DataFrames

1. Build a DataFrame from this list-of-lists plus a `columns` list, exactly as the raw data below implies:

```python
data = [
    ['Nissan', 'Stanza', 1991, 138, 4, 'MANUAL', 'sedan', 2000],
    ['Hyundai', 'Sonata', 2017, None, 4, 'AUTOMATIC', 'Sedan', 27150],
    ['Lotus', 'Elise', 2010, 218, 4, 'MANUAL', 'convertible', 54990],
    ['GMC', 'Acadia',  2017, 194, 4, 'AUTOMATIC', '4dr SUV', 34450],
    ['Nissan', 'Frontier', 2017, 261, 6, 'MANUAL', 'Pickup', 32340],
]

columns = [
    'Make', 'Model', 'Year', 'Engine HP', 'Engine Cylinders',
    'Transmission Type', 'Vehicle_Style', 'MSRP'
]
```

2. Now build the *same* DataFrame from a list of dictionaries instead (one dict per row, keys matching the column names). Confirm the two approaches give equivalent DataFrames.
3. Display just the first 2 rows.
<!-- #endregion -->

```python
# 1. build df from list-of-lists + columns

```

```python
# 2. build df from list of dicts

```

```python
# 3. first 2 rows

```

## Series

1. Try accessing the `Engine HP` column with dot notation (`df.Engine HP`). It will fail — why? Fix it using bracket notation.
2. Select just the `Make`, `Model`, and `MSRP` columns as a new DataFrame.
3. Add a new column `id` with values `[1, 2, 3, 4, 5]`, then overwrite it with `[10, 20, 30, 40, 50]`.
4. Delete the `id` column.

```python
# 1. dot notation failure + bracket fix

```

```python
# 2. select Make, Model, MSRP

```

```python
# 3. add then overwrite id column

```

```python
# 4. delete id column

```

## Index

1. Check `df.index` and `df.Make.index` — what do you notice about them?
2. Set a custom index: `['a', 'b', 'c', 'd', 'e']`.
3. Use `.iloc` to select the rows at positions 1, 2, and 4 (regardless of the custom labels).
4. Reset the index back to a default `RangeIndex`, dropping the old labels.

```python
# 1. inspect indexes

```

```python
# 2. custom index

```

```python
# 3. iloc[[1, 2, 4]]

```

```python
# 4. reset_index(drop=True)

```

## Accessing elements

1. Using `.iloc`, grab the single value at row position 0, column position 1.
2. Using `.loc`, grab the `Model` value for whichever row label corresponds to `Nissan Frontier`.

```python
# 1-2. iloc / loc single-value access

```

## Element-wise operations

1. Compute `df['Engine HP'] * 2`.
2. Compute the boolean Series `df['Year'] >= 2015`.

```python
# 1-2. element-wise ops

```

## Filtering

1. Filter the DataFrame to rows where `Make == 'Nissan'`.
2. Filter to rows where `Make == 'Nissan'` **and** `Year >= 2015` (remember to parenthesize each condition and use `&`, not `and`).

```python
# 1. Make == 'Nissan'

```

```python
# 2. Make == 'Nissan' & Year >= 2015

```

## String operations

1. Lowercase the `Vehicle_Style` column using `.str.lower()` (don't assign it yet — just view the result).
2. Now permanently replace spaces with underscores **and** lowercase everything in `Vehicle_Style`, assigning it back to the column.

```python
# 1. preview lowercased Vehicle_Style

```

```python
# 2. replace spaces + lowercase, assign back

```

## Summarizing operations

1. Run `.describe()` on the whole DataFrame and round to 2 decimals.
2. Compute `.nunique()` for every column.

```python
# 1. describe().round(2)

```

```python
# 2. nunique()

```

## Missing values

1. Count how many missing values are in each column.

```python
# 1. isnull().sum()

```

<!-- #region -->
## Grouping

1. This SQL query finds the average MSRP per transmission type:

```sql
SELECT
    transmission_type,
    AVG(MSRP)
FROM
    cars
GROUP BY
    transmission_type
```

Write the pandas equivalent using `.groupby(...).MSRP.mean()`.

2. Bonus: also compute the **max** MSRP per transmission type.
<!-- #endregion -->

```python
# 1. groupby mean

```

```python
# 2. bonus: groupby max

```

## Getting the NumPy arrays

1. Get the `MSRP` column as a plain NumPy array.
2. Convert the entire DataFrame to a list of dictionaries, one per record.

```python
# 1. MSRP.values

```

```python
# 2. to_dict(orient='records')

```
