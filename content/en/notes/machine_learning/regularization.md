---
title: Regularization
linktitle: Regularization
toc: true
type: docs
date: "2019-05-05T00:00:00+01:00"
draft: false
markup: mmark

menu:
  machine_learning:
    parent: Tips
    weight: 1

# Prev/next pager order (if `docs_section_pager` enabled in `params.toml`)
weight: 7

---

### Overfitting 

Idea: If we have too many features, the learned hypothesis may fit the training set very well, but fail to generalize to new examples.

### How to address?

Options:
1. Reduce number of features
  - Manually select
  - Model selection algorithm
2. Regularization
  - Keep all features, but reduce magnitude/ values of parameters $\theta_{j}$.
  - Works well when we have a lot of features, each of which contributes a bit to predict $y$.

### Regularization types

|LASSO|Ridge|Elastic Net|
|:---:|:---:|:---:|
|Shrinks coefficients to 0, Good for variable selection|Makes coefficients smaller|Tradeoff between variable selection and small coefficients|
|{{< figure src="lasso.png" title="" lightbox="true" >}}|{{< figure src="ridge.png" title="" lightbox="true" >}}|{{< figure src="elastic-net.png" title="" lightbox="true" >}}|
|$...+\lambda \| \| \theta \| \| _{1}$|$...+\lambda \|\| \theta \|\|_{2}^{2}$|$...+\lambda [ (1-\alpha) \|\| \theta \|\|_{1} + \alpha \|\|\theta \|\| _{2}^{2} ]$|
