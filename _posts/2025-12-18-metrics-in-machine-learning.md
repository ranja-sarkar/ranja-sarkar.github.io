---
tags: [machine-learning, metrics, functions]
---

Ranja Sarkar

![pc](https://github.com/user-attachments/assets/facda9c1-e8aa-4711-86e6-09bf555ad31a)

Metrics are measures of quantitative assessment. They are used for tracking performances in businesses as well as evaluating statistical models. The difference between evaluating a model and making a decision from the model output gets blurry in practice. 
Business decisions are made through hypothesis tests. A metric or loss function is used for assessment of model performance. A metric is a loss function, viceversa is not necessarily true. A test statistic (typically p-value) is used for the decision of action and inaction of the predictive model, which essentially means deciding if the model can be launched into production or not. A operationalized model needs monitoring, so we know if it’s making useful predictions with new data. 
📌Metrics are how humans draw meaning (information) from data and are typically designed for business users/end-users. 
📌Loss functions are designed for machines, although they may be identical to metrics for some problems. 

Supervised models where we have a target variable, the metrics to quantify their performance are well-defined, however, devising metrics to evaluate unsupervised models (there’s no target) becomes a tad difficult. 
Predictive models are framed as optimization problems, for instance optimizing the training of machine learning models with model parameters, then optimizing the model predictions to make a decision. 
A standard loss function (e.g. AIC) in general correlates well with a performance metric (e.g. RMSE), considered typically in forecasting models built with time-series data where, AIC is Akaike Information Criterion, and BIC is Bayesian Information Criterion. Every optimization problem seeks to minimize a loss function. 
An evaluation metric must reflect whatever it is we actually care about or desire when making predictions. For example, when we use MSE, we are implicitly saying that we think the cost of our prediction error should reflect the squared distance between what we predicted and what is correct. This may work well if we want to punish outliers or if our data is minimized by the mean. 
📌 MSE is utilized as both loss function during model training and metric during model prediction evaluation.

We may output the error in squared units (MSE) or square-rooted units (RMSE) or, we may want the error to reflect the linear distance between what we predicted and what’s correct, or we want our data to be minimized by the median. We could try Mean Absolute Error (MAE) in that case which is robust to outliers. 
MSE is known as L2 loss, and MAE is known as L1 loss. Whatever the case, we should be thinking of the evaluation metric as integral part of the modeling process, and select the best metric based on the specific concerns of the use-case. 
As in kNN classifier algorithm, L1 (Manhattan distance) and L2 (Euclidean distance) metrics are used to measure distances and gauge the proximity between two data points, however, the choice of metric depends on the nature of data and specific problem. 
📌The L2 metric is sensitive to outliers whereas the L1 metric is robust to them, given their mathematical forms. 
For some business problems, a metric is enough while for some other, one might have to choose a loss function for optimization and a metric for evaluation. While a metric tells how good/optimally the model fits to data, a test statistic tells if the model is good enough to the business for decision-making.

-----

In unsupervised machine learning, models learn patterns from unlabeled data. Unsupervised learners are comparatively difficult to evaluate as opposed to supervised learners, because there is no ground truth label and such models cannot be tested like supervised ones. However, there are some known measures to assess the quality of results produced by unsupervised algorithms in clustering or segmentation, data  dimensionality reduction, and anomaly detection. 

Here I list the measures or metrics for evaluation of the performance of clustering models, for example kmeans clustering which is centroid-based, DBSCAN which is density-based. These clustering algorithms learn patterns from data to segment/group the datapoints. 

The elbow method to choose optimal ‘k’ in kMeans clustering is based on within cluster sum of squares (WCSS) which decreases as the number of clusters increase. But instead a different method should be used to find the optimal number of clusters for a dataset. Here’s why and how. 

Variance-based and distance-based criteria (discussed below) seem to work better than the elbow criterion for choosing number of clusters for a given dataset in kMeans clustering. There’s no one optimal solution to a problem in clustering analysis. There are multiple interesting (and subjective) solutions and hence, kMeans clustering (least squares optimization problem) is essentially exploratory in nature.

📌 Calinski Harabasz (CH) Score → This index is also known as variance ratio criterion. A higher CH index means better defined clusters. CH score is the ratio of the sum of between-clusters (inter) dispersion and of within-cluster (intra)  dispersion for all clusters, where dispersion is defined as the sum of distances squared.

📌 Dunn Index → An evaluation metric (an internal cluster validation) that identifies sets of clusters which are compact with a smaller variance within cluster and well separated, where the means of different clusters are sufficiently far apart. Higher the Dunn index value, better is the clustering. The number of clusters that maximizes Dunn index is taken as the optimal number of clusters. 

📌 Davies Bouldin (DB) Score → Unlike Dunn index, better is the clustering (clusters are farther apart) when the DB index value is lower. The score is defined as the average similarity between clusters, where similarity is the ratio of within-cluster (intra) distances to between-clusters (inter) distances. Similarity therefore is a measure that compares the distance between clusters with the sizes of the clusters themselves. Lower the inter-cluster distances, higher the DB index value. 

📌 Silhouette Score → Capped between values -1 and 1, the Silhouette coefficient determines the compactness or density of clusters, a score close to 1 indicating data points completely within a cluster well-separated from other clusters. A score close to zero indicates that clusters overlap. It is an internal cluster validation scheme and is expensive to compute. 

There’s another metric known as adjusted Rand Index. It is capped between values 0 and 1, this index close to 1 indicates the clustering algorithm did a good job at assigning similar data points to same cluster, and an index value close to 0 indicates random assignment of data points, hence poorly performing (did not learn data pattern) algorithm.  

-----

It is in general difficult to design metrics for evaluating unsupervised ML models, owing to the nature of input data. Unlike clustering, the metrics in data dimensionality reduction algorithms like principal component analysis (PCA) are about information preservation or explaining maximum variance in the dataset; the proportion of variance explained (PVE),  cumulative PVE by the principal components are two such metrics. 

-----

Some well-known unsupervised machine learning algorithms for anomaly (outlier) detection in data have metrics driven by the minor percentage of contamination (abnormality) in input data, majority of the data being considered normal. ⬇️

Isolation Forest

One-class SVM

Local Outlier Factor (LOF)

Few other algorithms use a cluster method to determine what constitutes a ‘normal’ cluster. For example, PCA wherein anomalies belong to either sparse and smaller clusters or none.

Anomaly labels are almost never readily available. In manufacturing industries, even plant engineers often cannot label events as anomalies, what they do is reflect their assumptions about an anomaly. Only a few events for specific equipment classes can be definitively labeled. 

Anomaly detection in general remains an exercise of classification of ‘normal’ from deviation from normal or ‘anomaly’. An unsupervised deep learning (neural net) algorithm to detect anomaly is autoencoder where the model effectiveness is evaluated with the reconstruction error.

In unsupervised ML tasks, subject matter (domain) expertise and sound understanding of data is essential so evaluation metrics can be designed accordingly. A qualitative analysis of flagged incidents (rare) to assess their validity and potential impact is useful. A human-in-the-loop valildation of detected anomalies is required.  

For unsupervised learners, it is clear by now there is no obvious evaluation metric like for supervised ones and hence, it makes sense to use a weighted mixture of normalized metrics lying between [0, 1]. Also, keeping the evaluation metric same as the loss function used for model optimization is perhaps the right move to assess an unsupervised model. 




