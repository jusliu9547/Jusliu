---
title: Logistic Regression
linktitle: Logistic Regression
toc: true
type: docs
date: "2019-05-05T00:00:00+01:00"
draft: false
markup: mmark

menu:
  machine_learning:
    parent: Supervised Learning
    weight: 3

# Prev/next pager order (if `docs_section_pager` enabled in `params.toml`)
weight: 4

---

### Classification problem

When you applied linear regression into classification case, it comes two problems:
- Easily influent by extreme value
- $h_{\theta}(x)$ can be >1 or <0

### Logistic regression model

* $h_{\theta}(x) = g(\theta^{T}x) $

* $g(z) = \frac{1}{1+e^{-z}}$

* $h_{\theta}(x) = p(y = 1| x;\theta)$ probability that y = 1, given x, parameterized by $\theta$.

{{< figure src="sigmoid.png" title="Sigmoid function g(z)" lightbox="true" >}}

-> when $z > 0$, $g(z) >= 0.5$. $h_{\theta} = g(\theta^{T}x) >= 0.5$ whenever $\theta^{T}x >= 0$

### Cost function

$$Cost(h_{\theta}(x), y) = \begin{cases} -log(h_{\theta}(x)) & \text{if }y=1, \\
-log(1 - h_{\theta}(x)) & \text{if }y=0.\end{cases}$$

more simplified cost function...

$$ J(\theta) = \frac{1}{m} [\sum^{m}_{i = 1} y^{(i)} logh_{\theta}(x^{(i)}) + (1 - y^{(i)})log(1-h_{\theta}(x^{(i)}))]$$

### Multi-class classification

One-vs-all: Train a logistic regression classifier $h^{(i)}_{\theta}(x) $ for each class $i$ to predict the probability that $ y = i$. On a new input $x$, to make a prediction, pick class $i$ having the highest value.
