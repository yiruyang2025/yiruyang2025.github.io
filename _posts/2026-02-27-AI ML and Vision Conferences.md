---
layout: post
title: AI ML and Vision Conferences
date: 2026-03-01
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


## Release Ready

- [HuggingFace](https://huggingface.co/docs/hub/en/model-release-checklist)



<br>

## Brief

```
                 AI SYSTEM

        ┌──────── Learning ────────┐
        │                          │
   Deep Learning              Representation
        │                          │
        └──────── Perception ──────┘
                    │
                    ▼
            Probabilistic Inference
                    │
           Factor Graph / Optimization
                    │
                    ▼
                State Estimation
                    │
                    ▼
             Planning / Control
```


<br>



## When you're not Indexing Everything


<br>


```
def backtrack(index):
    res.append(list(path))
    for i in range(index, len(nums)):
        path.append(nums[i])
        backtrack(i + 1)
        path.pop()

def function_name(parameters) -> return_type:
List[List[str]] = a list of chessboards, where each chessboard is represented as a list of strings.
def findMedianSortedArrays(self, nums1: List[int], nums2: List[int]) -> float:

**edge case**
nums1_left_max = nums1[i-1] if i > 0 else float('-inf')
nums1_right_min = nums1[i] if i < m else float('inf')

**otherwise**
if i == 0:
    nums1_left_max = -∞
elif i == m:
    nums1_right_min = +∞
else:
    nums1_left_max = nums1[i-1]

**
Run-time analysis → produces → Algorithm complexity
T(n) = 3n² + 5n + 2 → O(n²)

**method**
All classes have a built-in method called __init__(), used to assign values to object properties, or to perform operations.
```

<br>

## Toolkits


## DFS on a decision tree

| Problem      | Index rule       | Meaning             |
| ------------ | ---------------- | ------------------- |
| Subsets      | next index = i+1 | increasing sequence |
| Combinations | next index = i+1 | choose k elements   |
| Permutations | any unused index | reorder elements    |
| N-Queens     | next row         | one queen per row   |

<br>

## Modularity

```
Complex System → Division → Independent Modules
**
Encapsulation → Abstraction → Independence → Reusability
**
Client → HTTP Request → API Endpoint → Service → Database
```

<br>

## CURD


| CRUD   | HTTP        |
| ------ | ----------- |
| Create | POST        |
| Read   | GET         |
| Update | PUT / PATCH |
| Delete | DELETE      |

<br>


## Algorithms

| Topic                            | Core Idea                               | Underlying Data Structure | Algorithmic Principle                     | Typical Problems Solved                                    | Key Insight                                                   |
| -------------------------------- | --------------------------------------- | ------------------------- | ----------------------------------------- | ---------------------------------------------------------- | ------------------------------------------------------------- |
| Kadane's Algorithm               | Find maximum subarray sum               | Array                     | Dynamic programming (prefix accumulation) | Maximum subarray, profit optimization                      | If current sum becomes negative, restart from next element    |
| Sliding Window (Fixed Size)      | Maintain a window of constant length    | Array / Queue             | Two pointers with constant window size    | Maximum sum of k elements, fixed-length substring problems | Move window by removing left element and adding right element |
| Sliding Window (Variable Size)   | Expand and shrink window dynamically    | Array / HashMap           | Two pointers with constraint checking     | Longest substring without repetition                       | Grow window until constraint breaks, then shrink              |
| Two Pointers                     | Use two indices moving through data     | Array                     | Linear scanning from multiple directions  | Sorted array search, pair sum problems                     | Each pointer moves at most n times → O(n)                     |
| Prefix Sums                      | Precompute cumulative sums              | Array                     | Preprocessing for range queries           | Range sum queries, subarray sums                           | sum(l,r) = prefix[r] − prefix[l−1]                            |
| Fast & Slow Pointers             | Detect cycles or midpoint               | Linked List               | Floyd's cycle detection                   | Cycle detection, middle node finding                       | Fast pointer moves twice as fast                              |
| Trie                             | Efficient prefix matching               | Tree (Prefix Tree)        | Character-based tree traversal            | Autocomplete, dictionary search                            | Each edge represents a character                              |
| Union-Find (Disjoint Set)        | Track connected components              | Disjoint Set Forest       | Path compression + union by rank          | Connectivity problems, cycle detection                     | Amortized almost constant time                                |
| Segment Tree                     | Efficient range queries and updates     | Binary Tree               | Divide-and-conquer range partition        | Range sum/min/max queries                                  | Query and update in O(log n)                                  |
| Iterative DFS                    | Depth-first traversal without recursion | Stack                     | Graph traversal                           | Graph connectivity, path search                            | Use explicit stack instead of recursion                       |
| Two Heaps                        | Maintain two balanced sets              | Min Heap + Max Heap       | Balanced partition                        | Median of data stream                                      | Keep heaps balanced for quick median                          |
| Subsets (Backtracking)           | Generate all subsets                    | Recursion Tree            | DFS state-space exploration               | Power set generation                                       | Each element: choose or skip                                  |
| Combinations                     | Choose k elements from n                | Recursion Tree            | Backtracking with index control           | Combination generation                                     | Ensure increasing indices                                     |
| Permutations                     | Generate all orderings                  | Recursion Tree            | Backtracking with visited tracking        | Permutation generation                                     | Use visited array                                             |
| Dijkstra's Algorithm             | Shortest path from source               | Graph + Priority Queue    | Greedy algorithm                          | Shortest path in weighted graph                            | Always expand smallest distance node                          |
| Prim's Algorithm                 | Minimum spanning tree                   | Graph + Priority Queue    | Greedy tree expansion                     | MST construction                                           | Add smallest edge to growing tree                             |
| Kruskal's Algorithm              | Minimum spanning tree                   | Graph + Union-Find        | Greedy edge selection                     | MST construction                                           | Sort edges and avoid cycles                                   |
| Topological Sort                 | Order nodes in DAG                      | Graph (Adjacency List)    | BFS (Kahn) or DFS                         | Task scheduling, dependency resolution                     | Nodes processed after dependencies                            |
| 0/1 Knapsack                     | Choose items with weight constraint     | DP Table                  | Dynamic programming                       | Resource allocation                                        | Each item chosen once                                         |
| Unbounded Knapsack               | Unlimited items allowed                 | DP Table                  | Dynamic programming                       | Coin change problems                                       | Items can be reused                                           |
| LCS (Longest Common Subsequence) | Compare sequences                       | DP Matrix                 | Dynamic programming                       | String similarity                                          | DP based on prefix comparisons                                |
| Palindromes                      | Check symmetric substrings              | String / DP Table         | Dynamic programming or center expansion   | Longest palindromic substring                              | Expand around center                                          |


<br>


## Shortest-Path Algorithms


| Scenario                                                                      | Algorithm           | Core Principle                                                                                                                    | Mathematical Formulation                                                              | Time Complexity                                                                              | When to Use                                                                                                                                                                       |
| ----------------------------------------------------------------------------- | ------------------- | --------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Single-source shortest paths with possible negative edge weights              | Bellman–Ford        | Repeatedly relax every edge. One additional pass detects a reachable negative-weight cycle.                                       | d(v) ← min{d(v), d(u) + w(u,v)}, applied to every edge for at most V − 1 passes       | O(VE)                                                                                        | Use when negative edge weights may exist or when reachable negative-weight-cycle detection is required.                                                                           |
| Single-source shortest paths using a queue-based Bellman–Ford heuristic       | SPFA                | Reprocess only vertices whose distance estimates have changed.                                                                    | If d(u) + w(u,v) < d(v), update d(v) and enqueue v if it is not already in the queue. | Worst case: O(VE); often faster in practice, but with no general O(E) average-case guarantee | Use as a practical heuristic on favorable sparse graphs; avoid it when worst-case performance must be guaranteed.                                                                 |
| All-pairs shortest paths, especially for dense or relatively small graphs     | Floyd–Warshall      | Use dynamic programming while progressively allowing each vertex to serve as an intermediate vertex.                              | dᵏᵢⱼ = min(dᵏ⁻¹ᵢⱼ, dᵏ⁻¹ᵢₖ + dᵏ⁻¹ₖⱼ)                                                   | O(V³)                                                                                        | Use for dense graphs, small-to-medium V, or when a simple all-pairs method is preferred. Negative edges are allowed, but negative-weight cycles invalidate finite shortest paths. |
| All-pairs shortest paths on sparse graphs with possible negative edge weights | Johnson’s Algorithm | Use Bellman–Ford to compute vertex potentials, reweight all edges to nonnegative values, and then run Dijkstra from every vertex. | w′(u,v) = w(u,v) + h(u) − h(v), where h(v) is obtained using Bellman–Ford             | O(VE + V² log V)                                                                             | Use for sparse graphs containing negative edges but no negative-weight cycles.                                                                                                    |




<br>

## Operations

| Category          | Syntax                | Meaning                       | Typical Use                 | Comment              |                |
| ----------------- | --------------------- | ----------------------------- | --------------------------- | -------------------- | -------------- |
| Floor division    | `x // y`              | Integer division (round down) | Binary search midpoint      | `# integer division` |                |
| Division          | `x / y`               | Floating-point division       | Average / ratio             | `# float division`   |                |
| Modulo            | `x % y`               | Remainder after division      | Even check / circular index | `# remainder`        |                |
| Power             | `x ** y`              | Exponentiation                | Exponential growth          | `# power`            |                |
| Absolute value    | `abs(x)`              | Absolute value                | Distance / difference       | `# absolute value`   |                |
| Minimum           | `min(a,b)`            | Smaller value                 | Greedy / comparison         | `# choose smaller`   |                |
| Maximum           | `max(a,b)`            | Larger value                  | Greedy / comparison         | `# choose larger`    |                |
| Equality          | `a == b`              | Check equality                | Condition checks            | `# equal`            |                |
| Inequality        | `a != b`              | Check inequality              | Condition checks            | `# not equal`        |                |
| Comparison        | `<, >, <=, >=`        | Value comparison              | Sorting / conditions        | `# compare values`   |                |
| Logical AND       | `a and b`             | Both true                     | Multi-condition check       | `# logical and`      |                |
| Logical OR        | `a or b`              | At least one true             | Multi-condition check       | `# logical or`       |                |
| Logical NOT       | `not a`               | Negation                      | Condition inversion         | `# logical not`      |                |
| Membership        | `x in s`              | Element exists                | Set / list lookup           | `# membership test`  |                |
| Assignment        | `x = v`               | Assign value                  | Variable update             | `# assignment`       |                |
| Increment         | `x += 1`              | Add and assign                | Counters                    | `# increment`        |                |
| Range loop        | `for i in range(n)`   | Iterate n times               | Linear traversal            | `# iterate indices`  |                |
| Length            | `len(arr)`            | Number of elements            | Loop bounds                 | `# array length`     |                |
| Index access      | `arr[i]`              | Access element by index       | Array operations            | `# element access`   |                |
| Slicing           | `arr[a:b]`            | Subarray extraction           | Substring / subarray        | `# slice`            |                |
| Set insert        | `s.add(x)`            | Add element                   | Visited set                 | `# insert into set`  |                |
| Set remove        | `s.remove(x)`         | Remove element                | Backtracking                | `# remove element`   |                |
| Dict lookup       | `dict[key]`           | Access value                  | Hash map                    | `# lookup value`     |                |
| Dict default      | `dict.get(k,0)`       | Safe lookup                   | Frequency count             | `# default lookup`   |                |
| Heap push         | `heapq.heappush(h,x)` | Insert in heap                | Priority queue              | `# push heap`        |                |
| Heap pop          | `heapq.heappop(h)`    | Remove smallest               | Dijkstra / top-k            | `# pop heap`         |                |
| Queue push        | `q.append(x)`         | Add element                   | BFS queue                   | `# enqueue`          |                |
| Queue pop         | `q.popleft()`         | Remove front                  | BFS traversal               | `# dequeue`          |                |
| Bit AND           | `x & y`               | Bitwise AND                   | Bit tricks                  | `# bitwise and`      |                |
| Bit OR            | `x                    | y`                            | Bitwise OR                  | Bit operations       | `# bitwise or` |
| Bit XOR           | `x ^ y`               | Bitwise XOR                   | Unique element problems     | `# bitwise xor`      |                |
| Left shift        | `x << k`              | Multiply by `2^k`             | Bitmask / powers            | `# shift left`       |                |
| Right shift       | `x >> k`              | Divide by `2^k`               | Bit operations              | `# shift right`      |                |
| Power of two test | `x & (x-1) == 0`      | Check power of two            | Bit trick                   | `# power of two`     |                |
| Binary search mid | `mid = (l+r)//2`      | Compute midpoint              | Binary search               | `# midpoint`         |                |




<br>

## Patterns

```
Problem
  ↓
Pattern recognition
  ↓
Data structure
  ↓
Algorithm
  ↓
Complexity analysis
```

<br>

## OOP

| Concept           | Simple Definition                                                  | Key Question                                                        | Main Risk                                                            |
| ----------------- | ------------------------------------------------------------------ | ------------------------------------------------------------------- | -------------------------------------------------------------------- |
| **Encapsulation** | Hide internal implementation behind a controlled interface         | What should users be allowed to access or change?                   | Exposing too much creates coupling and allows invalid state changes  |
| **Inheritance**   | A subclass extends a parent class through an **is-a** relationship | Can the subclass safely replace the parent?                         | Misuse creates fragile hierarchies and broken behavior               |
| **Polymorphism**  | One interface supports multiple implementations                    | Can new behavior be added without changing existing callers?        | Poor interfaces lead to type checks and repeated conditionals        |
| **Abstraction**   | Show only the details needed by the user                           | What should the user understand, and what should the system handle? | Too high becomes restrictive; too low exposes unnecessary complexity |





<br><br><br>

## Millennium Prize Problems


| **Problem Name** | **Field** | **Core Nature** | **Fundamental Question** | **Status** |
|---|---|---|---|---|
| **Riemann Hypothesis** | Analytic Number Theory | Distribution of prime numbers through the zeros of the Riemann zeta function | Do all nontrivial zeros of \(\zeta(s)\) have real part \(1/2\)? | Unsolved |
| **P versus NP** | Theoretical Computer Science | Computational complexity and efficient algorithms | Is every problem whose solution can be verified in polynomial time also solvable in polynomial time? | Unsolved |
| **Navier–Stokes Existence and Smoothness** | Partial Differential Equations / Fluid Mechanics | Global behavior of three-dimensional incompressible fluid flow | For smooth initial data, do physically reasonable solutions always exist globally and remain smooth, or can finite-time singularities develop? | Unsolved |
| **Yang–Mills Existence and Mass Gap** | Mathematical Physics / Quantum Field Theory | Rigorous construction of quantum Yang–Mills theory | Can a nontrivial quantum Yang–Mills theory on \(\mathbb{R}^4\) be constructed rigorously and shown to possess a positive mass gap? | Unsolved |
| **Hodge Conjecture** | Algebraic Geometry / Topology | Relationship between topology and algebraic cycles | Is every rational Hodge class on a smooth projective complex variety a rational linear combination of classes of algebraic cycles? | Unsolved |
| **Birch and Swinnerton-Dyer Conjecture** | Algebraic Number Theory | Rational points on elliptic curves | Does the order of vanishing of an elliptic curve’s \(L\)-function at \(s=1\) equal the rank of its group of rational points? | Unsolved |
| **Poincaré Conjecture** | Geometric Topology | Characterization of the three-dimensional sphere | Is every closed, simply connected three-dimensional manifold homeomorphic to the three-sphere \(S^3\)? | **Solved by Grigori Perelman (2002–2003)** |

<br><br><br><br><br><br><br><br><br><br>





## ICML vs. NeurIPS vs. ICLR

| Conference | Full Name                                            | Founded                                                                                         | Core Positioning                                                                             | Strongest Research Fit                                                                                                                                                   | Typical Review Emphasis                                                                                                                              |
| ---------- | ---------------------------------------------------- | ----------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------- |
| ICML       | International Conference on Machine Learning         | Originated in 1980 as the International Workshop on Machine Learning; later developed into ICML | Foundational machine-learning methods, theory, and algorithms                                | Statistical learning, optimization, reinforcement learning, probabilistic methods, generalization, causality, and principled ML algorithms                               | Technical correctness, methodological novelty, rigorous assumptions, theoretical or empirical justification, and broad relevance to machine learning |
| NeurIPS    | Conference on Neural Information Processing Systems  | Founded in 1987                                                                                 | Broad interdisciplinary flagship conference for machine learning and artificial intelligence | Deep learning, ML theory, reinforcement learning, generative models, neuroscience, AI for science, datasets, systems, responsible AI, and interdisciplinary applications | Novelty, significance, technical quality, empirical strength, reproducibility, clarity, and potential impact across a broad research community       |
| ICLR       | International Conference on Learning Representations | First held in 2013                                                                              | Leading venue for representation learning and frontier deep-learning research                | Neural architectures, self-supervised learning, generative models, foundation models, multimodal learning, optimization, and representation learning                     | Originality, conceptual clarity, strong experiments, meaningful ablations, reproducibility, and clear discussion through the OpenReview process      |




<br><br>


## ICLR

- [2025 - Representation Alignment for Generation: Training Diffusion Transformers Is Easier Than You Think](https://sihyun.me/REPA/), ICLR'25 Oral
- [2026 - Continuous control with deep reinforcement learning(DDPG)](https://patents.google.com/patent/US20170024643A1/en), Test of Time 2026

<br>


| **Generation**                                       | **Representative Mechanisms**                                     | **Core Representation Form**                    | **Advantages and Limitations**                                                                                                                                                                                                                                                                                               |
| ---------------------------------------------------- | ----------------------------------------------------------------- | ----------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Traditional Statistical and Handcrafted Features** | SIFT, HOG, Mel Spectrograms, PCA                                  | Fixed handcrafted basis                         | Computationally predictable and interpretable, but constrained by human-designed assumptions and often unable to preserve higher-order phase information or complex nonlinear global geometry.                                                                                                                               |
| **Discrete Quantized Representations**               | VQ-VAE, EnCodec, RVQ, dVAE                                        | Discrete codebook indices, codes, or symbols    | Naturally compatible with categorical and autoregressive Transformers. However, quantization introduces irreversible discretization error, discontinuous latent transitions, and risks such as codebook collapse or underutilization.                                                                                        |
| **Continuous Differentiable Representations**        | Continuous VAEs, M-Layers, Implicit Neural Representations (INRs) | Continuous real-valued latent vectors or fields | Preserve differentiability and support smooth latent variation without discrete quantization boundaries. They are well suited to diffusion and flow-matching models that learn continuous-time vector fields, although smoothness and Lipschitz continuity must be encouraged or enforced rather than assumed automatically. |



<br><br>

## ICLR Best / Outstanding Papers (2017–2026)

| Year | Official Best / Outstanding Paper Topics | Representative Authors |
|---|---|---|
| **2026** | Transformer succinctness; multi-turn LLM evaluation | Pascal Bergsträßer, Ryan Cotterell, Anthony Widjaja Lin; Philippe Laban, Hiroaki Hayashi, Yingbo Zhou, Jennifer Neville |
| **2025** | LLM safety alignment; LLM fine-tuning dynamics; null-space-constrained model editing | Xiangyu Qi et al.; Yi Ren, Danica J. Sutherland; Junfeng Fang et al. |
| **2024** | Diffusion-model generalization; interactive world simulators; long-sequence models; protein generation; Vision Transformer registers | Zahra Kadkhodaie et al.; Sherry Yang et al.; Ido Amos et al.; Nathan C. Frey et al.; Timothée Darcet et al. |
| **2023** | Few-shot dense prediction; GNN expressivity; text-to-3D generation; representations in embodied navigation | Donggyun Kim et al.; Bohang Zhang et al.; Ben Poole et al.; Erik Wijmans et al. |
| **2022** | Diffusion inference; differential privacy; learnable CNN strides; GNN expressivity; task-aware distribution comparison; neural collapse; meta-learning | Fan Bao et al.; Nicolas Papernot, Thomas Steinke; Rachid Riad et al.; Floris Geerts, Juan L. Reutter; Shengjia Zhao et al.; X. Y. Han et al.; Sebastian Flennerhag et al. |
| **2021** | Hypercomplex networks; complex-query answering; game-theoretic PCA; graph-network simulation; binaural speech synthesis; neural-tangent-kernel theory; differentiable NAS; score-based diffusion | Aston Zhang et al.; Erik Arakelyan et al.; Ian Gemp et al.; Tobias Pfaff et al.; Alexander Richard et al.; Atsushi Nitanda, Taiji Suzuki; Ruochen Wang et al.; Yang Song et al. |
| **2020** | No official Best or Outstanding Paper Award | — |
| **2019** | Structured recurrent networks; sparse trainable subnetworks | Yikang Shen, Shawn Tan, Alessandro Sordoni, Aaron Courville; Jonathan Frankle, Michael Carbin |
| **2018** | Adam convergence; spherical CNNs; continuous adaptation through meta-learning | Sashank J. Reddi, Satyen Kale, Sanjiv Kumar; Taco S. Cohen et al.; Maruan Al-Shedivat et al. |
| **2017** | Deep-network generalization; recursive neural programs; privacy-preserving knowledge transfer | Chiyuan Zhang et al.; Jonathon Cai, Richard Shin, Dawn Song; Nicolas Papernot et al. |


<br><br>

## ICLR Oral Research Topics


| Period        | Dominant Oral Topics                        | Representative Keywords                                                                                                                                                                     |
| ------------- | ------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **2017–2019** | Deep Learning Foundations                   | Generalization, Optimization, Theory, Privacy, Lottery Ticket, RNNs                                                                                                                         |
| **2020–2021** | Representation Learning & Generative Models | Self-Supervised Learning, Diffusion Models, Graph Neural Networks, Neural Simulation, Neural Architecture Search                                                                            |
| **2022–2023** | Foundation Generative Models                | Diffusion, Text-to-3D, Scientific Machine Learning, Protein Modeling, Graph Learning, Embodied AI                                                                                           |
| **2024–2026** | Foundation Models & AI Agents               | Large Language Models, AI Agents, Long-Context Modeling, Alignment, Safety, Model Editing, Vision-Language Models, World Models, Robotics, Transformer Theory, Mechanistic Interpretability |



<br><br><br><br>


## ICML


- [2024 - Some Lessons from Adversarial Machine Learning](https://nicholas.carlini.com/), Alignment, Nicholas Carlini
- [2020 - Are we done with ImageNet?](https://arxiv.org/abs/2006.07159), [Lukas Beyer](https://lucasb.eyer.be/)'s blog

<br>

## What ICML Awards Tell Us: From Better Models to Better Questions

*A selective review of ICML award-winning research, 2016–2026*

> **Scope.** This article highlights selected ICML award-winning papers and uses them to examine changes in machine learning research. It is not an exhaustive list of all awards, Oral presentations, or Spotlights. Award titles follow the terminology used by each year’s organizers where verified.
>
> **Last checked:** 25 November 2026.

## A useful distinction: recognition today and impact over time

A conference award and a Test of Time Award answer different questions.

- **Best Paper / Outstanding Paper** recognizes work selected from a particular year’s conference.
- **Test of Time** recognizes earlier work whose influence became clear over subsequent years.
- **Oral / Spotlight** identifies papers selected for special presentation or distinction; it is not itself a best-paper award.

Consider **Batch Normalization**. Published at ICML in 2015, it received the **2025 Test of Time Award**. In the same year, ICML recognized *Trust Region Policy Optimization* and *Variational Inference with Normalizing Flows* as Test of Time honorable mentions.

The lesson is not that current awards are unimportant. It is that **immediate recognition and long-term influence are different outcomes**.

Sources: [Batch Normalization](https://proceedings.mlr.press/v37/ioffe15.html) · [ICML 2025 award summary](https://aihub.org/2025/07/16/congratulations-to-the-icml2025-award-winners/)

---

## 2016–2020: From new architectures to questions of reliability

This period includes influential advances in deep learning and a growing body of work asking whether models and evaluation methods behave as claimed.

| Year | Selected paper and distinction | Central contribution |
|---|---|---|
| **2016** | *Dueling Network Architectures for Deep Reinforcement Learning* — Best Paper | Separates state value and action advantage when estimating Q-values, improving value-based reinforcement learning on the evaluated tasks. |
| **2016** | *Pixel Recurrent Neural Networks* — Best Paper | Models image distributions autoregressively, showing how recurrent architectures can generate images one pixel at a time. |
| **2016** | *Ensuring Rapid Mixing and Low Bias for Asynchronous Gibbs Sampling* — Best Paper | Studies conditions under which asynchronous Gibbs sampling remains efficient and incurs controlled bias. |
| **2017** | *Understanding Black-box Predictions via Influence Functions* — Best Paper | Adapts influence functions to estimate how training examples affect a prediction, offering a tool for inspecting model behavior. |
| **2018** | *Obfuscated Gradients Give a False Sense of Security* — Best Paper | Shows that several adversarial defenses can appear robust because their gradients are difficult to use, while adaptive attacks can circumvent them. |
| **2018** | *Delayed Impact of Fair Machine Learning* — Best Paper | Demonstrates that the long-term effects of decisions can differ from what a static fairness criterion suggests. |
| **2019** | *Challenging Common Assumptions in the Unsupervised Learning of Disentangled Representations* — Best Paper | Shows that unsupervised disentanglement is not identifiable without suitable inductive biases, and examines the assumptions behind empirical claims. |
| **2020** | *On Learning Sets of Symmetric Elements* — Outstanding Paper | Studies neural architectures for sets whose elements themselves have symmetry. |
| **2020** | *Tuning-free Plug-and-Play Proximal Algorithm for Inverse Imaging Problems* — Outstanding Paper | Develops a plug-and-play approach that reduces manual parameter tuning for inverse imaging. |

**Why these papers matter together.** The 2018 robustness and fairness papers do more than propose a better model: they ask whether a commonly used evaluation supports the conclusion researchers want to draw. The 2019 disentanglement paper makes a related point mathematically: a desirable representation cannot generally be identified without assumptions.

This does not mean ICML had stopped valuing new architectures. The selected papers illustrate **coexisting research priorities**, not a complete replacement of one theme by another.

Sources: [ICML 2018 official awards](https://icml.cc/Conferences/2018/Awards) · [ETH Zurich on the 2019 award](https://ethz.ch/en/the-eth-zurich/portrait/latest-honours-and-prizes/2019/06/icml-best-paper-award-for-francesco-locatello.html) · [ICML 2020 official awards](https://icml.cc/Conferences/2020/Awards) · [Curated ICML awards list](https://github.com/SarahRastegar/Best-Papers-Top-Venues#ICML)

---

## 2021–2023: Optimization, assumptions, and scientific guarantees

| Year | Selected paper and distinction | Central contribution |
|---|---|---|
| **2021** | *Unbiased Gradient Estimation in Unrolled Computation Graphs with Persistent Evolution Strategies* — Outstanding Paper | Proposes a gradient-estimation method for long unrolled computation graphs, relevant to settings such as hyperparameter optimization. |
| **2022** | *Do Differentiable Simulators Give Better Policy Gradients?* — Outstanding Paper | Investigates when gradients through differentiable simulators help policy optimization and when they can be problematic. |
| **2022** | *Causal Conceptions of Fairness and their Consequences* — Outstanding Paper | Clarifies how different causal assumptions lead to different fairness concepts and conclusions. |
| **2022** | *G-Mixup: Graph Data Augmentation for Graph Classification* — Outstanding Paper | Uses graphons to construct a graph-specific form of Mixup for graph classification. |
| **2022** | *Understanding Dataset Difficulty with V-Usable Information* — Outstanding Paper | Studies predictive information relative to a specified model family, offering a model-dependent view of dataset difficulty. |
| **2022** | *Bayesian Model Selection, the Marginal Likelihood, and Generalization* — Outstanding Paper | Examines how marginal likelihood and generalization relate, including limitations of common interpretations. |
| **2023** | *Learning-Rate-Free Learning by D-Adaptation* — Outstanding Paper | Addresses learning-rate selection for stochastic convex optimization and develops corresponding guarantees. |
| **2023** | *A Watermark for Large Language Models* — Outstanding Paper | Introduces a way to embed and statistically detect a watermark in generated text without retraining the language model. |
| **2023** | *Self-Repellent Random Walks on General Graphs* — Outstanding Paper | Studies random walks that discourage revisits and analyzes their sampling properties. |

**A recurring pattern:** some contributions propose a new algorithm, while others clarify **when a method works, what its guarantees actually say, or which assumptions determine the answer**.

For 2023, the official award committee said it considered clarity, insight, creativity, and the **potential for lasting impact**. That is a selection criterion—not proof that every winning paper will have equal long-term impact.

Sources: [ICML 2023 official awards and selection process](https://icml.cc/Conferences/2023/Awards) · [ICML award collection](https://github.com/SarahRastegar/Best-Papers-Top-Venues#ICML) · [PES paper](https://proceedings.mlr.press/v139/vicol21a.html)

---

## 2024–2026: Generative models, evaluation, and social consequences

### 2024: Generative models meet new questions about trust

Selected ICML 2024 Best Paper recipients include:

| Paper | Research question |
|---|---|
| *VideoPoet: A Large Language Model for Zero-Shot Video Generation* | Can an autoregressive model generate and transform video across multiple modalities? |
| *Genie: Generative Interactive Environments* | Can a model learn interactive environments from video without action labels? |
| *Scaling Rectified Flow Transformers for High-Resolution Image Synthesis* | Can rectified-flow transformers scale to high-resolution image generation? |
| *Stealing Part of a Production Language Model* | What information about a production language model can be extracted through black-box access? |
| *Position: Considerations for Differentially Private Learning with Large-Scale Public Pretraining* | What privacy claims are justified when public pretraining is combined with private learning? |

These papers point to two simultaneous interests: **more capable generative systems** and **more careful scrutiny of what those systems expose, protect, or allow us to conclude**.

Sources: [ICML 2024 awards listing](https://icml.cc/virtual/2024/awards_detail) · [ETH Zurich on the privacy Position Paper](https://inf.ethz.ch/news-and-events/spotlights/infk-news-channel/2024/07/best-paper-awards-at-icml.html) · [University of British Columbia on Genie](https://www.cs.ubc.ca/award/2024/07/best-paper-award)

### 2025: Collaboration, generation, and statistical foundations

| Selected Outstanding Paper | Main idea |
|---|---|
| *CollabLLM: From Passive Responders to Active Collaborators* | Trains models to consider the longer-term quality of multi-turn collaboration. |
| *Train for the Worst, Plan for the Best: Understanding Token Ordering in Masked Diffusions* | Studies the relationship between training and decoding order in masked diffusion models. |
| *Score Matching with Missing Data* | Extends score-matching methodology to settings with missing observations. |
| *Conformal Prediction as Bayesian Quadrature* | Connects conformal prediction with Bayesian quadrature. |
| *Roll the Dice & Look Before You Leap* | Studies limitations of next-token prediction for creative generation. |
| *The Value of Prediction in Identifying the Worst-Off* | Examines when prediction can help identify people who are worst off. |

The two Outstanding Position Papers addressed the **future of work** and the **conference peer-review process**, respectively. Position Papers should be read as arguments about what the community should do, rather than as ordinary method papers.

Sources: [ICML 2025 awards summary](https://aihub.org/2025/07/16/congratulations-to-the-icml2025-award-winners/) · [Curated ICML list](https://github.com/SarahRastegar/Best-Papers-Top-Venues#ICML)

### 2026: Challenging assumptions and improving sampling theory

| Paper | Official distinction | Main idea |
|---|---|---|
| [*The Flexibility Trap*](https://icml.cc/virtual/2026/oral/71086) | Outstanding Paper | Challenges an assumption about the value of arbitrary token generation order in diffusion language models. |
| [*High-Accuracy Sampling for Diffusion Models and Log-Concave Distributions*](https://icml.cc/virtual/2026/oral/71132) | Outstanding Paper | Gives high-accuracy sampling results with polylogarithmic dependence on the target error under the paper’s assumptions. |
| [*Position: The Alignment Community is Unintentionally Building a Censor’s Toolkit*](https://icml.cc/virtual/2026/oral/71119) | Outstanding Position Paper | Argues that alignment tools can also be repurposed for censorship. |
| [*Motion Attribution for Video Generation*](https://icml.cc/virtual/2026/oral/71049) | Outstanding Paper Honorable Mention | Studies attribution of motion in video generation. |
| [*To Grok Grokking: Provable Grokking in Ridge Regression*](https://icml.cc/virtual/2026/oral/71134) | Outstanding Paper Honorable Mention | Studies grokking in a theoretically analyzable ridge-regression setting. |

The official 2026 announcement describes a selection process that considered potential longevity, interest beyond a narrow subcommunity, and topic diversity. Those are useful signals for understanding what the committee valued that year; they are **not a formula for predicting future awards**.

Source: [ICML 2026 official award announcement](https://blog.icml.cc/2026/07/05/announcing-the-icml-2026-awards/)

---

## What can—and cannot—be inferred from Oral and Spotlight?

Oral and Spotlight papers are useful starting points for reading, but their selection should not be confused with proof of lasting influence.

Three cautions matter:

1. **Award status and presentation status are different labels.** A paper may have one, both, or neither.
2. **Terminology and counting conventions can vary by year.** Before adding Oral and Spotlight counts, check whether one is included in the other.
3. **The most visible paper at a conference is not necessarily the most influential ten years later.**

A practical reading strategy is therefore:

- Start with the official **Best / Outstanding Paper** list.
- Read later **Test of Time** selections to see which ideas proved durable.
- Sample **Oral / Spotlight** papers by research question, not only by popularity.
- Compare a paper’s claims with later replications, extensions, and limitations.

---

## Five research threads visible in the selected papers

These are interpretations of the selected examples above, not a statistical analysis of every ICML paper.

### 1. Strong results increasingly come with questions about their assumptions

The 2018 adversarial-defense paper and the 2019 disentanglement paper ask different questions, but share a habit: identify an assumption, then test whether a widely accepted conclusion depends on it.

### 2. Evaluation is itself a research contribution

If a metric cannot distinguish success from failure, a better model alone will not fix the scientific problem. Robustness, fairness, representation learning, and generative-model evaluation all illustrate this point.

### 3. Generative modeling has broadened from image generation to interaction and audit

PixelRNN, Genie, language-model watermarking, and diffusion-language-model research address different capabilities. Read together, they show a growing range of questions: what can be generated, controlled, attributed, or detected?

### 4. Theoretical and empirical papers remain complementary

ICML continues to recognize sampling theory, optimization, and statistical learning alongside large-scale generative systems. There is no single required combination of theory and experiments; the evidence should match the claim.

### 5. Social consequences are part of the research conversation

Fairness, privacy, the future of work, and the possible misuse of alignment methods show how machine learning papers can also ask who is affected by a technology and how.

---

## What this suggests for ICML 2027 submissions

ICML 2027 requires each submission to select **one primary Contribution Type**:

| Contribution Type | Primary focus |
|---|---|
| **General** | A contribution naturally evaluated under standard ML research expectations. |
| **Theory** | Mathematical results, analysis, proofs, or theoretical frameworks. |
| **Application-driven** | A meaningful real-world use case that substantially shapes the research. |
| **Concept and Feasibility** | A highly novel, potentially broad idea supported by convincing feasibility evidence. |
| **Negative Results** | A rigorous, informative negative finding that changes understanding of an important question. |
| **Datasets, Evaluations, and Benchmarks** | Resources, evaluation methods, metrics, audits, or data-centered analyses that advance scientific understanding. |
| **Position papers** | A defensible argument about what the community should do. |

These types **guide evaluation; they are not separate tracks or acceptance quotas**. A Theory paper may include experiments, and a Negative Results paper may propose a remedy. The selected type should reflect the paper’s primary contribution.

For Theory, the official guidance states that a paper does not need to beat empirical state of the art merely to be significant. Reviewers may nevertheless request appropriately scoped evidence when needed to interpret or validate its claims.

Source: [ICML 2027 Contribution Types](https://icml.cc/Conferences/2027/ContributionTypes)

### Important dates

According to the official schedule checked on **25 November 2026**:

| Milestone | Date |
|---|---|
| Abstract submission deadline | **14 January 2027, 11:59 p.m. AoE** |
| Full paper submission deadline | **22 January 2027, 11:59 p.m. AoE** |
| First-stage rejection notification | **23 February 2027** |
| Final decisions | **3 May 2027** |
| Conference | **31 July–6 August 2027, Rio de Janeiro** |

The main paper is limited to **eight pages**, with additional pages permitted for references, impact statement, and appendices under the call’s rules. Authors should recheck the official call and policy pages before submitting.

Sources: [ICML 2027 dates](https://icml.cc/Conferences/2027/Dates) · [ICML 2027 Call for Papers](https://icml.cc/Conferences/2027/CallForPapers)

---

## A writing checklist inspired by these papers

The following is a **personal synthesis**, not an official ICML requirement or a guaranteed route to an award.

1. **State a concrete claim.** What does the reader learn that could turn out to be false?
2. **Explain why the question matters.** Who would make a different research or practical decision if the claim is true?
3. **Identify the missing assumption.** Under what conditions does an existing conclusion fail or hold?
4. **Choose evidence that tests the central claim.** A decisive counterexample, a theorem, a controlled experiment, or a real-world evaluation may each be appropriate for different claims.
5. **Compare against the strongest relevant alternatives.** Include simple baselines and disclose differences in data, prior knowledge, and compute.
6. **Separate the result from its interpretation.** Report what was measured, what follows from it, and what remains unknown.
7. **Make limitations useful.** Explain where the result stops applying and which future test would challenge it.

> The most memorable research question is often not “Can we improve this score?” but “What does this score actually tell us?”

---

**Further reading**

- [ICML 2018 official awards](https://icml.cc/Conferences/2018/Awards)
- [ICML 2020 official awards](https://icml.cc/Conferences/2020/Awards)
- [ICML 2023 official awards](https://icml.cc/Conferences/2023/Awards)
- [ICML 2024 awards listing](https://icml.cc/virtual/2024/awards_detail)
- [ICML 2025 award summary](https://aihub.org/2025/07/16/congratulations-to-the-icml2025-award-winners/)
- [ICML 2026 official awards](https://blog.icml.cc/2026/07/05/announcing-the-icml-2026-awards/)
- [ICML 2027 Call for Papers](https://icml.cc/Conferences/2027/CallForPapers)
- [Best Papers of Top Venues — curated GitHub list](https://github.com/SarahRastegar/Best-Papers-Top-Venues#ICML)




<br><br><br><br><br><br><br><br><br><br>



## NIPS

- [2026 - Scaling](https://scholar.google.com.cu/citations?hl=en&user=2ZxBaA0AAAAJ&view_op=list_works&sortby=pubdate)
- [2026 - Fetch.ai: An Architecture for Modern Multi-Agent Systems](https://arxiv.org/pdf/2510.18699)


<br><br><br><br><br><br><br><br><br><br>


## Nature Portfolio

| Journal                               | Primary Scope                                             |   Journal Type | 2025 JIF | 2025 Five-Year JIF |
| ------------------------------------- | --------------------------------------------------------- | -------------: | -------: | -----------------: |
| Nature Reviews Cancer                 | Cancer biology, oncology, cancer prevention and treatment | Review-focused |     60.7 |               85.0 |
| Nature Reviews Materials              | Materials science and materials engineering               | Review-focused |     83.3 |              110.4 |
| Nature Reviews Drug Discovery         | Drug discovery, pharmaceutical research and development   | Review-focused |     91.2 |              131.3 |
| Nature Reviews Molecular Cell Biology | Molecular biology, cell biology and related technologies  | Review-focused |    118.0 |              147.0 |
| Nature Reviews Immunology             | Fundamental and clinical immunology                       | Review-focused |     47.1 |               73.8 |

<br>

| Journal                     | Primary Scope                                            |  Publishing Model | 2025 JIF | 2025 Five-Year JIF |
| --------------------------- | -------------------------------------------------------- | ----------------: | -------: | -----------------: |
| Nature Medicine             | Biomedical, translational and clinical research          |            Hybrid |     52.5 |               52.5 |
| Nature Biotechnology        | Biotechnology, bioengineering and technology translation |            Hybrid |     44.5 |               50.9 |
| Nature Materials            | Materials science and engineering                        |            Hybrid |     38.0 |               44.6 |
| Nature Energy               | Energy generation, storage, distribution and policy      |            Hybrid |     70.1 |               66.6 |
| Nature Nanotechnology       | Nanoscience and nanotechnology                           |            Hybrid |     37.5 |               42.6 |
| Nature Chemistry            | Chemistry and interdisciplinary chemical research        |            Hybrid |     24.5 |               24.0 |
| Nature Physics              | Fundamental and applied physics                          |            Hybrid |     18.0 |               21.5 |
| Nature Photonics            | Photonics, optics and light-based technologies           |            Hybrid |     38.1 |               39.5 |
| Nature Climate Change       | Climate science, impacts, mitigation and adaptation      |            Hybrid |     26.9 |               35.6 |
| Nature Neuroscience         | Fundamental and systems neuroscience                     |            Hybrid |     20.3 |               24.9 |
| Nature Genetics             | Genetics, genomics and functional genomics               |            Hybrid |     25.5 |               35.3 |
| Nature Machine Intelligence | Artificial intelligence, machine learning and robotics   |            Hybrid |     29.8 |               36.0 |
| Nature Communications       | Multidisciplinary natural, applied and health sciences   | Fully open access |     18.1 |               18.9 |

<br>

| Journal | Primary Scope             |              Journal Type | 2025 JIF | 2025 Five-Year JIF |
| ------- | ------------------------- | ------------------------: | -------: | -----------------: |
| Nature  | Multidisciplinary science | Flagship research journal |     56.1 |               56.7 |


<br><br>



## Science Family


| Journal                        | Primary Scope                                                                 |                   Publishing Model | 2025 JIF | 2025 Five-Year JIF |
| ------------------------------ | ----------------------------------------------------------------------------- | ---------------------------------: | -------: | -----------------: |
| Science Robotics               | Robotics, embodied intelligence, autonomous systems and bio-inspired machines | Subscription/hybrid-access journal |     25.5 |               33.3 |
| Science Translational Medicine | Translational medicine and clinically relevant biomedical research            | Subscription/hybrid-access journal |     15.6 |               16.8 |
| Science Immunology             | Fundamental, translational and clinical immunology                            | Subscription/hybrid-access journal |     16.4 |               17.5 |
| Science Advances               | Multidisciplinary science                                                     |                  Fully open access |     13.9 |               14.8 |
| Science Signaling              | Cellular signaling, regulatory biology, physiology and disease mechanisms     | Subscription/hybrid-access journal |      7.0 |                7.6 |



<br><br><br><br><br><br><br><br><br><br>


## TMLR, Journal of Machine Learning Research (JMLR)

- [2021 - Sparsity in Deep Learning: Pruning and Growth for Efficient Inference and Training in Neural Networks](https://www.jmlr.org/papers/volume22/21-0366/21-0366.pdf/)



<br><br><br>





<br><br>



## CVPR


## Models

| Concept / Model          | Original Paper / Key Reference                                        | Year | Organization / Research Team    |
| ------------------------ | --------------------------------------------------------------------- | ---- | ------------------------------- |
| GPT-5                    | No public architecture paper released (model announced Aug 7, 2025)   | 2025 | OpenAI                          |
| Claude 4 (Opus / Sonnet) | Claude 4 Model Card                                                   | 2025 | Anthropic                       |
| Claude (Model Series)    | Constitutional AI: Harmlessness from AI Feedback                      | 2022 | Anthropic (Yuntao Bai et al.)   |
| GPT-4                    | GPT-4 Technical Report                                                | 2023 | OpenAI                          |
| GPT-3                    | Language Models are Few-Shot Learners                                 | 2020 | OpenAI (Tom Brown et al.)       |
| LLaMA (Model Series)     | LLaMA: Open and Efficient Foundation Language Models                  | 2023 | Meta AI (FAIR)                  |
| CLIP                     | Learning Transferable Visual Models From Natural Language Supervision | 2021 | OpenAI (Alec Radford et al.)    |
| DALL·E                   | Zero-Shot Text-to-Image Generation                                    | 2021 | OpenAI (Aditya Ramesh et al.)   |
| DALL·E 2                 | Hierarchical Text-Conditional Image Generation with CLIP Latents      | 2022 | OpenAI (Aditya Ramesh et al.)   |
| Stable Diffusion         | High-Resolution Image Synthesis with Latent Diffusion Models          | 2022 | LMU Munich (CompVis) and Runway |




<br><br><br><br><br><br><br><br><br>
<br><br><br><br><br><br><br><br><br><br>



## ECCV

- [2024 - Oral - Minimalist Vision with Free form Pixels](https://eccv.ecva.net/virtual/2024/oral/147)
- [2022 - Best Papers and 📍 Demo On-device](https://eccv2022.ecva.net/files/2022/10/ECCV22-Awards.pdf)



<br><br><br><br>



## Classic LLM / NLP Milestones

| Field                        |                                                                                                                       Who |            When | What they proposed                           | Why it was proposed / core motivation                                                                                                                           |
| ---------------------------- | ------------------------------------------------------------------------------------------------------------------------: | --------------: | -------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Long-range Sequence Modeling |                                                                                   **Sepp Hochreiter, Jürgen Schmidhuber** |        **1997** | **LSTM**                                     | To address the vanishing-gradient problem in recurrent neural networks and learn long-term dependencies in sequences. ([ACL Anthology][1])                      |
| Word Representation          |                                                   **Tomas Mikolov, Kai Chen, Greg Corrado, Jeffrey Dean, Ilya Sutskever** |        **2013** | **Word2Vec / Skip-gram / Negative Sampling** | To learn efficient distributed word vectors that capture semantic and syntactic relationships while training quickly on large corpora. ([arXiv][2])             |
| Neural Machine Translation   |                                                                                **Ilya Sutskever, Oriol Vinyals, Quoc Le** |        **2014** | **Sequence-to-Sequence Learning**            | To map one sequence to another using neural networks, especially for machine translation, without hand-designed alignment rules. ([arXiv][3])                   |
| Attention Mechanism          |                                                                        **Dzmitry Bahdanau, Kyunghyun Cho, Yoshua Bengio** | **2014 / 2015** | **Neural Attention for Machine Translation** | To let the decoder dynamically focus on relevant source tokens, solving the bottleneck of compressing an entire sentence into one fixed vector.                 |
| Transformer                  | **Ashish Vaswani, Noam Shazeer, Niki Parmar, Jakob Uszkoreit, Llion Jones, Aidan Gomez, Łukasz Kaiser, Illia Polosukhin** |        **2017** | **Transformer**                              | To replace recurrence and convolution with self-attention, enabling parallel training and better long-range dependency modeling. ([papers.neurips.cc][4])       |
| Contextual Pretraining       |                                                          **Jacob Devlin, Ming-Wei Chang, Kenton Lee, Kristina Toutanova** |        **2018** | **BERT**                                     | To pretrain bidirectional language representations using masked language modeling, improving downstream NLP tasks through fine-tuning.                          |
| Generative Pretrained LM     |                                                                                           **Alec Radford et al., OpenAI** |        **2018** | **GPT-1**                                    | To show that unsupervised generative pretraining followed by supervised fine-tuning can produce strong NLP performance.                                         |
| Scaling Generative LM        |                                                                                           **Alec Radford et al., OpenAI** |        **2019** | **GPT-2**                                    | To show that larger autoregressive language models trained on broad web text can perform many tasks in a zero-shot style.                                       |
| Large-scale Few-shot LM      |                                                                                              **Tom Brown et al., OpenAI** |        **2020** | **GPT-3**                                    | To demonstrate that scaling parameters and data can produce strong in-context learning and few-shot generalization without task-specific fine-tuning.           |
| Instruction-following LLM    |                                                                                             **OpenAI / InstructGPT team** |        **2022** | **InstructGPT / RLHF alignment**             | To make pretrained language models follow human instructions more reliably by using supervised instruction data and reinforcement learning from human feedback. |
| Chat Interface LLM           |                                                                                                                **OpenAI** |        **2022** | **ChatGPT**                                  | To make LLMs usable through interactive dialogue, making instruction-following AI accessible to general users.                                                  |

[1]: https://aclanthology.org/D15-1280.pdf?utm_source=chatgpt.com "Multi-Timescale Long Short-Term Memory Neural Network ..."
[2]: https://arxiv.org/abs/1310.4546?utm_source=chatgpt.com "Distributed Representations of Words and Phrases and their Compositionality"
[3]: https://arxiv.org/abs/1409.3215?utm_source=chatgpt.com "Sequence to Sequence Learning with Neural Networks"
[4]: https://papers.neurips.cc/paper/7181-attention-is-all-you-need.pdf?utm_source=chatgpt.com "Attention is All you Need"



<br><br>


## Classic Computer Vision Milestones


| Field | Who | When | What they proposed | Core motivation |
|---|---|---:|---|---|
| Early Computer Vision | Lawrence G. Roberts | 1963 | *Machine Perception of Three-Dimensional Solids* | Infer 3D structure from 2D line drawings, establishing an early foundation of computer vision. |
| CNNs / Early Deep Vision | Yann LeCun, Léon Bottou, Yoshua Bengio, Patrick Haffner | 1998 | LeNet-5, *Gradient-Based Learning Applied to Document Recognition* | Recognize handwritten characters by learning spatial features through convolution, weight sharing, and backpropagation. |
| Large-Scale Deep Vision | Alex Krizhevsky, Ilya Sutskever, Geoffrey E. Hinton | 2012 | AlexNet, *ImageNet Classification with Deep Convolutional Neural Networks* | Scale deep CNNs to ImageNet using GPUs, ReLUs, and dropout, achieving a decisive ILSVRC 2012 victory. |
| Semantic Segmentation | Jonathan Long, Evan Shelhamer, Trevor Darrell | 2014–2015 | FCN, *Fully Convolutional Networks for Semantic Segmentation* | Convert classification networks into end-to-end, pixel-wise predictors that produce dense spatial outputs. |
| Biomedical Segmentation | Olaf Ronneberger, Philipp Fischer, Thomas Brox | 2015 | *U-Net: Convolutional Networks for Biomedical Image Segmentation* | Achieve precise biomedical segmentation with limited labeled data using contracting and expanding paths with skip connections. |
| Deep Residual Vision | Kaiming He, Xiangyu Zhang, Shaoqing Ren, Jian Sun | 2015–2016 | ResNet, *Deep Residual Learning for Image Recognition* | Make very deep networks easier to optimize by learning residual functions through identity shortcuts. |
| Object Detection | Shaoqing Ren, Kaiming He, Ross Girshick, Jian Sun | 2015 | *Faster R-CNN: Towards Real-Time Object Detection with Region Proposal Networks* | Replace external proposal methods with a Region Proposal Network that shares convolutional features with the detector. |
| Instance Segmentation | Kaiming He, Georgia Gkioxari, Piotr Dollár, Ross Girshick | 2017 | Mask R-CNN | Extend Faster R-CNN with a parallel branch that predicts a segmentation mask for each detected instance. |
| Vision Transformers | Alexey Dosovitskiy, Lucas Beyer, Alexander Kolesnikov, et al. | 2020–2021 | ViT, *An Image Is Worth 16×16 Words: Transformers for Image Recognition at Scale* | Represent images as sequences of patches and show that pure Transformers can rival CNNs when pretrained at scale. |
| Foundation Models for Segmentation | Alexander Kirillov, Eric Mintun, Nikhila Ravi, et al., Meta AI | 2023 | Segment Anything Model (SAM) | Build a promptable segmentation foundation model trained on 11 million images and more than 1 billion masks for zero-shot transfer to new images and tasks. |


<br><br><br><br>


## Pre-prints / Readings

- [2026 - Latentlens: Revealing Highly Interpretable Visual Tokens in LLMs](https://huggingface.co/papers/2602.00462)
- [2026 - You Cannot Feed Two Birds with One Score: the Accuracy-Naturalness Tradeoff in Translation](https://arxiv.org/abs/2503.24013)
- [2026 - Google Study Shows Quantum Computer Can Learn From Its Own Errors While It Computes](https://thequantuminsider.com/2026/07/10/google-study-shows-quantum-computer-can-learn-from-its-own-errors-while-it-computes/)



<br><br>









