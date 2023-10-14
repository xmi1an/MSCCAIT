# Practical-13.md

## Artificial Intelligence with ML

### Practical Program 13

Given a dataset for classification task. Write a program to implement Support Vector Machine and estimate its test performance.

```python
from sklearn import svm
from sklearn.model_selection import train_test_split
from sklearn.metrics import accuracy_score

# Load the dataset
# Replace 'dataset.csv' with the actual filename of your dataset
dataset = pd.read_csv('dataset.csv')

# Split the dataset into features and labels
X = dataset.iloc[:, :-1]
y = dataset.iloc[:, -1]

# Split the dataset into training and testing sets
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

# Create the SVM classifier
clf = svm.SVC()

# Train the classifier
clf.fit(X_train, y_train)

# Predict the labels for the test set
y_pred = clf.predict(X_test)

# Calculate the accuracy of the classifier
accuracy = accuracy_score(y_test, y_pred)

# Print the accuracy
print("Accuracy:", accuracy)
```
