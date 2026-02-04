---
tags: [data, error, machine-learning]
---

![IMG_2895](https://github.com/user-attachments/assets/8bfbb6aa-a2ca-49bf-9805-7cca411816ae)

<ins>**Measurement of model error**</ins>

The primary goal while building a predictive model must be to make it predictive of the desired target value. The closer the predicted value to the target, more accurate the model. Model error based on training data is misleading, the error the model exhibits on ‘new’ and unseen data yields actual results. In this context, error implies [residual](https://ranja-sarkar.github.io/2025/11/28/tests-&-measures.html).

When assessing the quality of a model, it is essential to accurately measure its **prediction error**. A model may fit the training data well, but may do a poor job of prediction on ‘new’ data. 

For example, if we sample 100 people and create a regression model to predict an individual's happiness based on wealth, we can record the squared error for how well the model does on the training dataset. Then if we sample a different 100 people from the population and apply our model to this new set, the squared error will almost always be higher. 

Turns out, prediction error = training error + f(model complexity)

As model complexity increases that is, adding parameters to the regression equation the model will do a better job fitting the training data, thereby reducing training error. This is a fundamental property of statistical models. No matter how unrelated the additional factors are to a model, adding them will decrease the training error.

In the happiness and wealth regression model, if we start with the simplest and then increase complexity by adding nonlinear or polynomial terms, what we get is something like,

Happiness = a + b(Wealth) + c(Wealth^2) + ϵ

The linear model (minus polynomial terms) seems a little too simple for the data, but once we pass a certain point, the prediction error starts to rise. The additional complexity helps us fit our training data, but causes the model to do a worse job of predicting on ‘new’ data. 

![hw](https://github.com/user-attachments/assets/115bdf7d-ca4d-4e32-8606-c5ef6c08ed3d)

Beyond this point, it is overfitting. Preventing overfitting is key to building robust and accurate predictive models. 

# Methods to accurately measure error

With higher optimism, the prediction error is higher beyond a certain model complexity. This is based on whether we want to rely on assumptions to adjust for the optimism, or we want to use the data for estimating the optimism. 

-----

Assumption-based or **parametric approaches** to measure error are faster to apply, but come at a high cost.  How much of the assumptions skews the results varies on a case-by-case basis. The error might be negligible in many cases, but fundamentally results derived from such techniques require a great deal of trust on the evaluator’s part.

1. Adjusted R^2

2. Information Theory

-----

**Non-parametric approaches** like cross-validation resampling are computationally intense but provide more confidence and security in the outcome.

1. Holdout set

2. Cross-validation (CV) -> K-fold CV, leave-one-out CV 

-----

The obvious issue in having a validation subset of data is that our estimate of the test error can be highly variable. 

The  **test set** is used to evaluate how the model will perform on unseen data.

The **validation set** is used to select which model (hyperparameter set) should be chosen.

The **train set** is used to learn the model parameters (or hyperparameters).

**An issue with the 'holdout set' approach is that it tends to overestimate the test error for models fit on the entire dataset. The 'validation set' approach reserves  decent-sized chunk of data for validation and testing.**  

-----

# Adjusted R^2

The goodness of fit, R^2 under-penalizes model complexity that is, it fails to decrease the prediction error as much as required with the addition of complexity in the model. This can lead to misleading conclusions. However, it is fast to compute and easy to interpret.

![rr](https://github.com/user-attachments/assets/94702b1f-86ff-4301-a1b8-6233eb0ffe41)

A variation in the independent (x) variable explains a variation in the dependent (y) variable. Zero linear relationship between x and y yields R^2 = 0 and R^2 = 1 means 100% variation in y is explained by variation in x. A negative R^2 means that our model is doing worse (capturing less variance in y) than a flat line through the mean of our data would. 

Adjusted R^2 is more accurate as it considers only significant features or independent variables in the dataset to predict the target or dependent variable. It properly penalizes the insignificant ones. 

![rr0](https://github.com/user-attachments/assets/e1589523-2e9f-401e-a988-f4644570a55e)

n =  number of rows in the dataset, m = number of the columns in the dataset. 

Use of adjusted R^2 however is less generalizable and may still overfit the (tabular) data.

# Information Theory

Information theoretic approaches assume a parametric model. If we adjust the parameters of a dataset in order to maximize its (distribution) likelihood we obtain the maximum likelihood estimate (MLE) of the model parameters. In other words, these approaches attempt to measure model error as how much information is lost between a candidate model and the true model. The true model is unknown, but given certain assumptions we can obtain an estimate of the difference between it and and proposed models. More this difference is, higher the error and worse the candidate model.

Akaike's Information Criterion (AIC) is defined as a function of the likelihood of a model and the number of parameters (m) in that model.

AIC = −2ln(likelihood) + 2m

Bayesian Information Criterion (BIC) for sample size n is given by,

BIC = −2ln(likelihood) + mln(n)

The first term in the equations can be thought of as the training error and the second term can be thought of as the penalty to adjust for the optimism. The goal is to minimize AIC/BIC. These measures or metrics require a model that can generate likelihoods, thereby needing a leap of faith that the specific equation used is theoretically suitable to the problem and associated data.

-----

# Holdout Set

We can directly measure how well a model predicts on new data by holding out a test dataset from the beginning.  

Adjusting a model in an iterative process by using a holdout dataset to test is a common mistake. If the holdout set is repeatedly used for testing a model during development, the holdout set becomes contaminated. It has been used as part of the model selection process and no longer yields unbiased estimates of the prediction error. Given enough data, this metric is highly accurate, it is conceptually simple and easy to implement. 


<img width="299" height="142" alt="03" src="https://github.com/user-attachments/assets/ddfcd45c-be24-47b3-a658-a4c99dc8acc3" />


**It has a potential conservative bias, nonetheless it is useful in practice as compared to overly optimistic predictions.**

# K-fold CV

For a 5-fold CV, there are 5 groups of data (of equal size) used to train the model and 5 groups that was not used to train the model but used to estimate the prediction error, ending up with 5 error estimates that are averaged to obtain a robust estimate of the error. 

![5cv](https://github.com/user-attachments/assets/3f02ea24-44cc-4df2-bdb0-61662ac59b3d)

When data is limited, CV is preferred to the holdout set method. CV gives estimates of variability of the prediction error. 
Smaller the number of folds, more biased are the error estimates (conservative indicating higher error than there is in reality). Another factor to consider is computational time which increases with the number of folds, when it seems prudent to use a smaller number of folds. 

Choosing the fold size (or number of folds) may be a con of the CV approach, it nevertheless provides good estimates of the model error. 

# Leave-one-out CV

For 4-fold, there are 4 training sets and 4 validation sets. Each time (each iteration) a different fold is used for training and validating the model. The test set remains untouched as it is the one final set (used only once), but the distributions of training and validation sets differ at every fold. 

<img width="640" height="465" alt="loocv" src="https://github.com/user-attachments/assets/5a9eee44-f5ed-4c2d-9eb0-88b1ee82b3eb" />


At the end of the procedure, we take the average of the validation sets' scores and use it as the model's estimated (training) performance. And finally, the test (prediction) error is estimated. With CV, the model generalizes well. 

**The CV approach typically does not overestimate the prediction error.**   

-----

There are [two goals](https://github.com/ranja-sarkar/ranja-sarkar.github.io/blob/de0b3818af489bb76b20b5268e1b0419d0c91d65/_posts/assets/breiman.pdf) of analysing data - *information* and *prediction*. And there are two approaches toward these goals - *data model* and *algorithmic model*.

The methods to measure model error must also be picked accordingly. 
For example, linear regression is an interpolation model by construct and the adjusted R^2 parametric approach is suitable for it. When it comes to prediction with algorithmic models like neural nets, model error is measured utilizing non-parametric resampling approaches like CV. 

We use either data or assumptions or both to adjust for the optimism, and estimate model error as accurately as possible.

<img width="436" height="236" alt="02" src="https://github.com/user-attachments/assets/82e5a119-608c-4af2-8ad1-f60d872582a6" />
