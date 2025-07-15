---
layout: post
title: State Spaces Models - 25
date: 2025-06-02
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

[2023 - Mamba](https://arxiv.org/pdf/2312.00752)

[2023 - RWKV](https://www.rwkv.com/)


<br><br>


**RNN vs. Mamba vs. Transformer**

```
Traditional RNN                              Transformer                                Mamba (Selective SSM)
─────────────                               ─────────────                              ──────────────────────
Sequential Processing                       Parallel Processing                        Selective Parallel Processing
h₁ → h₂ → ... → hₙ                         All positions simultaneously              Content-aware selective scan
(SLOW, O(n) steps)                         (FAST, O(1) steps but O(n²) memory)     (FAST, O(n) steps, O(n) memory)
     │                                           │                                          │
     ▼                                           ▼                                          ▼
Fixed State Compression                     No Compression (KV Cache)                Selective State Compression
Cannot filter content                       Stores everything                        Can focus/filter dynamically
     │                                           │                                          │
     ▼                                           ▼                                          ▼
Linear Time Complexity                      Quadratic Time Complexity                Linear Time Complexity
But limited effectiveness                   Effective but expensive                  Both effective AND efficient
```


<br>


**Efficiency vs. Effectiveness Tradeoff**

```
Sequence Modeling Challenge
───────────────────────────

Efficiency (Speed/Memory)  ←──── TRADEOFF ────→  Effectiveness (Quality)
        │                                              │
        ▼                                              ▼
RNNs: O(n) time                                Transformers: O(n²) time
Fixed compression                              Perfect information retention
Limited context                                Unlimited context (within window)
        │                                              │
        └────────────── MAMBA SOLUTION ────────────────┘
                              │
                              ▼
                    Selective Compression
                    O(n) time + Transformer quality
```


<br>


```
Traditional SSM (S4)                         Mamba Selective SSM
────────────────────                        ────────────────────

Time-Invariant Parameters                   Input-Dependent Parameters
┌─────────────────────┐                    ┌─────────────────────┐
│  Δ, A, B, C = const │                    │ Δ(x), B(x), C(x)    │
│  for all timesteps  │          →         │ = f(input_content)  │
└─────────────────────┘                    └─────────────────────┘
         │                                           │
         ▼                                           ▼
No Content Awareness                        Content-Aware Selection
┌─────────────────────┐                    ┌─────────────────────┐
│ Cannot distinguish  │                    │ Can selectively     │
│ important vs noise  │                    │ focus/ignore based  │
│ information         │                    │ on content          │
└─────────────────────┘                    └─────────────────────┘
         │                                           │
         ▼                                           ▼
Global Convolution                          Parallel Scan + Hardware Fusion
O(n log n) computation                      O(n) computation


Mamba Block Processing Pipeline
───────────────────────────────

Input Sequence x = [x₁, x₂, ..., xₙ]
         │
         ▼
Step 1: Input Projections
┌─────────────────────────────────┐
│ x → Linear projections          │
│ Generate: Δ, B, C parameters    │
│ Δ_t = softplus(Linear(x_t))     │
│ B_t = Linear_N(x_t)             │  
│ C_t = Linear_N(x_t)             │
└─────────────────────────────────┘
         │
         ▼
Step 2: Selective Discretization  
┌─────────────────────────────────┐
│ Convert continuous → discrete   │
│ A_bar_t = exp(Δ_t * A)          │
│ B_bar_t = Δ_t * B_t             │
│ Now parameters adapt to input!  │
└─────────────────────────────────┘
         │
         ▼
Step 3: Selective State Update
┌─────────────────────────────────┐
│ h_t = A_bar_t * h_{t-1} +       │
│       B_bar_t * x_t             │
│ (Computed via parallel scan)    │
└─────────────────────────────────┘
         │
         ▼
Step 4: Output Generation
┌─────────────────────────────────┐
│ y_t = C_t * h_t                 │
│ Selective output projection     │
└─────────────────────────────────┘
         │
         ▼
Final Output: y = [y₁, y₂, ..., yₙ]
```


<br>


**Performance Comparison**

```
Model Architecture Comparison
──────────────────────────────

Metric              RNN        Transformer    Mamba
──────              ───        ───────────    ─────
Time Complexity     O(n)       O(n²)          O(n)
Space Complexity    O(1)       O(n²)          O(n)
Parallelizable      ✗          ✓              ✓
Long Context        ✗          ✓              ✓
Content Selectivity ✗          Limited        ✓
Hardware Efficient  ✗          ✗              ✓

Performance Results (1.3B parameters):
─────────────────────────────────────
Language Modeling   8.5 PPL    8.0 PPL        8.0 PPL
Training Speed      1.0×       1.0×           1.1×
Inference Speed     1.0×       1.0×           5.0×
Memory Usage        Low        High           Medium
```



<br>

```
Traditional Transformer                    SSM (Mamba)
───────────────────────                    ───────────

Attention Mechanism:                      Selective State Space:
Attention(Q,K,V) = softmax(QK^T/√d)V      h_t = A_bar·h_{t-1} + B_bar·x_t
                                          y_t = C·h_t

Complexity: O(n²)                         Complexity: O(n)
Memory: O(n²)                            Memory: O(n)
Context: Limited by memory               Context: Unlimited
```


<br>

```
Continuous-Time System (Theory)              Discrete-Time System (Practice)
───────────────────────────────              ────────────────────────────────

Differential Equations                       Difference Equations
┌─────────────────────────────┐             ┌─────────────────────────────────┐
│ h'(t) = Ah(t) + Bx(t)       │      →      │ h_t = A_bar·h_{t-1} + B_bar·x_t │
│ y(t) = Ch(t)                │             │ y_t = C·h_t                     │
│                             │             │                                 │
│ Smooth, continuous flow     │             │ Step-by-step computation        │
│ Infinite precision          │             │ Digital computer friendly       │
│ Mathematical elegance       │             │ Practical implementation        │
└─────────────────────────────┘             └─────────────────────────────────┘

Parameter Transformation:
┌─────────────────────────────────────────────────────────────────────────┐
│ A: State transition matrix    →    A_bar = exp(Δ·A)                     │
│ B: Input projection matrix    →    B_bar = (Δ·A)^(-1)(exp(Δ·A)-I)·Δ·B   │
│ C: Output projection matrix   →    C: Remains unchanged                 │
│ Δ: Discretization step size   →    Controls temporal resolution         │
└─────────────────────────────────────────────────────────────────────────┘
```

<br>

```
Reservoir State Evolution Over Time
───────────────────────────────────

Time: t=0, t=1, t=2, t=3, ... (each step = Δ seconds)

t=0: Initial State
┌─────────────────────────────┐
│ h_0 = 100 liters (starting) │
│ x_0 = 20 liters input       │
│ y_0 = C × h_0 = output      │
└─────────────────────────────┘
          ↓
t=1: First Update  
┌─────────────────────────────┐
│ h_1 = A_bar×100 + B_bar×20  │
│ x_1 = 15 liters input       │
│ y_1 = C × h_1 = output      │
└─────────────────────────────┘
          ↓
t=2: Second Update
┌─────────────────────────────┐
│ h_2 = A_bar×h_1 + B_bar×15  │
│ x_2 = 25 liters input       │
│ y_2 = C × h_2 = output      │
└─────────────────────────────┘
          ↓
Continue step by step...

Core Magic: Δ (Time Step)
How often do we update?
-> Small Δ: Frequent updates, more precise, heavy computation
-> Large Δ: Fewer updates, efficient, may lose details
```


<br>

```
🧠 Neural Networks & AI:
Continuous Theory → Discrete Implementation
Perfect gradients → Backpropagation steps
Infinite precision → Digital computation

🎥 Video Processing:
Smooth motion → Frame-by-frame analysis
Continuous scenes → Discrete timesteps
Real-time flow → Processable chunks

💰 Financial Systems:
Continuous markets → **Tick-by-tick** updates
Instant prices → Sampled data points
Perfect info → **Practical decisions**

🌊 Engineering Systems:
Fluid dynamics → Digital simulations
Smooth flows → Computational fluid dynamics
Physical reality → Numerical solutions
```






<br><br><br>











<br>

# References

<br>

- [📍 2025 Gen-4 - **Character Consistency Across Scenes** - NYC is a Zoo](https://venturebeat.com/ai/runways-gen-4-ai-solves-the-character-consistency-challenge-making-ai-filmmaking-actually-useful/?utm_source=chatgpt.com)

<br>


# HCI

<br>

- Chatbots + Speech Processing

<br>

Some parellel Attention calculation

<br>

- **📍 MEMORY - Transformers vs. RNN / LSTM**
  
<br>

  - [Add Reflection - 2024 - You Only Cache Once: Decoder-Decoder Architectures for Language Models](https://arxiv.org/abs/2405.05254)<br>
    - **RetNet** - Retention Network -> Gated Retention
    - [2023 - RetNet: Retinal Disease Detection using Convolutional Neural Network](https://ieeexplore.ieee.org/abstract/document/10101661?casa_token=uZQehKNSJt0AAAAA:UWdRNBHC8WlsoNpwbNVIm9Wr147Q-292JEFwcP6bLglKLDlNtTVfIe7RuHyVD6ryjeuQTFUOaw)
    - **DeltaNet** - [2025 - Parallelizing Linear Transformers with the Delta Rule over Sequence Length](https://arxiv.org/abs/2406.06484)
   

<br><br>


- [2025 - **Memory**](https://www.youtube.com/watch?v=UCiSWcHSdYE)<br>


<br><br><br><br>

