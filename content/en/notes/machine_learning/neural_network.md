---
title: Neural Network
linktitle: Neural Network
toc: true
type: docs
date: "2019-05-05T00:00:00+01:00"
draft: false
markup: mmark


menu:
  machine_learning:
    parent: Deep Learning
    weight: 5

# Prev/next pager order (if `docs_section_pager` enabled in `params.toml`)
weight: 10

---

### Neural Networks

* Origin: Algorithms that try to mimic the brain.

Commonly used types of neural networks include convolutional and recurrent neural networks.

{{< figure src="neural-network.png" title="Neural Network Architecture" lightbox="true" >}}

By noting $i$ the $i^{th}$ layer of the network, $j$ the $j^{th}$ hidden unit of the layer and $a$ the output after activation function $g$ of $i^{th}$ layer of the network.

$$
a^{i}_{j} = g((w^{i}_{j})^{T} x + b^{i}_{j})
$$

AND vectorization version:

$$
a^{i} = g(\Theta^{i-1} a^{(i-1)})
$$

### Activation function

Activation functions are used at the end of a hidden unit to introduce non-linear complexities to the model. Here are the most common ones:

|Sigmoid|ReLU|Leaky ReLu|
|:---:|:---:|:---:|
|$ g(z) = \frac{1}{1+e^{-z}} $| $ g(z) = max(0, z) $|$ g(z) = max(\epsilon z, z), with \epsilon \ll 1$|
|{{< figure src="sigmoid.png" lightbox="true" >}}|{{< figure src="relu.png" lightbox="true" >}}|{{< figure src="leaky-relu.png" lightbox="true" >}}|

### Cost function
One of the most used cost function in neural network is cross-entropy, and is defiened as

$$
L(z, y) = -[ylog(z) + (1-y)log(1-z) ]
$$

### Backpropagation (Backprop)

Backpropagation is a method to update the weights in the neural network by taking into account the actual output and the desired output. The derivative with respect to weight $w$ is computed using chain rule and is of the following form:

$$
\frac{\partial L(z, y)}{\partial w} = \frac{\partial L(z, y)}{\partial a} * \frac{\partial a)}{\partial z} * \frac{\partial z)}{\partial w}
$$

As a result, the weight is updated as follow:

$$
w \gets w - \alpha \frac{\partial L(z, y)}{\partial w}
$$

### Gradient checking
Idea: Make sure the written gradient descent algorithm calculate the right gradient using the gradient approximation. And be sure to disable your gradient checking code before training.

### Random initialization
Idea: Avoid to make hidden units learn the identical things, instead of using zero initialization, take symmetry breaking random initialization.
