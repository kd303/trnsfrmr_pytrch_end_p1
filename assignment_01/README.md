# Assignment - 01 Questions/Answers

## What is a neural network neuron?
To put loosely a neural network neuron is set of inputs, a set of weights and an activation function. Neuron translates the inputs to a single output which can then be picked up as input to another layer of neurons. 
Each neuron has a weight vector for the number of inputs that neurons recives. Weights of these neuron are tunned duing traing stage such that the final output is biased toward either activation (usually 1) or non-activation (0 or -1). 

Activation function adds non-linear behavior and helps to decide whether the neuron should be 'activated' or not. Removing the activation function in NN just becomes a linear regression model which does not help in learning complex data, even adding more layers to the NN without non-linear function is just a sum of all linear functions which is also a linear function. Linear functions also derivates to a constant which does not have any relation to input so it is not possible to know which neuron were used to predic tthe outcome. Roughly each neuron learns a feature of given dataset in a language model it can be a token sequence different token and words appearning in context and in vision models it could be patterns, edges, shapes of a given dataset.

Essentially it is a vector of learned wieghts with non-linear activation function. 

*Vive les Neurons!* __Oh! - *Neurons can be dead like our brain cells ;)*__

## What is the use of the learning rate?

Learning rate in Machine Learning algorithms is a hyper-parameter, generally a user input value. Learning rate is used to scale the magnitude of parameters updates (weights generally) during gradient decent algorithms. 

Optimal selection learning rate can decide how fast or slow a particular cost function can be optimized. If Learning rate value is lower than optimal value then the number of iteration required to minimize the cost function is high. 

 There are different methods used for optimizing the learning rate
  -  Decaying learning rate and 
  -  Scheduled drop learning rate 
  -  Adaptive Learning rate
  -  [Cyclic learning rate](https://arxiv.org/pdf/1506.01186.pdf)
    
Decaying learning rate is reducing learning rate as number of epochs. In scheduled drop the learning rate does not drop continuously, it drop at a scheduled Epoch frequency. Other methods include Adaptive learning rate where the learning rate value increases or decreases based on gradient value of the cost function. Cyclic is basically the learning rate varies between a base rate and maximum rate cyclically. Having relatively small learnin rate also allows for wieghts to learn small incremental updates and the change in wieght values is not very high which helps in the function coverging.

[Good Resource on learning rate](https://machinelearningmastery.com/understand-the-dynamics-of-learning-rate-on-deep-learning-neural-networks/)

## How are weights initialized?

Weights in neural nets are initialized small and random. One of the very early techniques used is called Xavier and He initialization which basically tackled exploding and vanishing gradients during training of neural nets. Non-deterministic algorithms like neural nets use elements of randomness when making decisions during execution of algorithm that is different order of steps will be followed each time the algoritm is run (unlike say bubble sort/merge sort algorithm is run). 

Initializing all weights to zero may leand tthe neurons to learn the same features during training and both neurons will evolve symetrically during training and would learn same features.


## What is "loss" in a neural network?

Neural networks are trained using optimization process where to calculate the prediction error a loss function is required. Usually the objective function is either maximized or minimized, when we minimize the fuction it is usually call a cost function/loss function or error function. Loss function usually reduces all predicted asepects of a model to single scaler value. Configuration of the output layer as a choice of loss function as the way to calculate the error for a given problem. Softmax/Sigmoid are some of the output functions used as loss functions. For regression problem Mean Squied Error can be a loss function.


## What is the "chain rule" in gradient flow?

Gradient flow calculus is the set of rules used by the backprop algorithm to comput gradients. Back prop works by calculating the gradients a tthe out of the network then propogate or flowing these gradients back into network.



