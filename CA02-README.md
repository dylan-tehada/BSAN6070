# CA01-Naive Bayes Assignment

## Environment Used
Jupyter Notebook

## Installation
Download the [Data.zip](./mnt/data/Data.zip) file to access training and testing files.

## Packages Used
```python
import os
import numpy as np
from collections import Counter
from sklearn.naive_bayes import MultinomialNB
from sklearn.metrics import accuracy_score, confusion_matrix, classification_report
```

## Steps to Run Model
1. **Create a function named `make_Dictionary`** that creates a dictionary of the 3000 most common words and their corresponding frequencies.
2. **Create a function named `extract_features`** that returns a matrix where each row represents an email, and each column represents a word from the dictionary.
3. **Input the folder paths** for the train emails and the test emails and assign them to `TRAIN_DIR` and `TEST_DIR` respectively.
4. **Use the `make_Dictionary` function** on the training email dataset to create a dictionary of all the words in those emails.
5. **Use sklearn to initialize** the multinomial Naïve Bayes model.
6. **Train the model** on the training data.
7. **Make predictions** based on the trained model.
8. **Evaluate the predictions** of the trained model by generating an accuracy percentage.
