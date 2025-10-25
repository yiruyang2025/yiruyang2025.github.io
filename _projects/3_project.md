---
layout: page
title: 2025 - Thesis - 4d Animal Avatars from Videos
description: CVG
img: assets/img/4.jpg
importance: 3
category: work
related_publications: true
---

<br>


## Some Cute Things

- [Middlebury “dino” data set](https://vision.middlebury.edu/mview/?utm_source=chatgpt.com)



<br>



## Computational Robotics - Medical / Space

- [2025 - Visual Perception Engine](https://github.com/nasa-jpl/visual-perception-engine)
- [2025 - Visual Perception Engine: Fast and Flexible Multi-Head Inference for Robotic Vision Tasks](https://arxiv.org/abs/2508.11584)
- [📍 2025 - Space Science and Technology](https://eaps.ethz.ch/en/research/institutes/geophysics/space-science-technology.html)

<br>

- [Computational Robotics Lab](https://crl.ethz.ch/)
- [Automatic Control Lab](https://control.ee.ethz.ch/)
- [Autonomous Systems Lab](https://www.iris.ethz.ch/the-institute/autonomous-systems-lab.html)
- [Terensis - The next gen agriculture intelligence platform](https://www.terensis.io/)
- [Soft Robotics](https://mitpress.mit.edu/9780262049740/soft-robotics/)
- [Aria Data Provider](https://github.com/facebookresearch/projectaria_tools)


<br>


## Geometric Shape Modeling

- [📍 2025 - TetWeave: Isosurface Extraction using On-The-Fly Delaunay Tetrahedral Grids for Gradient-Based Mesh Optimization](https://igl.ethz.ch/projects/tetweave/) - Multi-view 3d reconstruction, geometric texture generation, gradient-based mesh optimization, Isosurface Representation, [📍 Fabricaible](https://www.fabricaible.com/)


<p align="left">
  <img src="https://yiruyang2025.github.io/assets/img/project3_1.jpg" alt="Project 1 Visualization" width="75%">
</p>

<br>

```
Marching Tetrahedra on Delaunay Triangulation
(isosurface extraction on arbitrary point clouds)
                 ↓
Directional Signed Distance
(spherical harmonics; edge-aware surface accuracy)
                 ↓
Adaptive Tetrahedral Grid
(resampling where error is high; grid fits unknown surfaces)
                 ↓
Regularization Terms
(fairness + ODT loss; improve mesh quality, avoid slivers)
```

<br>



## Mesh Generations


[📍 2025 - VertexRegen: Mesh Generation with Continuous Level of Detail](https://vertexregen.github.io/)


  - Controllable, ready-to-use mesh generation
  - Use a `Coarse Mesh` to estimate the global resolution initially, then gradually refine it to the local resolution


[1996 - Microsoft Research - Progressive Meshes](https://hhoppe.com/pm.pdf)

  - Training data: Use edge collapse to compress the high-precision mesh into different levels

  - Generation process: Use a generative model to learn the inverse operation—vertex splitting

  - Thus, generation proceeds from coarse to fine, yielding a complete mesh at each step


[2011 - High-quality passive facial performance capture using anchor frames](https://studios.disneyresearch.com/wp-content/uploads/2019/03/High-Quality-Passive-Facial-Performance-Capture-using-Anchor-Frames-1.pdf)


<br>


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


<br>


## References


- [2025 - TetWeave: Isosurface Extraction using On-The-Fly Delaunay Tetrahedral Grids](https://dl.acm.org/doi/abs/10.1145/3730851)
- [2024 - SENS: Part-Aware Sketch-Based Implicit Neural Shape Modeling](https://onlinelibrary.wiley.com/doi/full/10.1111/cgf.15015)
- [2022 - Enhancing computational fluid dynamics with machine learning](https://www.nature.com/articles/s43588-022-00264-7)
- [2025 - GLIMPSE: Generalized Locality for Scalable and Robust CT](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=11018464)
- [2024 - WaveBench: Benchmarking Data-driven Solvers for Linear Wave Propagation PDEs](https://hal.science/hal-04503454/)


<br>


## References / Reading List - Shape Modeling

- [Polyscope - Toolkit for demos](https://polyscope.run/py/)
- [SIGGRAPH 2025](https://s2025.conference-schedule.org/session/?sess=sess140)
- [2024 - DMesh: A Differentiable Mesh Representation](https://sonsang.github.io/dmesh-project/)
- [2025 - Piecewise Ruled Approximation for Freeform Mesh Surfaces](https://dl.acm.org/doi/abs/10.1145/3730866)
- [2025 - NeuralSVG: An Implicit Representation for Text-to-Vector Generation](https://sagipolaczek.github.io/NeuralSVG/) - logo Gen

<br>

- [UK Biobank](https://www.ukbiobank.ac.uk/)
- [SCAI](https://scai.ethz.ch/)
- [2025 - MC-MED](https://github.com/dkimlab/MCMED)
- Toolkit - [2025 - Brainchop: In-browser 3D MRI rendering and segmentation](https://github.com/neuroneural/brainchop)

<br>


## End-to-End Real-World Data Flow

```
Hospital CT / MRI
        ↓

DICOM (raw slices + metadata)
        ↓ Segmentation + Reconstruction

Surface Mesh (OBJ / STL / PLY / VTK)
        ↓ Projection

2D SVG (interactive) / PNG (static)
        ↓ Annotation

Surgeon marks points / lines on SVG
        ↓ Mapping

Handles mapped back to 3D mesh
        ↓ Deformation

FastAPI /deform → ARAP deformation applied
        ↓ Visualization

Updated 3D mesh rendered in LiverViewer (three.js)
        ↓ Export

Surgical plan → PDF / PNG / QR for clinical workflow
```

<br>


<br><br><br>
