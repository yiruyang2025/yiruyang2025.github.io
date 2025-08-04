---
layout: post
title: 3D Vision Foundation Models - 25
date: 2025-08-01
description: ⛺️
categories: Research
thumbnail: assets/img/9.jpg
images:
  lightbox2: true
  photoswipe: true
  spotlight: true
  venobox: true
---

<br>

## Topics

<br>

`Artificial Neural Networks`

<br>

[Colah's Blog](https://colah.github.io/)


<br><br>

`3D Vision & Multi-modality x Foundation Models`

<br>

## References

<br><br>

[2025 - FAM-HRI: Foundation-Model Assisted Multi-Modal Human-Robot Interaction Combining Gaze and Speech](https://arxiv.org/pdf/2503.16492)




<br><br><br>




| Model                          | Input Data Type   | Domain     | Extendable to 3D?                                                     |
| ------------------------------ | ----------------- | ---------- | --------------------------------------------------------------------- |
| `DINOv2`                     | 2D image          | 2D CV      | Yes — Can serve as a visual token encoder for NeRF or 3D Transformers |
| **Grounding DINO**             | 2D image + text   | 2D CV      | No — Not natively designed for 3D bounding boxes                      |
| `SAM2`(Segment Anything 2)  | 2D image          | 2D CV      | Yes — Extendable to video segmentation and can integrate depth        |
| Segment Anything 3D | Point cloud + RGB | 3D Vision  | Yes — Native 3D segmentation model                                    |
| `OpenScene / OpenMask3D`     | RGB + depth       | 3D + 2D CV | Yes — Multimodal cross-domain visual perception                       |


<br><br>


| Application Task                              | Model Type          | Recommended Models                                            |
| --------------------------------------------- | ------------------- | ------------------------------------------------------------- |
| `Eye Gaze + Image Analysis (e.g., FAM-HRI)`     | **2D CV**           | DINOv2 / SAM2 / Grounding DINO                                |
| Pick-and-Place Robot Manipulation             | **2D → 3D Hybrid**  | CV-based 2D mask projected into 3D (e.g., SAM2 + RGB-D depth) |
| 3D Reconstruction / Point Cloud Segmentation  | **3DV**             | PointNeXt, Point-BERT, OpenScene                              |
| `AR Glasses + Real-Time Semantic Understanding` | **Primarily 2D CV** | SAM2 + DINOv2 + GPT (e.g., FAM-HRI stack)                     |
| SLAM / Robot Navigation                       | **Strictly 3DV**    | ORB-SLAM3, MapTR, NeRF, MVSNet                                |



<br><br><br><br>


## References

<br><br>




**1. Collatz Conjecture / 3n + 1 problem / hailstone problem**

<br>

[1950 - Lothar Collatz “Über die Differenzengleichung xₙ₊₁ = aₙ xₙ + bₙ”, Mathematische Nachrichten, Bd. 3 (1950).](https://www.digizeitschriften.de/search?filter%5BZeitschriften%5D%5B1%5D=245319514%7Clog1&filter%5BObjekttyp%5D%5B1%5D=volume)

[2003 - The 3x+1 problem: An annotated bibliography (1963--1999) (sorted by author)](https://arxiv.org/abs/math/0309224)

[2017 - Collatz Conjecture in Color - Numberphile](https://www.youtube.com/watch?v=LqKpkdRRLZw)

<br><br>

**2. Erwin: A Tree-based Hierarchical Transformer for Large-scale Physical Systems [ICML'25]**

[repo](https://github.com/maxxxzdn/erwin)




<br><br>

**3. Self-Distillation Loss + Diffusion Loss**

```
Representation Robustness  ←─── TRADE‑OFF ───→  Training Efficiency & Reuse
          ▲                                         ▲
          │                                         │
  Self‑Distillation Loss                 Pretrained Priors (Stable Diffusion, DINOv2)
  • Enforces invariance across           • Inject rich 2D visual semantics
    views/augmentations                  • Accelerate convergence, improve transfer
  • Stabilizes training dynamics
          │                                         │
          ▼                                         ▼
                  Diffusion Loss (Denoising Objective)
        • Learn to reverse a noise process on 3D data (e.g., point clouds)
        • Yields generative and noise‑robust latent features
          │                                               │
          └──────────── PROPOSED INTEGRATION ─────────────┘
                               │
                               ▼
                 Unified, High‑Quality 3D Latent Space
     → Better downstream performance (classification, segmentation, reconstruction)
     → Strong generalization from 2D/3D synergy
```


<br><br>

**3**

<br><br>

**4**

<br><br>

**5**



<br><br><br><br>




`Articles`

<br>

[2024 - nGPT: Normalized Transformer with Representation Learning on the Hypersphere](https://arxiv.org/abs/2410.01131)

[2021 - Multimodal Neurons in Artificial NNs](https://distill.pub/2021/multimodal-neurons/)

[2018 - The Building Blocks of Interpretability](https://distill.pub/2018/building-blocks/)

[2008 - Kernel methods in machine learning](https://projecteuclid.org/journals/annals-of-statistics/volume-36/issue-3/Kernel-methods-in-machine-learning/10.1214/009053607000000677.full)



<br><br><br>






## References


**1. Contrastive Loss**

[1993 NIPS - Signature Verification using a “Siamese” Time Delay Neural Network](https://proceedings.neurips.cc/paper/1993/hash/288cc0ff022877bd3df94bc9360b9c5d-Abstract.html)

[2006 CVPR - Dimensionality Reduction by Learning an Invariant Mapping](https://ieeexplore.ieee.org/document/1640964)




**Implementations**

[CLIP]  
[DALL·E 3]


<br><br>


**2. Fusion**


[2011 - Multimodal Deep Learning](https://d1wqtxts1xzle7.cloudfront.net/74090107/icml11-MultimodalDeepLearning-libre.pdf?1635868597=&response-content-disposition=inline%3B+filename%3DMultimodal_deep_learning.pdf&Expires=1752407377&Signature=Oq6xDECIppt4tyqVPOPbxUz2Tp6hPlMk7oSIG4~iwiJ6pONeoF6RzJgaLcquZ14DamAru-WXhiwiuOyeRaQtbzcohkXJBlxW1MEyJH7vinRGVk8otM2Arv0j00DWw3jv~lcZ1m5VkMhPMNZC69dxrzKYF94I8TsLiQZhuMeJ9K0v1fC6yy5vxpo2y0TB0Xy1AEc~YX2vLqEAEWYmJCdhi16UH1v0T38etc12g1I-olQvpcevbh-IW9jwpxzdnLbJgXh-~Fs2kKr31G-q~1XsDrK302ywvQicxDKDxDmFg-xKLXrCrYfkwwZ4z~wQDaCmFDJrUvCCkrvFgbJk4hT9sQ__&Key-Pair-Id=APKAJLOHF5GGSLRBV4ZA)


[2019 - ViLBERT: Pretraining Task-Agnostic Visiolinguistic Representations](https://arxiv.org/abs/1908.02265)


[2019 - UNITER: UNiversal Image-TExt Representation Learning](https://arxiv.org/abs/1909.11740)


<br><br><br><br>



`Study Notes`

<br>

**nGPT vs. Mamba**

```
Deep Learning Training Challenge
─────────────────────────────────────────────────────────────────
Training Efficiency (Steps)  ←──── TRADEOFF ────→  Architecture Complexity
        │                                                      │
        ▼                                                      ▼
Simple architectures:                              Complex architectures:
Fast convergence but                               Slow convergence, needs
limited performance                                warmup, weight decay, etc.
        │                                                      │
        └─────────────── nGPT SOLUTION ────────────────────────┘
                                    │
                                    ▼
                        Hypersphere Geometry
                    4-20x faster training + architectural elegance
```


```
Sequence Processing Challenge  
───────────────────────────────────────────────────────────────
Computational Efficiency     ←──── TRADEOFF ────→    Context Understanding
        │                                                    │
        ▼                                                    ▼
RNNs: O(n) complexity                              Transformers: O(n²) complexity
Sequential processing                               Parallel processing
Limited context window                             Global attention
        │                                                     │
        └──────────────── MAMBA SOLUTION ─────────────────────┘
                                    │
                                    ▼
                          Selective State Space
                    O(n) complexity + global understanding
```


<br>






**nGPT - Training Optimization**

```
Solution: Mathematical reinterpretation
├── Transformer = Hypersphere optimizer
├── Normalization = Geometric constraints
└── Updates = Spherical interpolation
```



<br>


**Mamba - Inference Efficiency**

```
Solution: Architectural paradigm shift
├── Attention mechanism → State space model
├── Parallel computation → Selective recursion
└── Global perception → Compressed memory
```


<br><br>

## "2020 - System Design Interview An Insider’s Guide" - Alex Xu - Ver_1.0

<br>

[2024 - A Beginner’s Guide to System Design](https://medium.com/@sentalkssane/a-beginners-guide-to-system-design-76d64689788b)

<br>

**Common Data Capacity Units (Power-of-Two Table)**

```
| Unit Symbol | Name     | Definition                          | Exact Bytes         | Decimal Approximation |
| ----------- | -------- | ----------------------------------- | ------------------- | --------------------- |
| bit         | bit      | a single binary digit               | 1 bit               | —                     |
| B           | byte     | 8 bits                              | 8 bits              | —                     |
| KiB         | kibibyte | 2¹⁰ bytes = 1 024 bytes             | 1 024 B             | ≈ 1.02 KB (10³)       |
| MiB         | mebibyte | 2²⁰ bytes = 1 048 576 bytes         | 1 048 576 B         | ≈ 1.05 MB (10⁶)       |
| GiB         | gibibyte | 2³⁰ bytes = 1 073 741 824 bytes     | 1 073 741 824 B     | ≈ 1.07 GB (10⁹)       |
| TiB         | tebibyte | 2⁴⁰ bytes = 1 099 511 627 776 bytes | 1 099 511 627 776 B | ≈ 1.10 TB (10¹²)      |
```



<br><br><br>

