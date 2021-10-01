# Understanding of Neural nets using Excel and doing Calculation using back-propagation

This entire process is created using [excel sheet](/session_02/NN_Manual_Computation.xlsx)

## Step : 1 : Define a neural net with 1 hidden layers with 2 neuron, 2 inputs

Here is what NN looks like

![Image of NN Net](/session_02/NN_Definition.JPG)

## Step : 2 : Define the columns in excel for inputs (i1, i2) output (t1, t2), initialize the random values for the wieghts define basic equation for forward pass

Here we are using Sigmoid σ(x) = 1/(1 + exp(x)) as activation function

  * h1 = i1*w1 + i2*w2
  * h2 = i1*w3 + i2*w4
  * a_h1 = 1/(1 + exp(-h1))
  * a_h2 = 1/(1 + exp(-h2))
  * o1 = ah_1*w5 + ah2*w6
  * o2 = ah_1*w7 + a_h2*w8
  * a_o1 = 1/(1 + exp(-o1))
  * a_o2 = 1/(1 + exp(-o2))
  * E1 = 1/2* (t1- a_o1)^2
  * E2 = 1/2*(t2 - a_o2)^2

## Step : 3 : Calculate partial derivatives of above functions & Apply chain rule where required (all hidden layer and last layer functions 

Here is partial derivative of E1 w.r.t nueron h1 and activation function a_h1

  * __∂E1/∂h1 = ∂E1/∂a_o1 * ∂a_o1/∂o1 * ∂o1/∂a_h1__
  * __∂E1/∂a_h1 = ∂E1/∂a_o1 * ∂a_o1/∂o1 * ∂o1/∂a_h1__
  
Similarly for the first layer the derivatives would be

  * __∂E_t/∂w1 = ∂E_t/∂a_o1 * ∂a_o1/∂o1 * ∂o1/∂a_h1 * ∂_ah1/∂h1 * ∂h1/∂w1__
  * __∂E_t/∂w1 = ∂E_t/∂a_h1 * ∂_ah1/∂h1 * ∂h1/∂w1__
  * __∂E_t/∂w1 = ∂E_t/∂a_h1 * a_h1*(1-a_h1)* ∂h1/∂w1__
  * __∂E_t/∂w1 = ∂E_t/∂a_h1 * a_h1 * (1-a_h1)* i1__ *equation 1*


Calculating __∂E_t/∂a_h1__


  -  __∂E1/∂h1 = ∂E1/∂a_o1*∂a_o1/∂o1*∂o1/∂a_h1__
  -  __∂E1/∂a_h1 = ∂E1/∂a_o1*∂a_o1/∂o1*∂o1/∂a_h1__
  -  __∂E1/∂a_h1 = (a_a1 - t1)*a_o1*(1-a_o1)*w5__
  -  __∂E2/∂a_h2 = (a_o1 - t1)*a_o1*(1-a_o1)*w6__
  -  __∂E2/∂a_h1 = (a_o2 - t2)*a_o2*(1-a_o2)*w7__
  -  __∂E_t/∂a_h1 = ∂(E1 + E2)/∂a_h1 = (a_o1 - t1)*a_o1*(1-a_o1)*w5 + (a_o2 - t2)*a_o2*(1-a_o2)*w7__
  -  __∂E_t/∂a_h2 = ∂(E1 + E2)/∂a_h2 = (a_o1 - t1)*a_o1*(1-a_o1)*w6 + (a_o2 - t2)*a_o2*(1-a_o2)*w8__  *equation 2*

So finally **∂E_t/∂w1** would be puting the value of *equation 2* in *eqaution 1*

  __∂E_t/∂w1 = (a_o1 - t1)*a_o1*(1-a_o1)*w5 + (a_o2 - t2)*a_o2*(1-a_o2)*w7 * * a_h1 * (1-a_h1)* i1

Similarly calculate all the values

## Final step define the learning rate (lr) and update the weight values as 

  __(w1 - (lr)*∂E_t/∂w1)__ 

Upon repating the iteration with same input and output value loss is generated here is the Final snapshot of the Excel sheet

![Image of ExcelSheet](/session_02/NN_usingExcel.JPG)





