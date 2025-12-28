---
tags: []
---

Ranja Sarkar

A model's vias and variance manifest in how the model underfits and overfits to data. A graphical illustration of bias and variance, accuracy and precision of a model gives us an idea of an optimal model.

<img width="447" height="422" alt="01" src="https://github.com/user-attachments/assets/b20c2667-8f26-4c68-b24e-75a7fd8a4b62" />

 
# Learning curve

A learning curve helps diagnose bias and variance in an ML model. It is a plot of model’s error as a function of the data (training) size. 

![03](https://github.com/user-attachments/assets/937d6de6-1d65-461d-b6a8-462f65866e9c)


**Where does the error in predictions from the model come from?** 

Either from variance (too much capacity) that is, not enough information in the dataset 

Or from bias (too little capacity) that is, not enough representation of the true function. 


# Validation curve

A validation curve helps find the sweet spot between underfitting and overfitting and build a model that generalizes well. It is a plot of the model's error as a function of a model hyperparameter. 

In the region where both the training error and validation error are high, we have a model with high bias. In the region with the training error staying low and validation error increasing, we begin to see the effects of high variance. The validation error remains high as the model is not able to generalize from training data to new data. 

