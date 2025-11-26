---
tags: [physics, models, machinelearning]
---

Ranja Sarkar

The [paper by Jared Willard et al (2020)](https://github.com/ranja-sarkar/ranja-sarkar.github.io/blob/bd0e97bb7a75469e16be738cf528f040927ed0d7/_posts/assets/Phys-ml.pdf) about the integration of Physics with machine learning makes for an insightful read. The paper provides the objectives of such integration, **a brief summary of which** is as follows. Please read the paper for more details.
 
 **Finding representations of more complex physics-based models**
    
Reduced-order models (ROMs) are those computationally inexpensive representations. Constructing ROMs involves dimensionality reduction that attempts to capture most important dynamical characteristics of often large, high-fidelity simulations and models of physical systems.

**Discovering governing equations**
   
Many dynamical systems (e.g. finance) have no formal analytic descriptions and often, data is abundant in such cases but the underlying governing equations remain elusive. There’re some data-driven techniques for identification of unknown, potentially governing equations of nonlinear systems and are based on the Occam’s razor principle, where the goal is to use only a few equation terms to describe the given system. 

**Solving PDEs**

Governing equations are known for many physical systems but, direct numerical solutions of PDEs using common traditional methods prove to be expensive, hashtag#neuralnetworks have shown success in approximating solutions across different kinds of physics-based PDEs. 

**Uncertainty quantification** 

This is of great importance as it makes it possible to characterize the quantiles and skews in distributions and allows for examining how close predictions are to being acceptable or sensitivity analysis of input features. Variants of hashtag#neuralnetworks have exhibited success here, as a surrogate for expensive traditional simulations and ones that have greater scalability than Gaussian processes. Also, the integration of prior physics knowledge has the potential to allow for better characterization of uncertainty. 

**Data generation**

Physics-based approaches for data generation often rely on running simulations or conducting physical experiments, which tend to be very time consuming. Also, they are restricted by what can be produced by only physics-based models. Hence, there's an increasing interest in hashtag#deeplearning approaches like GAN, VAE, that learn data distributions in an unsupervised setting and have the potential to generate new data beyond what could be produced by traditional approaches. 

------

Along similar line is **Ben Moseley's** [thesis](https://ora.ox.ac.uk/objects/uuid:b790477c-771f-4926-99c6-d2f9d248cb23/files/d8p58pd35h).
His doctoral research thesis is about Physics-informed machine learning. One of the thesis chapters talks about scalable [Physics-informed neural network (pinn)](https://benmoseley.blog/my-research/so-what-is-a-physics-informed-neural-network/).

<img width="484" height="194" alt="pinn" src="https://github.com/user-attachments/assets/acef87ff-dad7-41c4-9f17-96493ae947dc" />


This broadly come under [Scientific Machine Learning (SciML)](https://github.com/SciML), the open-source software for which is available [here](https://sciml.ai/).

![sciml](https://github.com/user-attachments/assets/cc5ba07e-61cf-4d52-ab56-d31708b208f3)


