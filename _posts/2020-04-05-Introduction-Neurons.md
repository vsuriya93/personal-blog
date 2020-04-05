---
layout: post
title: Introduction to Neurons
---
<img src="{{site.baseurl}}/images/1_overview.png">

# Introduction

**w** - Weight Vector <br>
**x** - Input Vector

We say our output is dot product of `w.T * x`

Here output can mean both output at the intermediate layers or at the output layer (the last layer in the network)

In structure each neuron takes weight vector and input (or output from previous layers) and does a dot product.

Typically we apply a function `g(.)` on the output of the neurons to learn non-linear decision surfaces.

# Weights and Bias - Intution

<img src="{{site.baseurl}}/images/2_weight_intution.png">

Lets consider the image shown above. We can clearly see
1. Weight being perpendicular the hyperplane (see the red line)
2. There is something like `step` separating left and right sides

We will address the first case - why the weight has to be perpendicular to the hyperplane.

Say for `b=0` then we have `w.T*x=0` - In this case the only way we can get `0` on the right if `w` and `x` are orthogonal. For example if `x = [1,0]` then only if `w` is of the form `[0,y]` (for all y) we will get the rhs to be `0`

Please refer to the links in Resources for a more general case

The way we interpret `Bias b` is that this determines the location of the ridge/step we see in the above figure. Increasing or decreasing bias would accordingly shift the position of the ridge. So if we need values >=0 (for the predictions) the move the ridge to the left towards -1

The function `g.()` referred here uses **tanh** activation. It is a non-linear activation which sqashes the values of input between `[-1,1]`.

In the next post we will take a look at various activation functions for the neural network

## Resources

[Course Slides](http://info.usherbrooke.ca/hlarochelle/ift725/1_01_artificial_neuron.pdf)

[Course Video](https://www.youtube.com/watch?v=SGZ6BttHMPw&list=PL6Xpj9I5qXYEcOhn7TqghAJ6NAPrNmUBH)

[StackOverflow](https://stackoverflow.com/questions/10177330/why-is-weight-vector-orthogonal-to-decision-plane-in-neural-networks/10357067#10357067)

[StackExchange](https://datascience.stackexchange.com/questions/6054/in-svm-algorithm-why-vector-w-is-orthogonal-to-the-separating-hyperplane)
