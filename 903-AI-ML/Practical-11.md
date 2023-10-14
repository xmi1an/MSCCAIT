# Practical-11.md

## Artificial Intelligence with ML

### Practical Program 11

Study and Implement various Ensemble method of classifier: Bagging, Boosting, Stacking.

```python
# Bagging
from sklearn.ensemble import BaggingClassifier
from sklearn.tree import DecisionTreeClassifier

# Create a base classifier
base_classifier = DecisionTreeClassifier()

# Create a bagging classifier
bagging_classifier = BaggingClassifier(base_classifier, n_estimators=10)

# Fit the bagging classifier on the training data
bagging_classifier.fit(X_train, y_train)

# Boosting
from sklearn.ensemble import AdaBoostClassifier

# Create a base classifier
base_classifier = DecisionTreeClassifier()

# Create an AdaBoost classifier
boosting_classifier = AdaBoostClassifier(base_classifier, n_estimators=10)

# Fit the boosting classifier on the training data
boosting_classifier.fit(X_train, y_train)

# Stacking
from sklearn.ensemble import StackingClassifier
from sklearn.linear_model import LogisticRegression

# Create a list of base classifiers
base_classifiers = [('classifier1', DecisionTreeClassifier()), ('classifier2', RandomForestClassifier())]

# Create a stacking classifier
stacking_classifier = StackingClassifier(estimators=base_classifiers, final_estimator=LogisticRegression())

# Fit the stacking classifier on the training data
stacking_classifier.fit(X_train, y_train)
```
