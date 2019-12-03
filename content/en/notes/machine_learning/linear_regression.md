---
title: Linear Regression
linktitle: Linear Regression
toc: true
type: docs
date: "2019-05-05T00:00:00+01:00"
draft: false
markup: mmark


menu:
  machine_learning:
    parent: Supervised Learning
    weight: 1

# Prev/next pager order (if `docs_section_pager` enabled in `params.toml`)
weight: 3

---

### Example data (House price prediction case)

|Size | Number of bedrooms | Number of floors | Age of house|Price|
|:------:|:------:|:------:|:------:|:------:|
|2104|5|1|45|460|
|1416|3|2|40|232|
|1534|3|2|30|315|
|852|2|1|36|178|
|...|...|...|...|...|

Notation:
* $n$ = number of features
* $m$ = number of training data
* $x^{(i)}$ = input features of $i^{th}$ training example
* $x^{(i)}_{(j)}$ = value of feature $j$ in $i^{th}$ training example

Model structure:
* Hypothesis: $h_{\theta}(x) = \theta^{T}x$
* Parameters: $\theta$, $n + 1$ dimensional vector
* Cost function: $J(\theta) = \frac{1}{2m} ( \sum_{i = 1}^{m} (h_{\theta}(x^{(i)}) - y^{i})) ^2$

Gradient descent:

$$
\text{repeat until convergence}
\\
\{
\theta_{j} := \theta_{j} - \alpha \frac{\partial}{\partial \theta_{j}} J(\theta)
\}
$$ (simultaneously update for every $j = 0, ..., n$)

### Gradient descent in practice

#### Feature scaling

Idea: Make sure features are on a similar scale.
* Mean normalization
  - Replace $x_{j}$ with $x_{j} - \mu_{j}$ to make features have approximately zero mean.
  
$$
x_{(j)} \gets \frac{x_{(j)} - \mu_{(j)}}{\text{range of } x_{(j)}}
$$

#### Learning rate 
* Debugging: Make sure gradient descent is working correctly.
* Choose the apporpriate learning rate $\alpha$.
  - if $\alpha$ is too small: slow convergence.
  - if $\alpha$ is too large: $J(\theta)$ may not decrease on every iteration; may not converge.

### Normal equation 

Idea: The method to solve for $\theta$ analytically as follow:

$$
\theta = (X^{T}X)^{-1}X^{T}y
$$

|Gradient Desent|Normal Equation|
|:---:|:---:|
|Need to choose $\alpha$|.|
|Needs many iterations|.|
|.|Need to compute $$(X^{T}X)^{-1}$$ which is $O(n^3)$ |
|Works well even when $n$ is large|Slow if $n$ is large|
