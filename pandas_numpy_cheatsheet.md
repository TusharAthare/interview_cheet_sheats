
# Pandas and NumPy Q&A Cheatsheet for SDE-2 Interview

## Pandas

### Q1: How do you create a DataFrame from a dictionary?
```python
import pandas as pd

data = {'Name': ['Alice', 'Bob'], 'Age': [25, 30]}
df = pd.DataFrame(data)
print(df)
```

### Q2: How do you handle missing data in a DataFrame?
```python
# Fill missing values
df.fillna(value, inplace=True)

# Drop rows/columns with missing values
df.dropna(axis=0, inplace=True)  # axis=0 for rows, axis=1 for columns

# Check for missing values
df.isnull().sum()
```

### Q3: How do you filter rows in a DataFrame?
```python
filtered_df = df[df['Age'] > 25]
print(filtered_df)
```

### Q4: How do you group data and perform aggregation?
```python
grouped = df.groupby('Category').agg({'Sales': 'sum', 'Profit': 'mean'})
print(grouped)
```

### Q5: How do you merge two DataFrames?
```python
df1 = pd.DataFrame({'ID': [1, 2], 'Name': ['Alice', 'Bob']})
df2 = pd.DataFrame({'ID': [1, 2], 'Age': [25, 30]})

merged = pd.merge(df1, df2, on='ID')
print(merged)
```

### Q6: How do you apply a custom function to a column?
```python
df['New_Column'] = df['Age'].apply(lambda x: x * 2)
```

### Q7: What is the difference between `loc` and `iloc`?
- `loc`: Access rows/columns by labels or conditions.
- `iloc`: Access rows/columns by integer positions.

```python
# Using loc
print(df.loc[0, 'Name'])

# Using iloc
print(df.iloc[0, 1])
```

### Q8: How do you pivot a DataFrame?
```python
pivot = df.pivot_table(values='Sales', index='Region', columns='Product', aggfunc='sum')
print(pivot)
```

## NumPy

### Q1: How do you create an array and perform basic operations?
```python
import numpy as np

arr = np.array([1, 2, 3])
print(arr + 2)
```

### Q2: How do you create special types of arrays?
```python
zeros = np.zeros((2, 2))
ones = np.ones((2, 2))
identity = np.eye(3)
```

### Q3: How do you perform element-wise operations?
```python
arr1 = np.array([1, 2, 3])
arr2 = np.array([4, 5, 6])

result = arr1 + arr2
print(result)
```

### Q4: How do you calculate statistics on an array?
```python
arr = np.array([1, 2, 3, 4])

mean = np.mean(arr)
std_dev = np.std(arr)
sum_total = np.sum(arr)
```

### Q5: How do you reshape or flatten an array?
```python
arr = np.array([[1, 2], [3, 4]])

# Reshape
reshaped = arr.reshape((4, 1))

# Flatten
flattened = arr.flatten()
```

### Q6: How do you index and slice arrays?
```python
arr = np.array([[1, 2, 3], [4, 5, 6]])

# Indexing
print(arr[0, 1])  # Output: 2

# Slicing
print(arr[:, 1])  # Output: [2, 5]
```

### Q7: How do you handle missing data in NumPy arrays?
```python
arr = np.array([1, 2, np.nan, 4])

# Replace NaN with a value
arr = np.nan_to_num(arr, nan=0)

# Check for NaN values
print(np.isnan(arr))
```

### Q8: How do you perform matrix multiplication?
```python
matrix1 = np.array([[1, 2], [3, 4]])
matrix2 = np.array([[5, 6], [7, 8]])

result = np.dot(matrix1, matrix2)
print(result)
```

### Q9: What are broadcasting rules in NumPy?
Broadcasting allows operations on arrays of different shapes.
```python
arr1 = np.array([1, 2, 3])
arr2 = np.array([[1], [2], [3]])

result = arr1 + arr2
print(result)
```

### Q10: How do you generate random numbers in NumPy?
```python
random_arr = np.random.rand(3, 2)  # Uniform distribution
normal_arr = np.random.randn(3, 2)  # Normal distribution
```

---

Use these Q&As to review key Pandas and NumPy concepts for interviews. Practice these with variations to ensure confidence.
