---
# Course title, summary, and position.
linktitle: Machine Learning
summary: Machine Learning taught by Andrew Ng (CS229)
weight: 1

# Page metadata.
title: Overview
date: "2018-09-09T00:00:00Z"
lastmod: "2018-09-09T00:00:00Z"
draft: false  # Is this a draft? true/false
toc: true  # Show table of contents? true/false
type: docs  # Do not modify.

# Add menu entry to sidebar.
# - name: Declare this menu item as a parent with ID `name`.
# - weight: Position of link in menu.

menu:
  example:
    name: Overview
    weight: 1
markup: mmark
---
## Definition 

* Field of study that gives computers the ability to learn without explicitly programmed. Arthur Samuel(1959)
* A computer program is said to *learn* from **experience E** with respect to some **task T** and some **performance measure P**, if its performance on T, as measured by P, improves with experience E. Tom Mitchell(1998)

### Type of problem

| | Regression | Classification |
|:------:|:------:|:------:|
|Outcome|Continuous value|Discrete value|
|Example|Housing price|Breast cancer|
|Algorithm|Linear regression|Logistic regression, SVM|

### Type of model

| |Discriminative model|Generative model|
:------:|:------:|:------:
|Goal|Estimate $P(y\|x)$  directly|Estimate $P(x\|y)$ then deduce $P(y\|x)$|
|What's learned|Desicion boundary|Probability distribution of data|
|Algorithm|Logistic regression, SVM|Naive Bayes, Latent Dirichlet Allocation(LDA)|

### Notations 

* Hypothesis: The hypothesis is denotes as $h_{\theta}$ and is the model we want to select. For a given data $x^{i}$ the model prediction is $h_{\theta}(x^{(i)})$

* Loss function: The difference between the predicted value $z$ according to the selected model and the real data value $y$. The common loss functions include {{< hl >}}least square error {{< /hl >}}, {{< hl >}}logistic loss{{< /hl >}}, {{< hl >}}hinge loss{{< /hl >}}, and {{< hl >}}cross entropy loss{{< /hl >}}.

* Cost function: The cost function $J$ is used to measure the performance of a model, and is defined with loss function as follows:

$$ J(\theta) = \sum_{i=1}^{m} L(h_{\theta}(x^{i}, y^{i})) $$

* Gradient descent: The update rule to optimize the model parameters by the set learning rate $\alpha$ and the computed gradient of each parameter.

$$\theta \gets \theta - \alpha\nabla J(\theta)$$

  and more explicitly:

$$
\text{repeat until convergence}
\{
\theta_{j} := \theta_{j} - \alpha \frac{\partial}{\partial \theta_{j}} J(\theta)
\}
$$



