--- 
tags: [networks, neuralnets, data, deep learning]  
---



The earliest neural networks are the feed-forward neural networks (NNs) or multilayer perceptrons (MLPs), where input values flow forward linearly (forward pass) and gradients/derivatives flow backward linearly (backpropagation) through a network. 


<img width="289" height="116" alt="nn" src="https://github.com/user-attachments/assets/01cc8002-6f5d-4728-b883-cc6976ab6d9c" />

Forward propagation is when data moves from left to right in the network, and backward propagation is when the gradient moves from right (output layer) to left (input layer) in the network.

Prominent NN architectures are GNNs, RNNs, CNNs, GANs, and transformers.

Graph neural networks [(GNNs)](https://distill.pub/2021/gnn-intro/) on graphs with translational symmetry in all dimensions are CNNs ([convolutional neural networks](https://www.datacamp.com/tutorial/introduction-to-convolutional-neural-networks-cnns)).

GNNs on one-dimemsional directed line graph are RNNs ([recurrent neural networks](https://keras.io/guides/sequential_model/)).

The self-attention mechanism in a decoder in the transformer architecture can be viewed as GNN that is, a neural network on a fully connected graph on all tokens of the context window.it can be thought of as a (special) directed graph where one token is connected to all previous tokens in the context window. 

-----

📌 The Goal

An important consideration besides the target value or performance benchmark is the choice of the metric. Several performance metrics may be used to measure the effectiveness of the application and they are usually diﬀerent from the loss functions used while training the neural network. 

“Metrics are how humans draw meaning from data and are typically designed for end users of the application. Loss functions are designed for machines, they may or may not be identical to metrics.”

📌 Data

When deciding if more data is required, it is necessary to decide how much more to gather. It is helpful to plot curves showing the relationship between training data size and model error. By extrapolating such curves, one can estimate how much additional training data would be needed to achieve a certain level of performance. Usually, adding a small fraction of the entire datatset will not have a noticeable eﬀect on generalization error. It is therefore recommended to experiment with training dataset sizes on a logarithmic scale. If gathering more data is not feasible, the only other way to improve generalization error is to improve the learning algorithm itself. This becomes the domain of researchers and not that of applied practitioners much. 

Please read this paper on the effectiveness of data in deep learning. 

📌 Model Capacity

When deciding on adjusting hyperparameters for model improvement, there are two basic approaches - manual and automatic. Manual hyperparameter tuning can work very well when there’s a good starting point. For many applications however, these starting points are not available and in those cases, automated hyperparameter tuning helps ﬁnd the optimal configuration. 

When there are fewer hyperparameters to tune, the common practice is to perform a grid search. There is an alternative to grid search - random search, which is lesser exhaustive and converges faster to good values of the hyperparameters. The main reason that random search ﬁnds good configuration faster than grid search is that it has no wasted experimental runs.

A neural network with higher number of layers and hidden units per layer has higher representational capacity that is, it’s capable of representing more complicated functions. The neural network cannot necessarily learn the complex relationships if the algorithm cannot discover while training how some functions do a better job of minimizing the cost function, or if regularization terms such as weight decay forbid some of these functions. 

Hyper-parameters other than the learning rate requires monitoring of both train and test error to diagnose if the model is overﬁtting, then adjusting the network’s capacity appropriately. 

The learning rate is perhaps the most important hyperparameter during optimization as it controls the eﬀective model capacity in a more complicated way than others, and the capacity is highest when the learning rate is correct given the problem. 

Framework

Practitioners turn typically to exisiting frameworks to solve problems with deep learning. The widely used and popular deep learning frameworks are tensorflow and pytorch. For details, please read this article.  
