# Practical-05.md

## Artificial Intelligence with ML

### Practical Program 5

Basic exercises on Python Machine Learning Packages such as Numpy, Scikit, and Matplotlib. Given a dataset, write a program to compute the Covariance, Correlation between a pair of attributes. Also, compute the Covariance Matrix and Correlation Matrix.

```python
import numpy as np
import pandas as pd

# Load the dataset
dataset = pd.read_csv('dataset.csv')

# Compute the Covariance between two attributes
attribute1 = dataset['attribute1']
attribute2 = dataset['attribute2']
covariance = np.cov(attribute1, attribute2)[0][1]

# Compute the Correlation between two attributes
correlation = np.corrcoef(attribute1, attribute2)[0][1]

# Compute the Covariance Matrix
covariance_matrix = np.cov(dataset.T)

# Compute the Correlation Matrix
correlation_matrix = np.corrcoef(dataset.T)

# Print the results
print("Covariance between attribute1 and attribute2:", covariance)
print("Correlation between attribute1 and attribute2:", correlation)
print("Covariance Matrix:")
print(covariance_matrix)
print("Correlation Matrix:")
print(correlation_matrix)
```
