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
- X_train: Training data features.
- y_train: Training data labels.
- k: Number of neighbors to consider (default is 5)

**predict(self, X_test)**
- distaces:
Calculates the Euclidean distance to the other points in the test files, he calculates as many times as there are x_train(data) in self.X_train.
- sorted_distances_indices:
Sort the indices of the nearest neighbors by the count of how high k is, in our example, 5 (sorted in ascending order).
- neighbor_labels:
Here, a list is created with the labels from y_train for each y in sorted_distances, so for the 5 neighbors, the labels are placed here.
- most_common:
The max function takes the largest element and outputs it. neighbor_labels is the list from which I take the data key=neighbor_labels.count gives the count of elements in neighbor_labels to the max function
-> in short: the element that occurs in neighbor_labels is stored in most_common.
