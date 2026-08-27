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

## 1.9 Introduction to Pandas

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
import numpy as np
import pandas as pd
```

## DataFrames

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

```python
df = pd.DataFrame(data, columns=columns)
```

```python
df
```

```python
data = [
    {
        "Make": "Nissan",
        "Model": "Stanza",
        "Year": 1991,
        "Engine HP": 138.0,
        "Engine Cylinders": 4,
        "Transmission Type": "MANUAL",
        "Vehicle_Style": "sedan",
        "MSRP": 2000
    },
    {
        "Make": "Hyundai",
        "Model": "Sonata",
        "Year": 2017,
        "Engine HP": None,
        "Engine Cylinders": 4,
        "Transmission Type": "AUTOMATIC",
        "Vehicle_Style": "Sedan",
        "MSRP": 27150
    },
    {
        "Make": "Lotus",
        "Model": "Elise",
        "Year": 2010,
        "Engine HP": 218.0,
        "Engine Cylinders": 4,
        "Transmission Type": "MANUAL",
        "Vehicle_Style": "convertible",
        "MSRP": 54990
    },
    {
        "Make": "GMC",
        "Model": "Acadia",
        "Year": 2017,
        "Engine HP": 194.0,
        "Engine Cylinders": 4,
        "Transmission Type": "AUTOMATIC",
        "Vehicle_Style": "4dr SUV",
        "MSRP": 34450
    },
    {
        "Make": "Nissan",
        "Model": "Frontier",
        "Year": 2017,
        "Engine HP": 261.0,
        "Engine Cylinders": 6,
        "Transmission Type": "MANUAL",
        "Vehicle_Style": "Pickup",
        "MSRP": 32340
    }
]
```

```python
df = pd.DataFrame(data)
df
```

```python
df.head(n=2)
```

```python

```

## Series

```python
df.Engine HP
```

```python
df['Engine HP']
```

```python
df[['Make', 'Model', 'MSRP']]
```

```python
df['id'] = [1, 2, 3, 4, 5]
```

```python
df['id'] = [10, 20, 30, 40, 50]
```

```python
df
```

```python
del df['id']
```

```python
df
```

## Index


```python
df.index
```

```python
df.Make.index
```

```python
df.index = ['a', 'b', 'c', 'd', 'e']
```

```python
df
```

```python
df.iloc[[1, 2, 4]]
```

```python
df = df.reset_index(drop=True)
```

```python
df
```

## Accessing elements

```python

```

## Element-wise operations

```python
df['Engine HP'] * 2
```

```python
df['Year'] >= 2015
```

## Filtering

```python
df[
    df['Make'] == 'Nissan'
]
```

```python
df[
    (df['Make'] == 'Nissan') & (df['Year'] >= 2015)
]
```

## String operations

```python
'machine learning zoomcamp'.replace(' ', '_')
```

```python
df['Vehicle_Style'].str.lower()
```

```python
df['Vehicle_Style'] = df['Vehicle_Style'].str.replace(' ', '_').str.lower()
```

```python
df
```

## Summarizing operations

```python
df.describe().round(2)
```

```python
df.nunique()
```

## Missing values


```python
df.isnull().sum()
```

## Grouping



```
SELECT 
    transmission_type,
    AVG(MSRP)
FROM
    cars
GROUP BY
    transmission_type
```

```python
df.groupby('Transmission Type').MSRP.max()
```

## Getting the NumPy arrays

```python
df.MSRP.values
```

```python
df.to_dict(orient='records')
```

```python

```
