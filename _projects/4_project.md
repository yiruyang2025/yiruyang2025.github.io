---
layout: page
title: 2026 - Project and Thesis - Liver Predictor
description: Vision Patent, University Hospital of Zürich
img: assets/img/4.jpg
importance: 4
category: work
related_publications: true
---

<br>

## Topic and PI

- [Dr. Yong Wang](https://scholar.google.com/citations?user=CTXOhoYAAAAJ&hl=en)
- [Dr. Wei Wei](https://scholar.google.com/citations?user=rZLVC2sAAAAJ&hl=en)

- [📍 2025 - Transfer learning between different computer vision tasks](https://scholar.google.com/citations?view_op=view_citation&hl=en&user=8gruapYAAAAJ&sortby=pubdate&citation_for_view=8gruapYAAAAJ:RYcK_YlVTxYC)
  - Thesis topic, Validation of A Vision Patent On Transplant Donor Medical Data from Swiss Hospital

<br>


<p align="left">
  <img src="https://yiruyang2025.github.io/assets/img/project4_1.png" alt="Project 1 Visualization" width="75%">
</p>


<br>

## References

- ViT: An Image is Worth 16x16 Words: Transformers for Image Recognition at Scale, ICLR 2021.
- Large-scale pancreatic cancer detection via non-contrast CT and deep learning, Nature 2023.
- BYOL: Bootstrap your own latent: A new approach to self-supervised Learning, GDM, NeurIPS 2020.
- CLIP: Learning Transferable Visual Models From Natural Language Supervision, ICML 2021.
- AlexNet: ImageNet Classification with Deep Convolutional Neural Networks, NeurIPS 2012.
- 📍 ResNet: Deep Residual Learning, CVPR 2015.
- [2026 - Scaling medical imaging report generation with multimodal reinforcement learning](https://rexrank.ai/)


```
        Representation Learning
                   ▲
                   │
Small / Limited Supervision ──── Tabular / Medical Data
```

- Moderate clustering metrics across PCA, t-SNE, and UMAP indicate non-random latent structure but insufficient outcome separability, highlighting the need for representation learning beyond geometric proximity in raw tabular space.


<br>


## The 'Right Abstraction' for A System

```
Category                          | Focus Area / Topics
----------------------------------|------------------------------------------------------------
Representation & Inductive Bias   | Network architecture design
                                  | Multimodal alignment (vision–language–action)
                                  | World models
                                  | 
                                  | Impact of good inductive bias:
                                  | - 10× less data required
                                  | - 100× lower training cost

Learning × Control                | Model-based reinforcement learning
                                  | Differentiable MPC
                                  | Latent dynamics models
                                  | Structured sim-to-real methods
                                  |
                                  | Key insight:
                                  | - Control background is a major advantage
                                  | - Not brute-force learning

System-level AI                   | ML compilers
                                  | Scheduling on heterogeneous hardware
                                  | Memory-aware training
                                  | Inference optimization
                                  |
                                  | These areas strongly reward intelligent
                                  | system and structure design

Robotics / Embodied AI            | Not actuators, SEA, or motors
                                  | (These are constrained by physics)
                                  |
                                  | Instead focus on:
                                  | - Contact representation
                                  | - Hybrid system abstraction
                                  | - Task decomposition
                                  | - Perception–control interfaces
                                  | - Failure-aware planning
                                  |
                                  | Goal:
                                  | - Replace large sets of heuristics with
                                  |   a unified abstraction
```


<br>


## Liver Donor - 39 Real-world Patient Cases

```
FEATURES = [
    "donor_age",
    "AST",
    "ALT",
    "bilirubin",
    "DCD",
    "cold_ischemia_time",
    "warm_ischemia_time",
]

encoder = TabularEncoder(input_dim=len(FEATURES)*2)
classifier = TransplantabilityHead(z_dim=64)

encoder.eval()
classifier.eval()

p = predict_transplantability(
    "donor_012.json",
    encoder,
    classifier,
    FEATURES
)

print(f"Predicted P(TX) = {p:.3f}")
```


<br>

## Metric-Scale 3D Reconstruction


**Definition**

- "Metric-scale" means that the reconstructed 3D scene is expressed in **real-world physical units (e.g., meters)** rather than up-to-scale or normalized units.

- **Up-to-scale reconstruction** recovers only the structure's shape, not its real scale factor.  
  Example: a room reconstructed as either 3 m or 30 m wide appears identical.
- **Metric-scale reconstruction** estimates a global scale parameter that converts the up-to-scale 3D structure into real-world dimensions.
- In MapAnything, a global metric scale token $m$ is predicted such that:
$$
X_i^{metric} = m \cdot X_i^{\sim}
$$
where $X_i^{\sim}$ is the up-to-scale reconstruction.

---

**Pipeline**

**Objective**

- To perform **feed-forward, metric-scale 4D reconstruction** of dynamic scenes using a **Time-Varying Generalized Camera** model.

**Concept**

- MapAnything models static multi-view geometry using a generalized camera (fixed light-ray set).  

$$
\mathcal{C}(t) = \{ (p_i(t), d_i(t)) \}
$$
where each pixel corresponds to a ray with a time-dependent origin $p_i(t)$ and direction $d_i(t)$.

---

**Input Design**


| Input Type | Description | Example |
|-------------|--------------|----------|
| Image sequence $I_t$ | Temporal image frames or asynchronous event accumulations | RGB / event frames |
| Geometric priors | Extrinsics, intrinsics, sparse depth, IMU | VICON, COLMAP, SLAM |
| Time label $t$ | Frame or event timestamp | μs or ms |
| Optional motion prior | Scene flow or optical flow initialization | RAFT3D, DynamicStereo |

---

**Model Architecture**

**Encoder**
- Vision Transformer backbone (e.g., DINOv2 / ViT-L)
- Temporal Positional Encoding (TPE):
  $$
  \text{TPE}(t) = \sin(\omega t + \phi)
  $$
- Token = image patch + geometric features + time embedding

**Transformer Core**
- Based on MapAnything’s Alternating-Attention Transformer
- Extended to cross-attention over **(views × time)**
- Introduce **motion-aware attention block** modeling $\partial p / \partial t$

**Decoder Heads**
- **Ray directions**: $R_i(t)$  
- **Depths along rays**: $D_i(t)$  
- **Camera poses**: $P_i(t) = [R_i(t), T_i(t)]$  
- **Global scale**: $m(t)$  
- **Scene flow**: $F_i(t) = X_i(t+\Delta t) - X_i(t)$  
- **Temporal clustering**: cluster latent features by motion patterns

---

**Loss Functions**


| Loss | Meaning | Expression |
|------|----------|------------|
| $L_{geom}$ | Geometric consistency (RDP structure) | As in MapAnything |
| $L_{metric}$ | Metric scale consistency | $\|\log m_{\text{pred}} - \log m_{\text{gt}}\|$ |
| $L_{flow}$ | Temporal scene flow consistency | $\|X_t + F_t - X_{t+\Delta t}\|$ |
| $L_{cluster}$ | Motion clustering | Contrastive or self-distillation |
| $L_{smooth}$ | Temporal smoothness | $\|X_{t+1} - 2X_t + X_{t-1}\|$ |
| $L_{mask}$ | Dynamic mask supervision | BCE or uncertainty weighting |


- Adaptive Robust Loss is used to weight all residuals (see Section 8).

---

**Output**

- The model outputs:
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

**Training Strategy**

| Stage | Goal | Data |
|--------|------|------|
| 1. Static pretraining | Learn static geometry and scale | MapAnything datasets |
| 2. Temporal alignment | Temporal consistency learning | Dynamic Replica / TartanAirV2 |
| 3. Spatio-temporal fine-tuning | Train flow and clustering heads | Synthetic dynamic datasets |
| 4. Self-supervised finetuning | Real data adaptation | Photometric + geometric consistency |

---

**Adaptive Robust Loss**

**Core Idea**

- Adaptive Robust Loss is a **general parametric loss family** that unifies and generalizes $L_2$, $L_1$, Cauchy, Geman–McClure, and other robust losses under a single formulation.

**General form**

$$
L(x; \alpha, c) = \frac{|\alpha - 2|}{\alpha} \left( \left( \frac{(x/c)^2}{|\alpha - 2|} + 1 \right)^{\alpha/2} - 1 \right)
$$

where:
- $\alpha$: shape parameter controlling robustness
- $c$: scale parameter controlling residual normalization

**Special cases**

| $\alpha$ | Equivalent Loss | Behavior |
|-----------|----------------|-----------|
| 2 | L2 (Gaussian) | Sensitive, fast convergence |
| 1 | L1 (Laplacian) | Moderately robust |
| 0 | Cauchy | Heavy-tailed, robust |
| -2 | Geman–McClure | Very robust |
| $\to \infty$ | Welsch / Tukey | Bounded, ignores outliers |

**Adaptive Mechanism**

$\alpha$ and $c$ are **learnable** via backpropagation, allowing the model to automatically tune its robustness:
- At early stages: smaller $\alpha$ → higher robustness
- Later: $\alpha \to 2$ → smoother convergence

- This adaptivity stabilizes training on long-tailed error distributions common in visual geometry.

**Benefits**

- Unifies all standard robust losses  
- Automatically adjusts to dataset noise level  
- Requires no manual tuning  
- Widely used in SLAM, SfM, VO, and 3D reconstruction tasks


---

**Evaluation Metrics**

| Category | Metric |
|-----------|---------|
| Geometry | Depth rel, τ, ATE RMSE |
| Temporal consistency | Flow EPE, Temporal Chamfer distance |
| Clustering | Adjusted Rand Index (ARI), mIoU |
| Scale | Relative Scale Error |
| Overall | Reconstruction quality over time |

---



<br>

## What Kinds of Computer Vision Tasks It Can Be Applied To

- [2025 - Transfer learning between different computer vision tasks](https://patentimages.storage.googleapis.com/0a/f0/2c/1f28d09af469a8/US12272442B2.pdf)

| Task Category                   | Example Tasks                                | Why Transfer Learning Helps                                            |
| ------------------------------- | -------------------------------------------- | ---------------------------------------------------------------------- |
| **Image Classification**        | Object or scene classification               | Reuses low- and mid-level visual features learned from large datasets. |
| **Object Detection**            | Bounding box localization and recognition    | Transfers backbone representations to detection heads.                 |
| **Semantic Segmentation**       | Pixel-level labeling of images               | Leverages shared visual structure across tasks.                        |
| **Depth Estimation**            | Predicting depth or geometry from images     | Adapts learned visual cues to geometric inference.                     |
| **Video Understanding**         | Action recognition, temporal perception      | Transfers spatial features to temporal models.                         |
| **Domain Adaptation**           | Cross-domain image understanding             | Allows adaptation between different visual domains.                    |
| **Robotics Perception**         | Object recognition for manipulation          | Enables rapid adaptation to new environments.                          |
| **Autonomous Systems**          | Road scene understanding, obstacle detection | Shares representations across perception subtasks.                     |
| **Multi-task Learning Systems** | Unified perception pipelines                 | Supports multiple vision tasks using a shared model backbone.          |


<br><br>



<br>
