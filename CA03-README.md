# Decision Tree Model Assignment

## Packages Used
The following packages need to be installed and imported to run the notebook:
- `pandas` - for data manipulation and analysis
- `numpy` - for numerical operations
- `autoviz` - for automated exploratory data analysis
- `sklearn.preprocessing` (LabelEncoder) - for encoding categorical variables
- `sklearn.tree` (DecisionTreeClassifier) - for training and evaluating decision tree models
- `graphviz` - for visualizing the decision tree

## Explanation of the Assignment
This assignment involves training a decision tree model to make predictions based on a dataset containing attributes such as education, income, and occupation. The goal is to build, evaluate, and fine-tune the model for optimal performance.

## Steps to Complete the Assignment

### 1. Data Source and Contents
- Upload the census data CSV file: [census_data.csv](https://github.com/ArinB/MSBA-CA-03-Decision-Trees/blob/master/census_data.csv?raw=true)
- Inspect the dataset for its structure and characteristics

### 2. Data Quality Analysis
- Use AutoViz to generate a data quality report
- Identify and address any missing data

### 3. Build Decision Tree Classifier Models
- Prepare the dataset by encoding categorical values
- Split the dataset into feature and target variables
- Divide the dataset into training and test subsets
- Train a decision tree model using `sklearn.tree.DecisionTreeClassifier` with given hyperparameters
- Make predictions using the trained model

### 4. Evaluate Decision Tree Performance
- Generate a confusion matrix visualization
- Compute and display accuracy, precision, recall, and F1 scores

### 5. Tune Decision Tree Performance
- Train the model multiple times with different hyperparameters
- Compare results to select the best-performing tree

### 6. Visualize Your Best Decision Tree using GraphViz
- Use `graphviz` to visualize the decision tree with the highest accuracy

### 7. Conclusion
- Summarize insights and key takeaways from the trained model

### 8. Prediction using Your Trained Decision Tree Model
- Make a prediction based on a set of predetermined feature values
- Calculate probabilities for each predicted outcome
