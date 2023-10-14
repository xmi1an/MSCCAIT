# Practical-10.md

## Artificial Intelligence with ML

### Practical Program 10

Write a program to implement feature reduction using Principle Component Analysis.

```python
import numpy as np
from sklearn.decomposition import PCA

def feature_reduction(data, n_components):
    pca = PCA(n_components=n_components)
    reduced_data = pca.fit_transform(data)
    return reduced_data

# Example usage
data = np.array([[1, 2, 3], [4, 5, 6], [7, 8, 9]])
reduced_data = feature_reduction(data, n_components=2)
print(reduced_data)
```

In this program, we first import the necessary libraries: `numpy` and `sklearn.decomposition.PCA`.

Then, we define a function `feature_reduction` that takes in the data and the number of components to reduce to. Inside the function, we create an instance of the `PCA` class with the specified number of components. We then use the `fit_transform` method to perform the dimensionality reduction on the data.

Finally, we demonstrate the usage of the `feature_reduction` function with an example dataset. We create a numpy array `data` with three samples, each having three features. We then call the `feature_reduction` function with `n_components=2` to reduce the dimensionality to two components. The reduced data is stored in the `reduced_data` variable, which is then printed.

This program demonstrates how to use Principle Component Analysis (PCA) for feature reduction. PCA is a technique used to reduce the dimensionality of high-dimensional data while preserving most of the information. It achieves this by finding the principal components, which are linear combinations of the original features that capture the most variance in the data.

Note: The example usage provided is for illustration purposes only. In practice, you would typically use a real dataset for feature reduction.
