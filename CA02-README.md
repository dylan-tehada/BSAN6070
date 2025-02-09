# Naïve Bayes Email Classification

## Environment Used
Jupyter Notebook

## Installation
Download the [Data.zip](https://brightspace.lmu.edu/d2l/le/content/268149/viewContent/3385848/View) file to access training and testing files.

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

## Understanding the Defined Functions

### `make_Dictionary`
The function requires one input, `root_dir`. It begins by creating an empty list titled `all_words`, which captures all words in the email files. Using `os.path.join` and a `for` loop, it iterates through and combines all emails in each file into `emails`. Once the emails are combined, the function employs `for` loops to iterate through each message and each line of each email. The `.split` function is then used to separate the words in each message, which are added to the `all_words` list. Words that are a single letter or a number are removed from the list, ensuring that only significant words are captured for the spam detection analysis.

### `extract_features`
This function requires one argument: `mail_dir`. The function starts by creating a list of file paths by using `os.path.join` and a `for` loop to iterate through the file path of emails. Then a features matrix and training labels are initialized. The feature matrix is a 2D array where each column is a word and the rows are the emails. The labels is a 1D array that distinguishes between spam and non-spam emails. `Count` and `docID` are then initialized to keep track of the number of spam emails and the email being iterated through. Each file is then iterated through and opened using a `for` loop. The contents of the email are read and a `.split()` function is used to split the contents of the email into words. This list of words is then cross-referenced with a preexisting dictionary, which is created in the `make_Dictionary` function and added to the features matrix. Then the emails that are spam and the ones that aren't are separated based on the name of each file. If the name of the file starts with "spmsg" then it is a spam email and indicated as so in the train labels. Finally, the `features_matrix` and `labels` are returned, showing which emails are spam or not along with the count of each word in the emails.
