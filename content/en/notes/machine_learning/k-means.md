---
title: K-means
linktitle: K-means
toc: true
type: docs
date: "2019-05-05T00:00:00+01:00"
draft: false
markup: mmark


menu:
  machine_learning:
    parent: Unsupervised Learning
    weight: 1

# Prev/next pager order (if `docs_section_pager` enabled in `params.toml`)
weight: 3

---

### K-means algorithm
* Random initialize $K$ cluster centroids $\mu_{1}$, $\mu_{2}$, ..., $\mu_{k}$
* Repeat
  - Cluster assignment stage
      - for $i$ = 1 to $m$ \\
        c := index (from 1 to $K$) of cluster centroid closest to $x^{i}$
  - Move centroids
      - for $k$ = 1 to $K$ \\
        $\mu_{k}$ := average (mean) of points assigned to cluster $k$

{{<figure src = "k-means.png">}}

### Cost/ Distortion function
Optimization object:

$$
\mathop{\min}_{c^{1}, ..., c^{m}, \mu_{1}, ..., \mu_{k}} J(c^{1}, ..., c^{m}, \mu_{1}, ..., \mu_{k}) = \frac {1}{m} \sum^{m}_{i=1} || x^{i} - \mu_{c^{i}} ||^2
$$

### Choosing the value of $K$

* Elbow method
* Sometimes, you're running K-means to get clusters to use for some later/downstream purpose. Evaluate K-means based on a metric for how well it serve for the later purpose.
