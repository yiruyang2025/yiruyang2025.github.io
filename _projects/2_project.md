---
layout: page
title: 2025 - Master Thesis and Project
description: 4D Reconstruction, Connectomics, CVG, 
img: assets/img/4.jpg
importance: 2
category: work
related_publications: true
---

<br>

## Related Coursework

- ViT, DINOv3, Semantic-SAM, Diffusion, OpenScene, NExF, 
- [2025 - 3D Vision](https://cvg.ethz.ch/lectures/3D-vision/)
- [2025 - Seminar in Visual Computing](https://cvg.ethz.ch/lectures/Doctoral-Seminar/)
- [2025 - Mixed Reality](https://cvg.ethz.ch/lectures/Mixed-Reality/)

<br>


## Reading List / References

  - [2025 - St4RTrack](https://st4rtrack.github.io/)
  - [2025 - MonST3R](https://monst3r-project.github.io) - Feed forward, geometry from videos
    - [codebase](https://colab.research.google.com/drive/1-fc8uBxaXC2gbgBJQF-Jf_f0BVmJ-uTP?usp=drive_link)
  - [2024 - DUSt3R: Geometric 3D Vision Made Easy](https://europe.naverlabs.com/research/publications/dust3r-geometric-3d-vision-made-easy/)

<br>


  - [📍 2025- Wayve.ai](https://arxiv.org/pdf/2506.02265)
  - [2024 - DiffusionDrive](https://arxiv.org/abs/2411.15139)
  - [2024 - SplatFields - Neural Gaussian Splats for Sparse 3D and 4D Reconstruction](https://github.com/markomih/SplatFields/tree/main)

<br>

  - [2025 - Multi-layer perceptron-based computer vision neural networks](https://patents.google.com/patent/US20250316074A1/e)
  - [2021 - KiloNeRF: Speeding up Neural Radiance Fields with Thousands of Tiny MLPs](https://openaccess.thecvf.com/content/ICCV2021/html/Reiser_KiloNeRF_Speeding_Up_Neural_Radiance_Fields_With_Thousands_of_Tiny_ICCV_2021_paper.html)

<br>


**Attended Master Thesis Project Defense at cvg**

  - 01 Sep 2025 - 📍 Reconstructing Complete Garments with Foundation Models
    - Pattern Prediction on Fabric Recognition
    - 'Garments are both cultural artifacts and engineered products, but most generative models produce visuals that cannot be manufactured. This thesis introduces a foundation model for pattern-centric garment generation, where outputs are sewing patterns—panels, seams, and annotations—ready for CAD and simulation. A new tokenizer and multimodal dataset enable structured decoding from text or image inputs in a unified framework. In parallel, we investigate fabric recognition from large-scale product data, underscoring the challenge of linking garment shape to material behavior. Experiments show state-of-the-art pattern prediction, strong generalization, and predictable scaling. Together, these contributions move digital fashion toward simulation-ready, fabrication-oriented design.'
    - [2025 - AIpparel: A Multimodal Foundation Model for Digital Garments](https://igl.ethz.ch/projects/aipparel/aipparel_paper.pdf)
    - [2025 - Single View Garment Reconstruction Using Diffusion Mapping Via Pattern Coordinates](https://arxiv.org/html/2504.08353v1)
  - 10 Sep 2025 - An Interactive, Foundation-Model-Empowered Video Annotation Interface for Constructing a Challenging Video Object Segmentation Dataset
    - SAM 2, DINOv2, GPT-4o, 📍 `real-time Annotation`
    - demo - nutsh
  - 02 Oct 2025 - VSLAM-LAB: A Comprehensive Framework for Visual SLAM Baselines and Datasets, pixi
    - 2024 - Gaussian Splatting SLAM, demo
  - 09 Oct 2025 - Controllable Visual Generation using 3D prior
    - HIL D 55.2, ETH Hönggerberg, 14:00
  - StreamSplat: A Framework for Self-Supervised, Online Novel View Synthesis
    -  Friday Oct 10th, 15:00-15:30 Zurich Time
  - (Uncertainty-Aware 3D Mapping, Monday, October 13th, Zoom)
  - From Sensors to Solutions: Permanent Laser Scanning in 📍 Environmental Monitoring, Prof. Dr.-Ing. Daniel Czerwonka-Schröder, 22 October 2025, 4:45 p.m, HIL D 53, Hönggerberg


<br><br>



## Benchmarks and SOTAs

## 1. 4D

  - [2025 - St4RTrack](https://st4rtrack.github.io/)

<br>

## 2. 3D


  - [2025 - MonST3R: A Simple Approach for Estimating Geometry in the Presence of Motion](https://monst3r-project.github.io/)
  - [2024 - AGILE3D](https://ywyue.github.io/AGILE3D/)
  - [2016 - COLMAP 1](https://github.com/colmap/colmap) - baseline 1
  - [2025 - COLMAP 2](https://developer.nvidia.com/blog/how-to-instantly-render-real-world-scenes-in-interactive-simulation/) - baseline 2

<br>


## Key Contributions

- A FFN for 4d Construction, neat and simple pipeline


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


## Some Related Art works

  - [2025 - VGGT](https://vgg-t.github.io/)
  - [2023 - OpenScene](https://openaccess.thecvf.com/content/CVPR2023/papers/Peng_OpenScene_3D_Scene_Understanding_With_Open_Vocabularies_CVPR_2023_paper.pdf) - Open set
  - [2018 - GQN](https://deepmind.google/discover/blog/neural-scene-representation-and-rendering/) - SSL, Neural scene representation

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


## Motion

  - [2025 - Probabilistic Methods for Monocular 3D Human Reconstruction](https://scholar.google.com/scholar?hl=en&as_sdt=0%2C5&q=Probabilistic+Methods+for+Monocular+3D+Human+Reconstruction&btnG=)
  - [Mahcine Learning Street Talk](https://x.com/MLStreetTalk/status/1952743787454668931)
  - [3D gaussian](https://shivangi-aneja.github.io/projects/scaffoldavatar/)

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

## Visual SLAM Pipeline

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

## VGGT (Learning-driven)

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

## Why Squared (L2) Loss

### 1. Mathematical Reason  
Squaring makes the error smooth, continuous, and differentiable, which is required for gradient-based optimization

We update parameters using gradient descent:

$$
\hat{a}_{k+1} = \hat{a}_k - \gamma \nabla L(\hat{a}_k)
$$

To perform this optimization, the loss \(L\) must be differentiable with respect to \(\hat{a}\)

Define the loss function as:

$$
L = \| e \|^2 = e^\top e = \sum_i (b_i - F_i(\hat{a}))^2
$$

Then, the gradient is:

$$
\nabla_{\hat{a}} L = -2 J_F(\hat{a})^\top (b - F(\hat{a}))
$$

This ensures, 
- Continuous and smooth gradient direction  
- Analytical update expression  
- Compatibility with automatic differentiation (autodiff)

If instead we used the absolute error (L1 norm):

$$
L = \| e \| = \sum_i |b_i - F_i(\hat{a})|
$$

the gradient would be non-continuous at \(e = 0\), causing oscillation or instability during optimization.

<br>

### 2. Statistical
The squared loss corresponds to assuming Gaussian noise in the measurements

Assume the observation model:

$$
b = F(\hat{a}) + \epsilon, \quad \epsilon \sim \mathcal{N}(0, \sigma^2 I)
$$

Then the likelihood function is:

$$
p(b \mid \hat{a}) = \frac{1}{Z} \exp\!\left(-\frac{1}{2\sigma^2}\| b - F(\hat{a}) \|^2\right)
$$

Taking the negative log-likelihood (Maximum Likelihood Estimation):

$$
-\log p(b \mid \hat{a}) = \frac{1}{2\sigma^2}\| b - F(\hat{a}) \|^2 + \text{const.}
$$

Thus minimizing the squared loss is equivalent to Maximum Likelihood Estimation (MLE) under Gaussian noise


<br>

### 3. Optimization

The squared loss amplifies large errors and stabilizes convergence

Large residuals receive stronger penalties:

$$
L = (b - F(\hat{a}))^2
$$

Hence,
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


<br><br>


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


## 4D

  - [2025 - 4DNex](https://x.com/janusch_patas/status/1957697411591336114?s=46&t=1tqSPaJVuc_ns2oTMZs8EQ) - 4d scene understanding
  - [2024 - CAT4D](https://cat-4d.github.io/) - 4d Reconstruction from video



```
[ Multi-view Cameras + Rig Info ]
            ↓
         (Rig3R)
     3D Scene Understanding
            ↓
   [ BEV / Map / Agent Context ]
            ↓
        (DiffusionDrive)
   Multi-Modal Trajectory Generation
            ↓
     Control & Real-Time Driving
```

<br>


## 3D

  - [2025 - VGGT](https://vgg-t.github.io/)
  - [📍 2023 - OpenScene](https://openaccess.thecvf.com/content/CVPR2023/papers/Peng_OpenScene_3D_Scene_Understanding_With_Open_Vocabularies_CVPR_2023_paper.pdf)
  - [📍 2024 - Segment3D](https://link.springer.com/chapter/10.1007/978-3-031-72754-2_16)
  - [2023 - AGILE3D](https://ywyue.github.io/AGILE3D/)
  - [COLMAP], [GLOMAP]

<br>


## 2D

  - [ViT], [DINOv3], [SAM 3]


<br>


## Some Products

  - [2025 - RealityScan](https://x.com/RealityCapture_/status/1932422430967922793)
  - [3DV projects 2024](https://cvg.ethz.ch/lectures/3D-vision/assets/3DV_Projects_2024.pdf)
  - [3DV projects 2025]


<br><br><br>



