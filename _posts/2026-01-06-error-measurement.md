---
tags: [data, error, machine-learning]
---

Ranja Sarkar

![IMG_2895](https://github.com/user-attachments/assets/8bfbb6aa-a2ca-49bf-9805-7cca411816ae)

The primary goal while building a predictive model must be to make it predictive of the desired target value. The closer the predicted value to the target, more accurate the model. Model error based on training data is misleading, the error the model exhibits on ‘new’ and unseen data yields actual results. When assessing the quality of a model, it is essential to accurately measure its **prediction error**. A model may fit the training data well, but may do a poor job of prediction on ‘new’ data. 

For example, if we sample 100 people and create a regression model to predict an individual's happiness based on wealth, we can record the squared error for how well the model does on the training dataset. Then if we sample a different 100 people from the population and apply our model to this new set, the squared error will almost always be higher. 

Turns out, prediction error = training error + f(model complexity)

As model complexity increases that is, adding parameters to the regression equation the model will do a better job fitting the training data, thereby reducing training error. This is a fundamental property of statistical models. No matter how unrelated the additional factors are to a model, adding them will decrease the training error.

In the happiness and wealth regression model, if we start with the simplest and then increase complexity by adding nonlinear or polynomial terms, what we get is something like,

Happiness = a + b(Wealth) + c(Wealth^2) + ϵ

The linear model (minus polynomial terms) seems a little too simple for the data, but once we pass a certain point, the prediction error starts to rise. The additional complexity helps us fit our training data, but causes the model to do a worse job of predicting on ‘new’ data. 

![hw](https://github.com/user-attachments/assets/115bdf7d-ca4d-4e32-8606-c5ef6c08ed3d)

Beyond this point, it is overfitting. Preventing overfitting is key to building robust and accurate predictive models. 

# Methods for accurate measurement of error

With higher optimism, the prediction error is higher. This is based on whether we want to rely on assumptions to adjust for the optimism, or we want to use the data for estimating the optimism. 

Assumption-based or parametric approaches to measure error are faster to apply, but come at a high cost.  How much of the assumptions skews the results varies on a case-by-case basis. The error might be negligible in many cases, but fundamentally results derived from such techniques require a great deal of trust on the evaluator’s part.

1. Adjusted R^2

2. Information Theory

Non-parametric approaches like cross-validation resampling are computationally intense but provide more confidence and security in the outcome.

1. Holdout set

2. Cross-validation (cv): k-fold cv, leave-one-out cv

-----

# Adjusted R^2

R^2 under-penalizes model complexity that is, it fails to decrease the error as much as required with the addition of complexity in the model. This can lead to misleading conclusions. However, it is fast to compute and easy to interpret.

![rr](https://github.com/user-attachments/assets/94702b1f-86ff-4301-a1b8-6233eb0ffe41)

A variation in the independent (x) variable explains a variation in the dependent (y) variable. Zero linear relationship between x and y yields adj. R^2 = 0 and adj. R^2 = 1 means 100% variation in y is explained by variation in x.  A negative R^2 means that our model is doing worse (capturing less variance in y) than a flat line through the mean of our data would. 

Adjusted R^2 is more accurate as it considers only significant features or independent variables in the dataset to predict the target (dependent variable). It properly penalizes the insignificant ones. 

![rr0](https://github.com/user-attachments/assets/e1589523-2e9f-401e-a988-f4644570a55e)

n =  number of rows in the dataset, m = number of the columns in the dataset. 

Use of adjusted R^2 however is less generalizable and may still overfit the data.

# Information Theory

