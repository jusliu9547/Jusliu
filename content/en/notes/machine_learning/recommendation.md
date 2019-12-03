---
title: Recommendation System
linktitle: Recommendation System
toc: true
type: docs
date: "2019-05-05T00:00:00+01:00"
draft: false
markup: mmark

menu:
  machine_learning:
    parent: Application
    weight: 1

# Prev/next pager order (if `docs_section_pager` enabled in `params.toml`)
weight: 8

---
### Example data

|Movie|Alice|Bob|Carol|Dave|$x_{1} (romance)$|$x_{2} (action)$|
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|Love at last|5|5|0|0|0.9|0|
|Romance forever|5|?|?|0|1.0|0.01|
|Cute puppies of love|?|4|0|?|0.99|0|
|Nonstop car chases|0|0|5|4|0.1|1.0|
|Swords vs. karate|0|0|5|?|0|0.9|

#### Notation
* $n_{u}$: number of user
* $n_{m}$: number of movie
* $r(i, j) = 1$ if user $j$ rated movie $i$
* $y^{(i, j)}$: rating by user $j$ on movie $i$ (if defined)
* $\theta^{(j)}$: parameter vector for user $j$
* $x^{(i)}$: parameter vector for movie $i$
* For user $j$, movie $i$, predicted rating: 
$$
(\theta^{(j)})^{T}(x^{(i)})
$$


### Content-based 
Using hand-engineer feature $x_{1} (romance)$ and $x_{2} (action)$ to calculate the user preference.

#### Optimization objective

* To learn $\theta^{(j)}$ (parameter for user $j$)

$$
\mathop{\min}_{\theta^{(j)}} \frac{1}{2} \sum _{i:r(i, j)=1} ((\theta^{(j)})^{T}x^{(i)} - y^{(i, j)})^2 + \frac{\lambda}{2}  \sum_{k=1}^{n} (\theta^{(j)}_{k})^2
$$

* To learn $\theta^{(1)}, \theta^{(2)}, ..., \theta^{(n_{u})}$

$$
\mathop{\min}_{\theta^{(1)}, \theta^{(2)}, ..., \theta^{(n_{u})}} \frac{1}{2} \sum_{j=1}^{n_{u}} \sum _{i:r(i, j)=1} ((\theta^{(j)})^{T}x^{(i)} - y^{(i, j)})^2 + \frac{\lambda}{2} \sum_{j=1}^{n_{u}} \sum_{k=1}^{n} (\theta^{(j)}_{k})^2
$$

### Collaborative filtering
To address some of the limitations of content-based filtering like hand-engineer, collaborative filtering uses similarities between users and items simultaneously to provide recommendations.

#### Optimization objective:

1. Given $ x^{(1)}, ..., x^{(n_{m})}$, estimate $ \theta^{(1)}, ..., \theta^{(n_{u})} $:

$$
\mathop{min}_{\theta^{(1)}, ..., \theta^{(n_{u})}} \frac{1}{2} \sum_{j=1}^{n_{u}} \sum _{i:r(i, j)=1} ((\theta^{(j)})^{T}x^{(i)} - y^{(i, j)})^2 + \frac{\lambda}{2} \sum_{j=1}^{n_{u}} \sum_{k=1}^{n} (\theta^{(j)}_{k})^2
$$

2. Given $ \theta^{(1)}, ..., \theta^{(n_{u})} $, estimate $ x^{(1)}, ..., x^{(n_{m})}$:

$$
\mathop{min}_{\theta^{(1)}, ..., \theta^{(n_{u})}} \frac{1}{2} \sum_{i=1}^{n_{m}} \sum _{i:r(i, j)=1} ((\theta^{(j)})^{T}x^{(i)} - y^{(i, j)})^2 + \frac{\lambda}{2} \sum_{i=1}^{n_{m}} \sum_{k=1}^{n} (x^{(i)}_{k})^2
$$

3. Minimizing $ x^{(1)}, ..., x^{(n_{m})}, \theta^{(1)}, ..., \theta^{(n_{u})} $ simultaneously:

$$
J(x^{(1)}, ..., x^{(n_{m})}, \theta^{(1)}, ..., \theta^{(n_{u})}) = \frac{1}{2} \sum_{i=1}^{n_{m}} \sum _{i:r(i, j)=1} ((\theta^{(j)})^{T}x^{(i)} - y^{(i, j)})^2 + \frac{\lambda}{2} \sum_{i=1}^{n_{m}} \sum_{k=1}^{n} (x^{(i)}_{k})^2 + \frac{\lambda}{2} \sum_{j=1}^{n_{u}} \sum_{k=1}^{n} (\theta^{(j)}_{k})^2
$$

namly,

$$
\mathop{min}_{x^{(1)}, ..., x^{(n_{m})}, \theta^{(1)}, ..., \theta^{(n_{u})}} J(x^{(1)}, ..., x^{(n_{m})}, \theta^{(1)}, ..., \theta^{(n_{u})})
$$

#### Collaborative filtering algorithm:

1. Initialize $ x^{(1)}, ..., x^{(n_{m})}, \theta^{(1)}, ..., \theta^{(n_{u})} $ to small random values.
2. Minimize $J(x^{(1)}, ..., x^{(n_{m})}, \theta^{(1)}, ..., \theta^{(n_{u})}) $ using gradient descent 
3. For a user with parameters $\theta$ and a movie with learned features $x$, predict a star rating of $\theta^{T}x$

