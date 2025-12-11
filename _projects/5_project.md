---
layout: page
title: 2026 - Thesis - Neural Diffusion
description:
img: assets/img/4.jpg
importance: 5
category: work
related_publications: true
---

<br>

## Topics

  - [📍 Click Here](https://zenodo.org/), [AiiDA.net](https://www.aiida.net/)
  - [Thesis](https://sirop.org/app/013a8549-281d-475b-bc42-1a63fff75d98?_k=D4wOn3UvPzaQuIzU)
  - [CERN](https://home.cern/), [PSI](https://www.psi.ch/en)

<br>


## Tool Kits


- [Project MONAI](https://github.com/Project-MONAI)



<br>



## References

  - [2025 - ZapBench](https://github.com/google-research/zapbench)
  - [Development of the Nervous System](https://www.mls.uzh.ch/en/research/hajnal/teaching.html)
    - [Stoeckli Esther](https://www.mls.uzh.ch/en/research/stoeckli/research.html)
  - [Topological Deep Learning](https://decisive-stomach-548.notion.site/Topological-Deep-Learning-2a1425ccedaa800782f5ca86486c5080?showMoveTo=true&saveParent=true)
  - 2025 - TopoBench: A Framework for Benchmarking Topological Deep Learning](https://arxiv.org/pdf/2406.06642)
  - [2025 - some others - Discovering Symbolic Cognitive Models from Human and Animal Behavior](https://www.biorxiv.org/content/10.1101/2025.02.05.636732v1)
  - [2024 - Neural Diffusion Models](https://arxiv.org/pdf/2310.08337)
  - [2024 - Lightplane: Highly-Scalable Components for Neural 3D Fields](https://arxiv.org/pdf/2404.19760)


<br>


## Best Normalization

| **Data Distribution Characteristics**       | **Method**    | **Formula**                                                | **Core Assumption**                                                                 |
| ------------------------------------------- | --------------------------------------- | ---------------------------------------------------------- | ----------------------------------------------------------------------------------- |
| **Gaussian-like Distribution**              | Standard z-score normalization          | ((x - \mu) / \sigma)                                       | Most data points are concentrated near the mean; few outliers exist.                |
| **Skewed or Heavy-Tailed Distribution**     | Robust z-score (Median + MAD)           | ((x - \text{median}) / \text{MAD})                         | Extreme values exist; the median provides a more stable estimate.                   |
| **Bounded Values (0–1, Ratio-type Data)**   | Min–Max normalization                   | ((x - x_{\text{min}}) / (x_{\text{max}} - x_{\text{min}})) | Data lies within a fixed range; preserving proportional relationships is important. |
| **Log-Normal or Multiplicative Noise Data** | Log transform + z-score                 | (\log(x)) or (\log(1 + x)) → z-score                       | Noise varies multiplicatively; log transformation linearizes it.                    |
| **Mixed Noise or Asymmetric Distributions** | Quantile normalization / Rank transform | Mapping by quantiles                                       | The exact values are less important; only the rank order matters.                   |

<br>

## Brain Signals (Why Median + MAD)


| **Property**                  | **Meaning**                                       | **Impact**                                     |
| ----------------------------- | ------------------------------------------------- | ---------------------------------------------- |
| **Non-stationary**            | The mean varies across time and sessions          | Mean and standard deviation become unstable    |
| **Heavy-tailed distribution** | Strong artifacts or high-amplitude spikes         | Standard deviation is inflated by outliers     |
| **Weak signal + mixed noise** | High-frequency oscillations + low-frequency drift | Large mean variation, clear skewness           |
| **Inter-channel variation**   | Each sensor has different sensitivity             | Requires independent per-channel normalization |


<br><br><br>





