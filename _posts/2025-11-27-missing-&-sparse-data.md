---
tags: [data-handling, exploration, analysis]
---

Ranja Sarkar

![named](https://github.com/user-attachments/assets/b35c1f2a-d7c9-4cca-8c4e-e7f1d9af34a8)

Missing values in tabular data occur when information is either not available or difficult to find. Grasping the underlying reasons of the absence of data and scrutinizing the nature of missingness are crucial. Often, understanding the data-generating mechanism becomes important. 

**Missingness** is absence. **Sparsity** is scantiness.

![11](https://github.com/user-attachments/assets/04f4a9ae-2a76-4cf1-8ff1-b3cef401bf7d)

Sparse data is subtly different from missing data. Some values are not present in missing data whereas values are present but zero in sparse data. We often come across sparse datasets with many variables having zero values, presenting challenges in data preparation for training a model. 

![22](https://github.com/user-attachments/assets/7181383c-6ee5-46e9-9cb4-149fd24c3738)


Values are known in sparse data unlike missing data, but they're not useful. This makes it difficult to identify the relevant features in sparse tabular data. If all features are used for machine learning (violating maximum relevance-minimum redundancy), overfitting of model occurs. On the other hand, if too many features are removed (too much data compression), we are at a risk of losing valuable information. 

-----

**Handling missing data** demands a nuanced approach, far beyond quick fixes. If a dataset contains a large percentage of missing values, their presence can be detrimental to statistical estimation. 

There exist [missingness patterns](https://github.com/ranja-sarkar/ranja-sarkar.github.io/blob/e840bbe96ba301e263f9f0e23cd405fba268ba0b/_posts/assets/kjae-miss.pdf) viz.,

1. Missing completely at random (MCAR)

2. Missing at random (MAR)

3. Missing not at random (MNAR)

For filling in the gaps or imputing correctly, we must spot the profound business implications of our choices, as missing values may harbor insights capable of driving real impact. Leveraging domain expertise is essential, otherwise the outcome may be biased or erroneous. Missingness thus requires delving deeper into its root causes and tailoring the methods of imputation accordingly. A [benchmark of data imputation methods](https://www.frontiersin.org/journals/big-data/articles/10.3389/fdata.2021.693674/full) is required to guide our data preprocessing method selection. Acoording to this 2021 paper, strategies of data imputation vary depending on the missingness pattern or nature (MCAR, MAR, MNAR).  

![dd](https://github.com/user-attachments/assets/970a0131-f944-4fb6-a472-718bd96dc5dd)


Out of these types, MNAR raises the level of difficulty of handling missing data, because the missingness falls in line with unobserved/implicit features and is capable of distorting the entire data analysis. I will discuss one method from each type, please read the [2013 paper](https://github.com/ranja-sarkar/ranja-sarkar.github.io/blob/e840bbe96ba301e263f9f0e23cd405fba268ba0b/_posts/assets/kjae-miss.pdf) for further details. 

💡 **Mean/median/mode Imputation**

The following scenarios arise while using a [pandas](https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.dropna.html) dataframe function (python) to drop rows or columns in tabular data having missing values.

-> dropna(): drops all rows with missing values.

-> dropna(how = ‘all’): drops the rows where all column values are missing.

-> dropna(thresh = minimum_value): drops rows based on a threshold/minimum 

-> dropna(axis = 1): drops all columns with missing values. 

The fillna() pandas function is used to impute with mean or median of the feature or column for continuous or discrete numeric data. Mean and median imputation can provide a good estimate of the missing values for normally distributed and skewed data respectively. However, mean imputation is sensitive to outliers, and median imputation essentially makes the assumption that the data is MCAR which might be not be true in every case. For categorical/qualitative data (nominal or ordinal), the best measures of central tendency are mode and median. 


💡 **Multiple Imputation**

This is a method wherein the missing information in a feature/column is filled by considering the information from other features in the dataset. This method can however be computationally expensive for large datasets. 

The reliance of random forest algorithm on bootstrapping and feature randomness inherently mitigates missing data issues, for example when a feature has missing values, splits on that feature are avoided during model training. It uses a straightforward approach of "surrogate split”, where missing values are substituted using correlated features or majority-class decisions. This retains the implicit simplicity and robustness of the algorithm.

The XGBoost algorithm can also handle missing data, an example is in [this article](https://link.springer.com/article/10.1007/s42452-020-3128-y)

Multiple Imputation by Chained Equations (MICE) and Fully Conditional Specification (FCS) find use in some cases. MICE, for example performs imputation for features with missing data within a separate model which makes it possible to capture complex interactions between them. FCS imputes missing values one at a time, conditional on observations, it then repeats the process multiple times to create several complete datasets. 

💡 **Maximum Likelihood Estimation (MLE)**

The assumption that the observed data are a sample drawn from a multivariate normal distribution helps to estimate the missing data, and it is done ny using conditional distributions of other (relatively complete) features. Expectation Maximization is a type of MLE that can be used to generate a new dataset in which the missing values have been imputed with values estimated by MLE.

-----

**Handling sparse data** too demands a nuanced approach. Using sparse data to train a model require good amount of computing resources owing to their large size. They require longer processing time which limits the throughput. There are methods to mitigate these challenges, other than feature hashing wherein each feature is converted into a fixed-length array of values using a hashing function (maps each to an index) that makes it feasible to store the features. 


![hash](https://github.com/user-attachments/assets/2993d0ee-86c2-4fef-80ff-6ff9e1903981)

💡 Setting a threshold to the percentage of non-zero values in a feature also helps decide which feature to drop from the data. The one falling below this threshold if removed reduces sparsity of the dataset. There are other methods to do the attain the objective for example, PCA, t-SNE. 

💡 **PCA** is an unsupervised learning algorithm that identifies principal components (PCs) of the data along principal axes, the directions in which the data varies most. PCs represent the data in a lower-dimensional space with most variability, and preserve maximum information. PCA thus helps identy the top features to train a model, ensuring the model is reliable.  

💡 t-distributed Stochastic Neighbour Embedding or **t-SNE** is also an unsupervised learning algorithm. It is a nonlinear dimensionality reduction technique used to cluster (also visualize) high-dimensional data. A low dimensional embedding of the data is obtained with t-SNE while preserving global structure of the data. To use t-SNE with sparse data, the sparse matrix must first be converted into a dense matrix. 

![ss](https://github.com/user-attachments/assets/bba8800d-b418-497c-af47-3988852736c9)

💡 There are some machine learning algorithms designed to perform well with sparse data. Support Vector Machines (SVM) performs well with sparse data because it efficiently uses a subset of data known as support vectors for maximum margin and reliable training of the model. If there are non-linearities in the feature relationships, a flexible and data-adaptive approach (non-parametric model) is k-Nearest Neighbours (kNN). [XGBoost](https://xgboosting.com/train-xgboost-with-sparse-array/) incorporates sparsity-aware split finding while optimizing the model, providing robust handling of sparse data.  

-----

When working with **text data** and [natural language processing (NLP)](https://smltar.com/embeddings), sparsity arises because many documents do not contain most words resulting in zero values. There are special data structures and algorithms for handling such data. For example, an array can more efficiently store the locations and values of the non-zero elements (not all elements) than other data structures. 

-----

Finally, **sensitivity analysis** which is defined as studying how the uncertainty in model output can be allocated to its inputs, the sources of uncertainty is important. Assumptions made while imputation of missing values cannot be definitively validated for correctness hence, sensitivity analysis becomes essential to evaluate the robustness of the model trained with processed (missing & sparse) data. 

