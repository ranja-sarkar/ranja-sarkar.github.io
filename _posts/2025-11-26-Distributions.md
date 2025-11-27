--- 
tags: [probability, statistics]  
---
Ranja Sarkar

<img width="289" height="157" alt="bb" src="https://github.com/user-attachments/assets/ea82d644-9d6c-41f8-9c23-6c633dccada0" />

-----
During my doctoral research, I had used the software Mathematica by Wolfram. My visits to the Wolfram Mathworld page gradually became rare events. 
I visited it recently and landed at their pages of [Probability and Statistics](https://mathworld.wolfram.com/topics/ProbabilityandStatistics.html). 
And I couldn't help exclaim, 'how beautifully demonstrated!”

Maybe I was too distracted back then to have not noticed, or I was too much into partial differential equations (PDEs).

The French Mathematician, A. de Moivre developed 'normal distribution' as an approximation to [binomial distribution](https://mathworld.wolfram.com/BinomialDistribution.html). 

The [normal distribution](https://mathworld.wolfram.com/NormalDistribution.html) becomes a 'standard normal distribution' of a variate with zero mean & unity variance.  
 
The ratio of two standard normal variates gets us a [Cauchy](https://mathworld.wolfram.com/CauchyDistribution.html) variate.   
The square of a standard normal variate gets us a [Chi-squared](https://mathworld.wolfram.com/Chi-SquaredDistribution.html) variate.  

The addition/sum of Chi-squared variates gets us a [gamma](https://mathworld.wolfram.com/GammaDistribution.html) variate (another Chi-squared variate) and the ratio of two independent gamma variates gets us a beta variate.  
The beta distribution, for both shape parameters equal to unity that is, beta (1, 1) becomes a standard [uniform distribution](https://mathworld.wolfram.com/UniformDistribution.html).  

One can use [Box-Muller transformation](https://mathworld.wolfram.com/Box-MullerTransformation.html) on two independent standard uniform variates to arrive at two standard normal variates.  
 
I dug up the web deeper and found an [illustration](https://www.math.wm.edu/~leemis/chart/UDR/UDR.html) of the relationships between distributions.

------

Uniform distribution, wherein outcomes are equally likely and standard normal distribution are **continuous probability distributions**. In the [latter](https://github.com/ranja-sarkar/ranja-sarkar.github.io/blob/bfff302d9d74c8e00c0557045ce44960d4c97d0d/_posts/assets/nd.png), mean, median, and mode of the distribution coincide. The curve of the distribution is bell-shaped and symmetrical about the line x=μ (mean). The total area under the curve is 1. 

<img width="317" height="252" alt="iqr" src="https://github.com/user-attachments/assets/5039f80b-0ead-4809-ba87-85fe820148a6" />

Exponential (1-parameter) and Weibull (2-parameter) distributions are also continuous probability distributions. To know more about them, please refer to [the page](https://reliability.readthedocs.io/en/latest/Equations%20of%20supported%20distributions.html) of reliability engineering.

On the other hand, Bernoulli distribution is a **discrete probability distribution**, wherein a single trial has 2 possible outcomes. If X defines the outcome of the trial and P (y-axis) is the probability of success of 1 outcome, it follows a Bernoulli distribution.

<img width="255" height="184" alt="px" src="https://github.com/user-attachments/assets/a3393118-25e2-40d6-99b4-a5b5fd1bdbf3" />


In a binomial distribution, **n** identical trials have 2 possible outcomes in each and can be thought of as multiple independent Bernoulli trials. In a [Poisson distribution](https://mathworld.wolfram.com/PoissonDistribution.html), there are large number of rare events or occurences with unlimited outcomes. 

----

Fitting the [right kind of distribution](https://reliability.readthedocs.io/en/latest/Fitting%20a%20specific%20distribution%20to%20data.html) to a dataset is not straight-forward, there are many ways to write the equations of the distributions (PDF, CDF, etc.), and the distribution parametrization needs careful attention.

For example, where do we use the **Weibull distribution**?

It is largely used in reliability engineering. [Reliability](https://github.com/MatthewReid854/reliability?tab=readme-ov-file) is the probability that a system will perform its intended function adequately in a specified period of time. The Weibull distribution adapts to increasing, decreasing, and constant time-to-failure or time between events in mechanical systems. 

<img width="181" height="353" alt="wbd" src="https://github.com/user-attachments/assets/52a8989a-2cf4-4b86-a729-24105e3f8eef" />


