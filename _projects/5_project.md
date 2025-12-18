---
layout: page
title: 2026 - Thesis - Brain Mapping / Camera
description: SSL
img: assets/img/4.jpg
importance: 5
category: work
related_publications: true
---

<br>

## Topics

  - [EU Open Research Repository](https://zenodo.org/), [AiiDA.net](https://www.aiida.net/)
  - [Thesis](https://sirop.org/app/013a8549-281d-475b-bc42-1a63fff75d98?_k=D4wOn3UvPzaQuIzU)
  - [CERN](https://home.cern/), [PSI](https://www.psi.ch/en)


<br>


## References

- [2025 - 📍 ZapBench](https://github.com/google-research/zapbench)
- [Development of the Nervous System](https://www.mls.uzh.ch/en/research/hajnal/teaching.html)
    - [Stoeckli Esther](https://www.mls.uzh.ch/en/research/stoeckli/research.html)
- [Topological Deep Learning](https://decisive-stomach-548.notion.site/Topological-Deep-Learning-2a1425ccedaa800782f5ca86486c5080?showMoveTo=true&saveParent=true)
- [2025 - TopoBench: A Framework for Benchmarking Topological Deep Learning](https://arxiv.org/pdf/2406.06642)


<br>

## A Dynamic Camera with Signal Fusion / Space

- [📍 2013 - Self-Calibration and Visual SLAM with a Multi-Camera System on a
Micro Aerial Vehicle](https://people.inf.ethz.ch/pomarc/pubs/HengAURO15.pdf) and its references



<br><br><br><br>


## 3D/4D Non-Rigid Reconstruction vs. Series Elastic Actuators (SEA)

- Both problems replace impossible exact control or exact reconstruction with explicit structural priors that guarantee stability, coherence, and robustness under uncertainty

| Aspect                    | 3D / 4D Non-Rigid Reconstruction                                                              | Series Elastic Actuators (SEA)                                                                                            |
| ------------------------- | --------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------- |
| One-sentence essence      | Recover a time-varying continuous geometry from incomplete, noisy, and indirect observations. | Design a physical actuation system that remains stable, controllable, and predictable under uncertainty and non-rigidity. |
| Nature of the system      | Perceptual and representational                                                               | Physical and mechanical                                                                                                   |
| Objects involved          | Humans, animals, cloth, hair, soft bodies                                                     | Motors, gears, springs, loads, environment                                                                                |
| Type of non-rigidity      | Geometric deformation and topology change                                                     | Mechanical compliance and elasticity                                                                                      |
| Source of difficulty      | Incomplete observations and ill-posed inference                                               | Unknown contacts, shocks, delays, and model mismatch                                                                      |
| Observations / inputs     | 2D images, videos, sparse points, patch-level features                                        | Motor states, force sensing, spring deformation                                                                           |
| True target               | 3D / 4D geometry with spatiotemporal consistency                                              | Stable force / impedance interaction with the environment                                                                 |
| Local–global coupling     | Local deformation affects global shape                                                        | Local elastic deformation affects global stability                                                                        |
| Failure mode if untreated | Drift, collapse of correspondence, inconsistent geometry                                      | Instability, shocks, damage, unsafe interaction                                                                           |
| Core strategy             | Introduce structural priors to regularize an ill-posed inverse problem                        | Introduce mechanical structure to regularize an uncontrollable system                                                     |
| Role of structure         | Geometry, smoothness, correspondence, temporal coherence                                      | Passive elasticity, impedance, energy storage                                                                             |
| What structure replaces   | Impossible exact reconstruction from data alone                                               | Impossible exact control of rigid, high-gain actuators                                                                    |
| Problem class             | “Structural degeneration + ill-posed inverse problem”                                         | “Physical interaction + uncertainty problem”                                                                              |


<br>



## Tool Kits


- [Project MONAI](https://github.com/Project-MONAI)



<br>


## Best Normalization

| **Data Distribution Characteristics**       | **Method**                              | **Formula**                                      | **Core Assumption**                                                                 |
| ------------------------------------------- | --------------------------------------- | ------------------------------------------------ | ----------------------------------------------------------------------------------- |
| **Gaussian-like Distribution**              | Standard z-score normalization          | $z = \dfrac{x - \mu}{\sigma}$                    | Most data points are concentrated near the mean; few outliers exist.                |
| **Skewed or Heavy-Tailed Distribution**     | Robust z-score (Median + MAD)           | $z = \dfrac{x - \mathrm{median}}{\mathrm{MAD}}$  | Extreme values exist; the median provides a more stable estimate.                   |
| **Bounded Values (0–1, Ratio-type Data)**   | Min–Max normalization                   | $x' = \dfrac{x - x_{\min}}{x_{\max} - x_{\min}}$ | Data lies within a fixed range; preserving proportional relationships is important. |
| **Log-Normal or Multiplicative Noise Data** | Log transform + z-score                 | $\log(x)$ or $\log(1 + x);\rightarrow;$ z-score  | Noise varies multiplicatively; log transformation linearizes it.                    |
| **Mixed Noise or Asymmetric Distributions** | Quantile normalization / Rank transform | $x \mapsto \mathrm{rank}(x)$ or quantile mapping | Exact values are less important; relative ordering matters.                         |



<br>

## Brain Signals (Why Median + MAD)


| **Property**                  | **Meaning**                                       | **Impact**                                     |
| ----------------------------- | ------------------------------------------------- | ---------------------------------------------- |
| **Non-stationary**            | The mean varies across time and sessions          | Mean and standard deviation become unstable    |
| **Heavy-tailed distribution** | Strong artifacts or high-amplitude spikes         | Standard deviation is inflated by outliers     |
| **Weak signal + mixed noise** | High-frequency oscillations + low-frequency drift | Large mean variation, clear skewness           |
| **Inter-channel variation**   | Each sensor has different sensitivity             | Requires independent per-channel normalization |


<br><br><br>





