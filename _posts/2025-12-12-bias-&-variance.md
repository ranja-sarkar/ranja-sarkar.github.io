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

# Model complexity

The error is also a function of the model complexity.

📌 What does it mean by underfitting & low model complexity?

Our model’s so simple, it fails to adequately capture the relationships in the data. The high error is a direct result of the lack of complexity in the model.

📌 What does it mean by overfitting & high model complexity?

Our model’s so specific to the (train) data that it’s no longer applicable to new data samples. In other words, our model’s so complex that instead of learning true trend underlying the dataset, it memorizes noise. As a result of this, the model is not generalizable to unseen data that is, beyond data with which the model is trained.


<img width="280" height="163" alt="mc" src="https://github.com/user-attachments/assets/598ff1e3-b292-4674-92e2-9121268cbf46" />

For example, if more polynomial terms are added to a linear regression model, the resulting model complexity increases. This means bias has a negative first-order derivative or slope in response to model complexity while variance has a positive slope. In effect, the sweet spot for any model is the level of complexity at which the increase in bias is equivalent to the decrease in variance. If the model complexity exceeds this sweet spot, we are over-fitting while if the complexity falls short of the sweet spot, we are under-fitting. In practice, there is no analytical way to find this spot. We must explore differing levels of model complexity, then choose the complexity (level) that minimizes the error.  


📌 A **validation curve** helps find the sweet spot between underfitting and overfitting, to build a model that generalizes well. It is a plot of the model's error as a function of the hyperparameter.

<img width="638" height="432" alt="02" src="https://github.com/user-attachments/assets/9dac74be-151b-492e-8763-b4d25df967d1" />


In the region where both the training error and validation error are high, we have a model with high bias. In the region with the training error staying low and validation error increasing, we begin to see the effects of high variance. The validation error remains high as the model is not able to generalize from training data to new data. 

An optimal model aims to minimize bias as well as variance. It lays in the sweet spot - not too simple, not too complex. Hyperparameters may be used to control the the bias-variance tradeoff in models. For example, [kNN](http://vision.stanford.edu/teaching/cs231n-demos/knn/) is a classic one. We can observe the tradeoff in kNN directly by playing with the hyperparameter k which is the number of nearest neighbours. 

When k is small, only a small number of neighbors is considered during the classification vote. The resulting islands are a result of high variance, as classifications are determined by very localized neighborhoods. For medium k, we see smooth the regions that follow along the true decision boundary.

<img width="873" height="203" alt="10" src="https://github.com/user-attachments/assets/78ffbe12-dc84-4abd-8938-f14145f51f00" />

<img width="860" height="182" alt="110" src="https://github.com/user-attachments/assets/67a34c17-066f-4092-b92c-6aea8ecebfe5" />

For large k, we see very smoothed regions that deviate sharply from the true decision boundary, If we go too high, we’ll obtain a majority vote which is high bias. 

<img width="854" height="187" alt="111" src="https://github.com/user-attachments/assets/64d0a885-2a65-457d-9074-2b20a7e7a513" />

