---
title: Model Selection
linktitle: Model Selection
toc: true
type: docs
date: "2019-05-05T00:00:00+01:00"
draft: false
markup: mmark

menu:
  machine_learning:
    parent: Tips
    weight: 3

# Prev/next pager order (if `docs_section_pager` enabled in `params.toml`)
weight: 7

---

When selecting a model, we distinguish data into 3 different parts as follow:

|Training set|Validation/Dev set|Testing set|
|:---:|:---:|:---:|
|Model is trained(80% usually)|Model is assessed(20% usually)|Model gives predictions|

Once the model has been chosen, it is trained on the entire dataset and tested on the unseen test set. These are represented in the figure below:

{{< figure src="train-val-test.png" lightbox="true" >}}

### Cross validation

A method is used to select a model that does not rely too much on the initial training set. The different types are summed up in the table below:

|k-fold|Leave-p-out|
|:---|:---|
|Training on $k-1$ folds and assessment on the remaining one.|Training on $n-p$ observations and assessment on the $p$ remaining ones|

{{< figure src="cross-validation.png" lightbox="true" >}}
