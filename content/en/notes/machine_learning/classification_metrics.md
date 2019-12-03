---
title: Classification Metrics
linktitle: Classification Metrics
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
weight: 8

---
### Confusion matrix

The confusion matrix is used to have a more complete picture when assessing the performance of a model and deal with skewed data. It is defined as follows:

{{<figure src = "confusion_matrix.png" >}}

### Main metrics

|Metric|Formula|Interpretaion|
|:---|:---:|:---:|
|Accuracy|$\frac {TP + TN}{TP + TN + FP + FN}$|Overall performance of model|
|Precision|$\frac {TP}{TP+FP}$|How accurate the positive predictions are|
|Recall/ Sensitivity|$\frac{TP}{TP+FN}$|Converge of actual positive sample|
|Specificity|$\frac{TN}{TN+FP}$|Converge of actual negative sample|
|F1 score|$\frac{2TP}{2TP+FP+FN}$|Hybrid metric useful for unbalanced classes|

### ROC

The receiver operating curce, also noted ROC, is the plot of TPR versus FPR by varying the threshold. These metrics are summed up below:

|Metric|Formula|Equivalent|
|:---|:---:|:---:|
|True Positive Rate, TPR|$\frac{TP}{TP+FN}$|Recall, sensitivity|
|False Positive Rate, FPR|$\frac{FP}{TN+FP}$|1-specificity|

### AUC

The area under the receiving operating curve, also noted AUC or AUROC, is the area below the ROC as shown in the following figure:

{{<figure src = "roc-auc.png">}}
