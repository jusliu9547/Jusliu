---
title: Error/ Ceiling Analysis
linktitle: Error/ Ceiling Analysis
toc: true
type: docs
date: "2019-05-05T00:00:00+01:00"
draft: false
markup: mmark

menu:
  machine_learning:
    parent: Tips
    weight: 5

# Prev/next pager order (if `docs_section_pager` enabled in `params.toml`)
weight: 8

---

### Error analysis

Manually examine the examples (in cross validation set) that your algorithm made errors on. See if you spot any systematic trend in what type of examples it is making errors on.

### Ceiling analysis

Estimate the errors due to each component to decide what part of the pipeline should spend the most time trying to improve.
