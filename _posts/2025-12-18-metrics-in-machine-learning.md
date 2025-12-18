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

