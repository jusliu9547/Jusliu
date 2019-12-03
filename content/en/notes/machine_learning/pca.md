---
title: PCA
linktitle: Dimension Reduction
toc: true
type: docs
date: "2019-05-05T00:00:00+01:00"
draft: false
markup: mmark


menu:
  machine_learning:
    parent: Unsupervised Learning
    weight: 2

# Prev/next pager order (if `docs_section_pager` enabled in `params.toml`)
weight: 3

---

### Motivation

1. Data compression
2. Data visualization

### PCA algorithm

The pinciple component algorithm procedure is a dimension reduction technique that projects the data on $k$ dimensions by maximizing the variance of the data.

1. Data preprocessing: feature scaling/ mean normalization

$$
x^{(i)}_{j} = \frac {x^{(i)}_{j} - \mu_{j}}{\sigma_{j}}
$$

2. Compute covariance matrix 

$$
\Sigma = \frac{1}{m} \sum^{n}_{i = 1} (x^{(i)})(x^{(i)})^{T}
$$

3. Compute $\mu_{1}, ..., \mu_{k} $ the $k$ orthogonal eigenvectors of $\Sigma$

4. Project the data on $span_{\mathbb{R}}(\mu_{1}, ..., \mu_{k} )$

{{<figure src = "pca.png">}}

### Choosing $K$ (number of principle component)

1. Average squared projection error
2. Total variation in the data (how much variance you want to retain)
