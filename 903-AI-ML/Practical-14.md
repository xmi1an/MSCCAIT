# Practical-14.md

## Artificial Intelligence with ML

### Practical Program 14

Write a program to implement K means clustering algorithm. Select your own dataset to test the program.

```python
import numpy as np
from sklearn.cluster import KMeans
import matplotlib.pyplot as plt

# Generate random data
np.random.seed(0)
X = np.random.rand(100, 2)

# Perform K-means clustering
kmeans = KMeans(n_clusters=3, random_state=0)
kmeans.fit(X)

# Get cluster labels and centroids
labels = kmeans.labels_
centroids = kmeans.cluster_centers_

# Plot the data points and centroids
plt.scatter(X[:, 0], X[:, 1], c=labels)
plt.scatter(centroids[:, 0], centroids[:, 1], marker='x', color='red')
plt.xlabel('Feature 1')
plt.ylabel('Feature 2')
plt.title('K-means Clustering')
plt.show()
```

In this program, we first generate a random dataset with 100 data points and 2 features. We then perform K-means clustering with 3 clusters using the `KMeans` class from the `sklearn.cluster` module. The `fit` method is used to fit the model to the data and find the cluster labels and centroids. Finally, we plot the data points with different colors representing different clusters, and the centroids are marked with red crosses.

You can select your own dataset and modify the number of clusters according to your needs.

