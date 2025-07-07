---
layout: post
title: Some Background Knowledge for Artificial Neural Networks
date: 2025-07-01
description: 🔹
categories: AI/ML
thumbnail: assets/img/9.jpg
images:
  lightbox2: true
  photoswipe: true
  spotlight: true
  venobox: true
---

<br>


`Some Websites`

<br>

[Colah's Blog](https://colah.github.io/)




<br><br>



`Articles`

<br>

[2024 - nGPT: Normalized Transformer with Representation Learning on the Hypersphere](https://arxiv.org/abs/2410.01131)

[2021 - Multimodal Neurons in Artificial NNs](https://distill.pub/2021/multimodal-neurons/)

[2018 - The Building Blocks of Interpretability](https://distill.pub/2018/building-blocks/)


<br><br><br>



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
