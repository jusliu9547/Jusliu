---
title: Support Vector Machine
linktitle: SVM
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
weight: 8

---

The goal of support vector machines is to find the line that maximizes the minimum distance to the line.

The optimal margin classifier $h$ is such that:

$$
h(x) = sign(w^{T}x - b)
$$

{{<figure src="svm.png">}}

### Objective function

$$
\mathop{\min}_{\theta} C\  [\sum^{m}_{i = 1} y^{(i)} cost_{1}(\theta^{T}f^{i}) + (1 - y^{(i)})cost_{0}(\theta^{T}f^{i})] + \frac{1}{2} \sum^{m}_{j=1}\theta_{j} ^2
$$

$$
C = \frac{1}{\lambda}
$$

* Large C: Lower bias, higher variance.
* Smaller C: Higher bias, lower bias

### Kernel

In practice, the kernel $K$ defined by $K(x, z) = exp(- \frac {||x - z||^2}{2 \sigma ^2})$ is called the Gaussian kernel and is commonly used.

{{<figure src = "svm-kernel.png">}}
