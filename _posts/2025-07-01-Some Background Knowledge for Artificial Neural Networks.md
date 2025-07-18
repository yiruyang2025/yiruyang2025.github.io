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




<br><br><br><br>


## References

<br><br>

**1. Collatz Conjecture / 3n + 1 problem / hailstone problem**

<br>

[1950 - Lothar Collatz “Über die Differenzengleichung xₙ₊₁ = aₙ xₙ + bₙ”, Mathematische Nachrichten, Bd. 3 (1950).](https://www.digizeitschriften.de/search?filter%5BZeitschriften%5D%5B1%5D=245319514%7Clog1&filter%5BObjekttyp%5D%5B1%5D=volume)

[2003 - The 3x+1 problem: An annotated bibliography (1963--1999) (sorted by author)](https://arxiv.org/abs/math/0309224)

[2017 - Collatz Conjecture in Color - Numberphile](https://www.youtube.com/watch?v=LqKpkdRRLZw)

<br><br>


**2**


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
