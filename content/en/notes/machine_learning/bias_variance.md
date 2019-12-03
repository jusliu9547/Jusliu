---
title: Bias/ Variance
linktitle: Bias/ Variance
toc: true
type: docs
date: "2019-05-05T00:00:00+01:00"
draft: false
markup: mmark

menu:
  machine_learning:
    parent: Tips
    weight: 2

# Prev/next pager order (if `docs_section_pager` enabled in `params.toml`)
weight: 8

---

### Vocabulary

* Bias: The bias of a model is the difference between the expected prediction and the correct model that we try to predict for given data points.

* Variance: The variance of a model is the variability of the model prediction for given points.

* Bias/ variance tradeoff: The simpler the model, the higher the bias, and more complex the model, the higher the variance.

||Underfitting|Just right|Overfitting|
|:---|:---|:---|:---|
|Symptoms|High training error, training error close to test error, high bias|Training error slightly lower than test error|Very low training error, training error much lower than test error, high variance|
|Regression illustration|{{< figure src="regression-underfit.png" lightbox="true" >}}|{{< figure src="regression-just-right.png" lightbox="true" >}}|{{< figure src="regression-overfit.png" lightbox="true" >}}|
|Classification illustration|{{< figure src="classification-underfit.png" lightbox="true" >}}|{{< figure src="classification-just-right.png" lightbox="true" >}}|{{< figure src="classification-overfit.png" lightbox="true" >}}|
|Deep learning illustration|{{< figure src="deep-learning-underfit.png" lightbox="true" >}}|{{< figure src="deep-learning-just-right.png" lightbox="true" >}}|{{< figure src="deep-learning-overfit.png" lightbox="true" >}}|
|Possible remedies|Complexify model, Add more features, Train longer|.|Regualarization, Get more data|
