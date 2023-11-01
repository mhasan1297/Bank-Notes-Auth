# Banknote Authentication

Welcome to the Banknote Authentication project, which focuses on the classification of banknotes as either genuine or counterfeit. The project utilizes K-Means clustering as the primary machine learning technique to achieve this classification task.

## Table of Contents

- [Introduction](#introduction)
- [Data Preprocessing](#data-preprocessing)
- [K-Means Clustering](#k-means-clustering)
- [Visualizing K-Means Clustering](#visualizing-k-means-clustering)

## Introduction

The objective of this project is to create a system that can determine the authenticity of banknotes based on certain features. In this context, K-Means clustering is a suitable choice due to the numeric nature of the data features, making it an appropriate algorithm for finding similarity and proximity.

## Data Preprocessing

Before diving into the clustering process, it's crucial to prepare the data adequately. Here are the initial steps taken:

- Load the dataset from 'bank-note-auth.csv' using the Pandas library.
- Calculate the mean and standard deviation for each column to standardize the data.
- Standardize the dataset to ensure that each feature has a mean of 0 and a standard deviation of 1.

## K-Means Clustering

K-Means is a popular clustering algorithm for grouping data points into clusters based on their similarity. In this project, we perform K-Means clustering with the following steps:

- Initialize random centroids for the clusters.
- Assign data points to the nearest centroid based on the Euclidean distance.
- Update the centroid values by finding the geometric mean of each feature within the clusters.
- Repeat the assignment and update steps until convergence or for a specified number of iterations.

## Visualizing K-Means Clustering

To gain insights into the clustering process, we visualize the iterations of the K-Means algorithm using the Principal Component Analysis (PCA) technique. The scatter plots show how data points are assigned to clusters and how centroids move during each iteration.

### Example Plotting Code

```python
max_iterations = 100
k = 2

centroids = random_centroids(data, k)
old_centroids = pd.DataFrame()
iteration = 1

while iteration < max_iterations and not centroids.equals(old_centroids):
    old_centroids = centroids

    labels = get_labels(data, centroids)
    centroids = new_centroids(data, labels, k)
    plot_clusters(data, labels, centroids, iteration)
    iteration += 1
