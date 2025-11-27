---
tags: [data-handling, exploration, analysis]
---

Ranja Sarkar

Missing values in tabular data occur when information is either not available or difficult to find. Grasping the underlying reasons of the absence of data and scrutinizing the nature of missingness are crucial. Often, understanding the data generating  mechanism becomes important. 

**Handling missing data** demands a nuanced approach, far beyond quick fixes. If a dataset contains a large percentage of missing values, their presence can be detrimental to statistical estimation. 

There exist [missingness patterns](https://github.com/ranja-sarkar/ranja-sarkar.github.io/blob/e840bbe96ba301e263f9f0e23cd405fba268ba0b/_posts/assets/kjae-miss.pdf) viz.,

1. Missing completely at random (MCAR)

2. Missing at random (MAR)

3. Missing not at random (MNAR)

For filling in the gaps or imputing correctly, we must spot the profound business implications of our choices, as missing values may harbor insights capable of driving real impact. Leveraging domain expertise is essential, otherwise the outcome may be biased or erroneous. Missingness thus requires delving deeper into its root causes and tailoring the methods of imputation accordingly. A [benchmark of data imputaion methods](https://www.frontiersin.org/journals/big-data/articles/10.3389/fdata.2021.693674/full) is required to guide our data preprocessing method selection.


