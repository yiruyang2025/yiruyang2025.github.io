---
layout: page
title: 2025 - Project 3
description: 3D Representation Learning
img: assets/img/4.jpg
importance: 3
category: work
related_publications: true
---



<br><br>


[DINOv2]

[2025 - VGGT: Visual Geometry Grounded Transformer](https://arxiv.org/html/2503.11651v1?utm_source=chatgpt.com)

[2023 - AudioPaLM - Google Research](https://arxiv.org/abs/2306.12925)

[2023 - AudioCraft](https://github.com/facebookresearch/audiocraft)


<br><br>

**Structure of DINOv2 and Goals**

<br>

- Explore 3D representation learning by -> combining self-distillation loss and diffusion loss

- **Why pre-train 3D representations?**
  - `Goal` - Before 3D downstream tasks (such as segmentation, classification, and registration), let the model be trained on large-scale unlabeled point clouds to obtain universal and robust feature representations.

  - `Challenges` - Point clouds do not have natural pixel grids like images, but are more sparse and disordered, requiring special network structures (PointNet, Point Transformer...) and task design.

<br>

- **Self-Distillation's "Representation Learning" Advantages**
  - Principle - Let the model act as both a "teacher" and a "student" at the same time, aligning features with each other through different augmented views (or different model branches)
  - Effect - Methods such as DINOv2 can learn very discriminative features for downstream segmentation/classification, and do not rely on labels
 
<br>

- **Diffusion Loss' "Generative" Advantages**
  - Principle - Gradually add noise to the unlabeled point cloud during the training phase, and then let the network learn to denoise at each noise level. The loss is generally the mean square error between the predicted noise and the real noise
  - Effect - The network learns both global and local "generative capabilities" and can capture high-fidelity distribution details

<br><br>

`Improve 3D pretraining strategies by combining Self-Distillation & Diffusion Losses / Flow-matching Losses`

- Combine the representation learning strengths of self-distillation models—such as DINOv2, which excels at segmentation and classification—with the high-fidelity feature capabilities of current generative diffusion models
- Begin by fine-tuning a 3D point cloud diffusion model (e.g., PointDif) and integrating self-distillation losses inspired by DINOv2, or contrastive-like regularizers as introduced in Diffuse and Disperse
- Then analyze the impact of these representation-enhancing losses on downstream tasks such as 3D segmentation and 3D classification



<br>


## References 1

<br><br>

[1] DINOv2: Learning robust visual features without supervision, Oquab et al. TMLR 2023

[2] High-resolution image synthesis with latent diffusion models, Rombach et al. CVPR 2022

[3] Point Cloud Pre-training with Diffusion Models, Zheng et al. CVPR 2024

[4] Diffuse and Disperse, Wang et al. ArXiv 2025

[5] A Tale of Two Features: Stable Diffusion Complements DINO for Zero-Shot Semantic Correspondence, Zhang et al. NeurIPS 2023

[6] 3D Scene Understanding with Open Vocabularies, Peng at al. CVPR 2023

[7] Harnessing Text-to-Image Diffusion Models for Point Cloud Self-Supervised Learning, Chen et al. ArXiv 2025



<br>

[2025 - How I Understand Flow Matching](https://www.youtube.com/watch?v=DDq_pIfHqLs)

[Flow Matching - GIF](https://x.com/mathusmassias/status/1935246909473521829?s=46&t=1tqSPaJVuc_ns2oTMZs8EQ)


<br>




<br><br>


## References 2

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


