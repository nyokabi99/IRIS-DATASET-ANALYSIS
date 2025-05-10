## K-Nearest Neighbors Classification on the Iris Dataset
### Introduction
The Iris dataset is a classical benchmark in machine learning, comprising 150 samples of three iris species (Iris setosa, Iris versicolor, and Iris virginica), 
each described by four features (sepal length, sepal width, petal length, petal width).
In this analysis, we focus on distinguishing Iris versicolor and Iris virginica using a binary K-Nearest Neighbors (K-NN) classifier, 
evaluating performance as the number of neighbors k varies.
### Methodology
#### Data Preparation
- Filtered the dataset to include only the two target classes (versicolor and virginica).

- Split into training (≈80%) and test (≈20%) sets to evaluate generalization.

- Standardized features to zero mean and unit variance.

#### Modeling
- Trained separate K-NN models with k = 3, 4, 5, 7, and 9.

- For each k, predicted labels on the held-out test set.

- Computed overall accuracy, classification report (precision, recall, F1-score), and confusion matrix.
### Results

- 3-NN	0.818 (18/22)	  All 13 versicolor correctly identified (100% recall); 4 of 9 virginica misclassified.
  
- 4-NN	0.818 (18/22)	  Even k led to tie-breaking; overall performance mirrored k = 3.
  
- 5-NN	0.818 (18/22)	  Similar to k = 3/4; model still struggles with virginica boundary.
  
- 7-NN	0.864 (19/22)	  Improved separation; only 3 total misclassifications between classes.
  
- 9-NN	0.864 (19/22)	  Matches performance of k = 7, suggesting stability at higher k in this data partition.

### Discussion
Even vs. Odd k: Using an even k (e.g., 4) can produce ties in voting. In this case, tie-breaking defaulted to one class, yielding the same metrics as k = 3.

Model Capacity: Smaller k values (3–5) led to over-sensitivity to local variations, causing more virginica misclassifications.

Optimal k: Larger k values (7 and 9) smoothed decision boundaries, improving robustness and boosting accuracy from 81.8% to 86.4%. However, beyond a certain point, further increases in k risk biasing toward the majority class.


