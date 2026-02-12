--- 
tags: [networks, neuralnets, data, deep learning]  
---

![chrchgt](https://github.com/user-attachments/assets/1ffba787-8e90-43ce-9467-c6d1a70e3953)


The earliest **neural networks (NNs)** are the feed-forward neural networksor multilayer perceptrons (MLPs), where input values flow forward linearly (forward pass) and gradients/derivatives flow backward linearly (backpropagation) through a network. 

<img width="289" height="116" alt="nn" src="https://github.com/user-attachments/assets/01cc8002-6f5d-4728-b883-cc6976ab6d9c" />

Forward propagation is when data moves from left (input layer) to right (output layer) in the network, and backward propagation is when the gradient moves from right  to left  in the network. Prominent NN architectures are GNNs, RNNs, CNNs, GANs, and transformers.

---

📌 Recurrent Neural Networks (RNNs) process sequential data. Unlike feedforward NNs which process data in a single pass, RNNs process data across multiple time steps. This makes them well-suited for tasks like natural language processing (NLP) and time-series forecasting. They can learn patterns in sequences by connecting the output from one time step to the input of the next, remembering previous information. 

📌 Convolutional Neural Networks (CNNs) are specifically designed for processing spatial data, such as images. They use special convolutional layers to scan and identify local patterns within the input. This makes them more efficient for object detection and computer vision tasks. 

📌 Graph Neural Networks (GNNs) operate on graph-structured data. They are designed to learn, and encode the relationships (edges) between nodes in a graph, making them useful for tasks such as social network analysis, molecular property prediction, and recommendation systems. Information in teh form of scalars or embeddings can be stored at each graph node or edge.

<img width="230" height="224" alt="gnn" src="https://github.com/user-attachments/assets/4b22096c-94e4-4255-b3a5-40c895c253b5" />


[GNNs](https://distill.pub/2021/gnn-intro/) on graphs with translational symmetry in all dimensions are [CNNs](https://www.datacamp.com/tutorial/introduction-to-convolutional-neural-networks-cnns). GNNs on one-dimemsional directed line graph are [RNNs](https://keras.io/guides/sequential_model/).

<img width="281" height="103" alt="rnn" src="https://github.com/user-attachments/assets/6b38bcca-abc4-4048-8e03-c78bb6b5c5e9" />
<img width="337" height="136" alt="cnn" src="https://github.com/user-attachments/assets/84be81b0-ed98-4a69-8d15-2c8cbdfb22e5" />

📌 Transformers are architectures that rely on a self-attention mechanism to process input data, allowing them to handle long-range dependencies effectively. Self-attention allows for capturing relationships within input sequences and weigh the importance of different parts of the sequence. For details of this mechanism, refer to the [article](https://sebastianraschka.com/blog/2023/self-attention-from-scratch.html) by Sebastian Raschka. Transformers incorporate in their architectures feed-forward NNs in parts. 

<img width="299" height="144" alt="nns" src="https://github.com/user-attachments/assets/3a48419c-2d1c-489f-92ae-4a0fe283446a" />


The self-attention mechanism in a decoder in the transformer architecture can be viewed as GNN that is, a neural network on a fully connected graph on all tokens of the context window. It can be thought of as a (special) directed graph where one token is connected to all previous tokens in the context window. Transformers have been especially successful in tasks such as language translation and text summarization due to their ability to capture contextual information across large sequences. 

📌 Generative Adversarial Networks (GANs) consist of two distinct neural networks, a generator and a discriminator that compete against each other. The generator creates a data sample and the discriminator determines if that data sample came from the captured training/observed data or the generator. By optimizing against each other, GANs learn to generate new samples. GAN extracts representative latent embeddings of observed data distributions, and is known to approximate distributions very well. 

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
