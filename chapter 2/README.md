<div align="center">
    <h1>
       Chapter 2 : Learning Backwards. <br/>
</div>

### This Document is Submitted as part of END 3 Session 2.

## Contributors

* [Seetharaman Sikamani](https://github.com/seetha1971)
* [Umesh Birajdar](https://github.com/Umeshtriveni)
* [Srikanth Kandarp](https://github.com/silicon-ninja)

---
## Table of Contents:
---


### Excel Sheet Link:

https://docs.google.com/spreadsheets/d/18QbEoPFf3i-3y_hZxaRS-CCkRVyUc4AV4oRdK_skDcs/edit?usp=sharing


---

<div align="center">
    <h2>
       Network Architecture <br/>
</div>

<p align="center">
<img src="./assets/network_arch.png"  style="height: 1000 px; width:800px;">
</p>

---
## Components:
``` 
   * i1, i2 -> Input Neurons

   * o1, o2 -> Output Neurons  

   * t1, t2 -> Target values    

   * Input Layer  - 2 Input Neurons

   * Hidden Layer - 1 hidden layer with 2 neurons

   * Output Layer - 2 Output Neurons (For eg: binary -> yes and no)

   * h1, h2 -> Hidden layer Neurons  

   * a_h1, a_h2 -> Activation on h1, h2       

   * a_o1, a_o2  -> Activation on o1, o2 

   * E1, E2 -> Error calculated between target values and outputs
    
   * Weights: w1, w2, w3, w4, w5, w6, w7, w8 -> Weights of the Neural Network
```
---
## Layers:

*  Input Layer  - 2 Inputs
*  Hidden Layer - 1 hidden layer with 2 neurons
*  Output Layer - 2 Outputs
----

## Activation Function:
We have used sigmoid activation function for this neural network:

<p align="center">
<img src="./assets/activation.png"  style="height: 500 px; width:300px;">
</p>


---
## Error

* Etotal = E1 + E2 

* Mean Square Error (MSE): 

<p align="center">
<img src="./assets/mse.png"  style="height: 500 px; width:300px;">
</p>

---
## Derivations 
### Partial derivative: 
   In simple terms, we differentiate with respect to one variable and we keep others as constant. This is used in backpropagation. For example: z = x+y, here the rate of change of x over z, irrespective of y.

### Chain rule:
   In simpler terms, we can see that as parsing through layers. We first solve for one layer and move on to the next and next. For example: z= (x+y)^2, here the square is our first layer, we solve for that and move on to the (x+y) layer which is our second layer. If we had a co-efficient for x, then that would be solved next. 


<p align="center">
<img src="./assets/solve_1.png"  style="height: 800 px; width:500px;">
</p>

<p align="center">
<img src="./assets/solve_2.png"  style="height: 800 px; width:500px;">
</p>

<p align="center">
<img src="./assets/solve_3.png"  style="height: 800 px; width:500px;">
</p>

    
<p align="center">
<img src="./assets/solve_4.png"  style="height: 800 px; width:500px;">
</p>



---
## Steps in forward propagation:

* Weights are initialized with random values. 
* Dot products will be calculated at each stage between weights and the inputs (Previous layer's outputs for hidden and output layer)
* The activation functions are applied at each stage 
* Error is calculated between the target and the output of the last layer using MSE

---
## Steps in Backward Propagation:

* Partial differentiation is done at every stage. From error to the input layer using chain rule
* For the backward propagation, the weights values needs to be updated by 

<p align="center">
<img src="./assets/weights_updation.png"  style="height: 500 px; width:300px;">
</p>

    
    
* In backward propagation, though our weights are initially randomized, we let the network to learn the weights values by updating them after each step
* The backpropagation step provides an implementation of the chain rule
* And the error values are calculated with the new updated weights
* We have repeated the same steps for different learning rates and observations are recorded


---

## Results & Inference:

* For different learning rates, the forward and backward propagation are done and tabulated below
* When the learning rate is 2, the error seems to be low. The higher the learning rate, the network converged faster and less error is observed in this case. (Output nearer to the true values)

    
 
### Case 1 : Learning Rate at 0.1
    
<p align="center">
<img src="./assets/0.1.png"  style="height: 800 px; width:500px;">
</p>

### Case 2 : Learning Rate at 0.2
    
<p align="center">
<img src="./assets/0.2.png"  style="height: 800 px; width:500px;">
</p>

### Case 3 : Learning Rate at 0.5
    
<p align="center">
<img src="./assets/0.5.png"  style="height: 800 px; width:500px;">
</p>

### Case 4 : Learning Rate at 0.8
    
<p align="center">
<img src="./assets/0.8.png"  style="height: 800 px; width:500px;">
</p>

### Case 5 : Learning Rate at 1.0
    
<p align="center">
<img src="./assets/1.0.png"  style="height: 800 px; width:500px;">
</p>
    
### Case 6 : Learning Rate at 2.0
    
<p align="center">
<img src="./assets/2.0.png"  style="height: 800 px; width:500px;">
</p>
    
    
## Overview Screenshot

<p align="center">
<img src="./assets/overview.png"  style="height: 1000 px; width:800px;">
</p>
    
---
