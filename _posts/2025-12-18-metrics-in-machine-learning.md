---
tags: [machine-learning, supervised-unsupervised, metrics]
---

Ranja Sarkar

![pc](https://github.com/user-attachments/assets/facda9c1-e8aa-4711-86e6-09bf555ad31a)

Metrics are measures of quantitative assessment. They assess or track business performance as well as statistical model performance. A model (learning from data) is built from buiness data, so the metrics here are intertwined. The difference between assessing a machine learning model and making a business decision from the model output gets blurry in practice.

Business decisions are made through hypothesis tests. A metric or loss function is used for assessment of model performance. A metric is a loss function but viceversa is not necessarily true. A test statistic (typically p-value) is used for the decision of action and inaction on the model, which essentially means deciding if the model can be launched into production or not. A operationalized model needs monitoring, so we know if it’s making meaningful and useful predictions with new data. 

📌Metrics are how humans draw meaning (information) from data and are typically designed for business users. 

📌Loss functions are designed for machines, although they may be identical to metrics for some business problems. 

-----

**SUPERVISED MACHINE LEARNING**

The metrics to quantify the performance of supervised machine learning models are well-defined, as these models are trained with data having target variable or labels. These models are formulated as optimization problems, for instance optimizing the training of models with hyper-parameters, then optimizing the model predictions to make a decision. 

A standard loss function (e.g. AIC) correlates well in general with a performance metric (e.g. RMSE), considered typically in forecasting models built with time-series data where, AIC is Akaike Information Criterion, and BIC is Bayesian Information Criterion. Every optimization problem seeks to minimize a loss function, like AIC or BIC.

An evaluation metric must reflect whatever it is we actually care about or desire when making predictions. For example, when we use mean squared error (MSE), we are implicitly saying that we think the cost of our prediction error should reflect the squared distance between what we predicted and what is correct. This may work well if we want to punish outliers or if our data is minimized by the mean. 

<img width="770" height="343" alt="11" src="https://github.com/user-attachments/assets/f33bb1e8-417c-445c-a15e-d93f177c1e15" />


📌 MSE is utilized as both loss function and metric.

We may output the error in squared units (MSE) or square-rooted units (RMSE) or, we may want the error to reflect the linear distance between what we predicted and what’s correct, or we want our data to be minimized by the median. We could try mean absolute error (MAE) in that case which is robust to outliers. 

MSE is known as L2 loss, and MAE is known as L1 loss. 

<img width="212" height="61" alt="mse" src="https://github.com/user-attachments/assets/18c47025-943c-4b9d-902c-fd5ac3f8d0f3" />

Whatever the case, we should be thinking of the metric as integral part of the modeling process, and select the best metric based on the specific concerns of the use-case.

<img width="233" height="48" alt="mae" src="https://github.com/user-attachments/assets/08687404-3ea5-4495-ba5a-9e1ea93f9b99" />


As in kNN classifier algorithm, L1 (Manhattan distance) and L2 (Euclidean distance) metrics are used to measure distances and gauge the proximity between two data points, however the choice of metric depends on the nature of data and specific problem. 

📌The L2 metric is sensitive to outliers whereas the L1 metric is robust to them, given their mathematical forms. 

For some business problems, a metric is enough while for some other, one might have to choose a loss function for optimization and a metric for evaluation. While a metric or loss function tells how good/optimally the model fits to data, a test statistic tells if the model is good enough to make decisions for the business.

-----

**[UNSUPERVISED MACHINE LEARNING](https://scikit-learn.org/stable/unsupervised_learning.html)**

In unsupervised machine learning, models learn patterns from unlabeled data. Unsupervised learners are comparatively difficult to evaluate as opposed to supervised learners, because there is no ground truth label. However, there are some known measures to assess the quality of results produced by unsupervised algorithms in clustering, data dimensionality reduction, and anomaly detection. 

# Clustering

[kMeans clustering](https://github.com/ranja-sarkar/DecisionTree/blob/main/kMeans.ipynb) is a centroid-based algorithm that learns data pattern to cluster or segment data. The elbow method to choose optimal number of clusters ‘k’ for a given dataset in kMeans clustering is based on within cluster sum of squares (WCSS) which decreases as the number of clusters increase. 

<img width="516" height="393" alt="aic" src="https://github.com/user-attachments/assets/aae680e3-5473-4955-a8bd-23c4de84fb3e" />


However, a different method must be used to find k. Here’s [why and how](https://arxiv.org/pdf/2212.12189). 

Variance-based and distance-based criteria (discussed below) seem to work better than the elbow criterion for choosing number of clusters for a given dataset in kMeans clustering. There’s no one optimal solution to a problem in clustering analysis. There are multiple interesting (and subjective) solutions and hence, kMeans clustering (least squares optimization problem) is essentially exploratory in nature. There's [DBSCAN](https://colab.research.google.com/drive/1TYPoAXE46EPDdkrKhLYzS-C54MxaUxVr) which is a density-based algorithm to cluster data.

📌 [Calinski Harabasz](https://www.tandfonline.com/doi/abs/10.1080/03610927408827101) Score → The CH index is also known as variance ratio criterion. A higher CH index means better defined clusters. [CH score](https://scikit-learn.org/stable/modules/clustering.html#calinski-harabasz-index) is the ratio of the sum of between-clusters (inter) dispersion and of within-cluster (intra) dispersion for all clusters, where dispersion is defined as the sum of distances squared.

📌 [Dunn Index](https://www.tandfonline.com/doi/abs/10.1080/01969727408546059) → An evaluation metric (an internal cluster validation) that identifies sets of clusters which are compact with a smaller variance within cluster and well separated, where the means of different clusters are sufficiently far apart. Higher the Dunn index value, better is the clustering. The number of clusters that maximizes Dunn index is taken as the optimal number of clusters. 

📌 [Davies Bouldin](https://ieeexplore.ieee.org/document/4766909) Score → Unlike Dunn index, better is the clustering (clusters are farther apart) when the [DB index](https://scikit-learn.org/1.5/modules/clustering.html#davies-bouldin-index) value is lower. The score is defined as the average similarity between clusters, where similarity is the ratio of within-cluster (intra) distances to between-clusters (inter) distances. Similarity therefore is a measure that compares the distance between clusters with the sizes of the clusters themselves. Lower the inter-cluster distances, higher the DB index value. 

📌 [Silhouette](https://www.sciencedirect.com/science/article/pii/0377042787901257?via%3Dihub) Score → Capped between values -1 and 1, the Silhouette coefficient determines the compactness or density of clusters, a score close to 1 indicating data points completely within a cluster well-separated from other clusters. A score close to zero indicates that clusters overlap. It is an internal cluster validation scheme and is expensive to compute. 

There’s another metric known as [adjusted Rand score](https://scikit-learn.org/stable/modules/generated/sklearn.metrics.adjusted_rand_score.html). It is capped between values 0 and 1, this index when close to 1 indicates the clustering algorithm did a good job at assigning similar data points to same cluster, and an index value close to 0 indicates random assignment of data points, hence poorly performing algorithm.  

# Dimensionality Reduction

It is in general difficult to design metrics for assessing unsupervised models, owing to the nature of input data. Unlike clustering algorithms, the metrics in data dimensionality reduction algorithms like [principal component analysis (PCA)](https://ranja-sarkar.github.io/pca/) are about information preservation or explaining maximum variance in the dataset. The proportion of variance explained (PVE) and cumulative PVE by the principal components are two such metrics. 

# Anomaly Detection

Some well-known unsupervised machine learning algorithms for anomaly (outlier) detection in datasets have metrics driven by the minor percentage of contamination (abnormality) in input data, majority of the data being considered normal. They are [Isolation Forest](https://github.com/ranja-sarkar/DecisionTree/blob/main/Anomaly_Detection_IF_LOF.ipynb), [One-class SVM](https://github.com/ranja-sarkar/SVM/blob/main/1c_svm.ipynb), [Local Outlier Factor (LOF)](https://github.com/ranja-sarkar/DecisionTree/blob/main/Anomaly_Detection_IF_LOF.ipynb). Few other algorithms like PCA use a cluster method to determine what constitutes a ‘normal’ cluster, anomalies belong to either sparse and smaller clusters or none.

Anomaly labels are almost never readily available. In manufacturing industries, even plant engineers often cannot label events as anomalies, what they do is reflect their assumptions about an anomaly. Only a few events for specific equipment classes can be definitively labeled. 

Anomaly detection in general remains an exercise of classification of ‘normal’ and deviation from normal or ‘anomaly’. An unsupervised deep learning (neural net) algorithm to detect anomaly is autoencoder where the model effectiveness is evaluated with the reconstruction error.

In unsupervised machine learning tasks, subject matter (domain) expertise and sound understanding of data is essential so metrics can be devised accordingly. A qualitative analysis of flagged incidents (rare) to assess their validity and potential impact is useful. A human-in-the-loop valildation of detected anomalies is required.  

For unsupervised learners, it is clear by now there is no obvious metric like we have for supervised learners and hence, it makes sense to use a weighted mixture of normalized metrics lying between [0, 1]. Also, keeping the metric same as the loss function used for model optimization is perhaps the right move. 




