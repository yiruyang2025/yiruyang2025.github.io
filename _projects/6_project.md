---
layout: page
title: 2026 - DNA Discovery
description: And More, ()
img: assets/img/4.jpg
importance: 6
category: work
related_publications: true
---

<br>


## Topics - Prediction and Compression


```
In information theory, compression and prediction are essentially two sides of the same coin.
Claude Shannon, in his foundational work, revealed a core principle: the more accurate your
predictions of your data, the smaller you can compress it.
```

> **Better prediction → lower surprisal → fewer bits**

**Ideal coding length**

L(x₁:ₜ) = −Σₜ₌₁ᵀ log₂ P(xₜ | x&lt;ₜ)

where P(xₜ | x&lt;ₜ) is the probability of the next symbol xₜ given all previous symbols.

<br>


| Concept | Meaning |
|---|---|
| Core relationship | **Better prediction → lower surprisal → fewer bits** |
| Sequence | x₁, x₂, ..., xₜ |
| Ideal coding length | **L(x₁:ₜ) = −Σₜ₌₁ᵀ log₂ P(xₜ \| x&lt;ₜ)** |
| Conditional probability | P(xₜ \| x&lt;ₜ) is the probability assigned to the next symbol xₜ given all previous symbols. |
| Surprisal | −log₂ P(xₜ \| x&lt;ₜ) measures how unexpected the observed symbol is. |
| Highly predictable symbol | A high-probability symbol has low surprisal and requires fewer bits. |
| Unexpected symbol | A low-probability symbol has high surprisal and requires more bits. |
| Total compression cost | The coding length of the full sequence is the sum of the surprisal values of all symbols. |
| Main conclusion | Probabilistic prediction and entropy-based compression are two views of the same mathematical process. |



<br><br>



- [Computational Life: How Well-formed, Self-replicating Programs Emerge from Simple Interaction](https://research.google/people/105344/?&type=google), 2024
- [2016 - Unsupervised Representation Learning with Deep Convolutional Generative Adversarial Networks](https://arxiv.org/pdf/1511.06434), ICLR Test of Time




<br><br>



## Three Compression Boundaries

| Layer | Core Question | Mathematical Form | Meaning |
| :--- | :--- | :--- | :--- |
| **1. Information-Theoretic Boundary** | What is the minimum number of bits required under ideal conditions? | Lossless: $H(X)$ <br> Lossy: $R(D)$ | This is the fundamental theoretical limit determined by the source distribution and, for lossy compression, the chosen distortion measure. It assumes an ideal probability model, arbitrarily long coding blocks, and no practical limits on computation, memory, or latency. |
| **2. Algorithmic Boundary** | What is the best compression achievable under a finite computational budget? | $T(n) \le B$, therefore $R_B(D) \ge R(D)$ | The information-theoretic optimum may require prohibitively expensive or intractable search. A practical algorithm explores only a restricted set of encoding decisions, so its best achievable rate is generally no better than the theoretical rate–distortion limit. |
| **3. Format and System Boundary** | What is achievable after imposing real deployment constraints? | $R_{\mathrm{sys}}(D) \ge R_B(D) \ge R(D)$ | A real codec must satisfy bitstream syntax, decoder complexity, memory limits, latency, random access, parallelism, error resilience, streaming, hardware support, and backward compatibility. These constraints further reduce the feasible solution space. |



<br><br>
<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>





## References 1


- [2024 - Approximating Nash Equilibria in Normal-Form Games via Stochastic Optimization](https://iclr.cc/virtual/2024/oral/19744), ICLR Oral, C.3 Saddle Point Analysis
- [2026 - Zero Order Pretrain](https://x.com/FrancoisChauba1/status/2072433265232019871?s=20)




<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>



## References 2





<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>

<br><br><br><br><br><br><br><br><br><br><br><br>



## References

- [Earthdata Plugin](https://plugins.qgis.org/plugins/nasa_earthdata/)
- [DiffusionDrive](https://openreview.net/revisions?id=sh7vDLo5EY), CVPR highlight 2025.
- [Development of the Nervous System](https://www.mls.uzh.ch/en/research/hajnal/teaching.html), [Prof. Dr. Stoeckli Esther](https://www.mls.uzh.ch/en/research/stoeckli/research.html)
- [Demo](https://www.linkedin.com/posts/lou-kohler-voinov-9956a5236_ever-wondered-what-happens-to-an-rnn-during-ugcPost-7440301117588180993-uiPt?utm_source=social_share_send&utm_medium=member_desktop_web&rcm=ACoAAC5vvBgB20VgN9iW9bBoWdHZWq21kkV22wk)
- [2019 - Point-Voxel CNN for Efficient 3D Deep Learning](https://proceedings.neurips.cc/paper/2019/hash/5737034557ef5b8c02c0e46513b98f90-Abstract.html), NIPS
- [2020 - Searching efficient 3d architectures with sparse point-voxel convolution](https://arxiv.org/pdf/2007.16100)
- [2026 - nvidia/NV-Generate-MR-Brain](https://huggingface.co/nvidia/NV-Generate-MR-Brain)

<br><br><br><br>





<br><br><br><br><br><br><br><br>

