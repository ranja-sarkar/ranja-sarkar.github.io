---
tags: []
---

Ranja Sarkar

Let’s first talk about underfitting and overfitting of a model to data in other words, about a model’s bias and variance.

Above is the graphical illustration of bias and variance, which illustrates bias, variance, accuracy and precision of a model at one go.

# Learning curve

A learning curve helps diagnose bias and variance in an ML model. It is a plot of model’s error as a function of the data (training) size. 

Where does the error in model predictions come from? 

Either from variance (too much capacity) that is, not enough information in the dataset 

Or from bias (too little capacity) that is, not enough representation of the true function. 


# Validation curve

A validation curve helps find the sweet spot between underfitting and overfitting and build a model that generalizes well. It is a plot of the model's error as a function of a model hyperparameter. 

In the region where both the training error and validation error are high, we have a model with high bias. In the region with the training error staying low and validation error increasing, we begin to see the effects of high variance. The validation error remains high as the model is not able to generalize from training data to new data. 

