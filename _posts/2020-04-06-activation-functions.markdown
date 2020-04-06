---
layout: post
title:  "Introduction to Activation Functions"
date:   2020-04-06
---

In this post we will see various choices of activation functions.

| Activations   | Bounds        | Type       |
|:-------------:|:-------------:|:----------:|
| Linear        | Unbounded     | Linear     |
| Relu          | [0,Unbounded] | Non-Linear |
| Tanh          | (-1,1)        | Non-Linear |
| Sigmoid       | (0,1)         | Non-Linear |

# Show me Code

{% highlight python %}
import numpy as np

def linear(x): # Linear Activations
  return x

def sigmoid(x): # Sigmoid
  return (1/(1+np.exp(-x)))

def relu(x): # Rectified Linear Units
  return max(0,x)

def tanh(x): # Hyperbolic Tangent
  factor = np.exp(2*x)
  return (factor - 1)/(factor + 1)
{% endhighlight %}

# Why Activations

The textbook answer for this is `Helps inducing non-linearity in the Model`. Without these squashing functions neural networks can learn only linear mappings.

This is because, at each stage of the network `w.T*x` is a single dot product, and a series of dot product across layer can again be summarised into a single linear operator - which in essence does not help in model's capacity or complexity

For example - if we have (3*x + 2*x + 5*x) - these are linear sums. But this can be approximated to 10*x `into a single combined linear form`. for neural networks to be able to do cool-stuff like AI :) we need these kind of nonlinearities to build out models.

# Activation Visualization

Let's have a look at the various choice of activation functions and how they look like in 2-D space

## Linear

The idea of Linear activation is `f(x) = a*x` where a in most cases is set to `1` - but can also be made learnable in the network architecture.

<img src="{{site.baseurl}}/images/3_linear.png">

Note - stacking multiple linear layers amount to the same model capacity of folding the network into a single linear layer (refer to the intuition above)

## Sigmoid

This is one of the most commonly used activations in the neural network. Also this provided a lot of mathematical convenience (which we will see in gradient computation).

<img src="{{site.baseurl}}/images/4_sigmoid.png">

One fact to learn about sigmoid is that irrespective of the input values it always output values between 0 and 1. So if we having a regression task - probably sigmoid squashing may not help. However the in most models output of Sigmoid is interpreted as probability - example Logistic Regression.

## Tanh

Similar to Sigmoid - but here the squashing output range is bounded between (-1,1).

<img src="{{site.baseurl}}/images/5_tanh.png">

## Relu

Relu (Rectified Linear Units) - is not exactly Non-Linear, but may be understood as piecewise linear. In the sense, when x>0 then max(0,x) will be x and hence a linear function when x>0. And when x<=0 it is just plain 0.

`Good` - Its upper bound is unbounded - so we can scale to larger values - say predicting house price etc..

`Bad` - If for some reason `w.T*x` is <0 and Relu sets it to 0. Which means the neuron is in essence dead and has no further value in the network. This results in decay of model performance. Refer to the Dying Relu problem to understand this in detail.

<img src="{{site.baseurl}}/images/6_relu.png">

In comparison to other activations - the chances of neurons dying is much higher in relu and hence caution is required in implementation and debugging of the models

# Verdict

As we reach the end of this post one may ask - hey which activation is the best? In my opinion there is no single-function which fits all use cases. It depends on the nature of the problem and requirements from the models.

Watch out this space for more exciting contents on Neural Network. Bye!
