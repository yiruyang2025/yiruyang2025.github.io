---
layout: page
title: 2025 - Dataset
description: 4d Shape Modeling, Robots Navigation
img: assets/img/4.jpg
importance: 4
category: work
related_publications: true
---

<br><br>


Dataset Labeling for [2020 - Aria Glass Hardware](https://facebookresearch.github.io/projectaria_tools/docs/tech_spec/hardware_spec)

Egocentric Vision, Intent Prediction, Anticipation, Multimodal Learning

[HOT3D - 2025](https://facebookresearch.github.io/hot3d/)


<br><br>




## Mesh Generations

<br>

[📍 2025 - VertexRegen: Mesh Generation with Continuous Level of Detail](https://vertexregen.github.io/)


  - Controllable, ready-to-use mesh generation
  - Use a `Coarse Mesh` to estimate the global resolution initially, then gradually refine it to the local resolution

<br>

[1996 - Microsoft Research - Progressive Meshes](https://hhoppe.com/pm.pdf)

  - Training data: Use edge collapse to compress the high-precision mesh into different levels

  - Generation process: Use a generative model to learn the inverse operation—vertex splitting

  - Thus, generation proceeds from coarse to fine, yielding a complete mesh at each step

<br>

[2011 - High-quality passive facial performance capture using anchor frames](https://studios.disneyresearch.com/wp-content/uploads/2019/03/High-Quality-Passive-Facial-Performance-Capture-using-Anchor-Frames-1.pdf)


<br><br>



## Shape Modeling

<br>

[📍 2025 - TetWeave: Isosurface Extraction using On-The-Fly Delaunay Tetrahedral Grids for Gradient-Based Mesh Optimization](https://igl.ethz.ch/projects/tetweave/) - Multi-view 3d reconstruction, geometric texture generation, gradient-based mesh optimization, Isosurface Representation

<br>

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


<br><br><br><br><br><br>



## Bio / Medical - 4d, Modeling / Instant Segmentation

<br>

[2024 - Improving Out-of-Distribution Generalization in Graphs via Hierarchical Semantic Environments](https://openaccess.thecvf.com/content/CVPR2024/papers/Piao_Improving_Out-of-Distribution_Generalization_in_Graphs_via_Hierarchical_Semantic_Environments_CVPR_2024_paper.pdf)



<br><br><br><br><br><br>





<br><br>


## CUT3R

<br>


Navigation-level Scene Semantics

<br>

```
Sparse RGB / Depth / LiDAR (stream)
   ↓
Surface Fitting Module (Point cloud → implicit SDF)
   ↓
Continuous LOD generation
   ↓
4D Human Profile (geometry + temporal motion)
   ↓
Navigation / Control Integration
   - dynamic path planning
   - human-aware motion prediction
```




<br><br><br>

## Topics

<br>

## 1. On-device Realtime Machine Perception (MP) Signals

<br>

Visual Inertial Odometry (VIO)

  - 6 Degrees of freedom (6DOF) within a spatial frame of reference using Visual Inertial Odometry (VIO)
  - This allows for seamless navigation and mapping of the environment

<br><br>

## 2. Eye Tracking

<br>

  - Including: gaze per eye, vergence point, blink detection, pupil center estimation, pupil diameter, corneal center, etc.
  - A deeper understanding of the wearer’s visual attention and intentions

<br><br>

## 3. Hand Tracking

<br>

  - In 3D space

<br><br><br>

## References

<br>

[2020 - LEMMA: A Multi-view Dataset for Learning Multi-agent Multi-task Activities](https://link.springer.com/chapter/10.1007/978-3-030-58574-7_46)


<br><br>
