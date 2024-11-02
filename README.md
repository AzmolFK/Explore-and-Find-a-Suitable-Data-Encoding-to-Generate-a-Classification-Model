# Explore-and-Find-a-Suitable-Data-Encoding-to-Generate-a-Classification-Model

This repository This report delves into machine learning models for the classification of biological sequences, using a
dataset with sequences of varying lengths. To adapt these sequences for machine learning, we have explored
three distinct data encoding methods: k-mer encoding, binary encoding, and TF-IDF encoding. We have
utilized a Gradient Boosting Classifier, a robust tree-based ensemble method known for its effectiveness in
handling complex datasets. The classifier was assessed using 10-fold stratified cross-validation to ensure
reliable estimation of its performance across the dataset. To quantify the model’s performance, we have
focused on two key metrics: the average precision score, which provides a single-figure summary of the
precision-recall trade-off, and the F1-score, a harmonic mean of precision and recall, offering a balanced
measure of model accuracy.

## Brief Description & Justification of Data Encoding Methods
In this section, We will go through three data encoding methods: k-mer encoding, binary encoding, and TFIDF
encoding. Each encoding technique offers a unique way to represent the sequences, aiming to capture
essential features that are pertinent to the classification task.

### K-mer Encoding
K-mer encoding involves breaking down sequences into all possible subsequences of length k. This method
is widely used in genomics to capture local sequence patterns. The choice of k balances between capturing
detailed sequence information (larger k) and maintaining a manageable feature space (smaller k).
K-mers are powerful for capturing the local compositional patterns of sequences, which are crucial in many
biological contexts, such as identifying motifs or patterns associated with specific functions or characteristics.

### Binary Encoding
We have adapted Binary encoding in this context to represent the presence or absence of nucleotides in a
sequence. Each nucleotide (A, C, G, T, and N for unknown) is represented by a binary vector, making it a
simple yet effective way to summarize sequence composition.
Binary encoding is straightforward and captures essential information about nucleotide composition without
being influenced by sequence length. This makes it suitable for datasets with sequences of varying lengths.

### TF-IDF Encoding
Term Frequency-Inverse Document Frequency (TF-IDF) is a statistical measure used to evaluate the importance
of a word, in this case, a k-mer in a document relative to a collection of documents. It increases
proportionally to the number of times a word appears in the document but is offset by the frequency of the
word in the corpus.
TF-IDF is useful in highlighting k-mers that are frequent in a subset of sequences but not across all
sequences, thus helping identify distinctive sequence features. It’s an effective way to transform sequence
data into a feature space that reflects both the local and global sequence context.

## Tree-Based Method: Gradient Boosting Classifier
Gradient Boosting Classifier is a powerful tree-based ensemble method that builds models in a stage wise
fashion. It constructs a series of decision trees where each tree is trained to correct the errors made by the
previous ones. Unlike other ensemble methods that train trees independently, Gradient Boosting trains trees
one after another, with each new tree focusing more on instances that were misclassified by earlier trees.
The method uses a gradient descent algorithm to minimize a loss function. 

Gradient Boosting is particularly effective because it combines multiple weak learning models to create a
strong predictive model. Each tree in the ensemble contributes to refining the overall model by focusing on
difficult-to-classify instances, making the ensemble robust to overfitting and capable of handling a variety of
data distributions and complexities.

## Performance Metric to Assess Model Performance

### Average Precision Score
The average precision score summarizes the precision-recall curve into a single
value, representing the average of precision scores at each threshold. It is weighted by the increase in recall
from the previous threshold. It provides a comprehensive measure of performance across different levels
of class imbalance. This metric is particularly useful in contexts where the positive class is rare or when
the costs of false positives and false negatives are significantly different. It captures the trade-off between
precision and recall, offering a balanced view of model performance across the entire precision-recall spectrum.

### F1-Score
The F1-score is the harmonic mean of precision and recall, giving both metrics equal weight.
It ranges from 0 to 1, where 1 indicates perfect precision and recall, and 0 means that either the precision
or the recall is zero. The F1-score is valuable when we need a single metric to compare models’ performance
directly, especially in situations with an uneven class distribution. It’s useful when the costs of false positives
and false negatives are roughly equal and there is an interest in balancing precision and recall without giving
undue weight to one over the other.

## Comparison Table of Performance Metric for Each Encoding
Here’s a table with the mean average-precision-score and F1-score and their standard deviation per encoding -

![image](https://github.com/user-attachments/assets/4875df35-55c1-43d0-b5c5-ce570069a708)

## Data Visualization for The Performance of The Model
In this section, We will provide the comparison of the performance of the three data encoding: K-mer, Binary
and TF-IDF encoding using Precision-Recall curve.

In Figure 1, the graph of a precision-recall curve is illustrated that compares the performance of a Gradient
Boosting Classifier with three different data encodings: K-mer, Binary, and TF-IDF, on a sequence
classification task. The x-axis represents recall, and the y-axis represents precision.

From the graph, we can observe that the K-mer encoding (blue line) generally maintains a higher precision
for a given level of recall compared to the other two methods, indicating that it is the superior encoding
method for this specific dataset and classification task. This is especially evident at the left side of the graph,
where K-mer encoding shows a significant advantage at lower recall levels. The TF-IDF encoding (green
line) and Binary encoding (orange line) exhibit comparable performance, with TF-IDF slightly outperforming
Binary encoding at certain points.

![pr](https://github.com/user-attachments/assets/3c16ff82-418a-4223-8c96-74255c56da7c)


Therefore, based on this precision-recall analysis, the K-mer encoding is the best performer in effectively
balancing precision and recall for the Gradient Boosting classifier in this context.
