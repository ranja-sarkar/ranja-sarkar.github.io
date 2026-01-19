---
tags: [models, ensembles, machinelearning]
---

Ranja Sarkar

![title](https://github.com/user-attachments/assets/78520f1a-430f-4fb9-bf0e-05cfc57dbb67)

Ensembles execute multiple models, then combine their outputs to make the final prediction. Diversity in ensembling is necessary to achieve better performance, which can be met via different ways like bagging, boosting, etc..

# Bagging ensmeble

Bagging is bootstrapping followed by aggregation that is, bootstrap aggregating, and enables reduction of variance in the ensemble.
An example of a bagging ensemble is random forest.

ootstrapping involves creating multiple subsets of training data. Each subset is of equal size and training is carried out in a parallel manner. Aggregation combines the outputs of each learner/model.  In a regression task, typically the average (or weighted average) of predictions from each model is considered to make the final prediction. 

---

In a classification task, the final prediction can be based on majority vote rule. Let’s say, we have a binary classifier to predict class 0 and class 1 and there’re 3 learners/models.

Learner 1 predicts Class 0, learner 2 predicts Class 1, and learner 3 predicts Class 1. Then, Class 1 is the ensemble decision as it is the majority. This is the hard voting rule. There’s another rule - soft voting. Learner 1 predicts Class 0 with probability 98%, learner 2 predicts Class 0 with probability 47% and leaner 3 predicts Class 0 with probability 47%. The average probability of Class 0 is 64%. Thus, Class 0 is the ensemble decision. Soft voting considers how confident each voter is. 

Depending on the performance, we can also put a weight on each learner. 


---



# Boosting ensemble



# Stacking ensemble







