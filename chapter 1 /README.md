<div align="center">
    <h1>
       Chapter 1: Hello There, Kernel. <br/>
</div>

### This Document is Submitted as part of END 3 Session 1.

## Contributors

* [Seetharaman Sikamani](https://github.com/seetha1971)
* [Umesh Birajdar](https://github.com/Umeshtriveni)
* [Srikanth Kandarp](https://github.com/silicon-ninja)

---
## Table of Contents 
- [Questions to be Addressed]()

  * [<b>What is a neural network neuron ?</b>](#-center---b-what-is-a-neural-network-neuron----b---center-)

  * [<b>What is the use of the learning rate ?</b>](#-b-what-is-the-use-of-the-learning-rate----b---center-)

  * [<b>How are weights initialized ?</b></center>](#-center--b-how-are-weights-initialized----b---center-)
  * [<b>What is "loss" in a neural network ?</b></center>](#-center--b-what-is--loss--in-a-neural-network----b---center-)
  * [<b>What is the "chain rule" in gradient flow ?</b>](#-b-what-is-the--chain-rule--in-gradient-flow----b-)
- [References](#references)


---
## <center><b>Questions to be Addressed</b></center>
### <center> <b>What is a neural network neuron ?</b></center>

### <b> Answer:  </b>

The neuron is nothing more than a set of inputs, a set of weights, and an activation function. The neuron translates these inputs into a single output, which can then be picked up as input for another layer of neurons later on.

While details can vary between neural networks, the function f(x1,x2,…,xn)is often just a weighted sum: ```f(x1,x2,…,xn) = w1⋅x1+w2⋅x2+...+wn⋅xn``` Each neuron has a weight vector ``` w=(w1,w2,...,wn)```, where n is the number of inputs to that neuron. These inputs can be either the 'raw' input features — say temperature, precipitation, and wind speed for a weather model — or the output of neurons from an earlier layer.

The weights for each neuron are turned during the training stage such that the final network output is biased toward some value (usually 1) for signal, and another (usually -1 or 0) for background.

Non-linear behavior in a neural network is accomplished by use of an activation function (often a sigmoid function) to which the output of ```f```is passed and modified. This allows neural networks to describe more complicated systems while still combining inputs in a simple fashion.

<p align="center">
<img src="../Session%201/assets/image_1.png"  style="height: 600 px; width:300px;">
</p>

### <center><b>What is the use of the learning rate ?</b></center>
### <b> Answer:  </b>
The learning rate is a hyperparameter that controls how much to change the model in response to the estimated error each time the model weights are updated. Choosing the learning rate is challenging as a value too small may result in a long training process that could get stuck, whereas a value too large may result in learning a sub-optimal set of weights too fast or an unstable training process.



### <center><b>How are weights initialized ?</b></center>
### <b> Answer:  </b>
Weight initialization is an important consideration in the design of a neural network model. The nodes in neural networks are composed of parameters referred to as weights used to calculate a weighted sum of the inputs. Neural network models are fit using an optimization algorithm called stochastic gradient descent that incrementally changes the network weights to minimize a loss function, hopefully resulting in a set of weights for the mode that is capable of making useful predictions. This optimization algorithm requires a starting point in the space of possible weight values from which to begin the optimization process. Weight initialization is a procedure to set the weights of a neural network to small random values that define the starting point for the optimization (learning or training) of the neural network model.

Weight initialization follows simple heuristics, such as:

```
Small random values in the range [-0.3, 0.3]
Small random values in the range [0, 1]
Small random values in the range [-1, 1]
```
These modern weight initialization techniques are divided based on the type of activation function used in the nodes that are being initialized, such as “Sigmoid and Tanh” and “ReLU.”

### <center><b>What is "loss" in a neural network ?</b></center>
### <b> Answer:  </b>
Before understanding what exactly is the loss function lets look at optimization algorithm, the function used to evaluate a candidate solution (i.e. a set of weights) is referred to as the objective function.We may seek to maximize or minimize the objective function, meaning that we are searching for a candidate solution that has the highest or lowest score respectively.

Typically, with neural networks, we seek to minimize the error. As such, the objective function is often referred to as a cost function or a loss function and the value calculated by the loss function is referred to as simply “loss.”

### <center><b>What is the "chain rule" in gradient flow ?</b></center>
### <b> Answer: </b>

The algorithm is used to effectively train a neural network through a method called chain rule. In simple terms, after each forward pass through a network, backpropagation performs a backward pass while adjusting the model's parameters (weights and biases).
    
    
Let's look at an example of how it works ?

<p align="center">
<img src="../Session%201/assets/image_2.png"  style="height: px; width:px;"/>
</p>

The a and x1,x2,x3 are vector, W is the matrix

Output is the

<p align="center">
<img src="../Session%201/assets/image_3.png"  style="height: px; width:px;"/>
</p>

How to use chain rule to compute ? this, ```dy/dW```

We do, 

<p align="center">
<img src="../Session%201/assets/image_4.png"  style="height: px; width:px;">
</p>

Take differentials of the three equations that you derived.

<p align="center">
<img src="../Session%201/assets/image_5.png"  style="height: px; width:px;">
</p>

The desired gradient is a 3rd order tensor, use a vec-operation to flatten it into a matrix.

<p align="center">
<img src="../Session%201/assets/image_6.png"  style="height: px; width:px;">
</p>

----
## References 

1. https://www.analyticsvidhya.com/blog/2021/03/basics-of-neural-network/
2. https://becominghuman.ai/understanding-neural-networks-1-the-concept-of-neurons-287be36d40f
3. https://machinelearningmastery.com/weight-initialization-for-deep-learning-neural-networks/
4. https://machinelearningmastery.com/understand-the-dynamics-of-learning-rate-on-deep-learning-neural-networks/
---
