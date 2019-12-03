---
title: Gaussian Discriminant Analysis
linktitle: GDA
toc: true
type: docs
date: "2019-05-05T00:00:00+01:00"
draft: false
markup: mmark

menu:
  machine_learning:
    parent: Supervised Learning
    weight: 4

# Prev/next pager order (if `docs_section_pager` enabled in `params.toml`)
weight: 8

---
### Gaussian Discriminant Analysis Algorithm

The Gaussian Discriminant Analysis assumes that $y$ and $x|y = 0$ and $x|y = 1$ are such that:
* $y \sim Bernoulli(\phi)$
* $x|y = 0 ~ N(\mu_{0}, \Sigma)$
* $x|y = 1 ~ N(\mu_{1}, \Sigma)$

1. Fit model $p(x)$ by setting

$$
\mu = \frac{1}{m} \sum^{m}_{i = 1} x^{(i)} 
$$


$$
\Sigma = \frac{1}{m}\sum^{m}_{i = 1}( x^{(i)} - \mu)( x^{(i)} - \mu)^{T}
$$

2. Given a new example $x$, compute

$$
p(x) = \frac{1}{(2\pi)^{\frac{n}{2}}|\Sigma|^{\frac{1}{2}}}exp(-\frac{1}{2} (x-\mu)^{T} \Sigma^{-1}(x-\mu) )
$$

3. Flag an anamoly if $p(x) < \epsilon$

### Applications
Anamoly detection, Fraud detection, ...
