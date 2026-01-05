---
tags: [machine-learning, model, data, operations]
---

Ranja Sarkar

<img width="288" height="415" alt="tabo" src="https://github.com/user-attachments/assets/25d9f85e-c065-44fa-adc9-68065fa240d7" />

The critical points in model development lifecycle (MDLC) require careful consideration, to avoid setbacks and wastage in terms of expenses and resources. 
Mistakes identified in the lifecycle phases, from design to deployment must be addressed in time to prevent derailment. The model can be a decision tree 
and other machine learning ones, or neural networks and any deep learning model.

The term MDLC is inspired from SDLC (software developemnt lifecycle). Well, there are 7 critical points according to me.

✔️ Goal 🎯

Objectives should be well-defined with measurable goals, without which evaluating success of the project becomes difficult. Misaligned (to stakeholders) goals lead to infeasibility. Model evaluation as well as business metrics should be clear, hence end users must be involved in the early design phase of the project.

✔️ Data 

The model is only as good as the sample data it is trained with. Training a model on bad quality data would yield unreliable outcomes. Appropriate data preprocessing for missing values, category encoding etc. is crucial. Data quality can be good which means it is representative and consistent or can be bad which means it is biased, noisy, and inconsistent. Using information from the test dataset during model training (data leakage) could go unnoticed but would impact the model outcome severely. 

✔️ Model Selection

Choice of the algorithm to solve a problem is critical - training simple models for complex problems may lead to underfitting (failing to learn data pattern) and training unnecessarily complex models for simple tasks is not a good idea either, as it might lead to overfitting (failing to generalize to new, unseen data). 

Also, opting for fancy architectures without understanding the problem context might lead to wasted time and compute resources. 

✔️ Model Parameters 

Adopting arbitrary or default values of hyperparameters may result in suboptimal model even if the chosen algorithm is the most suitable for the problem at hand. The model cannot necessarily learn the relationships in a dataset if it cannot discover while training how some functions do a better job of minimizing the loss function, or if regularization of features in the dataset forbids these functions. Tuning or adjusting the hyperparameters appropriately ensures the model correctly represents the data.

✔️ Model Transparency

It is important that the mechanism of evaluating the model is robust. More than one metric is required to assess the performance, while exposing the model to a number of edge cases. Lack of interpretability results in opaque models. In high-stake domains like healthcare, it is essential that the model’s behavior, inputs, predictions, and limitations can be explained to stakeholders to gain their trust in the solution. 

The value of a model lies in the understanding shared between the developer and the end-user. In this regard, artifacts like [model cards](https://modelcards.withgoogle.com/) introduced by Google are useful.

✔️ Production Framework 

This one basically means the model deployment strategy - practitioners turn to established frameworks once the model is trained, evaluated, validated, and has the desired level of interpretability. Integration is an engineering process that requires not only technical expertise but careful planning to make the model a functional part of the system. Latency, throughput (data pipeline), memory efficiency, model retraining are aspects of the plan. Even well-performing models could be rendered useless in production environment if deployment is not well conducted. 

✔️ Monitoring & Feedback

Once the model is served to end users, they have to understand the model predictions and trust them, else usage would eventually go down. Making the model outcomes actionable is a key indicator of success and user feedback helps continuous improvement and detect areas needing revision. Models need to be monitored and maintained. Real-world data evolves, and since the models feed on data, their performances often decay over time due to data or concept drift or changes in the environment. Tracking models, setting threshold for alerts and establishing retraining strategy are essential to combat performance degradation. Otherwise, the damage may have been done  by the time something wrong is noticed.  



