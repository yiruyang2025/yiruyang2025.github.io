---
layout: page
title: 2025 - Thesis - Benchmark
description: 4D Reconstruction, DINO_4D
img: assets/img/4.jpg
importance: 2
category: work
related_publications: true
---

<br>

## Topics

- [2022 - AlphaCode](https://deepmind.google/blog/competitive-programming-with-alphacode/)
- ViT, DINOv3, Semantic-SAM, OpenScene, 📍SAP (Shape As Points), DiT

<br>


## Not Related But Art works

  - [2021 - Shape As Points: A Differentiable Poisson Solver](https://arxiv.org/abs/2106.03452)
  - [2023 - OpenScene](https://openaccess.thecvf.com/content/CVPR2023/papers/Peng_OpenScene_3D_Scene_Understanding_With_Open_Vocabularies_CVPR_2023_paper.pdf)
  - [2026 - PaperBanana](https://x.com/alphasignalai/status/2018815238829928711?s=46&t=1tqSPaJVuc_ns2oTMZs8EQ), [Jax](https://github.com/google-deepmind/penzai)
  - [2018 - GQN](https://deepmind.google/discover/blog/neural-scene-representation-and-rendering/)

<br>


## Motion

  - [2025 - 📍 Probabilistic Methods for Monocular 3D Human Reconstruction](https://scholar.google.com/scholar?hl=en&as_sdt=0%2C5&q=Probabilistic+Methods+for+Monocular+3D+Human+Reconstruction&btnG=)
  - [Mahcine Learning Street Talk](https://x.com/MLStreetTalk/status/1952743787454668931) - 📍 Genie 3

<br>


## Attended Doctoral Thesis Defense

- Generalizing Monocular 3D Estimation by Luigi Piccinelli, 9 Dec 2025 at 3pm, in Room HG D22

<br>


## Open Problems in Traditional 3DV

| **Aspect**                                           | **Unresolved Pain Point**                                                                    | **Why Existing Methods Are Not Enough**                                                                                                  | **Potential Directions to Solve**                                                                                             | **Existing Efforts (Yes / Partial / No)**                                                                                            |
| ---------------------------------------------------- | -------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| **1. Dynamic Scenes (non-static, non-rigid motion)** | Traditional SfM assumes static scenes; moving or deformable objects are treated as outliers. | Even with feature-metric refinement, rigid-scene assumptions fail; motion causes inconsistent correspondences and reconstruction errors. | Introduce dynamic NeRF, scene-flow-based SfM, or implicit dynamic field modeling to capture motion and deformation over time. | **Partial.** Dynamic NeRFs and neural SDF-flow methods partially address non-rigid motion.                                           |
| **2. Illumination / Appearance / Time Variance**     | CNN features degrade under extreme lighting, weather, or long-term changes.                  | Feature spaces are static and lack temporal conditioning or appearance adaptation.                                                       | Develop time-conditioned encoders, appearance flow fields, or illumination-invariant feature spaces within SfM.               | **Partial.** Some dynamic NeRF variants model lighting or appearance change, but classical SfM lacks such temporal modeling.         |
| **3. Extreme Viewpoint / Wide Baseline**             | Large viewpoint changes break local feature consistency and matching stability.              | Descriptors cannot generalize across large baselines, occlusions, or drastic view changes.                                               | Combine semantic, language, or diffusion priors for semantic-aware SfM that matches beyond local appearance.                  | **Partial.** Semantic-aware 3D reconstruction and NeRF methods show progress, but integration with classical SfM remains rare.       |
| **4. Sparse–Dense Gap**                              | SfM yields sparse geometry; dense methods (MVS) use incompatible representations.            | Sparse and dense optimization objectives differ, preventing unified reconstruction.                                                      | Employ unified implicit fields (feature fields, SDF, Gaussian splatting) that bridge sparse and dense representations.        | **Partial / Emerging.** Implicit and Gaussian-based fields begin to unify sparse–dense paradigms.                                    |
| **5. Geometry–Semantic Alignment**                   | Traditional SfM reconstructs only geometry, ignoring semantic consistency.                   | Lacks semantic identity or part-level alignment, limiting high-level scene understanding.                                                | Integrate vision-language or semantic embeddings (e.g., CLIP, DINOv3) and enforce cross-view semantic regularization.         | **Partial.** Semantic-aware 3D reconstruction is growing but still limited for geometry-based SfM.                                   |
| **6. Long-Term Consistency & Memory**                | Per-scene optimization causes drift; long-term or cross-session consistency is absent.       | No temporal memory; reconstructions over time remain inconsistent.                                                                       | Incorporate state-space models, latent geometry flow, or temporal latent dynamics for consistent long-term modeling.          | **Partial / Emerging.** Some dynamic NeRFs and latent-flow models handle temporal coherence, but not integrated into SfM frameworks. |


<br>

## Projection for the Semantic Prior

| Head Type       | Alignment Level | Semantic Context    | Output          | Computation     | Recommended Use                  |
| --------------- | --------------- | ------------------- | --------------- | --------------- | -------------------------------- |
| **Linear Head** | Patch-wise      | Local semantics     | 3D patch blocks | Fast (O(N×C)) | Gaussian Fur, fast inference     |
| **DPT Head**    | Multi-layer     | Global + contextual | Dense 3D map    | 3–5× heavier | Full 4D reconstruction, tracking |


<br>


## 2D Vision SSL Supervision

- [2024 - DINO-Foresight: Looking into the Future with DINO](https://arxiv.org/pdf/2412.11673)
- [2021 - DINO: Emerging Properties in Self-Supervised Vision Transformers](https://arxiv.org/abs/2104.14294)
- [2024 - DINOv2: Learning Robust Visual Features without Supervision](https://arxiv.org/pdf/2304.07193)
- [2025 - DINOv3](https://arxiv.org/pdf/2508.10104)

<br>

## 3D / 4D Reconstruction (and Tracking)

  - [📍 2025- Wayve.ai](https://arxiv.org/pdf/2506.02265)
  - [2025 - SAM 3D](https://ai.meta.com/blog/sam-3d/?utm_source=linkedin&utm_medium=organic_social&utm_content=video&utm_campaign=sam)
  - [2024 - UniDepth: Universal Monocular Metric Depth Estimation](https://arxiv.org/pdf/2403.18913)
  - [2024 - DiffusionDrive](https://arxiv.org/abs/2411.15139)
  - [2024 - SplatFields - Neural Gaussian Splats for Sparse 3D and 4D Reconstruction](https://github.com/markomih/SplatFields/tree/main)
  - [2011 - High-quality passive facial performance capture using 📍 anchor frames](https://d1wqtxts1xzle7.cloudfront.net/77751527/facial-libre.pdf?1640912246=&response-content-disposition=inline%3B+filename%3DHigh_quality_passive_facial_performance.pdf&Expires=1762643658&Signature=NgRyp~sdbcQRUFxAUbQDFiZr691HMb6kbVuUndJcpjW-430mrAb~surTn~nidAKIe7FrS9Pi~zfITeYBP1bJSgqi3~wIrv1XqXGIrRhQK8-~cfE7KicZvnqPWWRwSN8oxub51NbTyskeKeyY~X1kv6twwTR1X7xwAJfPk7N526XgBh5xQJto21DMkhjke7CCPnZ76XmMsYY4NH8qkxJKXOqOFCKGyfrzDnM3yMpsDedIVsicOwVeKROymIJAhBqPPYQnlgrVr7YRK5B77b5ln4vBd2FZwfuyiTINxodrC68DIHHufaL2zlekxGH1PCcYVKosEhuHZAcdvnfcEgVfsA__&Key-Pair-Id=APKAJLOHF5GGSLRBV4ZA)
<br>

  - [📍 2025 - MapAnything: Universal Feed-Forward Metric 3D Reconstruction](https://map-anything.github.io/)
  - [2025 - Multi-layer perceptron-based computer vision neural networks](https://patents.google.com/patent/US20250316074A1/e)
  - [2021 - KiloNeRF: Speeding up Neural Radiance Fields with 📍 Thousands of Tiny MLPs](https://openaccess.thecvf.com/content/ICCV2021/html/Reiser_KiloNeRF_Speeding_Up_Neural_Radiance_Fields_With_Thousands_of_Tiny_ICCV_2021_paper.html)
  - [2025 - Concerto: Joint 2D-3D Self-Supervised Learning Emerges 📍 Spatial Representations](https://pointcept.github.io/Concerto/)


  - [📍 2022 - Multi-layer perceptron-based computer vision neural networks](https://patents.google.com/patent/US12361696B2/en)


  - cute demo - [2024 - Physically Compatible 3D Object Modeling from a Single Image](https://gmh14.github.io/phys-comp/)
  - [2024 - DUSt3R: Geometric 3D Vision Made Easy](https://europe.naverlabs.com/research/publications/dust3r-geometric-3d-vision-made-easy/)
  - [2025 - TwoSquared: 4D Reconstruction from 2D Image Pairs](https://sangluisme.github.io/TwoSquared/)
  - [ICCV 2025 - AnyCalib: On-Manifold Learning for Model-Agnostic 📍 Single-View Camera Calibration](https://arxiv.org/pdf/2503.12701)
  - [ICCV 2025, 📍 Multimodal Spatial Intelligence](https://musi-workshop.github.io/)
  - [2025 - Depth Anything 3: recovering the visual space from any views](https://depth-anything-3.github.io/)

<br>

## Mesh

- [2024 - Mesh Simplification For Unfolding](https://cdl.ethz.ch/publications/mesh-simplification-for-unfolding/)


<br>


## Dealing With Continuous 3D Input Datasets

```
+---------------------------+
|  Discrete Token Sequence  |
|  ["age", "BMI", "asthma"] |
+------------+--------------+
             |
             v
+---------------------------+
|  Token Embedding Matrix   |
+---------------------------+
             |
             v
+---------------------------+
| Multi-Head Self-Attention |
|     O(N^2) complexity     |
+---------------------------+
             |
             v
+---------------------------+
|     Feed-Forward Layer    |
+---------------------------+
             |
             v
+---------------------------+
|   Output: Token-to-Token  |
|     symbolic reasoning    |
+---------------------------+
```

## Continuous Modal Inputs Include:

  - images
  - depth maps
  - 3D point clouds
  - 3D meshes
  - medical waveforms (ECG, PPG, Doppler)
  - neural biosignals (EEG/MEG)

Issue: Discrete symbolic models cannot directly represent geometry.

## Information Loss

```
 Continuous Data (image/depth/EEG/point cloud)
           |
           v
+------------------------------+
| Continuous Encoder (CNN/ViT) |
+------------------------------+
           |
           v
   Project to k "fake tokens"
           |
           v
+------------------------------+
| Traditional LLM Transformer  |
|   (expects symbolic tokens)  |
+------------------------------+
           |
           v
   LLM pretends to "understand"
   → But geometry/topology lost
```

<br>

## Attended Master Thesis Project Defense

  - 01 Sep 2025 - 📍 Reconstructing Complete Garments with Foundation Models
    - Pattern Prediction on Fabric Recognition
    - 'Garments are both cultural artifacts and engineered products, but most generative models produce visuals that cannot be manufactured. This thesis introduces a foundation model for pattern-centric garment generation, where outputs are sewing patterns—panels, seams, and annotations—ready for CAD and simulation. A new tokenizer and multimodal dataset enable structured decoding from text or image inputs in a unified framework. In parallel, we investigate fabric recognition from large-scale product data, underscoring the challenge of linking garment shape to material behavior. Experiments show state-of-the-art pattern prediction, strong generalization, and predictable scaling. Together, these contributions move digital fashion toward simulation-ready, fabrication-oriented design.'
    - [2025 - AIpparel: A Multimodal Foundation Model for Digital Garments](https://igl.ethz.ch/projects/aipparel/aipparel_paper.pdf)
    - [2025 - Single View Garment Reconstruction Using Diffusion Mapping Via Pattern Coordinates](https://arxiv.org/html/2504.08353v1)
  - 10 Sep 2025 - An Interactive, Foundation-Model-Empowered Video Annotation Interface for Constructing a Challenging Video Object Segmentation Dataset
    - SAM 2, DINOv2, GPT-4o, 📍 `real-time Annotation` -> [Segment.ai by Uber](https://segments.ai/) in 2025
    - demo - nutsh
  - 02 Oct 2025 - VSLAM-LAB: A Comprehensive Framework for Visual SLAM Baselines and Datasets, pixi
    - 2024 - Gaussian Splatting SLAM, demo
  - 09 Oct 2025 - Controllable Visual Generation using 3D prior
    - HIL D 55.2, ETH Hönggerberg, 14:00
  - StreamSplat: A Framework for Self-Supervised, Online Novel View Synthesis
    -  Friday Oct 10th, 15:00-15:30 Zurich Time
  - (Uncertainty-Aware 3D Mapping, Monday, October 13th, Zoom)
  - From Sensors to Solutions: Permanent Laser Scanning in 📍 Environmental Monitoring
    - Prof. Dr.-Ing. Daniel Czerwonka-Schröder, 22 Oct 2025, 4:45 p.m, HIL D 53, Hönggerberg
  - (iTwRL: Interactable Digital Twin for Reinforcement Learning, Nov 17th, 2pm, Zoom)
  - Learning 3D Human Foundation Models: A Data Request, Prov. Siyu Tang, Mon, 24-Nov-2025, 13:00–14:00, HG D 16.2
    - Computational methods to model human motion and behavior from visual inputs in real-world environments, Non-rigid 4D Reconstruction and Tracking
  - Guided Monocular Depth Estimation, Mon, Dec 8th, 2pm, CNB G 110 and Zoom, Sophie Selgrad
  - 22-Dec, MOBIUS goes 3D: Efficient Monocular 3D Object Detection, 2pm Zoom, by Hannes Stählin, Marta Tintore Gazulla, Vasile Lup

<br>


## During Training

| Implementation style         | Number of backward calls | Gradient behavior               | Characteristics                                                                                                  |
| ---------------------------- | ------------------------ | ------------------------------- | ---------------------------------------------------------------------------------------------------------------- |
| `(loss1 + loss2).backward()` | 1                        | Computes gradients jointly      | Simpler, but combined gradients are less controllable                                                            |
| Separate `backward()` calls  | 2                        | Computes gradients individually | Better suited for tasks requiring different weighting or multi-branch networks (e.g., semantic + diffusion loss) |

<br>

## Semantic vs. Photometric Consistency

- In traditional SfM / MVS / NeRF pipelines, pixel correspondence is established by enforcing **photometric consistency** across views:

$$
L_{\text{photo}} = \| I_t(p) - I_{t'}(w(p)) \|,
$$

- where $I_t(p)$ is the pixel intensity at location $p$ in frame $t$,
and $w(p)$ is the projection of that pixel into the target frame $t'$ using the estimated geometry.

---

- In contrast, **DINOv3**, built on the Vision Transformer (ViT), replaces raw pixel comparison with **semantic feature consistency**:

$$
L_{\text{semantic}} = \| f_{\text{DINO}}(I_t(p)) - f_{\text{DINO}}(I_{t'}(w(p))) \|,
$$

- where $f_{\text{DINO}}(\cdot)$ denotes patch-level semantic embeddings extracted by DINOv3.

---

- Because these $f_{\text{DINO}}$ features are patch-level and semantically stable,
they remain consistent under viewpoint changes, illumination variations, and partial occlusions—
enabling robust cross-frame and cross-view alignment beyond raw photometric matching.


<br>

- From **2D to 3D/4D reconstruction** is a highly **ill-posed inverse problem**, Projection model:

$$
I(x, y) = \Pi(X, Y, Z)
$$

- where the projection operator $\Pi$ maps a 3D point in the world coordinate space to a 2D pixel on the image plane

- The inverse problem is:

$$
\text{Given } I(x, y), \; \text{solve for } (X, Y, Z).
$$



- Two-dimensional pixel observations alone cannot uniquely deduce the true three-dimensional structure, so traditional methods rely heavily on geometric priors and multi-view constraints

<br>


## Traditional Pairwise Pipeline (O(T²))

```
      I1 —— I2 —— I3 —— ... —— IT
       ↕    ↕    ↕          ↕
      (I1,I2), (I1,I3), (I2,I3), (I3,I4), ... (IT-1,IT)
       └────────────── Dense Pairwise Matching ───────────────┘
```

## Anchor-based Pipeline (O(T))

```
       I1 ──────────▶ I2
        │            │
        │            ▼
        │──────────▶ I3
        │            │
        │            ▼
        │──────────▶ I4
        │            │
        │            ▼
        └──────────▶ IT
   (fixed anchor frame)

→ Each frame j only forms one pair (I1, Ij)
→ Each pair predicts (X^1_j, X^j_j) in the same world coordinate
```

<br>

## Diffusion Models vs. Flow Matching

| Problem Type              | Diffusion Models                                                            | Flow Matching                                                         |
| ------------------------- | --------------------------------------------------------------------------- | --------------------------------------------------------------------- |
| Non-rigid deformation     | Implicitly learns temporal consistency through noise-to-structure denoising | Requires explicit motion supervision                                  |
| Photometric inconsistency | Learns semantic-level feature representations beyond pixel matching         | Still relies on local intensity differences in continuous flow fields |
| Sparse-view limitation    | Uses generative priors to “complete” missing geometry                       | Requires sufficient observation constraints                           |
| Ill-posed inverse problem | Models latent structure distributions probabilistically via diffusion       | Deterministic ODE mapping, sensitive to noise                         |
| Temporal consistency      | Implicit diffusion process provides natural temporal smoothness             | Lacks explicit temporal regularization                                |


<br>

## Multi-View Matching

**Problem Definition**

- Given a set of frames  
  $$
  \{ I_1, I_2, \dots, I_T \},
  $$  
- and feature points extracted from each frame  
  $$
  \{ f_i^t \},
  $$  
- the goal is to find cross-frame correspondences  
  $$
  \pi: (f_i^t) \mapsto (f_j^{t+k}),
  $$  
- such that they represent the same real-world 3D point.



## Why It Is NP-hard

- This problem is equivalent to **graph matching**:

  - Each frame’s feature points form a node set.  
  - Correspondences between frames are edges.  
  - Matches must satisfy both geometric (epipolar) and temporal consistency constraints.  
  - The optimal matching minimizes:

  $$
  \min_{\pi} \sum_{t,k} \| P_t(f_i^t) - P_{t+k}(f_{\pi(i)}^{t+k}) \|^2,
  $$

- where $P_t$ is the projection matrix. When the number of views exceeds two, the search space grows exponentially. Multi-view matching can be reduced to the **Quadratic Assignment Problem (QAP)**, which is a classical **NP-hard** problem.


## Simplified and Practical Approaches

| Method | Principle | Time Complexity | Integration Module |
|--------|------------|----------------|--------------------|
| **Soft Attention Matching (Transformer)** | Replace hard matching with attention weights | O(T·N²) | St4RTrack Encoder |
| **Epipolar Constraint Filtering** | Geometric pre-filtering before soft match | O(N log N) | Projection Stage |
| **Hough-Voting / DINO Semantic Alignment** | Use semantic token similarity for weakly supervised matching | O(N) per frame | DINO Semantic Prior |
| **Graph Cut / Sinkhorn Normalization** | Approximate discrete matching via differentiable assignment | O(N³) | Differentiable Alignment |

<br>


## Step-by-Step: Constructing GT Pointmaps

**Example:** Point Odyssey

Each frame provides the scene mesh vertices in world coordinates:

$$
V_t = \{ v_k^t \in \mathbb{R}^3 \mid k = 1, \dots, N \}
$$

where each $v_k^t$ is a 3D vertex position at time $t$.

For each image pixel $(u, v)$, find its corresponding mesh vertex (via rasterization or ray casting):

$$
X_t(u,v) = \text{mesh2image}(V_t)
$$

This is the ground-truth pointmap at time $t$.

---

## 1. Tracking Branch Supervision

For the same vertex across time $i \to j$:

$$
X^i_j(u,v)^{GT} = V^j_k - V^i_k
$$

provided by the dataset’s 4D trajectories.

---

## 2. Reconstruction Branch Supervision

Per-frame depth maps or meshes provide supervision for:

$$
X^j_j
$$

which represents geometry reconstruction at time $j$.

All GT pointmaps are expressed in a **unified world coordinate frame**, transformed using the first frame’s camera extrinsics.

---

## Aligned Results — How They Are Computed

- During training and evaluation, predicted and GT pointmaps may differ in scale, rotation, or translation.  
Alignment ensures they are comparable.

---

**Step 1: Global Median Scale Alignment (default)**

- For each sequence, the predicted and GT pointmaps are scale-normalized:

$$
s = \text{median}\left( \frac{ \| GT_i \| }{ \| Pred_i \| } \right), \quad Pred \leftarrow s \cdot Pred
$$

---

**Step 2: SIM(3) Alignment (used in evaluation)**

- In Tables 4 and 5, an additional similarity transform alignment (scale + rotation + translation) is applied using the **Procrustes algorithm**:

$$
\min_{R, t, s} \sum_i \| GT_i - (s R Pred_i + t) \|^2
$$

The aligned prediction is then used to report metrics such as **APD₃ᴰ** and **EPE**.

---

**In summary:**  
- Ground-truth pointmaps are rasterized from dataset-provided 4D meshes, expressed in the world coordinate frame.  
During evaluation, predictions are scale- or SIM(3)-aligned to these GT pointmaps before computing accuracy metrics.

<br>

## Explicit vs. Implicit 3D Geometry Computation

| **Aspect**                   | **Explicit (Geometric Pipeline)**                                                                                                         | **Implicit (Neural Pipeline)**                                                                                         |
| ---------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| **Example Setup**            | Suppose you have a video with **10 frames**.                                                                                              | The same **10 frames** are input to a neural model.                                                                    |
| **Pairwise Matching**        | You must construct **10 × 10 = 100 image pairs** for feature matching.                                                                    | No explicit pair construction — attention layers automatically learn inter-frame relations.                            |
| **Feature Matching Cost**    | Each pair requires thousands of **RANSAC iterations** to reject outliers.                                                                 | Correlation across all frames is learned once through **self-attention** and optimized end-to-end.                     |
| **Pose Estimation**          | Each image pair needs **PnP / Essential Matrix** estimation to recover relative camera poses.                                             | The network implicitly infers all camera poses from global attention and latent camera tokens.                         |
| **Global Optimization**      | Requires **Bundle Adjustment (BA)** over thousands of variables (poses + 3D points).                                                      | A **single forward pass** of the network jointly refines all poses and points.                                         |
| **Computation Dependency**   | Each stage depends on the previous step (matching → pose → triangulation → BA), making the process **sequential and non-parallelizable**. | Entire pipeline is **feed-forward**; all operations are differentiable and **GPU-parallelizable** tensor computations. |
| **Computational Complexity** | Typically **O(T²)** to **O(T³)** due to pairwise matching and optimization across frames.                                                 | Approximately **O(T)** with Alternating-Attention (frame-wise + global), scalable to hundreds of frames.               |
| **Runtime**                  | Minutes to hours, depending on number of frames and optimization steps.                                                                   | Milliseconds to seconds for full reconstruction.                                                                       |
| **Memory Usage**             | High — needs to store large Jacobians, keypoints, and pairwise constraints.                                                               | Moderate — mainly token embeddings and attention maps.                                                                 |
| **Output**                   | Camera intrinsics/extrinsics, sparse or dense 3D structure after optimization.                                                            | Cameras, depth maps, and dense world-space point maps produced **directly from the network**.                          |
| **Parallelizability**        | Low — iterative geometric solvers are inherently serial.                                                                                  | High — all computations are **matrix multiplications on GPU**.                                                         |
| **Interpretability**         | High (based on explicit geometry equations).                                                                                              | Lower interpretability — geometry is **implicitly encoded** in network weights.                                        |
| **Representative Methods**   | SfM, COLMAP, MVSNet, NeRF (explicit camera poses).                                                                                        | VGGT, St4RTrack, MapAnything (implicit world-frame prediction).                                                        |

<br>


## DL For 3D Reconstruction

| **Bottleneck Source** | **Limitation of Classical Geometry Methods** | **Deep Learning Improvement Strategy** |
|------------------------|----------------------------------------------|----------------------------------------|
| **Dynamic Scenes** | Assume the scene is static | Introduce temporal modeling (RNN / GRU / Transformer) and learn deformation fields (e.g., D-NeRF, HyperNeRF) |
| **Sparse Viewpoints** | Insufficient view redundancy | Use pretrained priors, shape priors, or diffusion priors to fill in missing geometric information |
| **Real-time Requirement** | Optimization is slow and iterative | Replace optimization with feed-forward neural networks and learned depth estimators |
| **Weak or No Supervision** | Depend on accurate labels and calibration | Train via photometric consistency and self-supervised losses (e.g., Monodepth, NeuralRecon) |
| **Complex Illumination and Reflection** | Simplified lighting model (Lambertian assumption) | Learn implicit neural representations that model reflection and BRDF properties |
| **Temporal Consistency** | Treat each frame independently | Apply ConvGRU, flow matching, or diffusion-based temporal smoothing to maintain cross-frame consistency |

<br>


## Random Matrix

- Eigenvalues of large random matrices are statistically distributed across different systems

**Wigner’s Semicircle Law**

- <p>ρ(λ) = (1 / 2πσ²) √(4σ² − λ²), |λ| &lt; 2σ</p>

**Marčenko–Pastur Law**

- $\rho(\lambda) = \frac{1}{2\pi\sigma^{2} c \lambda} \sqrt{(\lambda_{+} - \lambda)(\lambda - \lambda_{-})}, \quad \lambda_{\pm} = \sigma^{2}(1 \pm \sqrt{c})^{2}$



<br>


## A. Continuous Geometry (Conceptual / Physical World)

| Geometry / Space            | Continuous or Discrete | Mathematical Definition                              | What It Encodes           | Role in 3D Reconstruction                                   |
| --------------------------- | ---------------------- | ---------------------------------------------------- | ------------------------- | ----------------------------------------------------------- |
| **Euclidean Space**         | Continuous             | $(\mathbb{R}^n, \langle \cdot,\cdot \rangle)$        | Length, angles, distances | Physical world model; final metric reconstruction           |
| **Affine Space**            | Continuous             | Vector space without origin                          | Parallelism, ratios       | Intermediate reconstruction (affine upgrade)                |
| **Projective Space**        | Continuous             | $\mathbb{P}^n = (\mathbb{R}^{n+1}\setminus{0})/\sim$ | Incidence, collinearity   | Natural space of images and cameras                         |
| **Smooth Manifold**         | Continuous             | Locally $\mathbb{R}^n$ with smooth atlas             | Differentiability         | Camera motion, pose spaces                                  |
| **Riemannian Manifold**     | Continuous             | Smooth manifold + metric tensor $g$                  | Curvature, geodesics      | Pose optimization, uncertainty modeling                     |
| **Lie Groups**              | Continuous             | Smooth groups (e.g. $SO(3), SE(3)$)                  | Rigid motion              | Camera pose and motion                                      |
| **Pseudo-Riemannian Space** | Continuous             | Indefinite metric                                    | Time/space separation     | Rare in reconstruction (mostly theoretical)                 |
| **Symplectic Manifold**     | Continuous             | Closed nondegenerate 2-form $\omega$                 | Phase-space dynamics      | Not core to reconstruction (used in dynamics, not geometry) |


<br>


## Continuous Geometric Structures Used Explicitly

| Structure                         | Continuous or Discrete | Mathematical Nature                  | Purpose in Reconstruction |
| --------------------------------- | ---------------------- | ------------------------------------ | ------------------------- |
| **Homogeneous Coordinates**       | Continuous             | Projective embedding                 | Linearizes projection     |
| **Absolute Conic / Dual Quadric** | Continuous             | Metric structure in projective space | Metric self-calibration   |
| **Epipolar Geometry**             | Continuous             | Algebraic constraints                | Two-view geometry         |
| **Multi-View Geometry**           | Continuous             | Projective relations                 | Structure from Motion     |
| **Camera Projection Models**      | Continuous             | Rational maps                        | Image formation           |


<br>


## B. Discrete Structures Approximating Continuous Geometry


| Geometry / Structure               | Continuous or Discrete | Mathematical Nature       | Role                       |
| ---------------------------------- | ---------------------- | ------------------------- | -------------------------- |
| **Graphs**                         | Discrete               | Vertices and edges        | Pose graphs, factor graphs |
| **Simplicial Complexes**           | Discrete               | Combinatorial topology    | Mesh representation        |
| **Polygonal Meshes**               | Discrete               | Piecewise-linear surfaces | Surface reconstruction     |
| **Voxel Grids**                    | Discrete               | Discretized volume        | Dense reconstruction       |
| **Point Clouds**                   | Discrete               | Sampled manifold          | SfM / LiDAR                |
| **Discrete Differential Geometry** | Discrete               | Discrete operators        | Curvature estimation       |
| **Finite Difference Operators**    | Discrete               | Numerical approximation   | Optimization               |


<br>


## Historical Evolution of Geometry in 3D Reconstruction


| Era                      | Dominant Geometry         | Continuous or Discrete | Key Mathematical Idea   |
| ------------------------ | ------------------------- | ---------------------- | ----------------------- |
| Classical Photogrammetry | Euclidean geometry        | Continuous             | Metric reconstruction   |
| Early Computer Vision    | Projective geometry       | Continuous             | Calibration-free vision |
| Multi-View Geometry      | Projective + affine       | Continuous             | Geometric invariants    |
| Modern SfM / SLAM        | Lie groups + optimization | Continuous             | Nonlinear estimation    |
| Dense Reconstruction     | Discrete geometry         | Discrete               | Surface approximation   |
| Learning-Based 3D        | Hybrid                    | Both                   | Geometry as constraint  |




<br>

## Key Contributions

```
[2000s] Classical 2D Stitching
   - Euclidean / Affine / Homography
   - Used in panoramas, satellite mosaics, medical imaging
   - Fast, lightweight, real-time

   Euclidean (3 DOF)
   ▢ → ▢
   Rigid rotation + shift
        |
        v
   Affine (6 DOF)
   ▢ → ⬠
   Parallel preserved (shear, scaling)
        |
        v
   Projective (8 DOF)
   ▢ → ⬳
   Perspective distortion (vanishing point)
-------------------------------------------------
        |
        v
[2010s] Multi-View Geometry
   - SfM (Structure from Motion), SLAM
   - SE(3) rigid motion + Bundle Adjustment
   - Full 3D scene reconstruction (static environments)
        |
        v
[2020s] Neural Implicit Representations
   - NeRF (Neural Radiance Fields)
   - Gaussian Splatting, Dynamic NeRF
   - Rich photorealistic 3D, supports dynamics
        |
        v
[2025 → ] Transformer & Foundation Models
   - VGGT (Geometry → Transformer sequence modeling)
   - DINOv3 (7B SSL backbone, dense visual features)
   - Replaces manual geometry → universal representations
   - Powers Pixel 10 AI (Gemini Nano + Tensor G5)
```


<br>

## Neural Differential Equations

**1. Core Idea**

- Neural Differential Equations (NDEs) generalize neural networks to continuous depth. 
- Instead of discrete layer updates, the hidden state evolves continuously over time according to an ordinary differential equation (ODE):

$$
\frac{d\mathbf{z}(t)}{dt} = f_\theta(\mathbf{z}(t), t), \quad \mathbf{z}(t_0) = \mathbf{z}_0
$$

- The solution is obtained by integrating over time:

$$
\mathbf{z}(t_1) = \mathbf{z}(t_0) + \int_{t_0}^{t_1} f_\theta(\mathbf{z}(t), t)\,dt
$$

**2. Comparison with Standard Neural Networks**

| Property | Standard NN | Neural Differential Equation |
|-----------|--------------|-------------------------------|
| Structure | Discrete layers | Continuous dynamics |
| Forward pass | $h_{k+1} = f_\theta(h_k)$ | $\frac{dh}{dt} = f_\theta(h,t)$ |
| Depth | Fixed | Continuous |
| Backpropagation | Chain rule | Adjoint sensitivity method |
| Interpretation | Layer mapping | Continuous-time dynamical system |


**3. Training via the Adjoint Method** 

- Gradients are computed by solving an adjoint ODE backward in time:

$$
\frac{da(t)}{dt} = -a(t)^\top \frac{\partial f_\theta(\mathbf{z}(t),t)}{\partial \mathbf{z}}, \quad 
\frac{dL}{d\theta} = -\int_{t_1}^{t_0} a(t)^\top \frac{\partial f_\theta(\mathbf{z}(t),t)}{\partial \theta}\,dt
$$

- This allows memory-efficient gradient computation since intermediate states do not need to be stored

**4. Variants**

- **Neural ODE:** Deterministic dynamics  
- **Neural SDE:** Stochastic systems with noise  
- **Neural PDE:** Parameterized partial differential equations  
- **Hamiltonian NN:** Conserves physical energy  
- **Controlled DE:** Handles continuous control inputs  


**5. Physical Interpretation**  

- The function \( f_\theta \) acts as a **learnable vector field** that defines how the system evolves in time 
- This enables learning unknown physical dynamics directly from data:

$$
\frac{\partial u}{\partial t} = f_{\text{known}}(u) + f_\theta(u)
$$

<br>

## Speed up Your Training in Multiple Ways


| **Category**                 | **Technique / Concept**                         | **Core Idea (One Line)**                                                                         | **Example Hardware / Framework**        |
| ---------------------------- | ----------------------------------------------- | ------------------------------------------------------------------------------------------------ | --------------------------------------- |
| **Kernel Optimization**      | **AI Kernel Auto-Tuning (Triton / AutoTVM)**    | Automatically generate and fuse optimal CUDA kernels for specific tensor shapes.                 | NVIDIA H100, PyTorch 2.5, Triton 2      |
| **Memory Efficiency**        | **FlashAttention 2 / Fused Ops**                | Combine attention and softmax in a single kernel to reduce memory and launch overhead.           | A100 / H100 / RTX 4090                  |
| **Precision Optimization**   | **FP8 / INT8 Quantization-Aware Training**      | Use ultra-low precision arithmetic with adaptive scaling for faster, energy-efficient training.  | NVIDIA Hopper, AMD MI300X               |
| **Graph Compilation**        | **TorchInductor / XLA / MetalFX Graph Capture** | Compile dynamic graphs into optimized static kernels for faster runtime.                         | PyTorch 2.x, TPU v6e, Apple M4 Max      |
| **Diffusion Optimization**   | **Fused Diffusion Sampling**                    | Merge denoising and upsampling into one fused kernel for diffusion-based training.               | DiffusionRefine, Stable Diffusion Turbo |
| **Adaptive Fine-Tuning**     | **LoRA / QLoRA / BitNet Adapters**              | Parameter-efficient fine-tuning for large models on limited hardware.                            | RTX 6000 Ada, M2 Ultra, Edge TPU        |
| **Sequence Modeling**        | **Mamba SSM / Linear Attention**                | Replace quadratic attention with state-space or linear-time models for long-sequence efficiency. | Transformer Engine (H100), FlashMamba   |
| **Hardware Co-Design**       | **Grace Hopper / TPU v6e / MI300X**             | Unified CPU–GPU/TPU memory design enabling zero-copy tensor access.                              | NVIDIA GH200, Google TPU Pods           |
| **Distributed Optimization** | **FSDP + ZeRO + NVLink 4.0**                    | Fully sharded data parallelism and high-speed interconnect for multi-GPU scaling.                | DGX H100 Cluster, NVSwitch              |
| **Emerging Paradigm**        | **Neural Compilation & Auto-Scheduling**        | Learn to generate compute graphs and schedule execution automatically.                           | TVM Unity, Modular Mojo                 |



<br>

## Models


```
Points → Delaunay Triangulation (Triangles)
      ○         ○───────○
       \       / \     /
        ○─────○───○───○
       / \     \ /     \
      ○   ○─────○──────○


Points → Voronoi Diagram (Cells)
      ○     │     ○
     ┌┼─────┼─────┼┐
     │ Cell │ Cell │
  ○──┼──────┼──────┼──○
     │ Cell │ Cell │
     └┼─────┼─────┼┘
      ○     │     ○


Points → Poisson / α-shapes (Smooth Surface)
        ●──────────●
      ╱              ╲
    ●                  ●
    ╲                  ╱
      ●──────────────●


Points → Volumetric / TSDF (Voxel Grid)
   ▓▓▓▓▓
   ▓███▓    Each cube = voxel
   ▓▓▓▓▓


Points → Implicit Fields (SDF / NeRF)
   f(x,y,z) = 0  → Surface
   Continuous function learned by NN
   "Shape emerges from equations"


Points → Modern Neural Models (GS / Transformer)
   ● Gaussian Splatting → soft blobs in 3D
   ● VGGT / MonST3R / PanSt3R → End-to-end feed-forward 3D/4D
   ● NeRF → Radiance fields, view-dependent rendering
```

<br>

## Fundamental Limitations of Voxel-Based Methods


| Issue                              | Explanation                                                                                                                 |
| ---------------------------------- | --------------------------------------------------------------------------------------------------------------------------- |
| **Cubic Resolution Complexity**    | A voxel grid discretizes 3D space uniformly, resulting in **O(N³)** memory and computation complexity.                      |
| **Exponential Memory Growth**      | Doubling the spatial resolution increases memory consumption by **8×**, making high-resolution representations impractical. |
| **Poor Scalability**               | Due to cubic scaling, voxel grids do not scale well to large scenes or fine geometric detail.                               |
| **Dimensional Mismatch**           | Real-world surfaces are **2D manifolds**, but voxel grids densely sample the entire **3D volume**.                          |
| **Wasted Representation Capacity** | Most voxels lie in empty space and do not contribute to the surface geometry, leading to severe inefficiency.               |



<br>


## Structure-from-Motion (SfM) Pipeline


```
Input: Multiple images (Image Sequence)
   ↓
1️⃣ Feature Extraction  
   - Detect keypoints and compute descriptors  
   - Methods: SIFT, ORB, SuperPoint, D2-Net  
   ↓
2️⃣ Feature Matching  
   - Find correspondences across images  
   - Techniques: Nearest Neighbor, RANSAC, StereoGlue  
   ↓
3️⃣ Camera Motion Estimation  
   - Estimate relative poses using Essential / Fundamental Matrix  
   - Recover camera extrinsics (Rotation R, Translation t)  
   ↓
4️⃣ Triangulation  
   - Back-project matched points  
   - Compute 3D scene points (sparse point cloud)  
   ↓
5️⃣ Bundle Adjustment (BA)  
   - Global non-linear optimization  
   - Refine camera poses and 3D points  
   - Minimize reprojection error  
   ↓
6️⃣ Output  
   - Optimized 3D point cloud (sparse or dense)  
   - Camera trajectory (motion path)  
```

<br>

## Visual Computing

```
2D → 3D Projection World                     Multi-View Segmentation World
═══════════════════════════════              ══════════════════════════════════
Pixel Point  →  Camera Intrinsics →          Multi-View Image →  Camera Extrinsics →
Corrected by Distortion → Project to 2D      Align Views Consistently → Back-Project to 3D
    ↓                   ↓                          ↓                       ↓
┌────────────┐   ┌────────────┐              ┌────────────┐   ┌────────────────┐
│ Pixel Coord│ → │ Metric Ray │      vs.     │ Seg. Mask  │ → │ 3D Point Cloud │
│ (u,v)      │   │ (K Matrix) │              │ (2D Image) │   │  or Voxels     │
└────────────┘   └────────────┘              └────────────┘   └────────────────┘
    ↓                   ↓                          ↓                 ↓
Distortion-Free    Accurate Geometry           Consistent 3D     Semantic Labels
Projection         Pixel → Metric Space        Reconstruction   in 3D Space


Summary:
1. Intrinsics: Ensure pixels map to correct metric coordinates
2. Extrinsics: Align multi-view cameras consistently
3. Distortion Params: Correct lens errors
4. Projection: World point → Image point
5. Back-Projection: Pixel + depth → World point
6. Goal: Lift 2D segmentation masks into 3D semantic segmentation

Camera = Projector (2D Screen View)
Extrinsics = GPS for Camera Pose
Segmentation = Paint Mask that Becomes 3D Object
```

<br>

## Classical SfM vs. VGGT


```
 Classical SfM / MVS World                   VGGT World
═══════════════════════════════════         ════════════════════════════════════
Find Keypoints → Match Pairs →              Drop Images → Transformer Thinks →
Estimate Pose → Triangulate →               One Forward Pass → Geometry Pops Out
Optimize BA → Wait Forever                  (Pose, Depth, Points, Tracks in ms)
     ↓                   ↓                          ↓
┌─────────────┐   ┌──────────────┐           ┌───────────────┐   ┌────────────────┐
│ Feature     │ → │ Epipolar     │    vs.    │ Transformer   │ → │ Unified Outputs│
│ Matching    │   │ Geometry     │           │ Global Context│   │ (Pose+Depth+3D)│
└─────────────┘   └──────────────┘           └───────────────┘   └────────────────┘
     ↓                   ↓                          ↓                    ↓
Fragile Matches     Heavy Optimization         Robust Priors        Instant Geometry
(SIFT/SuperPoint)   (Bundle Adjustment)        Learned Attention    Feed-forward Only

Hybrid approaches:
1. Use classical SfM to bootstrap intrinsics → fine-tune with VGGT outputs
2. Combine hand-crafted geometry checks (epipolar) with learned global priors

Classical SfM = Puzzle Builder with Thousands of Pieces (slow, error-prone)
VGGT = Instant Polaroid Printer that Prints 3D (fast, all-in-one)
```

<br>


## Why Squared (L2) Loss

## 1. Mathematical

- Squaring makes the error smooth, continuous, and differentiable, which is required for gradient-based optimization

- We update parameters using gradient descent:

$$
\hat{a}_{k+1} = \hat{a}_k - \gamma \nabla L(\hat{a}_k)
$$

- To perform this optimization, the loss \(L\) must be differentiable with respect to \(\hat{a}\)

- Define the loss function as:

$$
L = \| e \|^2 = e^\top e = \sum_i (b_i - F_i(\hat{a}))^2
$$

- Then, the gradient is:

$$
\nabla_{\hat{a}} L = -2 J_F(\hat{a})^\top (b - F(\hat{a}))
$$

- This ensures, 
  - Continuous and smooth gradient direction  
  - Analytical update expression  
  - Compatibility with automatic differentiation (autodiff)

- If instead we used the absolute error (L1 norm):

$$
L = \| e \| = \sum_i |b_i - F_i(\hat{a})|
$$

- the gradient would be non-continuous at \(e = 0\), causing oscillation or instability during optimization.

<br>

## 2. Statistical

- The squared loss corresponds to assuming Gaussian noise in the measurements

- Assume the observation model:

$$
b = F(\hat{a}) + \epsilon, \quad \epsilon \sim \mathcal{N}(0, \sigma^2 I)
$$

- Then the likelihood function is:

$$
p(b \mid \hat{a}) = \frac{1}{Z} \exp\!\left(-\frac{1}{2\sigma^2}\| b - F(\hat{a}) \|^2\right)
$$

- Taking the negative log-likelihood (Maximum Likelihood Estimation):

$$
-\log p(b \mid \hat{a}) = \frac{1}{2\sigma^2}\| b - F(\hat{a}) \|^2 + \text{const.}
$$

- Thus minimizing the squared loss is equivalent to Maximum Likelihood Estimation (MLE) under Gaussian noise


<br>

## 3. Optimization

- The squared loss amplifies large errors and stabilizes convergence

- Large residuals receive stronger penalties:

$$
L = (b - F(\hat{a}))^2
$$

- Hence,
  - Large errors are corrected faster (rapid early convergence)  
  - Small errors yield smaller gradients (smooth late convergence)

<br>

## Visual Computing - Coursework

| Tuesday (Topic)                                                                                                  | Thursday (Topic)                                                                               |
| ---------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| **Introduction to SfM** <br> Overview of Structure-from-Motion, applications in photogrammetry, robotics, AR/VR. | **The Multi-View Problem** <br> From 2D images to 3D geometry, role of camera models.          |
| **Image Features I** <br> Feature detection (SIFT, ORB).                                                         | **Image Features II** <br> Feature description and matching.                                   |
| **Epipolar Geometry** <br> Essential matrix, Fundamental matrix.                                                 | **RANSAC & Robust Estimation** <br> Outlier rejection in correspondences.                      |
| **Camera Pose Estimation I** <br> PnP problem, intrinsics vs extrinsics.                                         | **Camera Pose Estimation II** <br> Homography, motion from two views.                          |
| **Triangulation I** <br> Linear triangulation methods.                                                           | **Triangulation II** <br> Non-linear triangulation and uncertainty.                            |
| **Incremental SfM** <br> Sequential addition of cameras, growing reconstruction.                                 | **Global SfM** <br> Joint optimization across all cameras.                                     |
| **Bundle Adjustment I** <br> Definition and reprojection error.                                                  | **Bundle Adjustment II** <br> Nonlinear least squares, Levenberg–Marquardt optimization.       |
| **Sparse vs Dense Reconstruction** <br> Difference between sparse SfM and dense MVS.                             | **Multi-View Stereo (MVS)** <br> PatchMatch, depth map fusion.                                 |
| **Structure Representation** <br> Point clouds, meshes, voxel grids.                                             | **Surface Reconstruction** <br> Poisson surface reconstruction and variants.                   |
| **SfM in Practice I** <br> COLMAP basics: input images, output formats.                                          | **SfM in Practice II** <br> COLMAP visualization and debugging reconstruction.                 |
| **Limitations of Traditional SfM** <br> Drift, loop closure, scalability issues.                                 | **Robustness & Failures** <br> Low-texture scenes, repetitive patterns, robustness strategies. |
| **Extensions I: Dynamic Scenes** <br> Non-rigid SfM, motion segmentation.                                        | **Extensions II: Large-Scale SfM** <br> City-scale and aerial 3D reconstruction.               |
| **Learning-based SfM I** <br> Deep feature matching (SuperGlue, LoFTR).                                          | **Learning-based SfM II** <br> Neural reconstruction pipelines (DUSt3R, VGGT).                 |
| **Future of SfM** <br> From optimization-based to transformer-based methods.                                     | **SfM vs VGGT** <br> COLMAP vs VGGT, comparison of pros and cons.                              |


<br>


## References 1

**Frontiers in AI Research (2025)**

1. Long-Term Temporal & Structural Consistency  
- **Key Results**:  
  - FlowFormer (CVPR ’25): flow-matching for video coherence
  - VideoMamba (25)
  - MemoryNeRF (NeurIPS ’24): implicit scene memory across seconds  
- **Opportunities**:  
  - scalable frame-level memory modules  
  - layered geometric+semantic caching  
  - dynamic scene understanding

📍 2. Self-Supervised Learning from Extreme Sparsity  
- **Key Results**:  
  - `SparseMAE (ICCV ’23): masked autoencoding with <0.1 % tokens`
  - Contrastive-Sparse (ICLR ’24): adaptive masking focus on high-entropy regions  
- **Goals**:  
  - near-fully-supervised performance with ‰-level labels  
  - unified multi-task pretraining (classification, detection, generation)

📍 **3. DiT (Diffusion Transformer)**
- **Overview**: Combines Transformer context modeling with diffusion denoising  
- **Examples**  
  1. **KeyFace** – speech-driven face animation via stepwise denoising  
  2. **DiffLocks** – high-fidelity hair generation  
  3. **Pippo** – multi-view rendering with geometric and texture coherence  
- **Benefit**: Maintains character appearance/style across shots and supports conditional, coherent animation

**4. Priors**
- **Synthetic Priors (GASP, SynShot)**  
  - Generate “pseudo-real” head avatars (poses, expressions, lighting) to enrich training data  
  - Improves generalization to extreme poses and rare expressions  
- **Diffusion-based Priors (CAP4D, GAF)**  
  - Use pretrained diffusion models to produce high-quality 3D avatars or dynamic sequences  
  - Accelerates multi-view/multi-expression data generation and boosts video consistency


<br>


## Computer Vision: Historical Topics, Motivation, and Key Contributors

| Era          | Topic                                         | Key Contributors                               | Why It Was Introduced                                              | Backbone Significance                                                  |
| ------------ | --------------------------------------------- | ---------------------------------------------- | ------------------------------------------------------------------ | ---------------------------------------------------------------------- |
| 1960s–1970s  | Digital Images and Sensors                    | Russell Kirsch, Bell Labs                      | To represent visual information in discrete, machine-readable form | Established the pixel as the fundamental representation of visual data |
| 1960s–1970s  | Image Segmentation and Morphology             | Azriel Rosenfeld, Georges Matheron             | To extract structure and objects from raw images                   | Formalized vision as a structural decomposition problem                |
| 1970s        | Fourier Transform and Filtering               | Joseph Fourier (theory), applied by Bracewell  | To analyze frequency content of images                             | Introduced signal processing as a backbone for vision                  |
| 1970s–1980s  | Convolution and Image Features                | Hubel & Wiesel (biology), Marr (vision theory) | To model local receptive fields and feature extraction             | Connected biological vision to computational operators                 |
| 1980s        | Unitary Transformations and Image Compression | JPEG committee, Ahmed et al. (DCT)             | To reduce storage and transmission cost                            | Linked vision to information theory                                    |
| 1980s–1990s  | Warping, Optical Flow, Video Compression      | Horn & Schunck, Lucas & Kanade                 | To model motion and temporal correspondence                        | Introduced dynamics into visual modeling                               |
| 1980s        | Radon Transform                               | Johann Radon (theory), applied in CT           | To reconstruct images from projections                             | Connected vision with inverse problems and tomography                  |
| 1990s–2000s  | Handcrafted Feature Descriptors               | Lowe (SIFT), Dalal & Triggs (HOG)              | To achieve invariance to scale and viewpoint                       | Stabilized vision under geometric variation                            |
| 2012–present | Convolutional Neural Networks                 | LeCun, Hinton, Krizhevsky                      | To learn features directly from data                               | Shifted vision from analytic design to learned operators               |


<br>

Conceptual trajectory
  - Pixels → Signals → Features → Motion → Inverse Problems → Learned Representations

<br>

- Conceptual trajectory
    - Drawing → Transforming → Rendering → Physical Simulation → Geometry Processing → Differentiable Systems

<br>

## Structural Comparison of Vision and Graphics Backbones

| Aspect             | Computer Vision                 | Computer Graphics                        |
| ------------------ | ------------------------------- | ---------------------------------------- |
| Core Question      | What is in the image?           | How does an image arise?                 |
| Primary Direction  | Inverse problems                | Forward modeling                         |
| Mathematical Tools | Signal processing, optimization | Geometry, physics                        |
| Historical Shift   | Handcrafted → Learned features  | Deterministic → Differentiable pipelines |
| Current Frontier   | Learned operators, uncertainty  | Generative and probabilistic modeling    |



<br><br>

## Reference 1

- [2023 - Dense 4D Nanoscale Reconstruction of Living Brain Tissue](https://www.nature.com/articles/s41592-023-01937-5)
- [2023 - Guided 📍 Depth Super-Resolution by Deep Anisotropic Diffusion](https://github.com/prs-eth/Diffusion-Super-Resolution), PRS
- [2025 - You 📍 Only Train Once](https://people.phys.ethz.ch/~csakarid/YOTO/You_Only_Train_Once-Sakaridis-arXiv_2025.pdf), PRS


- [2025 - 📍 Transfer learning between different computer vision tasks](https://patentimages.storage.googleapis.com/0a/f0/2c/1f28d09af469a8/US12272442B2.pdf)
- [2025 - RocSync:Temporal Multi-Camera Synchronization](https://github.com/jaromeyer/RocSync)
- [2025 patent - Performing computer vision tasks using guiding code sequences](https://patents.google.com/patent/US20250356635A1/en)
- [2025 - Hierarchical 4D Scene Graph](https://nicolasgorlo.com/DAAAM_25/)
- [2025 - 4DGT: Learning a 4D Gaussian Transformer Using Real-World Monocular Videos, NeurIPS (Spotlight)](https://4dgt.github.io/)

<br>

## References 2 

  - [2023 - Point Cloud Pre-training with Diffusion Models](https://arxiv.org/pdf/2311.14960)
  - [2025 - Beyond neural scaling laws: beating power law scaling via data pruning](https://nips.cc/virtual/2022/poster/53016)
  - [2025 - Harnessing Text-to-Image Diffusion Models for Point Cloud Self-Supervised Learning](https://openaccess.thecvf.com/content/ICCV2025/papers/Chen_Harnessing_Text-to-Image_Diffusion_Models_for_Point_Cloud_Self-Supervised_Learning_ICCV_2025_paper.pdf)
  - [2021 - The fishyscapes benchmark: Measuring 📍 blind spots in semantic segmentation](https://link.springer.com/article/10.1007/s11263-021-01511-6)
  - [2025 - SNI-SLAM++: Tightly-Coupled 📍 Semantic Neural Implicit SLAM](https://ieeexplore.ieee.org/document/11260914)
  - [2025 - osmAG-LLM: Zero-Shot Open-Vocabulary Object Navigation via Semantic Maps and Large Language Models Reasoning](https://arxiv.org/abs/2507.12753)
  - [2025 - ProcGen3D: Learning Neural Procedural Graphs for Image-to-3D Reconstruction](https://xzhang-t.github.io/project/ProcGen3D/)
  - [2024 - Physics3D: Learning Physical Properties of 3D Gaussians via Video Diffusion](https://arxiv.org/pdf/2406.04338)
  - [2022 - Embodied Active Domain Adaptation for Semantic Segmentation via Informative Path Planning](https://arxiv.org/abs/2203.00549)


  - [2023 - Large Scale Dense 3D Reconstruction via 📍 Sparse Representations](https://www.ri.cmu.edu/app/uploads/2023/06/thesis-compressed.pdf)
  - [2022 - Understanding Uncertainty Maps in Vision with Statistical Testing](https://openaccess.thecvf.com/content/CVPR2022/html/Nazarovs_Understanding_Uncertainty_Maps_in_Vision_With_Statistical_Testing_CVPR_2022_paper.html)
  - [2025 - Pixels2Points: Fusing 2D and 3D Features for Facial Skin Segmentation](https://arxiv.org/pdf/2504.19718)
  - [2025 - Aerial Gym Simulator: A Framework for Highly Parallelized Simulation of Aerial Robots](https://arxiv.org/pdf/2503.01471)
  - [2019 - ICCV - Pix2Vox: Context-aware 3D Reconstruction from 📍 Single and Multi-view Images](https://www.infinitescript.com/project/pix2vox/)
  - [2015 - ShapeNet: An Information-Rich 3D Model Repository](https://arxiv.org/abs/1512.03012)



  - [2024 - SceneScript: Reconstructing Scenes With An Autoregressive 📍 Structured Language Model](https://arxiv.org/pdf/2403.13064)
  - [2025 - Prior2Former - Evidential Modeling of Mask Transformers for Assumption-Free Open-World Panoptic Segmentation](https://iccv.thecvf.com/virtual/2025/poster/317)
  - [2025 - Phantom: Subject-Consistent Video Generation via Cross-Modal Alignment](https://iccv.thecvf.com/virtual/2025/awards_detail)
  - [2017 - 📍 FlowNet 2.0: Evolution of Optical Flow Estimation with Deep Networks](https://openaccess.thecvf.com/content_cvpr_2017/papers/Ilg_FlowNet_2.0_Evolution_CVPR_2017_paper.pdf)
  - [2025 - GauSTAR: Gaussian Surface Tracking and Reconstruction](https://eth-ait.github.io/GauSTAR/)



<br><br><br><br>



