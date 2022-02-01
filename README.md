# Fake-News-Classifier-Using-LSTM-Deep-Learning-NLP
Fake News Classifier Using LSTM Deep Learning-NLP
Dataset: https://www.kaggle.com/c/fake-news/data#
ong Short Term Memory:
Before getting into LSTM, let’s understand quickly what RNN does?

RNN is a type of supervised deep learning algorithm. Here, the neurons are connected to themselves through time. The idea behind RNN is to remember what information was there in the previous neurons so that these neurons could pass information to themselves in the future for further analysis. It means that the information from a specific time instance (t1) is used as an input for the next time instance(t2). This is the idea behind RNN.

lstm architecture
Image source link: https://en.wikipedia.org/wiki/File:Recurrent_neural_network_unfold.svg

One of the major problems of RNN is the Vanishing gradient. In any neural network, the weights are updated in the training phase by calculating the error and back-propagation through the network. But in the case of RNN, it is quite complex because we need to propagate through time to these neurons.

The problem lies in calculating these weights. The gradient calculated at each time instance has to be multiplied back through the weights earlier in the network. So, as we go deep back through time in the network for calculating the weights, the gradient becomes weaker which causes the gradient to vanish. If the gradient value is very small, then it won’t contribute much to the learning process.

                                   New weight = Old weight – (learning rate * gradient)

backpropagation | lstm
Image source link: https://www.techleer.com/articles/185-backpropagation-through-time-recurrent-neural-network-training-technique/

Example: Let’s say from the above diagram that we have calculated the error at time instance (t3). To update the weights of all the neurons that have participated in calculating the output at time instance(t3), we need to propagate through time till time instance (t0).

In a nutshell, if the sequence is long, then RNN finds it difficult to carry information from a particular time instance to an earlier one because of the vanishing gradient problem.

To overcome this problem, We have LSTM (Long Short Term Memory)!

LSTM is an updated version of Recurrent Neural Network to overcome the vanishing gradient problem. Below is the architecture of LSTM with an explanation.

understanding lstm
Image reference: https://colah.github.io/posts/2015-08-Understanding-LSTMs/

It has a memory cell at the top which helps to carry the information from a particular time instance to the next time instance in an efficient manner. So, it can able to remember a lot of information from previous states when compared to RNN and overcomes the vanishing gradient problem. Information might be added or removed from the memory cell with the help of valves.

LSTM network is fed by input data from the current time instance and output of hidden layer from the previous time instance. These two data passes through various activation functions and valves in the network before reaching the output.
