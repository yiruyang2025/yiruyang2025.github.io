---
layout: page
title: 2026 - Master Thesis - Robotics, Security
description: ETH AI Center, UZH AI, PRS
img: assets/img/4.jpg
importance: 5
category: work
related_publications: true
---

<br>


- [2026](https://music.youtube.com/watch?v=kRCnR0m_vBY&list=OLAK5uy_lU5_UbT2MLEJq7uSs5NU4f76VC6p6-ceU)
- [2023 - Seeing a Rose in Five Thousand Ways](https://ai.stanford.edu/~yzzhang/projects/rose/)
- [2026 - VGGT-SLAM 2.0: Real-time Dense Feed-forward Scene Reconstruction](https://www.youtube.com/watch?v=GBdOvd6p4OU)
- [2026 - Reward-Conditioned Reinforcement Learning](https://arxiv.org/pdf/2603.05066)
- [📍 2017 - One-Shot Imitation Learning](https://proceedings.neurips.cc/paper/2017/hash/ba3866600c3540f67c1e9575e213be0a-Abstract.html)



<br>

## Products

- [Nvidia GEAR](https://research.nvidia.com/labs/gear/#open-positions)
- [Matic Robots](https://www.youtube.com/watch?v=i_8CKdULXWg), home, level-5
- [Rovex Technologies](https://www.linkedin.com/company/gorovex/), hospital
- [Fourier](https://www.fftai.com/)
- [Flow](https://flow-project.github.io/), city navigation
- [Taalas Inc.](https://x.com/taalas_inc?lang=en)

<br>


## Task Definition

```
The essence of LiDAR-free technology can be summarized as: transforming sparse measurements of the physical world into dense geometric inference.
```

- [📍 2020 - Convolutional Occupancy Networks](https://arxiv.org/pdf/2003.04618)
- [2022 - Scalable Diffusion Models with Transformers](https://www.wpeebles.com/DiT), William Peebles, DiT


<br>


## References


- [2026 - High-Dimensional Probability](https://www.math.uci.edu/~rvershyn/papers/HDP-book/HDP-2.pdf)
- [2025 - Visual Chronicles: Using Multimodal LLMs to Analyze Massive Collections of Images](https://arxiv.org/pdf/2504.08727)
- [📍 2026 - SteerVLA: Steering Vision-Language-Action Models in Long-Tail Driving Scenarios](https://steervla.github.io/)


<br>

<br><br><br><br>




## Detection and Tracking Algorithms

| Layer                     | Technical Components                    | Application                                                                                                       |
| ------------------------- | --------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------- |
| Detection Backbone        | RT-DETR                                 | Transformer-based object detection producing spatially consistent bounding boxes and feature embeddings for downstream multi-view association. |
| Temporal Association      | Query-Based Tracking (e.g., MOTR-style) | Maintains persistent object identities across frames using learnable spatiotemporal queries instead of heuristic matching.                     |
| Multi-View Correspondence | Epipolar Geometry                       | Filters cross-camera matches using the Fundamental Matrix to enforce geometric consistency before triangulation.                               |
| 3D Reconstruction         | Triangulation + PnP                     | Recovers metric 3D positions from validated multi-view 2D detections and refines camera pose estimates.                                        |
| Global Optimization       | Bundle Adjustment                       | Minimizes reprojection error jointly over camera poses and object trajectories to achieve globally consistent 4D reconstruction.               |
| Dynamic Motion Modeling   | Motion Decomposition                    | Separates object motion from camera motion to stabilize optimization under dynamic scenes.                                                     |
| Spatiotemporal Refinement | Uncertainty-Aware Optimization          | Weighs correspondences by confidence scores to improve robustness under occlusion, noise, and adverse weather conditions.                      |
| Identity Persistence      | Cross-Camera Re-Identification          | Uses learned feature embeddings to maintain consistent object identities across disjoint camera views.                                         |


<br>





<br><br><br><br><br>
