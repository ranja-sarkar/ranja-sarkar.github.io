---
tags: [models, ensembles, machinelearning]
---

Ranja Sarkar

![title](https://github.com/user-attachments/assets/78520f1a-430f-4fb9-bf0e-05cfc57dbb67)

Ensembles execute multiple models, then combine their outputs to make the final prediction. Diversity in ensembling is necessary to achieve better performance, which can be met via different ways like bagging, boosting, etc..

# Bagging ensemble

Bagging is bootstrapping followed by aggregation that is, bootstrap aggregating, and enables reduction of variance in the ensemble. An example of a bagging ensemble is random forest. 

![bagg](https://github.com/user-attachments/assets/cf67376a-809c-4c08-b4b9-772a39261228)


ootstrapping involves creating multiple subsets of training data. Each subset is of equal size and training is carried out in a parallel manner. Aggregation combines the outputs of each learner/model.  

In a regression task, typically the average (or weighted average) of predictions from each model is considered to make the final prediction. 

---

In a classification task, the final prediction can be based on majority vote rule. Let’s say, we have a binary classifier to predict class 0 and class 1 and there’re 3 learners/models. 

Learner 1 predicts Class 0, learner 2 predicts Class 1, and learner 3 predicts Class 1. Then, Class 1 is the ensemble decision as it is the majority. This is the **hard voting** rule. 

<img width="157" height="178" alt="vote1" src="https://github.com/user-attachments/assets/e9b5c862-01a9-4c8c-8036-e9cd37237ad8" />


There’s another rule - **soft voting**. Learner 1 predicts Class 0 with probability 98%, learner 2 predicts Class 0 with probability 47% and leaner 3 predicts Class 0 with probability 47%. The average probability of Class 0 is 64%. Thus, Class 0 is the ensemble decision. Soft voting considers how confident each voter is. 

<img width="193" height="113" alt="vote2" src="https://github.com/user-attachments/assets/3e955155-7629-497f-ad67-a9d355cde6c8" />


Depending on the performance, we can also put a weight on each learner. 



# Boosting ensemble

A boosting algorithm works in a sequential manner. The output from a model is fed as input to the next model in a sequential way. Each model tries to correct the errors in the previous model. Models are added sequentially until a stopping condition is met in the boosting method. Owing to the employment of additive combination there is reduction in bias in the boosting ensemble. 

![boost](https://github.com/user-attachments/assets/afc63f1c-e59f-4cd7-afc5-3ee48b22bbba)

**Adaptive Boosting**

In AdaBoost, weights of the samples are adjusted (focussing on misclassified examples) at each iteration - final prediction is a weighted sum of predictions of trees, the algorithm is easily influenced by outliers in the sample. 

**Gradient Boosting**

In gradient boosting, final prediction is an equal-weighted sum of predictions of trees that is, no re-weighting of samples occurs like in adaptive boosting. The algorithm works on the principle of gradient descent (minimize loss function with learning rate) and is less influenced by outliers and noise in the training sample. 

There are three notable boosting libraies.

📌 LightGBM

[Light gradient boosting machine](https://github.com/microsoft/LightGBM) by Microsoft is a fast, distributed, high-performance framework. It is memory efficient, its techniques like exclusive feature bundling (EFB) help reduce memory usage during training.

Find a [detailed comparison](https://xgboosting.com/xgboost-vs-lightgbm/) of lightGBM and XGBoost.


📌 CatBoost

[Categorical boosting](https://github.com/catboost/catboost) is a fast, scalable, high-performance gradient boosting algorithm, supporting computation on CPU as well as GPU. It is good for large datasets with multiple categorical variables (encoded), and has proved to be faster than lighGBM and XGBoost on a couple of occasions atleast.

Time to fit [500k samples with 28 features](https://openreview.net/pdf?id=ryexWdLRtm) is shown below:

<img width="326" height="61" alt="1" src="https://github.com/user-attachments/assets/5a9bf4fc-06e7-41d4-ace8-c9104c2bb769" />

CatBoost aims to reduce the need for extensive tuning, as compared to XGBoost. Find a [detailed comparison](https://xgboosting.com/xgboost-vs-catboost/) of CatBoost and XGBoost.

Results of [benchmarking & optimization of gradient boosting decision tree algorithms](https://arxiv.org/pdf/1809.04559) have been reported by many including [NVIDIA](https://github.com/NVIDIA/gbm-bench).



📌 XGBoost

[Extreme gradient boosting](https://github.com/dmlc/xgboost) is a scalable, portable, and distributed framework. It has proven to be a highly efficient, parallel tree boosting algorithm. According to [NVIDIA](https://www.nvidia.com/en-us/glossary/xgboost/), it is the most appealing algorithm to Data Scientists owing to its processing time as well as inference time.

As an example, see how an XGBoost regressor is faster than vanilla gradient boosting regressor [here](https://xgboosting.com/xgbregressor-faster-than-gradientboostingregressor/).

XGBoost has a strong [community](https://xgboost.ai/community), teh discussion forums are really useful for developers.

# Stacking ensemble

There's a stack of different individual models like SVM, kNN etc. and they are built using same training dataset. The features extracted from the output of these individual learners are called meta features. 

![stack](https://github.com/user-attachments/assets/67665c13-26ca-4a8b-8d78-90cb27a2e1e5)


In stacking, the training data is split into several equal parts (say 12 parts). Out of these 12 parts, a learner is built on 11 parts using a classifier or regression algorithm, for instance we use SVM and preserve one part for validation. In the next iteration, another part is preserved for validation and another classifier like kNN or decision tree regression algorithm is used to fit the training data. This strategy is repeated until the entire dataset is covered. The features extracted from predictions on each iteration are the features used to build a new learner. 

Stacking ensembles are not as widely used or not popular as the bagging and boosting ensembles. 



