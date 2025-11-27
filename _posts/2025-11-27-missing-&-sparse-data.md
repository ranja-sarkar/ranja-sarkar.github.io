---
tags: [data-handling, exploration, analysis]
---

Ranja Sarkar

-----

Missing values in tabular data occur when information is either not available or difficult to find. Grasping the underlying reasons of the absence of data and scrutinizing the nature of missingness are crucial. Often, understanding the data-generating  mechanism becomes important. 

![11](https://github.com/user-attachments/assets/04f4a9ae-2a76-4cf1-8ff1-b3cef401bf7d)

Sparse data is subtly different from missing data. Some values are not present in missing data whereas values are present but zero in sparse data. We often come across sparse datasets with many variables having zero values, presenting challenges in data preparation for training a model. Values are known in sparse data unlike missing data, but they're not useful. This makes it difficult to identify the relevant features in sparse tabular data. If all features are used for machine learning (violating maximum relevance-minimum redundancy), overfitting of model occurs. On the other hand, if too many features are removed (too much data compression), we are at a risk of losing valuable information. 

![22](https://github.com/user-attachments/assets/7181383c-6ee5-46e9-9cb4-149fd24c3738)


**Missingness** is absence. **Sparsity** is scantiness.

-----

**Handling missing data** demands a nuanced approach, far beyond quick fixes. If a dataset contains a large percentage of missing values, their presence can be detrimental to statistical estimation. 

There exist [missingness patterns](https://github.com/ranja-sarkar/ranja-sarkar.github.io/blob/e840bbe96ba301e263f9f0e23cd405fba268ba0b/_posts/assets/kjae-miss.pdf) viz.,

1. Missing completely at random (MCAR)

2. Missing at random (MAR)

3. Missing not at random (MNAR)

For filling in the gaps or imputing correctly, we must spot the profound business implications of our choices, as missing values may harbor insights capable of driving real impact. Leveraging domain expertise is essential, otherwise the outcome may be biased or erroneous. Missingness thus requires delving deeper into its root causes and tailoring the methods of imputation accordingly. A [benchmark of data imputation methods](https://www.frontiersin.org/journals/big-data/articles/10.3389/fdata.2021.693674/full) is required to guide our data preprocessing method selection.

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
