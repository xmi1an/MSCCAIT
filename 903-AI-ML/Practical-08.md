# Practical-08.md

## Artificial Intelligence with ML

### Practical Program 8

Write a program to demonstrate the working of the decision tree based ID3 algorithm. Use an appropriate data set for building the decision tree and apply this knowledge to classify a new sample.

```python
import pandas as pd
from sklearn.tree import DecisionTreeClassifier
from sklearn.model_selection import train_test_split
from sklearn.metrics import accuracy_score

# Load the dataset
data = pd.read_csv("dataset.csv")

# Split the dataset into features and target variable
X = data.drop('target', axis=1)
y = data['target']

# Split the dataset into training and testing sets
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

# Create a decision tree classifier
clf = DecisionTreeClassifier()

# Train the classifier on the training data
clf.fit(X_train, y_train)

# Predict the target variable for the testing data
y_pred = clf.predict(X_test)

# Calculate the accuracy of the classifier
accuracy = accuracy_score(y_test, y_pred)
print("Accuracy:", accuracy)
```

In this program, we first load the dataset from a CSV file using the pandas library. Then, we split the dataset into features (X) and the target variable (y). Next, we split the dataset into training and testing sets using the train_test_split function from the sklearn.model_selection module.

We create a decision tree classifier using the DecisionTreeClassifier class from the sklearn.tree module. We then train the classifier on the training data using the fit method.

After training the classifier, we use it to predict the target variable for the testing data using the predict method. Finally, we calculate the accuracy of the classifier by comparing the predicted target variable with the actual target variable using the accuracy_score function from the sklearn.metrics module.

Note: Replace "dataset.csv" with the actual filename of your dataset.
