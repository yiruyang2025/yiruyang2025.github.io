---
layout: page
title: 2025 - Master Thesis
description: 3D Reconstruction for Virus Drug / Treatment Design, Surface Fitting
img: assets/img/4.jpg
importance: 2
category: work
related_publications: true
---

<br><br>

[2021 - Scaling vision with sparse mixture of experts](https://scholar.google.com/citations?view_op=view_citation&hl=en&user=ZHnRsrsAAAAJ&citation_for_view=ZHnRsrsAAAAJ:qUcmZB5y_30C)

[2024 - soft MOE](https://arxiv.org/pdf/2308.00951)


[2025 - Probabilistic Methods for Monocular 3D Human Reconstruction](https://scholar.google.com/scholar?hl=en&as_sdt=0%2C5&q=Probabilistic+Methods+for+Monocular+3D+Human+Reconstruction&btnG=)

[Aug 2025 - Proxies Could Be The Key To Interacting With Physical Objects In Mixed Reality](https://www.uploadvr.com/research-proxies-mixed-reality/)

  - "Vision → AI Scene Structure" → "Constrained Optimized Layout" → "Gesture-Driven Lazy Follow" on Glasses

<br><br>


## 📍 `3D Reconstruction for Virus Treatment (Drug) Design`

<br>

**1. Feature extraction from the reconstructed structure using 3D CNN/Transformer**

<br><br>

**2. Model calibration using protein structure prediction (AlphaFold, RoseTTAFold) combined with experimental data**


<br><br>

**3. Shape complementarity analysis of viral surface antigen regions**





<br><br><br><br><br><br>


## References



<br><br><br><br><br><br><br><br><br><br>


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
         

<br>

```
‣ AffineGlue - Joint Matching and Robust Estimation is an end-to-end feature matching and robust model estimation framework. Its core design goal is to significantly reduce the combinatorial complexity of matching and estimation using single-point minimal solvers

‣ StereoGlue
```
<br>

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


<br><br>

[Implicit 3D Representations]

<br>

[2021 - D-NeRF](https://github.com/albertpumarola/D-NeRF)


[2025 - TetWeave](https://x.com/TheGraphicsFrog/status/1920360716097274059)


[C++ lib repo - toolkit](https://github.com/libigl)

<br>

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

<br><br>


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

<br><br>

[2023 - AGILE3D](https://arxiv.org/abs/2306.00977)

<br><br><br><br>


## Benchmark

<br><br><br><br>


## Dataset


<br><br><br><br><br>





<br><br>

[DINOv2] [OpenScene] [FAM-HRI]

[2025 - VGGT: Visual Geometry Grounded Transformer](https://arxiv.org/html/2503.11651v1?utm_source=chatgpt.com)

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

<br><br><br>


**Stage 1 – Cross-modal alignment**

`OpenScene, CLIP space, DINOv2 space, text-3D embedding`

<br>

**Goal**

The reconstructed 3D features are no longer purely geometric but instead contain semantic information and can be aligned with modalities such as text and images. This allows the model to:

  - Easier to understand the meaning of the reconstruction results

  - Cross-modal retrieval (text → point cloud, image → mesh)

  - Supports zero-shot labeling, classification, and querying


<br>

**Stage 2 – Shape the Semantic Space**

Geometric Consistency Filtering + `3D Hough Voting` + Contrastive Learning

<br>

**Goal**

  - Semantic grouping after filtering and voting (more general than standard segmentation)
  - A semantically shape-aware structure space that can be used as a priori for Stage 3

<br>

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

## Robotics



<br><br><br><br>




## References

<br>

[CAT-3D]

[2018 - Learning Priors for Semantic 3D Reconstruction](https://openaccess.thecvf.com/content_ECCV_2018/html/Ian_Cherabier_Learning_Priors_for_ECCV_2018_paper.html)

[2017 - Semantically Informed Multi‑view Surface Refinement](https://openaccess.thecvf.com/content_iccv_2017/html/Blaha_Semantically_Informed_Multiview_ICCV_2017_paper.html)

[2020 - Learning 3D Semantic Scene Graphs from 3D Indoor Reconstructions](https://openaccess.thecvf.com/content_CVPR_2020/html/Wald_Learning_3D_Semantic_Scene_Graphs_From_3D_Indoor_Reconstructions_CVPR_2020_paper.html)

[📍 2025 - CrossOver: 3D Scene Cross-Modal Alignment](https://openaccess.thecvf.com/content/CVPR2025/html/Sarkar_CrossOver_3D_Scene_Cross-Modal_Alignment_CVPR_2025_paper.html)

[📍 2002 - From Images to 3D Models](https://cacm.acm.org/research/from-images-to-3d-models/)

[2022 - Advancing the foundations of mixed reality](https://www.microsoft.com/en-us/research/blog/eccv-2022-highlights-advancing-the-foundations-of-mixed-reality/?OCID=msr_blog_ECCVHighlights_Lab)





<br><br>

**Trustworthy**

[2025 - IAP: Invisible Adversarial Patch Attack through Perceptibility-Aware Localization and Perturbation Optimization](https://arxiv.org/abs/2507.06856)

<br><br>


**CV**



[📍 2025 - VisualSpeaker](https://arxiv.org/pdf/2507.06060)

[2023 - 3DiFACE: Diffusion-based Speech-driven 3D Facial Animation and Editing](https://arxiv.org/abs/2312.00870)

[2022 - Tech helps (hopefully) - AR transcription and translation](https://x.com/Google/status/1524464030668177409)

[2025 - Eye Tracking](https://acl2025-eyetracking-and-nlp.github.io/)


<br><br>

**3D Vision**


[📍 2025 - AnyCam: Learning to Recover Camera Poses and Intrinsics from Casual Videos](https://openaccess.thecvf.com/content/CVPR2025/html/Wimbauer_AnyCam_Learning_to_Recover_Camera_Poses_and_Intrinsics_from_Casual_CVPR_2025_paper.html)

[2025 - Oral - MaskControl: Spatio-Temporal Control for Masked Motion Synthesis](https://www.ekkasit.com/ControlMM-page/)


[2025 - EgoVLA: Learning Vision-Language-Action Models from Egocentric Human Videos](https://rchalyang.github.io/EgoVLA/)


<br>

📍 Large multimodal models [CLIP], [DALL·E], [ALIGN]

📍 Implicit 3D representations [NeRF], [DeepSDF]


<br>

[1] Cherabier, I., Schönberger, J.L., Oswald, M.R., Pollefeys, M., Geiger, A.: Learning Priors for Semantic 3D Reconstruction. In: Proceedings of Conference on Computer Vision and Pattern Recognition (CVPR) (2018)

[2] Wang, Y., Pan, L., Pollefeys, M., Larsson, V.: Structure‑from‑Motion with a Non‑Parametric Camera Model. In: Proceedings of Conference on Computer Vision and Pattern Recognition (CVPR) (2025)

[3] Wald, J., Dhamo, H., Navab, N., Tombari, F.: Learning 3D Semantic Scene Graphs from 3D Indoor Reconstructions. In: Proceedings of International Conference on 3D Vision (3DV) (2020)

[4] Tombari, F., Di Stefano, L.: Object Recognition in 3D Scenes with Occlusions and Clutter by 📍 Hough Voting. In: Proceedings of International Conference on Computer Vision (ICCV) (2010)

[5] Peng, S., Genova, K., Jiang, C. M., Tagliasacchi, A., Pollefeys, M., Funkhouser, T.: OpenScene: 3D Scene Understanding with Open Vocabularies. In: Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition (CVPR) (2023)

[6] Song, S., Yu, F., Zeng, A., Chang, A.X., Savva, M., Funkhouser, T.: Semantic Scene Completion from a Single Depth Image. In: Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition (CVPR) (2017)




<br><br><br>



 - [ZapBench - 2025](https://zapbench-release.storage.googleapis.com/landing.html)

 - [State Space Models](https://yiruyang2025.github.io/blog/2025/State-Spaces-Models-25/)

 - [On the Tradeoffs of SSMs and Transformers](https://goombalab.github.io/blog/2025/tradeoffs/#mamba-putting-it-all-together)

- [2025 - SnapMoGen](https://arxiv.org/abs/2507.09122)


<br><br><br>

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


<br>


<br><br>

## Modules

<br>

**[Compressive Transformer]**

[Mamba], [RWKV]

[Differentiable Neural Computer]

[Sparse Access Memory]

[AlphaDev]

[Scaling 4D Representations](https://arxiv.org/pdf/2412.15212)

[Ego4D](https://ego4d-data.org/)


<br>

Causal ViViT

VQ-VAE

MaskGIT

C-ViViT 

T5X Encoder

Transformer in Latent Space

<br><br>



<br><br>


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


<br>

<br>


**Flow Matching Loss**
<br>

**Purpose**  
Enforce temporal smoothness by aligning latent representations of adjacent frames

**Definition**

$$
\mathcal{L}_{\mathrm{flow}} = \bigl\lVert z_{t+1} - \mathrm{warp}(z_t, f_{t\to t+1}) \bigr\rVert_{1}
$$

- $z_t, z_{t+1}$: latent features of frame $t$ and frame $t+1$
- $\mathrm{warp}(z_t, f_{t \to t+1})$: features $z_t$ warped by the predicted flow field $f_{t \to t+1}$ 
- $f_{t \to t+1}$: optical flow field predicted by a lightweight network

<br>

- **Domain**  
  - Flow Matching applies to video frames (temporal consistency)

- **Alignment Target**  
  - Flow Matching aligns adjacent frames’ latent features 

- **Warping Operation**  
  - Flow Matching includes a warp based on optical flow

- **Goal**  
  - Flow Matching improves frame-to-frame coherence in generated video



<br>

**Total Loss**

$$
\mathcal{L}_{\mathrm{flow}} = \bigl\lVert z_{t+1} - \mathrm{warp}(z_t, f_{t\to t+1}) \bigr\rVert_{1}
$$

<br><br>

## References

<br>

**Frontiers in AI Research (2025)**

<br>

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


<br><br>

<br><br><br>



