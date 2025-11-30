---
tags: [physics, models, machinelearning]
---

Ranja Sarkar

![tree](https://github.com/user-attachments/assets/7bc914de-82f2-4803-b4d4-831e76491b2f)


The [paper by Jared Willard et al (2020)](https://github.com/ranja-sarkar/ranja-sarkar.github.io/blob/bd0e97bb7a75469e16be738cf528f040927ed0d7/_posts/assets/Phys-ml.pdf) about the integration of Physics with machine learning makes for an insightful read. The paper provides the objectives of such integration, *a brief summary of which* is as follows. Please read the paper for more details.
 
 **Finding representations of complex Physics-based models**
    
Reduced-order models (ROMs) are the computationally inexpensive representations. Constructing ROMs involves dimensionality reduction that attempts to capture most important dynamical characteristics of often large, high-fidelity simulations and models of physical systems.

**Discovering governing equations**
   
Many dynamical systems (e.g. finance) have no formal analytic descriptions and often data are abundant in such cases, but the underlying governing equations remain elusive. There are some data-driven techniques for identification of unknown, potential governing equations of nonlinear systems and are based on the [Occam’s razor principle](https://www.newscientist.com/definition/occams-razor/), where the goal is to use only a few equation terms to describe the given system. 

**Solving PDEs**

Governing equations are known for many physical systems but direct numerical solutions of PDEs using common traditional methods prove to be expensive. Neural networks have shown success in approximating solutions across different kinds of Physics-based PDEs. 

**Uncertainty quantification** 

This is of great importance as it makes it possible to characterize the quantiles and skews in distributions and allows for examining how close predictions are to being acceptable or for sensitivity analysis of input features. Variants of neural networks have exhibited success here, as a surrogate for expensive traditional simulations and ones that have greater scalability than [Gaussian processes](https://thegradient.pub/gaussian-process-not-quite-for-dummies/). Also, the integration of prior Physics knowledge has the potential to allow for better characterization of uncertainty. 

**Data generation**

Physics-based approaches for data generation often rely on running simulations or conducting physical experiments, which tend to be very time-consuming. Also, they are restricted by what can be produced by only Physics-based models. Hence, there's an increasing interest in deep learning approaches like [GAN](https://ranjas.substack.com/p/generative-and-discriminative-models), [VAE](https://ranjas.substack.com/p/encoder-decoder-in-a-neural-network), that learn data distributions in an unsupervised setting and have the potential to generate new data beyond what could be produced by traditional approaches. 

------

Along similar line is **Ben Moseley's** [thesis](https://ora.ox.ac.uk/objects/uuid:b790477c-771f-4926-99c6-d2f9d248cb23/files/d8p58pd35h) (2022).
His doctoral research thesis is about Physics-informed machine learning. One of the thesis chapters talks about scalable [Physics-informed neural network (pinn)](https://benmoseley.blog/my-research/so-what-is-a-physics-informed-neural-network/).

<img width="484" height="194" alt="pinn" src="https://github.com/user-attachments/assets/acef87ff-dad7-41c4-9f17-96493ae947dc" />

This broadly come under [Scientific Machine Learning (SciML)](https://github.com/SciML), the open-source software for which is available [here](https://sciml.ai/).

![sciml](https://github.com/user-attachments/assets/cc5ba07e-61cf-4d52-ab56-d31708b208f3)


# References

1. [Validation of trustworthy SciML](https://github.com/ranja-sarkar/ranja-sarkar.github.io/blob/e23b92b2cac7a1b5a0b52b35dc4446ac6c3d20f5/_posts/assets/validation_sciML.pdf)

2. [Advancing the frontiers of research with SciML](https://www.arxiv.org/pdf/2501.18708)

3. [Physics-informed Deep Learning](https://github.com/maziarraissi/PINNs)

4. [Unreasonable effectiveness of deep learning in AI](https://github.com/ranja-sarkar/ranja-sarkar.github.io/blob/fc7884ad15bf94ea2e66f625d9bde7b951388ba7/_posts/assets/unreasonable-effectiveness-of-deep-learning-in-AI.pdf)

5. [Why is AI hard and Physics simple?](https://github.com/ranja-sarkar/ranja-sarkar.github.io/blob/15b3d94ed12fdde4485b7d84898f737545f0ed62/_posts/assets/Physics%20simple-AI%20hard.pdf)

6. [PINNs for solving nonlinear PDEs](https://github.com/ranja-sarkar/ranja-sarkar.github.io/blob/efdc65b9cd38d980cacb603186727f0c3805db6f/_posts/assets/PINN-solving-nonlinear-PDEs.pdf)

