# Practical-06.md

## Artificial Intelligence with ML

### Practical Program 6

Given a set of sample points in an N-dimensional feature space, write a program to fit the points with a hyperplane using Linear Regression. Calculate the sum of the residual error.

```python
import numpy as np

def linear_regression(X, y):
    # Add a column of ones to X for the intercept term
    X = np.c_[np.ones(X.shape[0]), X]

    # Calculate the coefficients using the normal equation
    coefficients = np.linalg.inv(X.T.dot(X)).dot(X.T).dot(y)

    # Calculate the predicted values
    y_pred = X.dot(coefficients)

    # Calculate the residual error
    residual_error = np.sum((y - y_pred) ** 2)

    return coefficients, residual_error

# Sample points
X = np.array([[1, 2], [3, 4], [5, 6]])
y = np.array([3, 5, 7])

# Fit the points with a hyperplane using Linear Regression
coefficients, residual_error = linear_regression(X, y)

print("Coefficients:", coefficients)
print("Residual Error:", residual_error)
```
