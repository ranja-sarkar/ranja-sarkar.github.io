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


