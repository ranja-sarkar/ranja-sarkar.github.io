---
tags: [data, bias, variance, machine-learning]
---

Ranja Sarkar

![IMG_2900](https://github.com/user-attachments/assets/0e1b6eac-94fd-40df-a668-93df933f4505)

A model's bias and variance manifest in how the model underfits and overfits to data. 

A graphical illustration of bias and variance, accuracy and precision gives us an idea about what an optimal model is - the one with low bias and low variance.

<img width="447" height="422" alt="01" src="https://github.com/user-attachments/assets/b20c2667-8f26-4c68-b24e-75a7fd8a4b62" />

 
# Learning curve

A learning curve helps diagnose bias and variance in a machine learning (ML) model. 

![03](https://github.com/user-attachments/assets/937d6de6-1d65-461d-b6a8-462f65866e9c)

It is a plot of the model’s error as a function of the data, the datasize with which the model is trained. [Learning curves](https://scikit-learn.org/stable/auto_examples/model_selection/plot_learning_curve.html) help check the scalability of ML models by providing an estimate of the cost to scale the models. 

-----

📌 Where does the error in predictions from the model come from? 

It either arises **from variance (too much capacity)** that is, not enough information in the dataset, or **from bias (too little capacity)** that is, not enough representation of the true function. 

The prediction or test error is defined as:

**Error = Variance + Bias^2 + Noise**

Noise is the irreducible error term that cannot fundamentally be reduced by any model. The variance is a function of the irreducible error, variance measures how much on an average predictions vary for a given datapoint. 

The bias term is about how rough the model space is - how quickly in reality do values change as we move through the variable/feature space. The rougher the space, faster the bias term increases. We can think of bias as measuring a systematic error in prediction. 

-----

For a highly **biased or underfitted** model, there will be fairly quick convergence to high errors with the validation or test and train subsets of data. This is when training on more data will not help improve model performance. 

<img width="217" height="260" alt="111" src="https://github.com/user-attachments/assets/8246b9de-1624-46a2-94ff-cbd60bb1ade4" />

Considering additional features in the dataset (horizontal expansion of data) may solve for underfitting, as then the model is more equipped to learn proper relationships in the dataset.

<img width="508" height="174" alt="221" src="https://github.com/user-attachments/assets/928439d5-c186-4e50-8870-289a4200b217" />

Increasing model capacity addresses underfitting. With increased capacity, the model learns and memorizes the data and generalizes well to new data.

-----

For a **high-variance or overfitted** model, there will be a fairly large gap between the errors produced by the validation or test and train sets of data as the model performs well for the train set but poorly for the validation or test set. 

What happens is the model captures noise too from the data, so having more model parameters than necessary leads to poor generalization. Generalization isn’t just about quantity, it’s also about quality of data and the right level of model complexity. For example, neural networks owing to over-parameterization tend to over-learn in general. So early stopping which is tuning the hyper-parameter 'epochs' helps prevents prevent overfitting of neural nets to data.


<img width="212" height="254" alt="333" src="https://github.com/user-attachments/assets/23759bce-ff3b-46d7-a108-63c74fd42801" />

Feeding more data during training of the model can help improve model performance, as then the model is able to generalize the relationships in the dataset.

<img width="193" height="259" alt="332" src="https://github.com/user-attachments/assets/d5939684-94e6-4e41-b334-75eaf0c629de" />

Explicit regularization means adding terms to the error, which prevents overfitting as the variance is reduced.

In a world with imperfections and finite data, there is a [tradeoff](https://scott.fortmann-roe.com/docs/BiasVariance.html) between minimizing the bias and minimizing the variance of a model.



# Validation curve

A validation curve helps find the sweet spot between underfitting and overfitting and build a model that generalizes well. It is a plot of the model's error as a function of the hyperparameter.

<img width="638" height="432" alt="02" src="https://github.com/user-attachments/assets/9dac74be-151b-492e-8763-b4d25df967d1" />


In the region where both the training error and validation error are high, we have a model with high bias. In the region with the training error staying low and validation error increasing, we begin to see the effects of high variance. The validation error remains high as the model is not able to generalize from training data to new data. 

