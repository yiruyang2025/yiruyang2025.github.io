---
layout: page
title: 2025 - Thesis - 4D MapAnything
description: Feed-forward 4D Reconstruction
img: assets/img/4.jpg
importance: 4
category: work
related_publications: true
---

<br>

## References

[2025 - MapAnything: Universal Feed-Forward Metric 3D Reconstruction](https://map-anything.github.io/)



<br><br>

## 1. Metric-Scale 3D Reconstruction

### Definition
"Metric-scale" means that the reconstructed 3D scene is expressed in **real-world physical units (e.g., meters)** rather than up-to-scale or normalized units.

- **Up-to-scale reconstruction** recovers only the structure's shape, not its real scale factor.  
  Example: a room reconstructed as either 3 m or 30 m wide appears identical.
- **Metric-scale reconstruction** estimates a global scale parameter that converts the up-to-scale 3D structure into real-world dimensions.

In MapAnything, a global metric scale token $m$ is predicted such that:
$$
X_i^{metric} = m \cdot X_i^{\sim}
$$
where $X_i^{\sim}$ is the up-to-scale reconstruction.

---

## 2. 4D_MapAnything: Pipeline Overview

### Objective
To perform **feed-forward, metric-scale 4D reconstruction** of dynamic scenes using a **Time-Varying Generalized Camera** model.

### Concept
MapAnything models static multi-view geometry using a generalized camera (fixed light-ray set).  
4D_MapAnything extends this to **time-varying ray geometry**:
$$
\mathcal{C}(t) = \{ (p_i(t), d_i(t)) \}
$$
where each pixel corresponds to a ray with a time-dependent origin $p_i(t)$ and direction $d_i(t)$.

---

## 3. Input Design

| Input Type | Description | Example |
|-------------|--------------|----------|
| Image sequence $I_t$ | Temporal image frames or asynchronous event accumulations | RGB / event frames |
| Geometric priors | Extrinsics, intrinsics, sparse depth, IMU | VICON, COLMAP, SLAM |
| Time label $t$ | Frame or event timestamp | μs or ms |
| Optional motion prior | Scene flow or optical flow initialization | RAFT3D, DynamicStereo |

---

## 4. Model Architecture

### Encoder
- Vision Transformer backbone (e.g., DINOv2 / ViT-L)
- Temporal Positional Encoding (TPE):
  $$
  \text{TPE}(t) = \sin(\omega t + \phi)
  $$
- Token = image patch + geometric features + time embedding

### Transformer Core
- Based on MapAnything’s Alternating-Attention Transformer
- Extended to cross-attention over **(views × time)**
- Introduce **motion-aware attention block** modeling $\partial p / \partial t$

### Decoder Heads
- **Ray directions**: $R_i(t)$  
- **Depths along rays**: $D_i(t)$  
- **Camera poses**: $P_i(t) = [R_i(t), T_i(t)]$  
- **Global scale**: $m(t)$  
- **Scene flow**: $F_i(t) = X_i(t+\Delta t) - X_i(t)$  
- **Temporal clustering**: cluster latent features by motion patterns

---

## 5. Loss Functions

| Loss | Meaning | Expression |
|------|----------|------------|
| $L_{geom}$ | Geometric consistency (RDP structure) | As in MapAnything |
| $L_{metric}$ | Metric scale consistency | $||\log m_{pred} - \log m_{gt}||$ |
| $L_{flow}$ | Temporal scene flow consistency | $||X_t + F_t - X_{t+\Delta t}||$ |
| $L_{cluster}$ | Motion clustering | Contrastive or self-distillation |
| $L_{smooth}$ | Temporal smoothness | $||X_{t+1} - 2X_t + X_{t-1}||$ |
| $L_{mask}$ | Dynamic mask supervision | BCE or uncertainty weighting |

Adaptive Robust Loss is used to weight all residuals (see section 8).

---

## 6. Output

The model outputs:
$$
\mathcal{O} = \{ X_i(t), P_i(t), F_i(t), m(t), C_i(t) \}
$$

Where:
- $X_i(t)$: metric 3D points  
- $P_i(t)$: camera poses  
- $F_i(t)$: scene flow  
- $m(t)$: metric scale  
- $C_i(t)$: motion clusters

---

## 7. Training Strategy

| Stage | Goal | Data |
|--------|------|------|
| I. Static pretraining | Learn static geometry and scale | MapAnything datasets |
| II. Temporal alignment | Temporal consistency learning | Dynamic Replica / TartanAirV2 |
| III. Spatio-temporal fine-tuning | Train flow and clustering heads | Synthetic dynamic datasets |
| IV. Self-supervised finetuning | Real data adaptation | Photometric + geometric consistency |

---

## 8. Adaptive Robust Loss

### Core Idea
Adaptive Robust Loss is a **general parametric loss family** that unifies and generalizes $L_2$, $L_1$, Cauchy, Geman–McClure, and other robust losses under a single formulation.

#### General form:
$$
L(x; \alpha, c) = \frac{|\alpha - 2|}{\alpha} \left( \left( \frac{(x/c)^2}{|\alpha - 2|} + 1 \right)^{\alpha/2} - 1 \right)
$$

where:
- $\alpha$: shape parameter controlling robustness
- $c$: scale parameter controlling residual normalization

#### Special cases:
| $\alpha$ | Equivalent Loss | Behavior |
|-----------|----------------|-----------|
| 2 | L2 (Gaussian) | Sensitive, fast convergence |
| 1 | L1 (Laplacian) | Moderately robust |
| 0 | Cauchy | Heavy-tailed, robust |
| -2 | Geman–McClure | Very robust |
| $\to \infty$ | Welsch / Tukey | Bounded, ignores outliers |

### Adaptive Mechanism
$\alpha$ and $c$ are **learnable** via backpropagation, allowing the model to automatically tune its robustness:
- At early stages: smaller $\alpha$ → higher robustness
- Later: $\alpha \to 2$ → smoother convergence

This adaptivity stabilizes training on long-tailed error distributions common in visual geometry.

### Benefits
- Unifies all standard robust losses  
- Automatically adjusts to dataset noise level  
- Requires no manual tuning  
- Widely used in SLAM, SfM, VO, and 3D reconstruction tasks

Reference:  
J. T. Barron, *"A General and Adaptive Robust Loss Function,"* CVPR 2019, Google Research.

---

## 9. Evaluation Metrics

| Category | Metric |
|-----------|---------|
| Geometry | Depth rel, τ, ATE RMSE |
| Temporal consistency | Flow EPE, Temporal Chamfer distance |
| Clustering | Adjusted Rand Index (ARI), mIoU |
| Scale | Relative Scale Error |
| Overall | Reconstruction quality over time |

---

## 10. Research Impact and Potential Directions

| Aspect | Potential Contribution |
|---------|------------------------|
| Theoretical | Extension from static to time-varying generalized camera model |
| Model | Feed-forward transformer for 4D dynamic reconstruction |
| Task | Unified 3D + scene flow + temporal clustering |
| Application | Dynamic SLAM, event-based perception, neural radiance flow reconstruction |

Potential publication venues: CVPR, ICCV, ICRA, NeurIPS.

---

## 11. Summary

**MapAnything** models arbitrary static camera systems through a generalized camera representation.  
**4D_MapAnything** extends this to **time-varying generalized cameras**, enabling **metric-scale, feed-forward 4D reconstruction** with dynamic clustering and temporal consistency.

This framework offers a unified foundation for dynamic scene understanding across vision and robotics.







<br>





## Topics

  - [2024 - Interactive4D: Interactive 4D LiDAR Segmentation](https://arxiv.org/abs/2410.08206)
  - [4D Lidar L1 Application Scenarios - Robots - Unitree](https://www.unitree.com/cn/LiDAR)
  - [Aeva – 4DLiDAR for Autonomous Navigation - Auto Driving - beyond Beam](https://www.aeva.com/)
  - [A Digital Geneva / Zurich](https://carla.readthedocs.io/en/latest/adv_digital_twin/)



## References

<br>
