---
layout: page
title: 2026 - Thesis - Liver Predictor
description: SSL, USZ
img: assets/img/4.jpg
importance: 4
category: work
related_publications: true
---

<br>

## References

- 📍 ViT: An Image is Worth 16x16 Words: Transformers for Image Recognition at Scale, ICLR 2021.
- Large-scale pancreatic cancer detection via non-contrast CT and deep learning, Nature 2023.
- BYOL: Bootstrap your own latent: A new approach to self-supervised Learning, Google Deepmind, NeurIPS 2020.
- CLIP: Learning Transferable Visual Models From Natural Language Supervision, ICML 2021.
- AlexNet: ImageNet Classification with Deep Convolutional Neural Networks, NeurIPS 2012.
- 📍 ResNet: Deep Residual Learning, CVPR 2015.
- 

```
        Representation Learning
                   ▲
                   │
Small / Limited Supervision ──── Tabular / Medical Data
```

Moderate clustering metrics across PCA, t-SNE, and UMAP indicate non-random latent structure but insufficient outcome separability, highlighting the need for representation learning beyond geometric proximity in raw tabular space.

<br>

## Impact of Realistic Quantum Noise Modeling on System Capability

| Noise Characteristic                  | Consequence If Ignored                                                                                    | Capability When Properly Modeled                                                                                             |
| ------------------------------------- | --------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------- |
| **Non-Gaussian Noise**                | Rare but large noise events catastrophically break control loops and invalidate average-error assumptions | Control policies become robust to outliers and extreme events, enabling reliable operation under real hardware conditions    |
| **Temporal Drift**                    | Continuous manual recalibration is required as device parameters slowly change over time                  | The system adapts online, tracking slow parameter drift automatically and maintaining performance without human intervention |
| **Non-Markovian Memory Effects**      | Gate fidelity collapses because past operations influence future behavior in unmodeled ways               | Long-horizon stability is achieved by learning history-dependent dynamics and compensating for hardware memory               |
| **Spatial and Temporal Correlations** | Crosstalk accumulates across qubits, causing errors to scale with system size                             | Coordinated, chip-level control strategies emerge that actively suppress correlated errors                                   |
| **Physical Noise Origins**            | Noise is treated as an abstract nuisance, offering no guidance for improving hardware                     | Learned models expose actionable physical causes, directly informing materials, layout, and electronics design               |
| **High-Dimensional Structure**        | Simplified models fail to represent reality and break as system size grows                                | Scalable AI models capture latent structure, enabling control and optimization of large-scale quantum processors             |


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

## References

- [2025 - MapAnything: Universal Feed-Forward Metric 3D Reconstruction](https://map-anything.github.io/)

<br>

## Robotics

**1. Series Elastic Actuators**

- [📍 1995 - Series Elastic Actuators](https://fab.cba.mit.edu/classes/865.15/people/rebecca.kleinberger/assets/papers/SEA_Pratt.pdf)
- [2017 - Intro](https://www.youtube.com/watch?v=gZLO2Am0Zk8)


<br>

**2. Advances in self-supervised multimodal learning - Prof. Dr. Hilde Kuehne (Tuebingen AI Center)**

- [2025 - Recording](https://www.youtube.com/watch?v=uhVzzW5d4W4)

<br>


**3. Products**


- [Apptronik](https://apptronik.com/)
- [📍 TNKR.ai](https://tnkr.ai/explore)




<br><br>



## 4D Gaussian Formulation

| Property              | 3D Gaussian Splatting          | 4D Gaussian Fields                          |
| --------------------- | ------------------------------ | ------------------------------------------- |
| Temporal modeling     | Static scene                   | Dynamic, time-dependent scene               |
| Parameterization      | Fixed $(\mu_i, \Sigma_i, c_i)$ | Functions $(\mu_i(t), \Sigma_i(t), c_i(t))$ |
| Motion representation | None                           | Explicit velocity field $v(\mathbf{x}, t)$  |
| Topology handling     | Fixed structure                | Supports appearance/disappearance           |
| Continuity            | Spatial smoothness             | Spatiotemporal smoothness                   |
| Rendering             | Per-frame splatting            | Motion-compensated splatting                |


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


## Multi-modal Inference

- The capacity to accurately interpret multimodal inputs typically only emerges in large models with billions of parameters 




<br>

## References

  - [2023 - Gpt-4 technical report](https://cdn.openai.com/papers/gpt-4.pdf)
  - [📍 2024 - Improved Baselines with Visual Instruction Tuning](https://openaccess.thecvf.com/content/CVPR2024/papers/Liu_Improved_Baselines_with_Visual_Instruction_Tuning_CVPR_2024_paper.pdf)


<br>



## Others

  - [2024 - Interactive4D: Interactive 4D LiDAR Segmentation](https://arxiv.org/abs/2410.08206)
  - [4D Lidar L1 Application Scenarios - Robots - Unitree](https://www.unitree.com/cn/LiDAR)
  - [Aeva – 4DLiDAR for Autonomous Navigation - Auto Driving - beyond Beam](https://www.aeva.com/)
  - [A Digital Geneva / Zurich](https://carla.readthedocs.io/en/latest/adv_digital_twin/)


<br>
