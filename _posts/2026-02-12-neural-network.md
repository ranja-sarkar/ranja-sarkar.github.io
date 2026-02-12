--- 
tags: [networks, neuralnets, data, deep learning]  
---

![chrchgt](https://github.com/user-attachments/assets/1ffba787-8e90-43ce-9467-c6d1a70e3953)


The earliest **neural networks (NNs)** are the feed-forward neural networksor multilayer perceptrons (MLPs), where input values flow forward linearly (forward pass) and gradients/derivatives flow backward linearly (backpropagation) through a network. Neurons are interconnected units/nodes arranged in layers in NNs. Each node in an input layer is a feature of the dataset. NNs can be wide, having many neurons in a given hidden layer and/or deep, having many hidden layers. More neurons/nodes enable complex learning at the cost of overfitting and more computational cost. 

<img width="289" height="116" alt="nn" src="https://github.com/user-attachments/assets/01cc8002-6f5d-4728-b883-cc6976ab6d9c" />

Forward propagation is when data moves from left (input layer) to right (output layer) in the network, and backward propagation is when the gradient moves from right to left  in the network. Prominent NN architectures are GNNs, RNNs, CNNs, GANs, and transformers.

# Architectures of a neural network

📌 Recurrent Neural Networks (RNNs) process sequential data. Unlike feedforward NNs which process data in a single pass, RNNs process data across multiple time steps. This makes them well-suited for tasks like natural language processing (NLP) and time-series forecasting. They can learn patterns in sequences by connecting the output from one time step to the input of the next, remembering previous information. 

📌 Convolutional Neural Networks (CNNs) are specifically designed for processing spatial data, such as images. They use special convolutional layers to scan and identify local patterns within the input. This makes them more efficient for object detection and computer vision tasks. 

📌 Graph Neural Networks (GNNs) operate on graph-structured data. They are designed to learn, and encode the relationships (edges) between nodes in a graph, making them useful for tasks such as social network analysis, molecular property prediction, and recommendation systems. Information in the form of scalars or embeddings can be stored at each graph node or edge.

<img width="230" height="224" alt="gnn" src="https://github.com/user-attachments/assets/4b22096c-94e4-4255-b3a5-40c895c253b5" />


[GNNs](https://distill.pub/2021/gnn-intro/) on graphs with translational symmetry in all dimensions are [CNNs](https://www.datacamp.com/tutorial/introduction-to-convolutional-neural-networks-cnns). GNNs on one-dimemsional directed line graph are [RNNs](https://keras.io/guides/sequential_model/).

<img width="281" height="103" alt="rnn" src="https://github.com/user-attachments/assets/6b38bcca-abc4-4048-8e03-c78bb6b5c5e9" />
<img width="337" height="136" alt="cnn" src="https://github.com/user-attachments/assets/84be81b0-ed98-4a69-8d15-2c8cbdfb22e5" />

📌 Transformers are architectures that rely on a self-attention mechanism to process input data, allowing them to handle long-range dependencies effectively. Self-attention allows for capturing relationships within input sequences and weigh the importance of different words/tokens of the sequence. For details of this mechanism, refer to the [article](https://sebastianraschka.com/blog/2023/self-attention-from-scratch.html) by Sebastian Raschka. Transformers incorporate in their architectures feed-forward NNs in parts. 

<img width="299" height="144" alt="nns" src="https://github.com/user-attachments/assets/3a48419c-2d1c-489f-92ae-4a0fe283446a" />


The self-attention mechanism in a decoder in the transformer architecture can be viewed as GNN that is, a neural network on a fully connected graph on all tokens of the context window. It can be thought of as a (special) directed graph where one token is connected to all previous tokens in the context window. Transformers have been especially successful in tasks such as language translation and text summarization due to their ability to capture contextual information across large sequences. 

📌 Generative Adversarial Networks (GANs) consist of two distinct neural networks, a generator and a discriminator that compete against each other. The generator creates a data sample and the discriminator determines if that data sample came from the captured training/observed data or the generator. By optimizing against each other, GANs learn to generate new samples. GAN extracts representative latent embeddings of observed data distributions, and is known to approximate distributions very well. 

# Hyper-parameters of a neural network

A network is a structure of interconnected nodes, in other words it is a structure of connected neurons arranged in layers, has one or more input nodes, a function node (activation function) and an output node. Typically, the NN parameters are activation function, dropout, epoch, early stopping, batch-size, learning rate. 

📌 **Activation function** → The function nodes taken together in a neural network form a hidden layer (or layers as there can be multiple)  that we change in accordance with the mathematical operation. It performs a weighted operation on the input layer that receives inputs and passes the result to the output layer. The mathematical operation is the activation function and must be non-linear in order to learn the underlying complex pattern in data and generalize from complex data.

An activation function decides how much signal to pass onto the next layer based on the input it receives. This idea of chaining many weighted signals together is what allows NNs to learn complex relationships in the dataset. Non-linear activation functions help solve intricate problems by adding layers of abstraction. More than two layers of perceptrons feeding one into another gives us MLPs. These layers are hidden and may be arbitrary in number. If we want to model a perceptron, we need a step function as the activation function. 

<img width="214" height="110" alt="pp" src="https://github.com/user-attachments/assets/be40c9aa-8995-489c-b6d9-46442bd1be9b" />

For simplicity, bias terms are not shown in the perceptron. Weights refer to the connections (edges) of the input nodes to the function nodes, to move forward in the network, weights of input signals must be adjusted. There are different types of activation functions, of which ReLu reduces computational cost and mitigates the vanishing gradient problem, but it can lead to dead units or neurons (where some of them never activate). The sigmoid or logistic function can suffer from the vanishing gradient problem during backpropagation.

![af](https://github.com/user-attachments/assets/283b00a6-b4d7-4d65-88c3-bf55dcba885f)


📌 **Dropout** → It refers to randomly dropping out or omitting neurons from both hidden and visible layers, while training a model to optimize performance of the network. It's a regularization technique to prevent overfitting.

![do](https://github.com/user-attachments/assets/988ca913-0c04-4660-b4b3-85208e4ecf09)

📌 **Epoch** → It is one full-cycle (complete pass) of learning from the (training) data, in other words an epoch is an iteration. Too many epochs may lead to overfitting of the model. There needs to be just the right number of iterations to arrive at an optimally fitted model. 

<img width="506" height="208" alt="es" src="https://github.com/user-attachments/assets/396e44d7-926f-432f-ba8f-17e7852f0c56" />

The algorithm updates the weights after each epoch while moving toward the minimum error (loss function). These updates are then tested, reversed through the network to identify errors, and repeated to produce optimal results. 

📌 **Early stopping** → It’s an implicit form of regularization that provides guidance to how many iterations can be run before the learner network begins to overfit. Beyond a certain point, improving the learner's fit to the training data comes at the expense of increased generalization error (also known as out-of-sample error). 

<img width="289" height="226" alt="epoch" src="https://github.com/user-attachments/assets/4b345f3f-9c4d-4c5a-aa72-97ee9e4c3843" />

The validatiom curve (error vs. epoch) shows that early stopping is just the right point to stop training the learner, so it doesn’t overfit. The datasize is also a crucial aspect while the model is trained. 

📌 **Batch** → It is either a subset of the training data (mini-batch), or each example in the training data, or the entire training data (batch) used in an epoch while training a model. The weight updates happen in these batches. For details on how to choose batch-size, refer to the [article](https://sebastianraschka.com/blog/2022/batch-size-2.html) by Sebastian Raschka.

![bs](https://github.com/user-attachments/assets/b03798e9-2e67-4eef-af56-77fcc444b430)

Gradient descent is the iterative method used to train NNs, the algorithm has to take just the right step (step-size neither too small nor too large) until convergence. This step-size is called the [learning rate](https://www.jeremyjordan.me/nn-learning-rate/).  

📌 **Learning rate** → It indicates the step-size that the gradient descent optimization method takes to move towards the local optimum. If the learning rate is too small, it will take more time to reach the optimum and if it is too large, it might start to diverge and never reach the optimal point. 

<img width="859" height="424" alt="lr" src="https://github.com/user-attachments/assets/28c4b78d-4e8a-4653-807a-753cff90d88e" />

Reaching convergence while training NNs can be difficult, nonetheless there’re ways to control it like picking an [optimizer](https://www.bdhammel.com/learning-rates/). A popular optimizer is the Adam optimizer wherein the learning rate is not set manually. [Adam](https://machinelearningmastery.com/adam-optimization-algorithm-for-deep-learning/) uses an adaptive learning rate. 

# Important points while building a neural network

📌 **Goal**

An important consideration besides the target value or performance benchmark is the choice of the [performance metric](https://ranja-sarkar.github.io/2025/12/18/metrics-in-machine-learning.html). Several metrics may be used to measure the effectiveness of the application backed by neural networks and they are usually diﬀerent from the loss functions (while training NN). The metrics have to align with the business goal.


📌 **Data**

When deciding if more data is required, it is necessary to decide how much more to gather. It is helpful to plot (learning) curves showing the relationship between training data size and model error. By extrapolating such curves, one can estimate how much additional training data would be needed to achieve a certain level of performance. Usually, adding a small fraction of the entire datatset will not have a noticeable eﬀect on generalization error. It is therefore recommended to experiment with training dataset sizes on a logarithmic scale. If gathering more data is not feasible, the only other way to improve generalization error is to improve the learning algorithm itself. This becomes the domain of researchers and not that of applied practitioners much. 

📌 **Model Capacity**

When deciding on adjusting hyperparameters for model improvement, there are two basic approaches - manual and automatic. Manual hyperparameter tuning can work very well when there’s a good starting point. For many applications however, these starting points are not available and in those cases, automated hyperparameter tuning helps ﬁnd the optimal configuration. 

When there are fewer hyperparameters to tune, the common practice is to perform a grid search. There is an alternative to grid search - random search, which is lesser exhaustive and converges faster to good values of the hyperparameters. The main reason that random search ﬁnds good configuration faster than grid search is that it has no wasted experimental runs.

![nn1](https://github.com/user-attachments/assets/27b02ec8-7342-44db-b589-556164967924)

A neural network with higher number of layers and hidden units per layer has higher representational capacity that is, it’s capable of representing more complicated functions. The neural network cannot necessarily learn the complex relationships if the algorithm cannot discover while training how some functions do a better job of minimizing the cost function, or if regularization terms such as weight decay forbid some of these functions. 

<img width="1102" height="478" alt="nn2" src="https://github.com/user-attachments/assets/6f1adfeb-bb49-4824-b549-9f0e2e8b27af" />

Hyper-parameters other than the learning rate requires monitoring of both train and test errors to diagnose if the model is overﬁtting, then adjusting the network’s capacity appropriately. The learning rate is perhaps the most important hyperparameter during optimization as it controls the eﬀective model capacity in a more complicated way than others, and the capacity is highest when the learning rate is correct given the problem. 

📌 **Framework**

Practitioners turn typically to exisiting frameworks to solve problems with deep learning. The widely used and popular deep learning frameworks are tensorflow and pytorch. For details, please read this article.  
