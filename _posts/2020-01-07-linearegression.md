
Ranja Sarkar


---

A linear model assumes that the effect of each independent variable/feature on the dependent variable/target does not depend upon the rest of the independent variables. Linear regression assumes a linearity in (beta-) coefficients of the variables. 

If two variables interact, they may or may not be associated. Whether two variables are associated says nothing about whether they interact in their impact on a third variable. Association between two variables means the values of one variable relate in some way to the values of the other, and is measured by correlation. Interaction between two variables means the effect of one of those variables on a third variable differs at different values of the other. 

Linear parameters in regression model

A regression model still qualifies as a linear model because it is the independent variable that is polynomial (quadratic, cubic, quartic, etc.), and not the beta coefficient. A non-linear relationship between Xs and Y (response/target) might exist while preserving the linear model, it happens when the equation is additive and the effects of each component can be easily separated. 

So the linear parameters are:





intercept (beta_0)



Slope or slopes (how much Y differs on an average for each unit difference in X, there can be multiple Xs and each one has its own slope) → beta_1, beta_2, etc.

epsilon is the residual error which is an unmeasured variable. It explains the residual variance, the unexplained variability in a dataset.

Univariate or bivariate data inspection is necessary to detect the relationships in the dataset. A simple scatter plot can reveal a curvilinear or nonlinear relationship. Inspection of residuals also reveals if a linear model is appropriate. A scatter plot of residuals indicates if a polynomial model (polynomial term or terms in the equation) would be a better fit to data. 

Interactions in regression model

interaction terms enable examining whether the relationship between the target and an independent variable changes depending on another independent variable.

Scale changes of the variables affect the intercept and not the slopes only if there’s no multiplicative or polynomial term indicating interaction.



An interaction term is effectively a multiplication of two (or more) variables that have a joint effect on the target. 

📌 Example

Let us investigate an equation where, x1 is a continuous feature and x2 is a Boolean flag taking values 0 or 1.  

For x2 = 1, we have y = 310 + 25x1 

For x2 = 0, we have y = 300 + 20x1 

We see when x1 = 0, the y-intercepts are different for the binary values of x2. With an interaction term, the effect of x1 on y is different for the two x2-values. 

beta_2 is the difference in the intercepts obtained with the x2-values, and beta_3 is the difference in slopes of x1 obtained with the x2-values. The regression lines might or might not intersect. 

The larger the difference in slopes or regression coefficients, larger the interaction effect on the response. 

📌 Note




Higher-order interactions between features are possible.



One can create interaction terms for numerical or continuous variables. 



By adding new variables (interaction terms) to the regression model, one can measure the effect of their interaction on the target. It’s crucial to interpret the coefficient of the interaction term carefully to understand the direction and the strength of the relationship.



By using interaction terms, one can make the specification of a linear model more flexible which can result in a better fit to the data and better predictive performance.



References





https://rinterested.github.io/statistics/lm_interactions_output_interpretation.html



https://janhove.github.io/posts/2017-06-26-continuous-interactions/



https://joelcarlson.github.io/2016/05/10/Exploring-Interactions/



https://www.theanalysisfactor.com/using-marginal-means-to-explain-an-interaction/




Interaction terms enable examining whether the relationship between the target and an independent variable changes depending on another independent variable.

