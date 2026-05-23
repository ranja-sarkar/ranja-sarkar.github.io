---
tags: [statistics, data]
---


![med1](https://github.com/user-attachments/assets/1478937b-a23f-4842-8a6f-f99d2856b973)


There are two schools of thought or approaches in statistical tests. One is frequentist, another is Bayesian. 

The frequentist approach is how often an outcome happens over repeated runs of the experiment/test. It’s an objective view of whether an experiment is repeatable. In the **frequentist** culture, relative frequency of occurrence of an event (observed in repetitions) in an experiment is a measure of the probability of that event. The **Bayesian** approach is a subjective view of the same. [Bayesian](https://github.com/ranja-sarkar/ranja-sarkar.github.io/blob/3dab2be104f4905452c182d3e1d53218b277e8ad/_posts/assets/Springer%20Nature_2020.pdf) takes into account how much faith we have in our results.

![100](https://github.com/user-attachments/assets/695f4f90-5612-48df-bb99-13d8d7203bac)
![200](https://github.com/user-attachments/assets/7f57336d-50ab-410a-a43a-f7f4ae56b992)


It includes prior knowledge about the data and personal beliefs about the results (likelihood). We start with a belief (prior) and we strengthen/weaken the prior with each evidence/datapoint that is, we update the belief to a degree. The updated belief is posterior probability. In the **Bayesian** culture, we’re uncertain about our model but the ground truth (reality) is our data; the focus is on the degree of belief about an unknown. 

*Probability is a measure of how likely something is, given our current knowledge.* 

It is all about beliefs in a Bayesian approach. The data we collect updates our prior (initial) belief. The posterior represents our updated understanding. Bayesian statistics finds the likelihood of alternatives explaining the data but strictly says these alternatives are driven by priors, which are informed or sensible but rarely objective. Bayesianism leaves a room for subjectivity. Bayesian thinking is about changing our mind and updating how we understand the world. The data we observe/collect is all that's real, so our beliefs ultimately need to shift until they align with the data.

---

The **law of large numbers** states that when a collection of random variables is a large sample, the **sample mean converges to true or expected mean if it exists**. The law applies to the mean obtained from a large number of repeated trials and claims that this value converges to the **expected value**. For a small sample, **there's a difference between these values called the error**.

Mean value is the observed (empirical) value, the one calculated from experimental measurements on collected data. Expected value is the theoretical (most likely) value, calculated from probability distributions. 

---

The **central limit theorem (CLT)** states that, given a sufficiently large sample size, the sampling distribution of the mean for a random variable approximates a normal distribution regardless of it’s distribution in the population. Below is the Wikipedia defnition.

<img width="446" height="82" alt="stats" src="https://github.com/user-attachments/assets/b39b31d9-170b-4487-8050-fc806e7fb43d" />

CLT is vital for two reasons, the normality assumption and the precision of estimates. The normality assumption is vital for parametric hypothesis tests of the mean. One might think that these tests are not valid when the data are non-normally distributed. However, if our sample size is large enough, CLT kicks in and produces sampling distributions that approximate a normal distribution. This fact allows us to use these hypothesis tests even when our data are non-normally distributed as long as the sample size is large enough. 

The 'precision of estimates' property of CLT becomes relevant when we use a sample to estimate the mean of an entire population. With a larger sample size, the sample mean is more likely to be close to the real population mean. In other words, the estimate becomes precise. 

It's mentionworthy here that **accuracy** and **precision** cannot be used interchangeably. Accuracy is being true to intention (degree of closeness of measured value to true value) while precision is true to itself (degree of closeness of repeated measured values).
---

Descriptive statistics helps draw inference about a sample. Inferential statistics helps infer about the population. If the sample is representative of the population, both stats yield same results.

**Probability** and **likelihood** are different terms. Probability is finding the chance of outcomes given a data distribution, and likelihood is finding the most likely distribution given the outcomes. Since likelihood is not probability, one can obtain likelihood greater than 1. 
Having stated this, it may be helpful to conceptually think of likelihood as "probability of the data given the parameters".

---

# Test types

The question we ask totally drives a statistical analysis. And asking the right question improves the [inference](https://lakens.github.io/statistical_inferences/).

Depending on our objective, we perform a **statistical test** which is typically a design-based approach. The test has a hypothesis to start with, and there's a measure. 

 📌 **Parametric tests**

If the objective is to find the correlation or linear relationship between two continuous variables, the Pearson correlation coefficient measures that only if the data is normally distributed. Due to this assumption, it's a parametric test. Pearson correlation is sensitive to outliers in data, a large sample is typically used in this test for reliable results. 

A T-test is a parametric test which measures whether a given cofficient/weight of a variable is significantly different than zero. 

While the correlation coefficient (Pearson) is easy to calculate and provides a measure of the strength of linear association in the data, it has its limitations.
In a [research study](https://github.com/ranja-sarkar/ranja-sarkar.github.io/blob/0df2e673d8a8a1b63e7b24e1313264e9abfdfed5/_posts/assets/corr.pdf), it has been found the range of observed data has an impact on the coefficient value.  If necessary, one should look into alternative methods as well.

📌 **Non-parametric tests**

If there's no assumption, we perform a non-parametric test and usually a Spearman correlation coefficient is checked. Spearman correlation coefficient is a measure of the monotonic (linear or nonlinear) relationship between two continuous or categorical variables and it's typically not sensitive to outliers. Kendall's tau is another coefficient that measures the association between categorical variables based on their ranks, and a small sample would suffice for this test.

If we have to compare unpaired or independent groups, we perform unpaired T-test, or a non-parametric test like Mann-Whitney test depending on the data.

The selection of a test depends on the objective and the type of data used in the test. 

<img width="628" height="245" alt="222" src="https://github.com/user-attachments/assets/e108713e-7ee0-4c7f-bb93-85f962176127" />

💡 Association between two variables is measured by correlation. Interation between two variables is different; if two variables interact, they may or may not be [associated](https://www.theanalysisfactor.com/interaction-association/).

📌 **Parametric models**

If the objective is to predict a target from one or more variables in the data, we perform regression (parametric model). 

Parametric models have some assumptions in place, like the normality of **residuals** which are the **differences between prediction (fitted response) and actual (observed response)**, the equation being linear in the coefficients/parameters of predictor variables. Independent or predictor variables if skewed in their distributions usually undergo transformation to normal (Gaussian) distributions while training linear models like regression, ANOVA so the inference or conclusions drawn from these models or tests are more reliable. 

💡 [Analysis of variance (ANOVA) and linear regression](https://www.linkedin.com/pulse/why-anova-linear-regression-same-analysis-the-analysis-factor-llc-tn8ff) are the same, just the results of the analyses are presented in different ways. 


📌 **Non-parametric models**

Non-parametric models like kNN, decision tree do not have the normality assumption. A variable transformation is usually not required while training non-linear models. Yet, predictions from such models often become reliable when the independent variables are normal.

Normality helps by offering better properties due to the CLT.

---

Asking the right question to solve a problem is similar to using the right measure as a test statistic.

[Data visualization](https://ranja-sarkar.github.io/2025/12/02/data-visualization.html) is an essential element of data exploration and understanding. For example, a [scatter plot](https://seaborn.pydata.org/generated/seaborn.scatterplot.html) helps us understand which measure (correlation coefficient etc.) to use for the data. The plot helps identify linear, nonlinear relationships between variables and spot outliers (if any) which may influence the correlation. 

While a box plot visually represents inter-quartile range (twice of quartile deviation), a [violin plot](https://plotly.com/python/violin/) shows the shape or density distribution of data. A violin plot must be used to explore skewed data. 

<img width="357" height="284" alt="vp" src="https://github.com/user-attachments/assets/314d9b9b-0fd9-4c9c-9428-3cd4405f8516" />

-----

Tests also measure central tendency and dispersion of data. 

📌 **Central tendency**

**Mode** is the best measure of central tendency for nominal qualitative (categorical) data, and **median** is the best for ordinal qualitative data. For interval/ratio types of quantitative (numeric) data, median is the best for a skewed distribution and mean for a normal distribution.

<img width="489" height="214" alt="sk" src="https://github.com/user-attachments/assets/1bd51666-8008-4c78-ac02-22fd023df229" />

While linear regression estimates conditional mean by minimizing squared residuals (OLS method), [quantile regression](https://www.aeaweb.org/articles?id=10.1257/jep.15.4.143) estimates quantile functions. Quantile regression estimates the quantiles which include the median by modeling entire conditional distribution of the response (dependent variable), making it robust to outliers and useful for skewed data. The mean/average does not tell the whole story, linear regression gives one "best fit" mean line; quantile regression provides multiple lines, showing how predictors affect lower, middle, and upper parts of the response's distribution. 

<img width="544" height="211" alt="333" src="https://github.com/user-attachments/assets/d909a9f8-d566-410a-b66a-d885610448bd" />


The first 4 [moments](https://gregorygundersen.com/blog/2020/04/11/moments/) of a distribution are mean, variance, skewness, kurtosis. While a symmetric distribution always has zero skewness of zero, the opposite claim is not always true that is, a distribution with zero skewness may be asymmetric.

<img width="283" height="248" alt="ks" src="https://github.com/user-attachments/assets/83041fd3-9568-4dd9-a712-4245bb293b26" />


💡 While skewness is a measure of the relative size of the two tails of a distribution, it is positive or negative depending on which tail is larger, kurtosis is a measure of the size of two tails together relative to the distribution.

---

There are **power transformations** that independent variables in a dataset usually undergo if they follow right-skewed or left-skewed distributions. Power transforms refer to a class of techniques utilizing a power function (logarithm or exponent) to make the probability distribution of the variable Gaussian (normal). Such transformations helps stabilize the variance of independent variables in the dataset.

The [Box-Cox transformation](https://feature-engine.trainindata.com/en/latest/user_guide/transformation/index.html) is a generalization of the power transformations family. They find a parameter 'lambda' that best transforms the variable, for example lambda = -1 is a reciprocal transform, lambda = 0 is a log transform, lambda = 0.5 is a square root transform.

<img width="225" height="41" alt="bc" src="https://github.com/user-attachments/assets/e5f64f82-e372-4410-a45d-2e038912351c" />

---

📌 **Dispersion**

A simple measure of **data dispersion** is its range. However, **variance** and standard deviation best serve the purpose.

<img width="457" height="162" alt="sd" src="https://github.com/user-attachments/assets/cc9e5a65-5ff3-4cde-916f-fe01d16ac3ad" />

The standard deviation (s) of a data sample is the degree to which individuals (records/observations) within the sample differ from the mean of the sample. The **standard error** of the sample (size n) is an estimate of how far its mean is likely to be away from the population mean. It is defined as s/sqrt(n).

---

**Covariance** is another measure, which depicts how two variables in a dataset move wrt each other. 

<img width="502" height="182" alt="cov" src="https://github.com/user-attachments/assets/b53b3e0c-f3b1-4ff5-8a49-f865cfdcac45" />

Covariance is related to correlation. So we are back to correlation (cor), the measure with which we started the topic.

<img width="293" height="78" alt="corr" src="https://github.com/user-attachments/assets/b4f054c1-e0b3-4dd3-bd4e-338f71bbb482" />

We shall see how correlation and covariance (cov) are different. Well, covariance is unstandardized version of correlation.

<img width="443" height="112" alt="co0" src="https://github.com/user-attachments/assets/1d652478-aa2f-46c0-b73e-528173132df4" />

Correlation is a measure of not only how two variables move wrt each other, but also how strongly those two are related and its value lies between -1 and +1.

<img width="529" height="203" alt="corr" src="https://github.com/user-attachments/assets/8176e107-80c9-4ddc-b5c0-a51a30e2b0b3" />

💡 Covariance provides the direction of relationship and has dimension (as the variable scale/unit). In a [covariance matrix](https://www.theanalysisfactor.com/covariance-matrices/), each diagonal element is the variance of a variable and the off-diagonals are covariances between two variables.

💡 Correlation provides the direction and strength of relationship and is dimensionless.  In a correlation matrix, the diagonals are unity. 

---

I shall wrap this post up by stating the two cultures of statistical modeling according to [Leo Breiman](https://github.com/ranja-sarkar/ranja-sarkar.github.io/blob/0bfc923a56cca1a92c2c782be8d08d6aa47a6326/_posts/assets/breiman.pdf).

1. **Data Model**, wherein the data-generating mechanism (some stochastic model) is assumed to be known and model parameters are estimated from the data. Example: linear regression.

2. **Algorithmic Model**, where the data-generating mechanism is unknown and uses an algorithm to find a function f(x) that operates on variables x in the data to estimate a response y. Example: Deep [neural network](https://ranja-sarkar.github.io/2026/02/12/neural-network.html).

Linear regression is also a neural network though, with a linear activation function. Therefore it's wise to use the term deep neural network or deep learning as an example of an algorithmic model.

<img width="164" height="64" alt="ll" src="https://github.com/user-attachments/assets/0c967c03-2de9-4315-a57b-099827b5f0c2" />

<img width="218" height="68" alt="ll1" src="https://github.com/user-attachments/assets/bc844b1f-8a2e-4744-91fe-a2dbface2bfb" />


If we use a linear activation function, no matter how many layers we stacked, neural networks would behave like a single-layer perceptron because the combination of linear functions is still a linear function. 

# References

1. [Bayesian Statistics the fun way](https://bookdown.org/pbaumgartner/bayesian-fun/)

2. [Not a Big Deal](https://www.statsig.com/blog/bayesian-vs-frequentist-statistics)

3. [Bayesian Models](https://www.r-bloggers.com/2019/05/bayesian-models-in-r-2/)
