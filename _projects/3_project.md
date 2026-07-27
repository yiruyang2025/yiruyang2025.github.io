---
layout: page
title: 2025 - Thesis - Flow-Matching / Diffusion, ()
description: Hash, Less Steps
img: assets/img/4.jpg
importance: 3
category: work
related_publications: true
---

<br>

Real-time is the only time. The rest is just latency.  --- `Hash Firm Zurich`
- If the hardware provides good enough memory bandwidth, then **indexing** becomes a more efficient / certain art than **computing**. Prompt some certain Numbers of different size for buildings + avoid lakes, etc. <- with `assigning some certain Hash Value for the diversity` if you like, some [Blender Demo](https://drive.google.com/file/d/1yHixdRDu0Iu6Sx7p0kxDcGuDV4XWsMYe/view?usp=sharing) Auto 3D Assets Prompting in Sep 2025.
- In a non-uniform hash space, the physical distance between sampling points must be taken into account, otherwise the reconstruction will collapse. The drift term of backdiffusion must be scaled according to the **metric tensor** of the manifold.
  - [DeepSDF: Learning Continuous Signed Distance Functions for Shape Representation](https://openaccess.thecvf.com/content_CVPR_2019/papers/Park_DeepSDF_Learning_Continuous_Signed_Distance_Functions_for_Shape_Representation_CVPR_2019_paper.pdf)
  - [📍 1998 - Large Steps in Cloth Simulation](https://www.cs.cmu.edu/~baraff/papers/sig98.pdf)
  - [2022 - DiffCloth: Differentiable Cloth Simulation with Dry Frictional Contact](https://www.csail.mit.edu/research/diffcloth-differentiable-cloth-simulation-dry-frictional-contact)
  - [2025 - Topology-Preserved Auto-regressive Mesh Generation in the Manner of Weaving Silk](https://arxiv.org/pdf/2507.02477)

```
spatial_dist = torch.norm(point_diff, dim=-1, keepdim=True) + 1e-8
normalized_diff = residual_diff / spatial_dist

Iter 1000–3000: HashSize ≈ full
Iter 4000–6000: HashSize ↓
Iter 7000+: HashSize << full # should be for Hash
```

<br>



## Paper Generator™

| Stage                      | Description                                                                                                                                                     |
| -------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Problem Selection**      | Choose a widely used problem where optimality is rarely critical or empirically evaluated.  |
| **Hardness Injection**     | Force a reduction to a well-known NP-hard problem to establish theoretical difficulty.    |
| **Heuristic Recovery**     | Apply a textbook-level greedy or local search heuristic with minor variations.     |
| **Approximation Blessing** | Provide a constant-factor approximation bound. <br/> Common values: 1/2, 1/e, 0.56 (“provable guarantee”).                                                    |
| **Moral High Ground**      | Claim novelty through theoretical legitimacy rather than structural insight. <br/>  |


<br>

## Topic

- [2023 - AlphaDev discovers faster sorting algorithms](https://deepmind.google/blog/alphadev-discovers-faster-sorting-algorithms/)
- 1993 - Computational Complexity - Christos Papadimitriou
- 2009 - Computational Complexity: A Modern Approach - Arora & Barak

- [2023 - Nuvo: Neural UV Mapping for Unruly 3D Representations](https://arxiv.org/pdf/2312.05283)
-  2021 - Shape As Points: A Differentiable Poisson Solver
- [2021 - Neural Geometric Level of Detail](https://arxiv.org/pdf/2101.10994)
- Tools in use, H200
- Diffusion: 5 steps, beta=[0.0001, 0.02] <- [0.1, 0.8]， Scaling residuals: std=1.2004 -> 0.1551


```
R(u,v) = Φ_θ((z_t, t, Nuvo(u,v)))
nuvo_features = diffusion_model.get_nuvo_features(points, nuvo_model)
spatial_dist = torch.norm(point_diff, dim=-1, keepdim=True) + 1e-8 <- change here for your 3D Hash value assignment
normalized_diff = residual_diff / spatial_dist <- change here
```

## Config

- python train.py --config configs/icml.yaml --sample_idx 5 --material stiff --diffusion_steps 10

```
- **Stage 1** (0-5000): Nuvo only
- **Stage 2** (5000-10000): Nuvo + ND with hash assignment
num_iterations: 10000
diffusion_start_iter: 5000

Input (Boxmesh) Details Analysis:
  Vertices: 67970
  Normal variation:
    Mean: 0.076664
    Std:  0.263265
    Max:  2.000000
  Curvature proxy:
    Mean: 104265.058453
    Std:  1197198.073828
    Max:  92199800.035140
  OK: Input (Boxmesh) has good details (mean >= 0.05)

Ground Truth (Sim) Details Analysis:
  Vertices: 67970
  Normal variation:
    Mean: 0.443511
    Std:  0.523963
    Max:  1.999905
  Curvature proxy:
    Mean: 825298.086679
    Std:  8333963.860213
    Max:  196949800.860008
  OK: Ground Truth (Sim) has good details (mean >= 0.05)

Residuals Analysis:
  Mean magnitude: 0.222847
  Std magnitude:  0.076963
  Max magnitude:  0.530114
  Min magnitude:  0.044882
  OK: Residuals are significant (mean >= 0.05)

High-frequency residuals:
  Mean: 0.087973
  Max:  0.934507
  OK: High-frequency details present
```



<p align="left">
  <img src="https://yiruyang2025.github.io/assets/img/project3_2.png" alt="Project 1 Visualization" width="75%">
</p>


<br>

## Tools

| Feature          | **Polyscope (Scientific Viewer)**                                              | **Blender (Production Renderer)**                          |
| ---------------- | ------------------------------------------------------------------------------ | ---------------------------------------------------------- |
| Primary goal     | Data inspection and debugging                                                  | High-fidelity visual rendering                             |
| Visual style     | Flat shading; color-coded scalar fields (e.g., UV charts, normals, error maps) | Photorealistic materials; global illumination; ray tracing |
| Geometry support | Robust to raw meshes, point clouds, non-manifold geometry                      | Requires clean topology or high-poly meshes                |
| Workflow         | Immediate, programmatic (C++ / Python API)                                     | Offline, manual setup (lights, cameras, shaders)           |
| Role in paper    | Qualitative analysis (UV consistency, error visualization)                     | Teaser and results (realistic wrinkles, shadows)           |

<br>

## End-to-End Dataflow

| Phase          | Component                               | Data Type       | Description                                                                       |
| -------------- | --------------------------------------- | --------------- | --------------------------------------------------------------------------------- |
| **Input**      | Sewing pattern prior                    | SVG / JSON      | 2D panel geometry, stitching graph, material constants                            |
|                | Base mesh $\mathcal{M}_{\text{base}}$   | OBJ / PLY       | Coarse 3D garment surface (low-frequency folds)                                   |
|                | Anchor frame $x_{\text{anchor}}$        | Tensor          | Initial shape distribution at $t_0$                                               |
| **Process**    | Nuvo mapping $f_\theta$                 | MLP             | Continuous mapping $(x,y,z)\rightarrow(u,v,k)$ over canonical UV charts           |
|                | Reverse diffusion                       | ODE / SDE       | 5–10 denoising steps in residual space $\mathcal{R}$                              |
|                | Loss constraints                        | Functions       | $\mathcal{L}*{\text{MSE}} + \mathcal{L}*{\text{LPIPS}} + \mathcal{L}_{\text{L1}}$ |
| **Output**     | Residual field $R$                      | Implicit / hash | High-frequency offsets (≤5% mesh scale) in UV space                               |
|                | Refined mesh $\mathcal{M}_{\text{ref}}$ | Mesh / points   | $\mathcal{M}*{\text{ref}}=\mathcal{M}*{\text{base}}+R(u,v)$                       |
| **Evaluation** | Metrics                                 | Scalars         | Panel L2 (cm), stitch accuracy, perceptual fidelity (LPIPS)                       |



<br>

**Overview**

- We demonstrate that, under high-performance hardware (H200) conditions, constructing a geometry-aligned discrete hash field is the optimal solution for handling high-frequency garment details compared to stacking deep MLPs.
- By defining the diffusion process `within the residual hash space`, we achieve 📍 `per-point refinement cost` does not scale with geometric complexity for complex nonlinear folds.
- `three_two_three` (bijective constraint): Equivalent to `assert hash_map.size() == unique_points.size()`. A low weight for this constraint indicates severe hash collisions, meaning multiple 3D points map to the same UV, resulting in a blurry rendering.
- `cluster` (clustering constraint): Equivalent to `assert is_adjacent(p1, p2) == is_adjacent(hash(p1), hash(p2))`. It ensures that spatially adjacent points are also close together in the hash bucket, preventing the rendering from becoming fragmented.


```
model:
  num_charts: 8
  use_vertex_duplication: true *https://github.com/ruiqixu37/Nuvo
-> then for the diffusion process -> It's just about tweaking details in a function space where the geometry is already aligned.
  hidden_dim: 256
  num_layers: 8
```

**Assign Hash to your Nvidia sponsored renders**
```
SELECT residual
FROM garment_surface
WHERE uv = (u, v);
```

- Nuvo is Data Indexer
- Diffusion is Error Corrector
- H200 is Hardware Accelerator

Can also add a **"stitching graph consistency check"**, which is essentially a `Union-Find problem in graph theory`, ensuring that the hash values ​​at the stitching points of two pieces eventually converge to the same value.


- By discretize the 3D space：
  - Hash function is Nuvo. It maps $P(x,y,z)$ to a specific (chart_id, u, v).
  - `Key` is these UV coordinates.
  - `Value` is the corresponding geometric residual $R$.
  - The `beauty` lies in avoiding all the pitfalls of high-frequency signal fitting, because the hash table itself can perfectly store high-frequency information, requiring `no` Fourier transform patching.
  - In academia, this is called `Discrete Latent Space Alignment`.
 
📍 **Notes** - Once it becomes discrete geometry, you don't have to work on it anymore, all been solved by a large `Hash Table` -> let's move on to Continuous Geometry / Signal Processing in [Liver predictor](https://github.com/yiruyang2025/Liver_Predictor)


```
python train_demo.py --config configs/demo.yaml --sample_idx 5

Losses: Diffusion (MSE) + LPIPS
- diffusion_weight: 1.0
- lpips_weight: 0.5
- l1_weight: 0.5 (metric only)
```

<br>

**Some Over-smooth Outcome**


<p align="left">
  <img src="https://yiruyang2025.github.io/assets/img/project3_4.png" alt="Project 1 Visualization" width="75%">
</p>



<p align="left">
  <img src="https://yiruyang2025.github.io/assets/img/project3_5.png" alt="Project 1 Visualization" width="75%">
</p>


- In LeetCode, `a coordinate point` is simply (x, y), the logic is very clear. However, in current computer graphics papers, the goal is to enable neural networks to optimize this point, The truth: This is essentially because `MLPs (Neural Networks) are too inefficient / un-flexible`, they can't remember high-frequency details. So, people manually add "external storage" to them.

- In LeetCode, your opponent is **computational complexity**, at SIGGRAPH, your opponent is **entropy**.
  - The hash-value mindset you `like` (for example, Instant-NGP) is essentially a classic *programmer’s counterattack*. It no longer tries to understand complex geometric continuity. Instead, it says: `I don’t care how complicated your surface is—I’ll just chop you up in hash space and look you up in a table`
  - This approach—trading space for time, and lookup tables for computation—may have little aesthetic appeal in the eyes of mathematicians, `but on an H200, it runs the fastest`

<br>

**Modern Hardware-aware Algorithm**

- In the CPU era, algorithms aimed to reduce instruction cycles;
- In the GPU era, algorithms aim to achieve memory coalescing and avoid branch prediction.


<br>

## The fundamental limitations of monocular (2D) video input

| Problem                     | Effect                                                                     |
| --------------------------- | -------------------------------------------------------------------------- |
| **Limited viewpoint**       | Depth, thickness, and surface normal directions are all ambiguous.         |
| **Lighting variation**      | Fur reflection, translucency, and self-occlusion make appearance unstable. |
| **Strong deformation**      | Animal skin and fur exhibit local non-rigid motion.                        |
| **No temporal supervision** | Hard to maintain frame-to-frame consistency.                               |


<br>

## Vector Field, Probability Flow, and the Continuity Equation in Diffusion / Flow

| Component                              | Mathematical Form                                                                        | What It Represents                                                                   | First Introduced / Formalized                                            | Why It Was Introduced                                                   | Original Application Domain                |
| -------------------------------------- | ---------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------ | ------------------------------------------------------------------------ | ----------------------------------------------------------------------- | ------------------------------------------ |
| **Vector field**                       | $u(x,t)$                                                                                 | Local infinitesimal rule specifying how a state changes at position $x$ and time $t$ | Classical differential geometry (19th century); formalized in ODE theory | To describe continuous-time dynamical systems via local evolution rules | Mechanics, fluid dynamics                  |
| **Probability density**                | $p(x,t)$                                                                                 | Distribution of samples over state space at time $t$                                 | Laplace, Gauss (18th–19th century probability theory)                    | To describe uncertainty and population-level behavior                   | Statistical physics                        |
| **Probability flow**                   | $p(x,t),u(x,t)$                                                                          | Flux of probability mass through space                                               | Boltzmann, Gibbs (late 19th century)                                     | To model transport of mass or particles                                 | Kinetic theory                             |
| **Divergence operator**                | $\nabla\cdot(\cdot)$                                                                     | Net outflow vs inflow at a point                                                     | Gauss, Green (19th century analysis)                                     | To quantify conservation laws                                           | Electromagnetism, fluid flow               |
| **Continuity equation**                | $\displaystyle \frac{\partial p(x,t)}{\partial t} = -\nabla\cdot\big(p(x,t),u(x,t)\big)$ | Conservation law governing how probability density evolves                           | Liouville (1838); later generalized in physics                           | To enforce mass/probability conservation under dynamics                 | Hamiltonian systems, statistical mechanics |
| **Interpretation in diffusion / flow** | same equation                                                                            | Distribution-level consequence of many samples following the same vector field       | Adopted in modern form by Villani, Ambrosio; used in ML after 2019       | To connect sample dynamics with density evolution                       | Normalizing flows, diffusion models        |
| **Key conceptual role**                | —                                                                                        | Vector field generates the time evolution of the entire distribution                 | Mathematical fact, not a modeling choice                                 | Enables continuous-time generative modeling                             | Flow models, continuous diffusion          |



<br>



## In a Hardware system, there are 3 essential layers

| Layer                              | Name                                                | Responsibility                                                                                  |
| ---------------------------------- | --------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| **Application Layer (App Layer)**  | Unreal / Unity / Blender / Games / Research Demos   | Handles rendering, logic, and user interaction.                                                 |
| **Runtime API Layer (Middleware)** | OpenVR / OpenXR / Oculus SDK / WindowsMR            | Provides VR hardware abstraction, pose tracking, frame synchronization, and display management. |
| **Device Layer (Hardware Layer)**  | HTC Vive / Valve Index / Meta Quest / Varjo / Pimax | Represents the physical headset, controllers, and tracking sensors.                             |


<br>

## User Feedback - If Dizzy


| Layer Frequency | Sensor / System                     | Primary Function                                     | Role in Tracking Pipeline                                                           |
| --------------- | ----------------------------------- | ---------------------------------------------------- | ----------------------------------------------------------------------------------- |
| High-frequency  | **IMU (gyroscope + accelerometer)** | Real-time orientation estimation and pose prediction | Provides low-latency motion updates and enables motion-to-photon latency reduction  |
| Mid-frequency   | **Photodiodes**                     | Receive sweeping laser signals from base stations    | Supplies angular constraints for pose correction                                    |
| Low-frequency   | **Lighthouse base stations**        | Provide absolute spatial reference                   | Ensures global consistency and long-term drift correction                           |
| Fusion layer    | **Sensor fusion algorithms**        | Produce stable 6DoF pose estimates                   | Combines inertial prediction with optical correction into a coherent state estimate |


<br>


## The Role of DP (DisplayPort)

| Component                   | Function                     | Description                                                                                             |
| --------------------------- | ---------------------------- | ------------------------------------------------------------------------------------------------------- |
| **DP (DisplayPort)**        | Physical video interface     | Transmits rendered frames from the GPU to the VR headset’s display.                                     |
| **Bandwidth**               | High data transfer rate      | Supports dual-eye high-resolution output (e.g., 2K–4K per eye).                                         |
| **Refresh Rate**            | Frame delivery speed         | Enables 90–120 Hz display updates to prevent motion sickness.                                           |
| **Latency**                 | Image update timing          | Ensures real-time synchronization between head movement and displayed image.                            |
| **Relation to Runtime API** | Software vs. hardware bridge | The Runtime API manages what is rendered; DisplayPort delivers it physically to the headset screen. |


<br>


## Time Alignment

- Without an internet connection, there is no external time source (such as NTP or PTP). Therefore, all components must share a master clock, and every process synchronizes around it
- What happens if your master clock is the system clock
  - You can run completely offline
  - You can maintain full timestamp consistency between Unreal, the EXE, and the HMD as long as every process refers to the same local system time or the same bridge-provided clock derived from it



<br>



## The essence of `NTP`

- To make sure that every computer (or process) in a network agrees on the same notion of time

| Component            | Role                                                                  |
| -------------------- | --------------------------------------------------------------------- |
| **NTP Server**       | Maintains accurate time (usually synchronized to GPS or atomic clock) |
| **NTP Client**       | Periodically queries the server to adjust its local clock             |
| **Network Protocol** | UDP (port 123), exchanging timestamps to compute delay and offset     |

<br>



## Volumetric Representation vs. NeRF vs. Gaussian Splatting


| **Property**              | **Volumetric Representation**              | **NeRF**                                                   | **Gaussian Splatting**                               |
| ------------------------- | ------------------------------------------ | ---------------------------------------------------------- | ---------------------------------------------------- |
| **Function form**         | Explicit voxel field $V(\mathbf{x})$       | Implicit neural field $f_{\theta}(\mathbf{x}, \mathbf{d})$ | Explicit Gaussian kernels ${G_i(\mathbf{x})}$        |
| **Rendering**             | Numerical volume integration               | Neural volume integration                                  | Analytical Gaussian accumulation                     |
| **Continuity**            | Piecewise (via interpolation)              | Continuous (via MLP)                                       | Continuous (via Gaussian kernel)                     |
| **Optimization goal**     | Photometric consistency                    | Photometric consistency                                    | Photometric consistency                              |
| **Storage**               | Dense voxel grid                           | Network weights                                            | Sparse Gaussian parameters                           |
| **Computation**           | Heavy $\mathcal{O}(V^3)$                   | Heavy $\mathcal{O}(R \times S)$                            | Lightweight $\mathcal{O}(N)$                         |
| **Best suited for**       | Static volumetric scenes                   | High-quality static fields                                 | Real-time dynamic 3D/4D scenes                       |
| **Mathematical relation** | Numerical approximation of volume integral | Neural approximation of the same integral                  | Analytical kernel approximation of the same integral |


<br>



## Implicit vs Explicit Representations

| **Concept** | **Implicit Representation** | **Explicit Representation** |
|--------------|-----------------------------|------------------------------|
| **Definition** | Geometry is represented by a *continuous function* (e.g., NeRF, SDF) that implicitly defines occupancy, density, or color at any 3D location. | Geometry is represented by *explicit surface elements*, such as vertices, faces, and normals in a mesh. |
| **Typical Form** | \( f_\theta(x, t) \rightarrow \{\sigma, c\} \) — density and color fields | \( (V, F) \) — mesh vertices and faces, deformed by pose parameters |
| **Key Property** | Continuous, topology-free, differentiable | Discrete, topology-fixed, physically interpretable |
| **Advantages** | ① Unconstrained topology  <br>② Smooth and differentiable  <br>③ Naturally fits neural fields | ① Precise control over surface  <br>② Compatible with animation and rendering  <br>③ Supports texture mapping and fur direction |
| **Drawbacks** | ① Ambiguous topology  <br>② Hard to extract exact normals  <br>③ Computationally heavy for rendering | ① Limited to known topology (e.g., SMAL)  <br>② Difficult to generalize across species |
| **Example** | **BANMo** – implicit volumetric field + neural blend skinning | **Animal Avatars** – explicit SMAL mesh + CSE pixel alignment |



<br>



## Geometric Shape Modeling


| Year     | Paper                                                                                                                | Type                 | Description                                                                                 | Core Mathematical Field                                |
| -------- | -------------------------------------------------------------------------------------------------------------------- | -------------------- | ------------------------------------------------------------------------------------------- | ------------------------------------------------------ |
| **2025** | **TetWeave: Isosurface Extraction using On-The-Fly Delaunay Tetrahedral Grids for Gradient-Based Mesh Optimization** | 🧱 + ⚙️ Hybrid       | Simultaneous mesh generation and optimization via differentiable Delaunay grids.            | **Computational Geometry + Variational Optimization**  |
| **2025** | **Reconfigurable Hinged Kirigami Tessellations**                                                                     | 🧱 Mesh Generation   | Generates deployable curved surfaces through geometric cutting and kinematic tiling.        | **Discrete Differential Geometry**                     |
| **2025** | **Computational Modeling of Gothic Microarchitecture**                                                               | ⚙️ Mesh Optimization | Topological and shape optimization of architectural microstructures.                        | **Topology Optimization**                              |
| **2025** | **Higher Order Continuity for Smooth As-Rigid-As-Possible Shape Modeling**                                           | ⚙️ Mesh Optimization | Extends ARAP formulation with higher-order geometric continuity.                            | **Differential Geometry + PDE Optimization**           |
| **2024** | **Mesh Parameterization Meets Intrinsic Triangulations**                                                             | ⚙️ Mesh Optimization | Improves mesh parameterization and smoothness via intrinsic metrics.                        | **Riemannian Geometry + Discrete Optimization**        |
| **2024** | **Fabric Tessellation: Realizing Freeform Surfaces by Smocking**                                                     | 🧱 Mesh Generation   | Generates freeform surfaces via geometric fabric tessellation design.                       | **Geometric Modeling + Computational Topology**        |
| **2024** | **SENS: Part-Aware Sketch-based Implicit Neural Shape Modeling**                                                     | 🧱 Mesh Generation   | Generates 3D meshes from sketches using implicit neural fields.                             | **Implicit Geometry + Neural Representation Learning** |
| **2022** | **Dev2PQ: Planar Quadrilateral Strip Remeshing of Developable Surfaces**                                             | ⚙️ Mesh Optimization | Remeshes curved surfaces into planar quadrilateral strips under developability constraints. | **Differential Geometry + Discrete Optimization**      |
| **2022** | **Iso-Points: Optimizing Neural Implicit Surfaces with Hybrid Representations**                                      | ⚗️ Hybrid            | Optimizes implicit fields into explicit renderable meshes.                                  | **Differentiable Geometry + Variational Optimization** |
| **2021** | **Developable Approximation via Gauss Image Thinning**                                                               | ⚙️ Mesh Optimization | Approximates surfaces toward developability constraints.                                    | **Differential Geometry + Optimization**               |
| **2020** | **Properties of Laplace Operators for Tetrahedral Meshes**                                                           | ⚙️ Mesh Optimization | Studies spectral and geometric properties of Laplace operators in tetrahedral meshes.       | **Spectral Geometry + Linear Algebra**                 |
| **2015** | **Instant Field-Aligned Meshes**                                                                                     | 🧱 Mesh Generation   | Generates meshes aligned with direction fields in real time.                                | **Vector Field Theory + Discrete Geometry**            |
| **2014** | **Pattern-Based Quadrangulation for N-Sided Patches**                                                                | 🧱 Mesh Generation   | Creates quadrilateral meshes using pattern-based surface decomposition.                     | **Combinatorial Geometry + Topology**                  |
| **2013** | **Sketch-Based Generation and Editing of Quad Meshes**                                                               | 🧱 Mesh Generation   | Produces and edits quad meshes directly from sketch input.                                  | **Geometric Modeling + Computational Geometry**        |
| **2013** | **Consistent Volumetric Discretizations Inside Self-Intersecting Surfaces**                                          | 🧱 Mesh Generation   | Constructs consistent volumetric meshes inside complex self-intersecting surfaces.          | **Numerical Geometry + Discretization Theory**         |
| **2013** | **Locally Injective Mappings**                                                                                       | ⚙️ Mesh Optimization | Optimizes parameterizations to avoid fold-overs and self-intersections.                     | **Nonlinear Optimization + Differential Geometry**     |
| **2007** | **As-Rigid-As-Possible Surface Modeling (ARAP)**                                                                     | ⚙️ Mesh Optimization | Foundational method for geometric shape deformation and energy minimization.                | **Variational Optimization + Linear Algebra**          |
| **2006** | **Laplacian Mesh Optimization**                                                                                      | ⚙️ Mesh Optimization | Classical Laplacian-based geometric smoothing and reconstruction.                           | **Discrete Differential Geometry + Linear Systems**    |
| **2004** | **Laplacian Surface Editing**                                                                                        | ⚙️ Mesh Optimization | Seminal differentiable deformation method for surface editing.                              | **Variational Calculus + Linear Algebra**              |
| **2003** | **High-Pass Quantization for Mesh Encoding**                                                                         | ⚙️ Mesh Optimization | Optimizes geometric compression via high-pass component quantization.                       | **Signal Processing on Manifolds**                     |
| **2002** | **Bounded-Distortion Piecewise Mesh Parameterization**                                                               | ⚙️ Mesh Optimization | Minimizes distortion under bounded mapping constraints.                                     | **Conformal Geometry + Convex Optimization**           |


<br><br><br><br><br><br><br><br><br><br>



## References 1 

- [2025 - Find Any Part in 3D](https://iccv.thecvf.com/virtual/2025/poster/98)
- [2024 - DressCode: Autoregressively Sewing and Generating Garments from TextGuidance](https://www.youtube.com/watch?v=ofFyJBKL-Qg)
- [📍 2025 - AIpparel: A Multimodal Foundation Model for Digital Garments](https://igl.ethz.ch/projects/aipparel/aipparel_paper.pdf)

<br>

## References 2


- [2026 - Need for Speed: Zero-Shot Depth Completion with Single-Step Diffusion](https://dtu-pas.github.io/marigold-ssd/)



<br><br><br>
