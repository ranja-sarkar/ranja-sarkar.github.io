---
tags: [data, regression, machine-learning]
---

![viet](https://github.com/user-attachments/assets/2de96c5c-9ea3-4623-97ad-f85de4d6d77f)

**Linear regression** is a supervised machine learning algorithm, aiming to explain the relationship between one (or more) independent variable (s) and a dependent variable called response or target. The coefficients or weights on the independent variables are what the model learns while it is trained and optimized. A linear regression model is trained by either ordinary least squares (OLS) fit or gradient descent method. 

![111](https://github.com/user-attachments/assets/2678e9a4-7f1c-4c41-ab9e-10f5ab412e3a)


A linear model assumes that the effect of each independent variable on the response does not depend upon the rest of the independent variables. Linear regression therefore assumes a linearity in  coefficients (beta) of the variables. Epsilon is the irreducible error (un-measured). It is the unexplained variability in a dataset.

# Association & interaction of variables 

Association between two variables means the values of one variable relate in some way to the values of the other, and is measured by correlation (coefficient). 

Whether two variables are associated has nothing to do with whether they interact in their impact on a third variable. Interaction between two variables means the effect of one of the variables on a third variable differs at different values of the other. If two variables interact, they may or may not be associated. 

Interaction terms enable examining whether the relationship between the target and an independent variable changes depending on another independent variable. Scale changes of the variables affect the intercept (beta_0) and not the slopes/gradients (beta_1, beta_2, etc.) only if there’s no multiplicative term indicating interaction. An interaction term is effectively a multiplication of two (or more) variables that have a joint effect on the target. By adding interaction terms to the regression model, one can measure the effect of their interaction on the target. It’s crucial to [interpret](https://rinterested.github.io/statistics/lm_interactions_output_interpretation.html) the coefficient of the interaction (new variable) carefully to understand the direction and the strength of the relationship.


# Linearity 

A regression model also qualifies as a linear model when the independent variable is polynomial (quadratic, cubic, quartic, etc.), in nature. Linearity lies with the beta coefficients so betas are the linear parameters along with the y-intercept.

<img width="175" height="164" alt="1" src="https://github.com/user-attachments/assets/5b4efd05-0ed5-4202-98e1-5ccc10cab79e" />


Linearity happens when the equation is additive and the effects of each component can be easily separated. A non-linear relationship between X and Y (response) might thus exist while preserving the linear model. 

<img width="353" height="164" alt="2" src="https://github.com/user-attachments/assets/e0219a33-9d8c-4f74-8aaf-917aa8344d57" />

A simple scatter plot can reveal a curvilinear or nonlinear relationship. Inspection of residuals also reveals if a linear model is appropriate to fit a dataset.  

📌 Example

Let us investigate an equation where, x1 is a continuous feature and x2 is a Boolean flag taking values 0 or 1.  

For x2 = 1, we have y = 310 + 25x1 

For x2 = 0, we have y = 300 + 20x1 

We see when x1 = 0, the y-intercepts are different for the binary values of x2. With an interaction term, the effect of x1 on y is different for the two x2-values. 


The larger the difference in slopes or regression coefficients, larger the interaction effect on the response. 

📌 **Note**: Higher-order interactions between variables are possible. One can create interaction terms for numerical continuous as well as categorical variables. By using interaction terms, one can make the specification of a linear model more flexible which can result in a better fit to the data and better predictive performance of the model.

-----

A measure to assess the goodness of fit to data is called the coefficient of determination, as it determines how well the numeric predictions approximate the true data points. There’s an irreducible error term in the regression equation that collects all the unmodeled parts of the data.

📌 Optimization methods

The OLS algorithm minimizes the sum of squared errors (SSE) wherein the cost or loss function is mean squared error (MSE = SSE/n) and optimization occurs in closed form. In fig.1 below, number of independent variables is m, the number of observations/rows in the dataset is n, and the y-intercept is also called the bias. The squaring of errors prevents negative and positive terms from canceling out in the sum and gives more weight to points further from the regression line, punishing outliers.


![lr](https://github.com/user-attachments/assets/c5860948-248b-44fa-beb5-2cdfb263d40c)

If the errors follow a normal distribution, OLS becomes MLE (maximum likelihood estimation) providing a probabilistic framework to draw inference from model estimates.


The gradient descent algorithm is an iterative process and minimizes the loss function by calculating the function derivative/slope and updating the weight/parameter after each iteration. This method therefore enables learning by making corrective updates to the estimates that move towards an optimal combination of parameters.  

![gd](https://github.com/user-attachments/assets/bb7012c9-8d7c-4ead-a485-76c8828d1969)


Post training a model, we might observe overfitting (the algorithm captures noise in the data), regularization of features helps reduce variance. Regularization prevents overfitting by not generating high coefficients for sparse predictor variables, also stabilizes the estimates especially when there's collinearity in data.

For an algorithm that involves non-convex optimizations (ones with local minima and maxima) adding (independent) variables could make it complex, harder to find the best set of model parameters and result in higher bias. However, for algorithms like linear regression with efficient and precise machinery, added variables will only always reduce bias. 

📌 Regularization methods

Explicit regularization is where one explicitly adds a term to the (often ill-posed) optimization problem. These terms could be priors, or constraints. The regularization or penalty term imposes a cost on the optimization function to make the optimal solution unique. Explicit regularization of regression models almost always ensures optimal model complexity. Implicit regularization includes early stopping which is prevalent in stochastic gradient descent algorithm used for training/optimizing deep neural networks. 

A regression model is represented by a number of columns (m), a number of rows (n) in the dataset and regression coefficients or weights (w) on the independent variables. The loss function J in a vanilla (basic) linear model is a squared term - square of the deviation of predicted value from actual value.

![jbasic](https://github.com/user-attachments/assets/af784587-252c-41f6-a0d5-3a5fc36dc109)


Regularized regression models, Lasso (L1) and Ridge (L2) are used for feature selection and reducing complexity of the model thereby enhancing model interpretability. There's a third type - ElasticNet that allows a balance of both L1 & L2 penalty terms, leading to better model performance in some cases. 


![l1](https://github.com/user-attachments/assets/fd0c443f-baf9-4fc4-8115-8801d1566b16)

![l2](https://github.com/user-attachments/assets/93cfea65-e969-4678-87f9-2d9c13725971)

<img width="514" height="75" alt="en" src="https://github.com/user-attachments/assets/95f30573-e9aa-4656-8c4a-5f5313e0800f" />







The terms ‘regressor’ (predictor or independent or explanatory variable) and ‘covariate’ may be used interchangeably, except that the latter must be used when there’s potential confounding. 

In L2 (Ridge) regularization, the regression coefficients are found by minimizing the L2 loss function and in L1 (Lasso) regularization, they're found by minimizing the L1 loss function. 




The L2 loss function is differentiable and hence, Ridge (L2) has an edge over Lasso (L1). There’s a mixing parameter beta in the elasticnet (EN) that balances L1 and L2 to get the best of both appraoches. When alpha is zero, we’re back to ridge and when alpha is 1, we’re back to lasso.







L2 regression retains all features, reducing the impact of less relevant features by shrinking their coefficients, L1 regression can set some coefficients to zero, effectively selecting a subset of most relevant features. If higher number of coefficients are forced to zero, it tends to increase the bias in the model. So tuning alpha ([0, 1]) to low values ensures the bias-variance tradeoff is well dealt with. 




🎯 Model Assessment

The sum of squared residuals (SSR) is a loss function. The goodness of fit (metric) is R^2, represented in terms of SSR (or SSE) and SST (total sum of squares). R^2 increases if the degree of freedom (n-m-1) of the dataset decreases and hence, the model loses its reliability. 

Please note that (n-1) is the degree of freedom for a single parameter or variable coefficient to be estimated. Degree of freedom is the number of independent parameters that a statistical analysis can estimate, in short the number of parameters free to vary. 





Additional model complexity is penalized with adjusted R2 , where adj. R^2 is a modified model assessment metric. Its value increases from R^2 when the new term improves the fit and decreases from R^2 when the term doesn’t improve the fit. In other words, adj. R^2 compensates/adjusts for inclusion of an irrelevant or unrelated variable term in the model and therefore, is an appropriate metric for evaluation. 

Resampling methods like cross-validation are used for better measurement or model assessment. 

