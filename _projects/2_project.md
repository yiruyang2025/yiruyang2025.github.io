---
layout: page
title: 2025 - Master Thesis 2
description: Surface Fitting, (4D Panoptic Reconstruction)
img: assets/img/4.jpg
importance: 2
category: work
related_publications: true
---

<br><br>

## Some topics

<br>

[2025 - Deepmind - The Era of Experience](https://storage.googleapis.com/deepmind-media/Era-of-Experience%20/The%20Era%20of%20Experience%20Paper.pdf)


<br>

**Pipeline**

```
Sparse Data (raw images/videos)  
   ↓  
SfM pipeline (COLMAP / GLOMAP → poses + sparse 3D)  
   ↓  
3D/4D Foundation Model (dense, semantic, multimodal reconstruction)
```

<br>

`3D -> 4D Segmentation / Understanding`

Achieve globally-consistent segmentation directly in 3D space --> extending it to Dynamic 4D scenes


<br><br>

## 1. 4D

<br>

[📍 2025 - 3DObjectReconstruction - Toolkit](https://github.com/NVIDIA/3DObjectReconstruction)


Single-view - [2025 - Shape of Motion: 4D Reconstruction from a Single Video](https://shape-of-motion.github.io/)


<br>

**Pipeline**

📍 [2025 - Shape of Motion] -> `Zero-shot` via Vocabulary scoring (+ Multi-View)

<br><br>

## 2. 3D

<br>

[📍 2024 - Segment3D](https://link.springer.com/chapter/10.1007/978-3-031-72754-2_16)

[📍 2023 - OpenScene](https://openaccess.thecvf.com/content/CVPR2023/html/Peng_OpenScene_3D_Scene_Understanding_With_Open_Vocabularies_CVPR_2023_paper.html)

[📍 2025 - VGGT](https://openaccess.thecvf.com/content/CVPR2025/html/Wang_VGGT_Visual_Geometry_Grounded_Transformer_CVPR_2025_paper.html)

[2025 - PanSt3R: Multi-view Consistent Panoptic Segmentation](https://arxiv.org/abs/2506.21348)


<br><br>

`1. Geometry-Centric 3D Models`

<br>

DUSt3R (CVPR 2024)

  - 2D Images → 🔗 Feature Matching → 🏗️ 3D Structure

<br>

MASt3R (ECCV 2024)

  - Images → 📌 3D-Aware Matching → 📏 Precise Geometry

<br>

VGGT (CVPR 2025)

  - Image Sequences → 🧠 Geometry-Grounded Attention → 🏛️ 3D Pose & Structure



<br>

`2. Semantic + Geometry Joint Models`

<br>

SAM (ICCV 2023, Meta AI) / SAM 2 (2024, Meta AI)

  - Video / 3D Stream → ⚡ SAM 2 Engine → 🎬 Consistent 2D/3D/4D Segmentation

<br>

PanSt3R (ICCV 2025)

  - Multi-View Images → 🔄 Fuse Masks → 🧩 3D Segmented Scene

<br>

4D Panoptic Extensions (CVPR 2024, Ego-Exo4D)

  - Video → 3D Panoptic + Time → 🌀 4D Reconstruction


<br><br><br>

**Some Other References**

<br>

[2024 - SceneFun3D](https://openaccess.thecvf.com/content/CVPR2024/html/Delitzas_SceneFun3D_Fine-Grained_Functionality_and_Affordance_Understanding_in_3D_Scenes_CVPR_2024_paper.html)

[2024 - AGILE3D](https://ywyue.github.io/AGILE3D/)

[2016 - COLMAP 1](https://github.com/colmap/colmap) - baseline 1

[2025 - COLMAP 2](https://developer.nvidia.com/blog/how-to-instantly-render-real-world-scenes-in-interactive-simulation/) - baseline 2

[2024 - MASt3R](https://link.springer.com/chapter/10.1007/978-3-031-73220-1_5)

[2024 - DUSt3R: Geometric 3D Vision Made Easy](https://openaccess.thecvf.com/content/CVPR2024/html/Wang_DUSt3R_Geometric_3D_Vision_Made_Easy_CVPR_2024_paper.html)


<br><br>

## 3. 2D

<br>

[📍 2025 - DINOv3 - checkpoints](https://huggingface.co/collections/facebook/dinov3-68924841bd6b561778e31009)

[2023 - Segment Anything](https://openaccess.thecvf.com/content/ICCV2023/html/Kirillov_Segment_Anything_ICCV_2023_paper.html)


<br>



<br>

<p align="left">
  <img src="https://yiruyang2025.github.io/assets/img/project2_1.jpg" alt="Project 1 Visualization" width="85%">
</p>

<br>

<p align="left">
  <img src="https://yiruyang2025.github.io/assets/img/project2_2.jpg" alt="Project 1 Visualization" width="85%">
</p>

<br>

<p align="left">
  <img src="https://yiruyang2025.github.io/assets/img/project2_3.jpg" alt="Project 1 Visualization" width="85%">
</p>

<br><br><br>







<br><br><br><br><br><br>


## Some Other topics

<br>

[2021 - Scaling vision with sparse mixture of experts](https://scholar.google.com/citations?view_op=view_citation&hl=en&user=ZHnRsrsAAAAJ&citation_for_view=ZHnRsrsAAAAJ:qUcmZB5y_30C)

[2024 - soft MOE](https://arxiv.org/pdf/2308.00951)


[2025 - Probabilistic Methods for Monocular 3D Human Reconstruction](https://scholar.google.com/scholar?hl=en&as_sdt=0%2C5&q=Probabilistic+Methods+for+Monocular+3D+Human+Reconstruction&btnG=)

[2025 - minFM: Minimal Flow Matching](https://github.com/Kai-46/minFM)

[NanoGPT (124M) in 3 minutes](https://github.com/KellerJordan/modded-nanogpt)


[Aug 2025 - Proxies Could Be The Key To Interacting With Physical Objects In Mixed Reality](https://www.uploadvr.com/research-proxies-mixed-reality/)

[2025 - GEN3C: 3D-Informed World-Consistent Video Generation with Precise Camera Control](https://github.com/nv-tlabs/GEN3C)


<br>

World Modeling / 3D Human Reconstruction, Surface Fitting


<br><br>



## World Models / [Reality Proxy](https://www.arxiv.org/pdf/2507.17248)

<br>

[Mahcine Learning Street Talk](https://x.com/MLStreetTalk/status/1952743787454668931)

[3d gaussian](https://shivangi-aneja.github.io/projects/scaffoldavatar/)

<br>

```
World models typically encounter two key challenges when constructing and maintaining a 3D representation of the environment:

Local drift accumulation
Even small per-frame registration errors can accumulate over time, causing the overall map to "distort" or "tear," undermining the reliability of long-term planning and dynamic prediction.

Poor matching consistency
Traditional RANSAC methods focus solely on the globally optimal rigid transformation, but do not consider spatial smoothness. This can easily lead to seemingly accurate but inconsistent local matches, resulting in map instability.

How does your "3D→3D StereoGlue" proposal address these issues?

Rotation-invariant local coordinate matching (based on Lipman et al., 2005)
Compute the alignment error in the local reference frame defined by the principal curvature of each point, rather than directly comparing in Euclidean space. This effectively filters out "outliers" whose errors appear small in global space but are inconsistent with the local geometry, significantly reducing drift.

Variational Smoothness Penalty (Based on Botsch & Sorkine, 2008)
While evaluating the number of inliers, a smoothing penalty is applied to the difference in rigid transformations between adjacent source points. This ensures spatial consistency and coherence across the entire point cloud registration, avoiding unphysical distortions such as "stretching" and "folding."

Single-Point Minimum Solver Integration (StereoGlue Framework)
Rigid transformation hypotheses are generated from a single matching point and efficiently verified using guided matching, significantly reducing the combinatorial complexity of RANSAC. This enables faster and more stable online updates of the 3D map, freeing up more computing power for subsequent dynamic learning and planning of the world model.

Core Value to DeepMind's World Model
Significantly reduces drift, maintaining high-precision registration even when processing tens of thousands of frames.

Improves long-term planning capabilities. The stable 3D map makes the model more reliable in predicting future states and rewards.

Computational efficiency is optimized, and the single-point solver and guided matching significantly accelerate the registration step, freeing up more resources for policy learning or world model training.
```




<br><br>

## Geometric Consistency 

<br>

[Y. Lipman, O. Sorkine, D. Levin, D. Cohen-Or, “Linear rotation-invariant coordinates for meshes”, ToG 24(3):479–487, 2005](https://dl.acm.org/doi/abs/10.1145/1073204.1073217?casa_token=FxLVarWWO0gAAAAA:s9Moc1rP5xJR041TDS4Sl1uRo44dSuEpItgMO3Ff1Sz99WG-6KW_oQG6ngOuHuEeHBtmN9_17HyO)



[M. Botsch & O. Sorkine, “On linear variational surface deformation methods”, TVCG 14(1):213–230, 2008](https://ieeexplore.ieee.org/abstract/document/4359478?casa_token=S9C_sHw74kUAAAAA:YjKWtiEuQylSlynlwzPBUrO-oZCl8SizIlRHoCgyPYtuQNM3p-ZTNntP7TZ9iOmQAiuOGjEa7g)


<br>

**A 3D -> 3D StereoGlue: Geometric Constraint based on Guided Matching**

<br>

| Method               | Domain                    | Feature & Minimal Solver                                                                                                                                                                             | Guided Matching                                                                                                                                                                                                                                                                                                                   | Score                                                                                                                                                                                   |
| -------------------- | ------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **StereoGlue_V2** | Point cloud → Point cloud | **Features & Solvers**<br>• Oriented 3D–3D correspondences (e.g., from GeoTransformer) + **Rotation-Invariant Local-Frame Coordinates** (Lipman et al. 2005)<br>• **Q-REG** (quadratic patch → R, t) | **1.** Estimate initial model θ(R,t) from a single 3D–3D correspondence<br>**2.** For each source point p₁, apply θ to obtain its mapped position T(p₁)<br>**3.** For its k nearest candidate q₂, compare in local-frame coordinates and select the one minimizing alignment error<br>**4.** If ∥T(p₁) – q₂∥ < ε, count as inlier | **Model score** = number of inliers;<br>**+ Variational smoothing**: add a local smoothness penalty between adjacent transforms in the score to encourage coherent inlier distributions |




<br>

| **Method**                            | **Domain**                      | **Feature & Minimal Solver**                                                                                                                                                                                                                        | **Guided Matching**                                                                                                                                                                                    | **Score**                                                                                 |
| ------------------------------------- | ------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------- |
| **AffineGlue**                        | 2D→2D (image–image)             | • Affine correspondences (ACs) via DoG+AffNet or SuperPoint+AffNet<br>• Solver: <br>  – **1 AC + gravity** (1AC+iG) for Essential/Homography<br>  – **1 AC + monodepth** (1AC+mD) for Essential<br>  – **1 AC + gravity** homography (new 1AC+iG-H) | For each source keypoint, re-project it using the hypothesis and choose the best among its **k** candidates (lowest epipolar or homography residual).                                                  | Count of 2D inliers whose residual ≤ threshold (optionally weighted by match confidence). |
| **StereoGlue**                        | 2D→2D & 2D→3D                   | • Same 2D feature setup as above<br>• Solvers:<br>  – 1 AC+iG/1AC+mD for Essential/Homography<br>  – P1AC for PnP (2D→3D)<br>  – 1 PC+iG for Essential, 1 AC+iG-H for Homography                                                                    | Identical guided matching: for each source feature, re-project (into image or 3D map) and pick the best among its **k** candidates under the model.                                                    | Number of (2D or 2D→3D) inliers under a strict reprojection threshold.                    |
| **3D→3D Adaptation**<br/>(e.g. Q-REG) | 3D→3D (point cloud–point cloud) | • Oriented 3D point pairs from descriptors (FPFH/SHOT/3DMatch/GeoTransformer)<br>• Solver: **Q-REG** fits a local quadratic at one point → gives relative rotation & translation from that single match                                             | Guided by rigid-transform: for each source 3D point, apply the hypothesized rigid transform and choose, among its **k** descriptor candidates, the one with the smallest Euclidean reprojection error. | Number of 3D point-pair inliers under a strict Euclidean distance threshold.              |
         

<br><br>

**Some Recent Progress**

```
**In the era of Handcrafted Features**

PFH/FPFH (Rusu & Cousins 2009) and SHOT (Tombari et al. 2010) already used LRF + local geometric histograms for 3D-to-3D registration, and were successfully applied in industrial libraries such as PCL and Open3D.

**In the era of Deep Learning**

3DMatch (Zeng et al. 2017), PPFNet/PPF-FoldNet (Deng et al. 2018–19), and FCGF (Choy et al. 2019) all employ "implicit LRF + differential geometric feature" learning, achieving registration success rates of over 90% and robustness to over 80% in extreme occlusion and noise scenarios.
The latest TEASER++ (Yang et al. 2021) can achieve globally optimal coarse point cloud registration with a 99% outlier score, and combined with the most advanced deep features in academia, it can achieve millimeter-level accuracy and industrial-grade stability.
```

<br><br>

**Some Background Knowledge**

[1. Jesse Douglas (1931). “Solution of the Problem of Plateau”](https://www.jstor.org/stable/1968115?seq=1)

  - Annals of Mathematics 33(3): 263–321.
  - DOI：10.2307/1968115

<br>

[2. Tibor Radó (1930). “The Problem of the Plateau”](https://link.springer.com/article/10.1007/BF02392418)

  - Acta Mathematica 54(1): 155–157.
  - DOI：10.1007/BF02392418

<br>

[3. Richard Courant (1950). “Dirichlet’s Principle, Conformal Mapping and Minimal Surfaces”](https://link.springer.com/book/10.1007/978-1-4612-9917-2)

  - Wiley, Chapter 6 is devoted to a discussion of variational principles for minimal surfaces


<br><br>


## Topics


<br>

[Implicit 3D Representations]

<br>

[2021 - D-NeRF](https://github.com/albertpumarola/D-NeRF)


[2025 - TetWeave](https://x.com/TheGraphicsFrog/status/1920360716097274059)


[C++ lib repo - toolkit](https://github.com/libigl)


[2025 - Google Research - Measuring heart rate with consumer ultra-wideband radar](https://research.google/blog/measuring-heart-rate-with-consumer-ultra-wideband-radar/)

<br><br>


## Shape Modeling

<br>

[2025 - TetSphere Splatting: Representing High-Quality Geometry with Lagrangian Volumetric Meshes](https://github.com/gmh14/tssplat)

<br>


| Dimension                   | TetSphere Splatting                                                            | NeRF (Implicit Volume Rendering)                                             | Implicit SDF (NeuS Family)                                       |
| --------------------------- | ------------------------------------------------------------------------------ | ---------------------------------------------------------------------------- | ---------------------------------------------------------------- |
| **Geometry Representation** | A set of deformable “tetra-spheres” (tetrahedral sphere primitives)            | Continuous volumetric density function $\sigma(\mathbf{x})$                  | Continuous signed distance field $D(\mathbf{x})$                 |
| **Representation Type**     | Explicit Lagrangian volumetric mesh—direct access to each primitive’s vertices | Implicit: query density and color at any point via an MLP                    | Implicit: query distance to surface and normal via an MLP        |
| **Geometry Extraction**     | Optimized “tetra-spheres” merged into a global mesh with no post-processing    | Requires volume rendering sampling → voxel grid or Marching Cubes extraction | Direct Marching Cubes extraction of the zero level-set surface   |
| **Compute Efficiency**      | Fast energy computation and optimization via libpgo/CUDA extension             | Slow: heavy MLP inference for both training and rendering                    | Moderate: fewer optimizations than NeRF; slower than point-based |
| **Memory & Storage**        | Depends on number of tetra-spheres, typically tens to hundreds of MB           | Network weights \~tens of MB; additional memory for rendering samples        | Similar to NeRF but without storing color parameters             |
| **Detail Quality**          | Fine control via geometric energy terms (smoothness, rigidity, volume)         | Excellent lighting, semi-transparency, and complex material effects          | High geometric fidelity and smooth mesh                          |
| **Editability**             | Results in an explicit mesh, easy to edit and process afterward                | Implicit field requires retraining or explicit conversion for editing        | Requires post-processing to extract and edit the mesh            |



<br><br><br>


## Topics

<br>


 [DINOv2] [FAM-HRI]

 <br>

`1. Regularization → Similar to Laplacian energy minimization`

<br><br>

`2. Maintaining rigidity/local consistency → Derived from ARAP/Linear deformation energy`

<br><br>


`3. Surface smoothness/curvature control → High-order continuity representations are also beginning to be incorporated into NeRF surface extraction`

<br><br>

[2025 - CrossOver](https://github.com/GradientSpaces/CrossOver)

<br><br>


## Geometric Constraint

<br>

| Geometric Constraint Type       | Corresponding Model Method   | Origin and Purpose                                                                      |
| ------------------------------- | ---------------------------- | --------------------------------------------------------------------------------------- |
| **Laplacian Smoothness**        | Curvature loss in NeRF/SDF   | Inspired by Sorkine’s mesh processing techniques; encourages local surface smoothness   |
| **As-Rigid-As-Possible (ARAP)** | ARAP-inspired loss           | Derived from ARAP deformation energy; preserves local geometric rigidity                |
| **High-Order Continuity (C²)**  | Curvature/Hessian-aware NeRF | Based on high-order surface modeling theory; enhances surface smoothness and continuity |




<br><br>

## 3D Reconstruction

<br>


| Dimension            | 3D Gaussian Splatting                      | Explicit Grids/Voxels (e.g., Instant-NGP)       | Tensor Factorization (TensoRF) | Implicit SDF (NeuS family)                              | Dynamic/4D Scenes (Tensor4D)           |
| -------------------- | ------------------------------------------ | ----------------------------------------------- | ------------------------------ | ------------------------------------------------------- | -------------------------------------- |
| **Speed**            | Near real-time                             | Real-time to ultra-real-time                    | Real-time to near real-time    | Moderate to slow                                        | Moderate                               |
| **Storage**          | Moderate (tens of MB)                      | High (hundreds of MB)                           | Low (a few MB)                 | Low–moderate (a few MB)                                 | Low–moderate                           |
| **Geometry Quality** | Continuous, high-fidelity                  | Discrete, voxelized feel                        | Good                           | Excellent (smooth meshes)                               | As static plus temporal coherence      |
| **Color/Lighting**   | Includes per-splat color                   | Includes (via textures or per-voxel)            | Usually includes color         | No (needs separate texture/renderer)                    | Matches static, adds time dimension    |
| **Ease of Use**      | Simple model, flexible multi-source fusion | Mature pipelines, relies on explicit structures | Requires tensor math           | Requires supervised SDF training / volumetric rendering | Requires temporal decomposition design |



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



| Feature               | Mesh-VAE (Explicit Representation)                                   | Implicit Geometry (e.g., NeRF, SDF)                                                                    |
| --------------------- | -------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------ |
| Core Idea             | Encodes and decodes fixed-topology meshes (e.g., triangle meshes)    | Learns a function $f(x) \rightarrow \mathbb{R}$ describing geometry per point (e.g., SDF or occupancy) |
| Data Structure        | Explicit meshes (vertices + faces)                                   | Continuous scalar fields (implicit functions)                                                          |
| Suitable For          | Bodies, faces, organs with consistent topology                       | Arbitrary topology, volumetric shapes (e.g., furniture, animals, organic forms)                        |
| Representative Models | Mesh-VAE, CoMA, SpiralVAE, MeshDiffusion                             | DeepSDF, Occupancy Networks, NeRF, SIREN                                                               |
| Advantages            | Controllable, interpretable, easy for interpolation and registration | No need for fixed mesh, can handle varying topology and finer geometry                                 |

<br><br>

| Framework Name             | Description                                                                                       |
| -------------------------- | ------------------------------------------------------------------------------------------------- |
| Latent Shape Prior NeRF    | Mesh-VAE encodes shape into latent space, which conditions NeRF for multi-shape rendering         |
| Mesh2ImplicitNet           | Latent vector from Mesh-VAE is used as a condition input to an implicit decoder like DeepSDF      |
| MedShape VAE → ImplicitNet | Mesh-VAE builds statistical shape space for medical organs; implicit model refines geometry       |
| Surface-to-Volume Flow     | Mesh is used to generate flow fields, which are converted to implicit fields for shape completion |


<br><br>

## Tasks Matching

<br>


| Task Description                        | Recommended Method       | Reason                                                                |
| --------------------------------------- | ------------------------ | --------------------------------------------------------------------- |
| Modeling same-topology objects          | Mesh-VAE                 | Mesh connectivity is fixed and suitable for morphable structures      |
| Generating arbitrary shapes or plants   | Implicit Geometry        | Better suited for freeform, non-uniform topology                      |
| Image-to-3D with high variation         | Hybrid (Mesh + Implicit) | Mesh gives structure; NeRF/SDF adds realism and detail                |
| Medical shape modeling with priors      | Mesh-VAE + SDF           | Prior modeling with explicit structure, refined via continuous fields |
| Rigging, animation, physical simulation | Mesh-VAE                 | Per-vertex manipulation is straightforward                            |

<br><br>

## Background Knowledge

<br>


[Algorithmic Simplicity](https://www.youtube.com/@algorithmicsimplicity)

[3D Reconstruction from Images](https://www.youtube.com/watch?v=tqBD6rxiul4)

[Andreas Geiger - Deep Models for 3D Reconstruction - 2020](https://www.youtube.com/watch?v=Rfb1J3fJMYA)

[2023 - AGILE3D](https://arxiv.org/abs/2306.00977)

[2023 - AudioPaLM - Google Research](https://arxiv.org/abs/2306.12925)

[2023 - AudioCraft](https://github.com/facebookresearch/audiocraft)


<br><br>

**Semantic Implicit (NeRF)**

[1] Monocular Semantic Reconstruction Using NeRF-Lifted Noisy Priors, tightly couples single-
view semantic segmentation with multi-view geometry, constrains 2D→3D semantic consistency
in NeRF through "Lifted Priors" and reconstructs the complete scene

<br><br>

| Method                     | Core Idea                                                                 |
| -------------------------- | ------------------------------------------------------------------------- |
| **DeepSDF**                | Fits a signed distance function (SDF) using a multilayer perceptron (MLP) |
| **Occupancy Networks**     | Implicitly predicts whether a point in 3D space is occupied               |
| **VQ-VAE 3D / ShapeCode**  | Encodes 3D shapes into discrete latent tokens for reconstruction          |
| **CLIP-Forge / GenRe**     | Generates implicit 3D shapes conditioned on image or language input       |
| **RegNeRF / SemanticNeRF** | Constrains implicit scene modeling using semantic priors                  |



<br><br>

| Directions                       | Methods                                         |
| --------------------------- | -------------------------------------------- |
| NeRF + Semantic Guidance             | Semantic NeRF, RegNeRF, Co-SLAM NeRF         |
| Feed-forward Reconstruction | One-Forward-NeRF, VolRecon, PlanarRecon      |
| Sparse-view Completion      | ReconFusion (CVPR 2024), SPARS3R (CVPR 2025) |
| Shape priors Projection          | ViT feature guidance, latent code fusion     |



<br><br><br><br>


## Research

<br>

**Stage 1 – Cross-modal alignment**

`OpenScene, CLIP space, DINOv2 space, text-3D embedding`

<br>

**Goal**

The reconstructed 3D features are no longer purely geometric but instead contain semantic information and can be aligned with modalities such as text and images. This allows the model to:

  - Easier to understand the meaning of the reconstruction results

  - Cross-modal retrieval (text → point cloud, image → mesh)

  - Supports zero-shot labeling, classification, and querying


<br><br>

**Stage 2 – Shape the Semantic Space**

Geometric Consistency Filtering + `3D Hough Voting` + Contrastive Learning

<br>

**Goal**

  - Semantic grouping after filtering and voting (more general than standard segmentation)
  - A semantically shape-aware structure space that can be used as a priori for Stage 3

<br><br>

**Stage 3 – Expand from Local → Global Shape Priors & Static → Dynamic**

`D-NeRF`

<br>

**Goal**

  - [2021 - CVPR D-NeRF: Neural Radiance Fields for Dynamic Scenes](https://openaccess.thecvf.com/content/CVPR2021/html/Pumarola_D-NeRF_Neural_Radiance_Fields_for_Dynamic_Scenes_CVPR_2021_paper.html?ref=labelbox.ghost.io)
  - [2023 - DeepLS: Local Search for Network Optimization Based on Lightweight Deep Reinforcement Learning](https://ieeexplore.ieee.org/abstract/document/10155296?casa_token=b8l78Uv-H1AAAAAA:U4ZrGd_uM2HkYEzeatrRLNIU9RPKDnyzng3i874NdXPrGdVPLDsBJgBFLWb-26OwSrxwryK7NA)

<br><br><br>

**Stage 4 – Self-Distillation for Efficiency & Real-time Inference**


`DINOv2`


<br>

**Goal**

   - Low Inference Latency
   - On-device



<br><br><br><br>



## Topics

<br>

- Veo3 - Deepmind
- Gen-4 - Runway
- Movie Gen - Meta
- Flow Loss

<br>


- [2023 - Flow Matching in Latent Space](https://arxiv.org/abs/2307.08698)<br>

- [2025 - Generative modelling in latent space](https://sander.ai/2025/04/15/latents.html)<br>

- [2025 - Runway Gen-4 solves AI video’s biggest problem: character consistency across scenes](https://venturebeat.com/ai/runways-gen-4-ai-solves-the-character-consistency-challenge-making-ai-filmmaking-actually-useful/?utm_source=chatgpt.com)<br>
  - 2025 - New York is a Zoo
  - 2025 - The Retrieval
<br>
- [Sparse Autoencoders - 2024 - Scaling and evaluating sparse autoencoder](https://arxiv.org/abs/2406.04093)



<br><br><br><br>



## References


<br>

- EVA-CLIP (2023), OpenCLIP (2023), CLIP-ViP (2023)
- [Multimodal Nerons in NNs](https://distill.pub/2021/multimodal-neurons/)
- LiT - 2022
- ALIGN - 2021


<br>

 
- [PaliGemma 2 - 2024](https://arxiv.org/abs/2412.03555)

- [CLIP - ICML 2021 - Learning Transferable Visual Models From Natural Language Supervision](https://arxiv.org/abs/2103.00020)

- [Multi-Layer Sparse Autoencoders - ICLR 2025](https://github.com/tim-lawson/mlsae)

- [Alpha-CLIP - CVPR 2024 - A CLIP Model Focusing on `Wherever` You Want](https://openaccess.thecvf.com/content/CVPR2024/html/Sun_Alpha-CLIP_A_CLIP_Model_Focusing_on_Wherever_You_Want_CVPR_2024_paper.html)


<br><br>


**Total Loss**

$$
\mathcal{L}_{\mathrm{flow}} = \bigl\lVert z_{t+1} - \mathrm{warp}(z_t, f_{t\to t+1}) \bigr\rVert_{1}
$$


<br><br><br>



## References

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

<br>

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


<br><br><br>



