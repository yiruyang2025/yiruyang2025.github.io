---
layout: page
title: 2025 - Thesis
description: Aria glass Gen-1, Dataset, Robots Navigation
img: assets/img/4.jpg
importance: 3
category: work
related_publications: true
---

<br><br>


Dataset Labeling for [2020 - Aria Glass Hardware](https://facebookresearch.github.io/projectaria_tools/docs/tech_spec/hardware_spec)

- [Aria Data Provider](https://github.com/facebookresearch/projectaria_tools)

Egocentric Vision, Intent Prediction, Anticipation, Multimodal Learning

[📍 HOT3D - 2025](https://facebookresearch.github.io/hot3d/)

[2020 - LEMMA](https://arxiv.org/pdf/2007.15781)


<br><br>


**Related Coursework / Paper**

- Learnt background knowledge, feel free to ask anything in the link

- [2025 - TetWeave](https://igl.ethz.ch/projects/tetweave/)

- ([Neuromorphic Engineering I](https://sites.google.com/view/ne-courses-ini/home?id=start)) - Giacomo Indiveri, Shih-Chii Liu, Melika Payvand

- ([Math Foundations for Computer Graphics and Vision - SS 22](https://cgl.ethz.ch/teaching/mathfound22/notes.php))


<br><br>



## 📍 Neuromorphic Engineering

<br>

- [Institute of Neuroinformatics](https://www.ini.uzh.ch/en/studies/courses.html) - UZH + ETHz




<br><br>

## Geometric Shape Modeling

<br>

[📍 2025 - TetWeave: Isosurface Extraction using On-The-Fly Delaunay Tetrahedral Grids for Gradient-Based Mesh Optimization](https://igl.ethz.ch/projects/tetweave/) - Multi-view 3d reconstruction, geometric texture generation, gradient-based mesh optimization, Isosurface Representation, [📍 Fabricaible](https://www.fabricaible.com/)

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


<br><br><br>



## (Mesh Generations)

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


## 4d Cardiac Modeling

<br>



[2024 - Improving Out-of-Distribution Generalization in Graphs via Hierarchical Semantic Environments](https://openaccess.thecvf.com/content/CVPR2024/papers/Piao_Improving_Out-of-Distribution_Generalization_in_Graphs_via_Hierarchical_Semantic_Environments_CVPR_2024_paper.pdf)

<br>


MRI

DTI

fMRI / functional Ultrasound, fUS

tractography

Mesh-VAE

Implicit Geometry - NeRF/SDF


<br>

| Technique           | Role in 4D Shape Modeling 🫀                                   | Output Type               |
| ------------------- | -------------------------------------------------------------- | -------------------------- |
| **MRI**            | High-resolution anatomy & cardiac cycle dynamics               | Volumes                    |
| **DTI**          | Maps myocardial fiber orientation                              | Fiber fields               |
| **fMRI / fUS**     | Functional imaging of blood flow & hemodynamics                | Functional volumes         |
| **Tractography**  | Reconstructs cardiac fiber pathways from DTI                   | Fiber tracts               |
| **Mesh-VAE**     | Learns latent representations of dynamic heart meshes          | Mesh embeddings            |
| **NeRF / SDF**    | Implicit geometry for smooth continuous 4D reconstructions     | Implicit surfaces          |
| **ML for CFD**    | AI-driven simulation of blood flow & pressure in beating heart | Flow fields / hemodynamics |



<br><br><br><br><br>





## References

<br>


**1. 3d Shape Modeling**

<br>


[2025 - TetWeave: Isosurface Extraction using On-The-Fly Delaunay Tetrahedral Grids](https://dl.acm.org/doi/abs/10.1145/3730851)


[2024 - SENS: Part-Aware Sketch-Based Implicit Neural Shape Modeling](https://onlinelibrary.wiley.com/doi/full/10.1111/cgf.15015)


<br><br>


**2. Computational Fluid Dynamics + PDE for Modeling**

<br>

[2022 - Enhancing computational fluid dynamics with machine learning](https://www.nature.com/articles/s43588-022-00264-7)


[2025 - GLIMPSE: Generalized Locality for Scalable and Robust CT](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=11018464)


[2024 - WaveBench: Benchmarking Data-driven Solvers for Linear Wave Propagation PDEs](https://hal.science/hal-04503454/)




<br><br><br><br>


## References 1 - 4d Scene Understanding

<br>







<br><br><br><br><br><br><br><br><br><br><br>


## References 2 / Reading List - Shape Modeling

<br>

[Polyscope - Toolkit for demos](https://polyscope.run/py/)

<br>

[SIGGRAPH 2025](https://s2025.conference-schedule.org/session/?sess=sess140)


[2024 - DMesh: A Differentiable Mesh Representation](https://sonsang.github.io/dmesh-project/)

[2025 - Piecewise Ruled Approximation for Freeform Mesh Surfaces](https://dl.acm.org/doi/abs/10.1145/3730866)


[2025 - NeuralSVG: An Implicit Representation for Text-to-Vector Generation](https://sagipolaczek.github.io/NeuralSVG/) - logo Gen



<br><br><br>
