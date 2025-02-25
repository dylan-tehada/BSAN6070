# Decision Tree Model Assignment

## Packages Used
The following packages need to be installed and imported to run the notebook:
```python
import pandas as pd
import numpy as np
from autoviz.AutoViz_Class import AutoViz_Class
from sklearn.preprocessing import LabelEncoder
from sklearn.tree import DecisionTreeClassifier
import graphviz
```

## Explanation of the Assignment
This assignment involves training a decision tree model to make predictions based on a dataset containing attributes such as education, income, and occupation. The goal is to build, evaluate, and fine-tune the model for optimal performance.

## Steps to Complete the Assignment

### 1. Data Source and Contents
- Upload the census data CSV file: [census_data.csv](https://github.com/ArinB/MSBA-CA-03-Decision-Trees/blob/master/census_data.csv?raw=true)
- Inspect the dataset for its structure and characteristics

### 2. Data Quality Analysis
```python
# Using AutoViz to generate a data quality report
AV = AutoViz_Class()
report = AV.AutoViz(filename="", dfte=df)
# Identifying missing values
print(df.isnull().sum())
```

### 3. Build Decision Tree Classifier Models
```python
# Encode categorical variables
encoder = LabelEncoder()
for col in X.columns:
    X[col] = encoder.fit_transform(X[col])

# Split dataset into training and test subsets
x_train = X[df['flag'] == 'train']
y_train = y[df['flag'] == 'train']
x_test = X[df['flag'] == 'test']
y_test = y[df['flag'] == 'test']

# Train decision tree model
model = DecisionTreeClassifier(max_depth=10)
model.fit(x_train, y_train)
```

### 4. Evaluate Decision Tree Performance
```python
from sklearn.metrics import confusion_matrix, accuracy_score, precision_score, recall_score, f1_score

# Predictions
y_pred = model.predict(x_test)

# Evaluation metrics
print("Accuracy:", accuracy_score(y_test, y_pred))
print("Precision:", precision_score(y_test, y_pred, average='weighted'))
print("Recall:", recall_score(y_test, y_pred, average='weighted'))
print("F1 Score:", f1_score(y_test, y_pred, average='weighted'))
```

### 5. Tune Decision Tree Performance
- Train the model multiple times with different hyperparameters
- Compare results to select the best-performing tree

### 6. Visualize Your Best Decision Tree using GraphViz
```python
from sklearn.tree import export_graphviz

dot_data = export_graphviz(model, out_file=None, feature_names=X.columns, class_names=['0', '1'], filled=True)
graph = graphviz.Source(dot_data)
graph.render("decision_tree")
```

### 7. Conclusion
- Summarize insights and key takeaways from the trained model

### 8. Prediction using Your Trained Decision Tree Model
```python
# Example prediction
sample_data = np.array([[3, 1, 2, 0]])  # Replace with actual values
prediction = model.predict(sample_data)
prediction_proba = model.predict_proba(sample_data)

print("Predicted Class:", prediction)
print("Prediction Probabilities:", prediction_proba)
```
