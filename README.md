# Machine-Learning
All the algorithm I learned in my machine learning course at my Uni.

The Documentation right now are the comments in the Codes.
The real Documentation will follow here.
My Lecturer allowed me tu upload these codes.
All the Test and train data is writen by him.
My Codes start with the comment: 'MY CODE:' and end with 'END'.

# K-Nearest Neighbors (KNN) Classifier
## Introduction

The K-Nearest Neighbors (KNN) classifier is a simple and effective algorithm for classification tasks. It classifies a data point by considering the class labels of its k nearest neighbors in the feature space. This implementation allows for customizable values of k.

## Usage
### Methods
**__init__(self, X_train, y_train, k=5)**
- *X_train:* Training data features.
- *y_train:* Training data labels.
- *k:* Number of neighbors to consider (default is 5)

**predict(self, X_test)**
- *distaces:*
Calculates the Euclidean distance to the other points in the test files, he calculates as many times as there are x_train(data) in self.X_train.
- *sorted_distances_indices:*
Sort the indices of the nearest neighbors by the count of how high k is, in our example, 5 (sorted in ascending order).
- *neighbor_labels:*
Here, a list is created with the labels from y_train for each y in sorted_distances, so for the 5 neighbors, the labels are placed here.
- *most_common:*
The max function takes the largest element and outputs it. neighbor_labels is the list from which I take the data key=neighbor_labels.count gives the count of elements in neighbor_labels to the max function
-> in short: the element that occurs in neighbor_labels is stored in most_common.

# Text Classification Pipeline
## Introduction

The text classification pipeline processes textual data to classify it into predefined categories. It involves several steps, such as text preprocessing, feature extraction, model training, and prediction. The goal is to automatically assign appropriate labels or categories to input text based on the patterns and information learned during the training phase. This pipeline is commonly used in natural language processing (NLP) tasks to automate the categorization of text data.

## Usage

- X receives the 'text' from the DataFrame (df).

- y receives the 'party' from the DataFrame (df).

- The training and test data (text) and labels (party) are defined, and
using train_test_split, the test files are calibrated to 20%.

- The pipeline consists of 2 stages:
    1. tfidf: converts the text files into vectors (one-hot encoding),
        representing the frequency of words or word combinations.
    2. classifier: assigns documents to their respective classes based on
        the average vectors.

- *param_grid:* 
defines a parameter grid that tfidf should explore, specifying the range or combinations of parameters to be tested.
- *grid_search:* creates an object:
The functions in the pipeline are utilized.
The model is trained three times (for each grid).
cv=5 means it is trained and tested five times on different subsets.
- *grid_search.fit:*
is where the search object is actually executed.
- *best_params, best_model:*
These variables store information about the best grid and model after the 5-fold cross-validation.
- *return:*
The model with the best results and the test files used for evaluation. It involves first training the model with the training data and then assessing its performance with the test data.

- *model:*
The best model returned from the function is stored here:
- *predictions:*
Here, the trained model is used to predict the labels of the test_data.
- *class_report:*
Here, a report is generated that summarizes the data:
1. Precision: The proportion of correct predictions.
2. Recall: The proportion predicted as positive and actually positive.
3. F1: The harmonic mean of precision and recall.
4. Support: Normalizes the values to maintain consistency even with more samples.