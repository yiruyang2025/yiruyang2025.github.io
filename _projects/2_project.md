---
layout: page
title: 2025 - Master Thesis 2
description: A Feed forward network for 4d Instance Segmentation
img: assets/img/4.jpg
importance: 2
category: work
related_publications: true
---

<br>

## Topics

<br>

**Related Coursework**

<br>

[3D Vision](https://cvg.ethz.ch/lectures/3D-vision/) - Learnt background knowledge

<br><br><br>


**Related Works**

<br>

[2025 - MonST3R](https://monst3r-project.github.io/) - Motion-aware 4D segmentation

[2018 - GQN](https://deepmind.google/discover/blog/neural-scene-representation-and-rendering/) - Unsupervised Learning, Neural scene representation


[2025 - VGGT](https://vgg-t.github.io/) - `Convert the` geometric `problem into` a sequence modeling problem of Transformer




<br><br><br>


## Key Contributions


<br>

A FFN for 4d Segmentation - Semantic -> Instance, for real-time Inference


Hierarchical, 

<br><br><br>



## Benchmarks and SOTAs

<br>

## 1. 4D

<br>






<br><br><br><br>


## 2. 3D

<br>

[2025 - MonST3R: A Simple Approach for Estimating Geometry in the Presence of Motion](https://monst3r-project.github.io/)


[2024 - AGILE3D](https://ywyue.github.io/AGILE3D/)

[2016 - COLMAP 1](https://github.com/colmap/colmap) - baseline 1

[2025 - COLMAP 2](https://developer.nvidia.com/blog/how-to-instantly-render-real-world-scenes-in-interactive-simulation/) - baseline 2




<br><br>

## Models

<br>

`1. Geometry-Centric 3D Models`

DUSt3R (CVPR 2024)
  - 2D Images → Feature Matching → 3D Structure

MASt3R (ECCV 2024)
  - Images → 3D-Aware Matching → Precise Geometry

VGGT (CVPR 2025)
  - Image Sequences → Geometry-Grounded Attention → 3D Pose & Structure

<br>

`2. Semantic + Geometry Joint Models`


SAM (ICCV 2023, Meta AI) / SAM 2 (2024, Meta AI
  - Video / 3D Stream → SAM 2 Engine → Consistent 2D/3D/4D Segmentation

PanSt3R (ICCV 2025)
  - Multi-View Images → Fuse Masks → 3D Segmented Scene

4D Panoptic Extensions (CVPR 2024, Ego-Exo4D)
  - Video → 3D Panoptic + Time → 4D Reconstruction


<br><br>

## Why FFN

<br>


| Category                               | Representative Works / Applications                                                                                                                                                                                                                                                                                                                 |
| -------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **FFN in 3D/4D Segmentation**          | **PointNet / PointNet++** (CVPR’17, FFN-style MLP, 3D semantic & instance segmentation) <br> **Flood-Filling Networks** (NeurIPS’17, large-scale neuron segmentation) <br> **Spatio-temporal FFNs** (MICCAI’19, biomedical 4D segmentation)                                                                                                         |
| **Transformers in 3D/4D Segmentation** | **DINOv3** (Meta, 2025 – open-vocabulary semantic features) <br> **VGGT** (CVPR’25 – geometry + segmentation backbone) <br> **PanSt3R** (CVPR’25, ETH – 4D panoptic segmentation) <br> **MonST3R** (CVPR’25, Meta+ETH – motion-aware segmentation) <br> **Shape of Motion** (CVPR’25, Meta Reality Labs – dynamic 4D reconstruction & segmentation) |
| **Frameworks (DeepMind / Google)**     | **TensorFlow 3D (TF3D)** – Google/DeepMind 3D segmentation library <br> **TensorFlow 4D (TF4D)** – experimental library for spatio-temporal 4D segmentation                                                                                                                                                                                         |
| **Industry Applications**              | **Meta Reality Labs** – AR/VR semantic & instance segmentation (Project Aria) <br> **DeepMind** – scene segmentation research (TF3D/TF4D) <br> **NVIDIA Isaac** – 4D obstacle segmentation for robotics <br> **Apple ARKit** – semantic scene segmentation for AR                                                                                   |




<br><br><br>



<br><br>


## 3. 2D

<br>

[2025 - DINOv3 - checkpoints](https://huggingface.co/collections/facebook/dinov3-68924841bd6b561778e31009)


<br><br><br><br>



## Some Other topics

<br>

[2024 - soft MOE](https://arxiv.org/pdf/2308.00951)


[2025 - Probabilistic Methods for Monocular 3D Human Reconstruction](https://scholar.google.com/scholar?hl=en&as_sdt=0%2C5&q=Probabilistic+Methods+for+Monocular+3D+Human+Reconstruction&btnG=)

[2025 - minFM: Minimal Flow Matching](https://github.com/Kai-46/minFM)

[NanoGPT (124M) in 3 minutes](https://github.com/KellerJordan/modded-nanogpt)


[Aug 2025 - Proxies Could Be The Key To Interacting With Physical Objects In Mixed Reality](https://www.uploadvr.com/research-proxies-mixed-reality/)


<br><br>



## World Models / [Reality Proxy](https://www.arxiv.org/pdf/2507.17248)

<br>

[Mahcine Learning Street Talk](https://x.com/MLStreetTalk/status/1952743787454668931)

[3d gaussian](https://shivangi-aneja.github.io/projects/scaffoldavatar/)

<br>


## Topics


<br>

[Implicit 3D Representations]


[2021 - D-NeRF](https://github.com/albertpumarola/D-NeRF)


[2025 - TetWeave](https://x.com/TheGraphicsFrog/status/1920360716097274059)


[C++ lib repo - toolkit](https://github.com/libigl)


<br><br>


## Shape Modeling

<br>

[2025 - TetSphere Splatting: Representing High-Quality Geometry with Lagrangian Volumetric Meshes](https://github.com/gmh14/tssplat)



<br><br>


```
Mesh-VAE World                          Implicit Geometry World
═══════════════════════════════         ══════════════════════════════════
Mold Shape  →  Fill Cream  →           Pour Batter → Let Shape Form →  
Keep Shape  →  Adjust Icing            Implicitly Shape via Function
(Topology)     (Latent Codes)          (SDF / NeRF Fields)
     ↓                ↓                         ↓
┌────────────┐  ┌────────────┐           ┌────────────┐  ┌────────────────┐
│ Cake Mold  │→ │ Cream Code │    vs.    │  Batter    │→ │ Shape Function │
│ (Mesh Topo)│  │ (Latent z) │           │ (No Mesh)  │  │ f(x) → Geometry│
└────────────┘  └────────────┘           └────────────┘  └────────────────┘
     ↓                ↓                         ↓               ↓
Consistent Shape   Editable Details         Any Shape      Learned Surface
Fixed Faces        Vertex Offsets           Continuous     Surface = f(x)=0


Hybrid models:
1. Use Mesh-VAE to encode coarse shape → condition NeRF/SDF to model fine detail
2. Combine structural control (mesh) with detail realism (fields)

🍨 NeRF = Gelato Machine with View-Conditioned Flavor Control
🏗️ SDF = Invisible Sculptor Guided by Distance and Space Curvature
```


<br><br>

## Visual SLAM Pipeline

<br>

```
Input Images (RGB / RGB-D / Stereo)
        ↓
Front-End Tracking
   - Feature Extraction (ORB, SuperPoint)
   - Feature Matching (KLT, StereoGlue)
   - Motion Estimation (PnP, Essential Matrix)
        ↓
Back-End Optimization
   - Bundle Adjustment (BA)
   - Sliding Window Optimization
        ↓
Loop Closure
   - Place Recognition
   - Pose Graph Optimization
        ↓
Mapping
   - Sparse Map (Point Cloud)
   - Dense Map (Depth / Voxel / Mesh)
   - Semantic Map (Object / Scene Labels)
        ↓
Output: Robust Trajectory + Map
```


<br><br>

## Visual Computing


<br>

## Classical SfM vs. VGGT

<br>

```
Classical SfM / MVS World                         VGGT World
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

📸 Classical SfM = Puzzle Builder with Thousands of Pieces (slow, error-prone)
🧠 VGGT = Instant Polaroid Printer that Prints 3D (fast, all-in-one)

💡 SfM is archaeology with chisels; VGGT is 3D printing with transformers
```

<br>

```
        Projective
  (collinearity, cross-ratio)
                 ↓
          Affine
   (parallelism, ratios of areas)
                 ↓
          Similarity
   (ratios of distances, angles)
                 ↓
   Tekin et al. (2018): CNN + PnP
   ---> Upgrade metric → Euclidean
                 ↓
          Euclidean (SE(3))
   (absolute distances, 6D pose)
                 ↓
          4D Spatio-temporal
   (geometry + temporal coherence)
```




<br>

**Classical SfM (Geometry-driven)**

<br>

```
Calibration
   ↓
K = [[fx, 0, px], [0, fy, py], [0,0,1]]
[R | t]
   ↓
Feature Matching (2D–2D)
   ↓
Epipolar Constraint: xᵢᵀ F xⱼ = 0
   ↓
Projection
   λ [x, y, 1]ᵀ = K [R | t] [X, Y, Z, 1]ᵀ
   ↓
Optimization (Bundle Adjustment)
   min {R,t,X} Σ ‖x − π(K,R,t,X)‖²
   ↓
Output
   • Camera poses
   • Sparse/Dense 3D point cloud
```

<br>

**VGGT (Learning-driven)**

<br>

```
Input Images
   ↓
Patch Embedding (DINO)
   ↓
Camera Tokens + Self-Attention
   ↓
Feed-forward Transformer
   ↓
Outputs (Direct Prediction)
   • Intrinsics K
   • Extrinsics [R | t]
   • Depth Maps
   • Point Maps
   • 3D Tracks
```



<br>

```
                ┌──────────────────────────────┐
                │  📍 Local Object Dynamics    │
                │ (SO(3) Forecasting, ICCV’25) │
                │  - Neural CDE + SG filter    │
                │  - Robust to noise & forces  │
                └─────────────┬────────────────┘
                              │
            Pose / Rotation Trajectories (SO(3)) 
                              │
      ┌───────────────────────▼──────────────────────────┐
      │           Global 4D Scene Modeling               │
      │────────────────────────────────────────────────  │
      │ MonST3R (CVPR’25)  → Geometry in motion          │
      │ Shape of Motion (CVPR’25) → Shape + motion priors│
      │ 4DNeX (CVPR’25)   → End-to-end 4D generation     │
      └─────────────┬───────────────────────┬────────────┘
                    │                       │
     ┌──────────────▼─────────────┐   ┌─────▼──────────────┐
     │ Geometric Backbone         │   │ Semantic Backbone  │
     │ VGGT (CVPR’25)             │   │ OpenScene (2023)   │
     │ - Camera intrinsics/extr.  │   │ - Open-vocab 3D    │
     │ - Depth, 3D tracks         │   │ - Semantic labels  │
     └────────────────────────────┘   └────────────────────┘
```


<br>


| Level                     | Method                            | Core Idea                                                                                                   | Input                                    | Output                                        | Use Case                                                |
| ------------------------- | --------------------------------- | ----------------------------------------------------------------------------------------------------------- | ---------------------------------------- | --------------------------------------------- | ------------------------------------------------------- |
| **Local Object Dynamics** | **SO(3) Forecasting (ICCV 2025)** | Neural CDE + Savitzky–Golay filtering for robust rotation forecasting under noise & non-conservative forces | Noisy pose estimates (tracking, sensors) | Future rotation trajectories (SO(3) manifold) | Robust object tracking, AR/VR pose estimation, robotics |
| **Global Scene Geometry** | **MonST3R (CVPR 2025)**           | Joint geometry estimation in motion scenes                                                                  | Multi-frame RGB                          | 3D geometry with motion consistency           | Dynamic scene reconstruction                            |
|                           | **Shape of Motion (CVPR 2025)**   | Learn shapes guided by motion priors                                                                        | Video sequences                          | 4D shapes with motion cues                    | Shape + motion joint modeling                           |
|                           | **4DNeX (CVPR 2025)**             | Transformer-based 4D scene understanding                                                                    | RGB + depth / multi-view                 | Semantic + geometric 4D representation        | AR/VR, semantic-aware 4D perception                     |
| **Geometric Backbone**    | **VGGT (CVPR 2025)**              | Feed-forward vision transformer for intrinsics, extrinsics, depth, point tracks                             | Multi-view images                        | Camera poses + 3D structure                   | SfM replacement                                         |
| **Semantic Backbone**     | **OpenScene (2023)**              | Open-vocab semantics in 3D                                                                                  | RGB + depth                              | 3D semantic labels                            | Open-world scene segmentation                           |




<br><br>

| Step / Component   | Classical SfM (Geometry-driven)                                                   | VGGT (Learning-driven, CVPR 2025)                                      | Core Formula                                     |
|--------------------|-----------------------------------------------------------------------------------|------------------------------------------------------------------------|--------------------------------------------------|
| Calibration        | Explicit intrinsics (fx, fy, px, py, distortion) + extrinsics (R, t).             | Learns intrinsics + extrinsics directly from images (camera tokens).    | K = [[fx,0,px],[0,fy,py],[0,0,1]]; [R | t]       |
| Correspondences    | 2D–2D feature matching (SIFT, SuperGlue, etc.).                                  | Implicit via tokenized features + self-attention.                       | xᵢᵀ F xⱼ = 0                                     |
| Projection Matrix  | Projects 3D → 2D using camera model.                                              | No explicit projection; jointly predicts depth, points, and poses.      | λ [x,y,1]ᵀ = K [R | t] [X,Y,Z,1]ᵀ                |
| Optimization       | Non-linear least squares (Bundle Adjustment, rotation averaging, distortion).     | Implicit optimization inside feed-forward transformer.                  | min {R,t,X} Σ ‖x − π(K,R,t,X)‖²                  |
| Speed & Efficiency | Incremental/global SfM → hours–days.                                              | < 1 second per scene.                                                   | —                                                |
| Output             | Camera poses + sparse/dense 3D point cloud (post-processing often needed).        | Direct prediction of intrinsics, extrinsics, depth, points, 3D tracks.  | —                                                |


<br>

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


<br><br><br><br>


## References 1

<br>

**Frontiers in AI Research (2025)**


1. Efficient Multimodal Alignment & Generation  
- **Key Results**:  
  - CLIPDraw++ (NeurIPS ’24): unified vision–language alignment  
  - Video-LLaMA (ICLR ’25): zero-shot text-to-video generation  
- **Challenges**: real-time deployment, fine-grained controllability, safety/robustness

📍 2. Long-Term Temporal & Structural Consistency  
- **Key Results**:  
  - FlowFormer (CVPR ’25): flow-matching for video coherence
  - VideoMamba (25)
  - MemoryNeRF (NeurIPS ’24): implicit scene memory across seconds  
- **Opportunities**:  
  - scalable frame-level memory modules  
  - layered geometric+semantic caching  
  - dynamic scene understanding

📍 3. Self-Supervised Learning from Extreme Sparsity  
- **Key Results**:  
  - `SparseMAE (ICCV ’23): masked autoencoding with <0.1 % tokens`
  - Contrastive-Sparse (ICLR ’24): adaptive masking focus on high-entropy regions  
- **Goals**:  
  - near-fully-supervised performance with ‰-level labels  
  - unified multi-task pretraining (classification, detection, generation)

4. Differentiable Physics & Hybrid Simulation  
- **Key Results**:  
  - DiffPhys (NeurIPS ’24): end-to-end differentiable physics engine  
  - FluidNeRF (CVPR ’25): fluid simulation within NeRF framework  
- **Directions**:  
  - trainable raytracing and material modules  
  - learned+classical simulator hybrids  
  - transferable “physical basis” representations

5. Verifiable Robustness & Explainable Security  
- **Key Results**:  
  - Certified Diffusion Robustness (ICLR ’25)  
  - Provable Transformer Defenses (NeurIPS ’24)  
- **Imperatives**:  
  - certified adversarial bounds  
  - causal traceability in generation/decision chains  
  - end-to-end system-level trust guarantees

📍 **1. DiT (Diffusion Transformer)**
- **Overview**: Combines Transformer context modeling with diffusion denoising  
- **Examples**  
  1. **KeyFace** – speech-driven face animation via stepwise denoising  
  2. **DiffLocks** – high-fidelity hair generation  
  3. **Pippo** – multi-view rendering with geometric and texture coherence  
- **Benefit**: Maintains character appearance/style across shots and supports conditional, coherent animation

📍 **2. Diadic Models**
- **Concept**: Model both speaking and listening behaviors for interactive avatars  
- **Examples**  
  - **INFP** / **DualTalk**: dual-branch networks for speaker lip sync and listener micro‐expressions  
- **Insight**: Ensures consistent identity/style in extended dialogues by modeling two-way interaction

**3. Priors**
- **Synthetic Priors (GASP, SynShot)**  
  - Generate “pseudo-real” head avatars (poses, expressions, lighting) to enrich training data  
  - Improves generalization to extreme poses and rare expressions  
- **Diffusion-based Priors (CAP4D, GAF)**  
  - Use pretrained diffusion models to produce high-quality 3D avatars or dynamic sequences  
  - Accelerates multi-view/multi-expression data generation and boosts video consistency

**4. Implications**
- **Architecture**: Adopt DiT’s diffusion-Transformer for cross-scene realface rendering  
- **Interaction Consistency**: Integrate diadic modeling to handle speaking and listening coherently  
- **Memory Extension**: Add a latent memory module to preserve character traits across sessions



<br><br><br><br>


## References 2

<br>


[📍 2025 - Forecasting Continuous Non-Conservative Dynamical Systems in SO(3)](https://bastianlb.github.io/forecasting-rotational-dynamics/) - Modeling the rotation of moving objects

[2024 - No Training, No Problem: Rethinking Classifier-Free Guidance for Diffusion Models](https://arxiv.org/abs/2407.02687)


[BERT], [Wav2Vec2] - SSL, masked reconstruction, contrastive loss


<br>

## 4D

<br>

[2025 - MonST3R: A Simple Approach for Estimating Geometry in the Presence of Motion](https://monst3r-project.github.io/)


[2025 - Shape of Motion](https://shape-of-motion.github.io/)


[2025 - 4DNex](https://x.com/janusch_patas/status/1957697411591336114?s=46&t=1tqSPaJVuc_ns2oTMZs8EQ) - 4D scene understanding

<br><br>


## 2D

<br>

[DINOv3]

[SAM 2]


<br>

## 3D

<br>


[2025 - VGGT](https://vgg-t.github.io/)

[📍 2023 - OpenScene](https://openaccess.thecvf.com/content/CVPR2023/papers/Peng_OpenScene_3D_Scene_Understanding_With_Open_Vocabularies_CVPR_2023_paper.pdf)

[📍 2024 - Segment3D](https://link.springer.com/chapter/10.1007/978-3-031-72754-2_16)

[2023 - AGILE3D](https://ywyue.github.io/AGILE3D/)

[COLMAP], [GLOMAP]


<br><br>


## Some Products

<br>

[2025 - RealityScan](https://x.com/RealityCapture_/status/1932422430967922793)


<br><br><br>



