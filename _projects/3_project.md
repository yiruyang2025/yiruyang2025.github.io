---
layout: page
title: 2026 - Project 3
description: Representation Learning
img: assets/img/4.jpg
importance: 3
category: work
related_publications: true
---

<br>


`Cross-Modal Representation Learning`

with 2 co-supervisors (hopefully)


<br>

Masked Flow Matching for Real-Time Signal Processing

[2010 - Meta-learning for time series forecasting and forecast combination](https://www.sciencedirect.com/science/article/pii/S0925231210001074?casa_token=eu0V3jGb8eIAAAAA:haVDZz9weP60Wt5smAtoHOmf0YEq8r8PPyf7BPNNaf6wLATzcWteTR6Vaqdda_6ipjyELg1YLs23)




<br>

**Backbone: Masked Flow Matching + Bayesian Layers**  
– Variational analogs of convolutional/fully-connected layers (e.g. `DenseVariational`, `BayesianLinear`)  
– Weights modeled by variational distribution $q(w)$  

<br><br>

**ELBO Loss**  
Minimize the negative Evidence Lower Bound:  

$$
\mathcal{L}_{\mathrm{ELBO}}(\theta, \phi)
=
\underbrace{\mathbb{E}_{w\sim q_\phi(w)}\bigl[\ell\bigl(f_w(x),\,y\bigr)\bigr]}_{\displaystyle\text{（1）Expected data loss}}
\;+\;
\underbrace{\lambda\;\mathrm{KL}\bigl(q_\phi(w)\,\|\,p(w)\bigr)}_{\displaystyle\text{（2）Variational Regularization}}
$$

<br><br>

**Inference via Weight Sampling**  
Perform $T$ stochastic forward passes with $w_t \sim q(w)$, then compute:  
$$
\mu(x) \;=\; \frac{1}{T}\sum_{t=1}^T f_{w_t}(x),
\quad
\sigma^2(x) \;=\; \frac{1}{T}\sum_{t=1}^T\bigl(f_{w_t}(x) - \mu(x)\bigr)^2
$$  

<br><br>

**Decision Making**  
If $\sigma(x) > \tau$, trigger a fallback or alert


<br>


<br><br>

## References

- Bayesian Neural Nets / BNN


<br><br>


