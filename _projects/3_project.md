---
layout: page
title: 2025 - Project 3
description: 3D Representation Learning
img: assets/img/4.jpg
importance: 3
category: work
related_publications: true
---




<br><br><br><br>


[DINOv2]

[2025 - VGGT: Visual Geometry Grounded Transformer](https://arxiv.org/html/2503.11651v1?utm_source=chatgpt.com)

<br>


[2023 - AudioPaLM - Google Research](https://arxiv.org/abs/2306.12925)

[2023 - AudioCraft](https://github.com/facebookresearch/audiocraft)


<br><br><br><br>







## References

<br><br>

[2015 - U-Net: Convolutional Networks for Biomedical Image Segmentation](https://arxiv.org/abs/1505.04597)

[2016 - V-Net: Fully Convolutional Neural Networks for Volumetric Medical Image Segmentation](https://arxiv.org/abs/1606.04797)

[2020 - nnU-Net: a self-configuring method for deep learning-based biomedical image segmentation](https://www.nature.com/articles/s41592-020-01008-z)

[2021 - TransUNet: Transformers Make Strong Encoders for Medical Image Segmentation](https://arxiv.org/abs/2102.04306)

[2021 - UNETR: Transformers for 3D Medical Image Segmentation](https://arxiv.org/abs/2103.10504)


<br><br>




<br><br><br><br><br><br><br><br>



## Some other topics

Masked Flow Matching for Real-Time Signal Processing

[2010 - Meta-learning for time series forecasting and forecast combination](https://www.sciencedirect.com/science/article/pii/S0925231210001074?casa_token=eu0V3jGb8eIAAAAA:haVDZz9weP60Wt5smAtoHOmf0YEq8r8PPyf7BPNNaf6wLATzcWteTR6Vaqdda_6ipjyELg1YLs23)


**Backbone: Masked Flow Matching + Bayesian Layers**  
– Variational analogs of convolutional/fully-connected layers (e.g. `DenseVariational`, `BayesianLinear`)  
– Weights modeled by variational distribution $q(w)$  

<br>

**ELBO Loss**  
Minimize the negative Evidence Lower Bound:  

$$
\mathcal{L}_{\mathrm{ELBO}}(\theta, \phi)
=
\underbrace{\mathbb{E}_{w\sim q_\phi(w)}\bigl[\ell\bigl(f_w(x),\,y\bigr)\bigr]}_{\displaystyle\text{（1）Expected data loss}}
\;+\;
\underbrace{\lambda\;\mathrm{KL}\bigl(q_\phi(w)\,\|\,p(w)\bigr)}_{\displaystyle\text{（2）Variational Regularization}}
$$

<br>

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


<br><br>

## References

- Bayesian Neural Nets / BNN


<br><br>


