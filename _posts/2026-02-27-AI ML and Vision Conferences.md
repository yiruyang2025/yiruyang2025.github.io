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


- [Blog 1](https://braydenzhang.com/blog/a-collection-of-cool-companies-(to-me))


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





<br>

## Millennium Prize Problems


| **Problem Name**                               | **Field**                  | **Core Nature**                  | **Fundamental Question**                                                              |
| ---------------------------------------------- | -------------------------- | -------------------------------- | ------------------------------------------------------------------------------------- |
| **Riemann Hypothesis**                         | Number Theory              | Structure of prime numbers       | Do prime numbers follow a hidden regularity? (Primes as the “atoms” of mathematics)   |
| **P vs NP Problem**                            | Computer Science / Logic   | Complexity of computation        | If verifying a solution is easy, is finding it also easy?                             |
| **Navier–Stokes Existence and Smoothness**     | Fluid Dynamics             | Behavior of turbulence           | Do solutions to fluid equations always remain smooth, or can singularities form?      |
| **Yang–Mills Existence and Mass Gap**          | Quantum Physics / Geometry | Origin of mass in quantum fields | Why do elementary particles have mass, and how can this be rigorously explained?      |
| **Hodge Conjecture**                           | Algebraic Geometry         | Structure of geometric spaces    | Can complex geometric objects be decomposed into simpler algebraic components?        |
| **Birch and Swinnerton-Dyer (BSD) Conjecture** | Algebraic Number Theory    | Arithmetic of elliptic curves    | Is there a deep connection between rational points and special values of L-functions? |


<br><br>


## ICML vs. NeurIPS vs. ICLR

| Conference | Full Name                                            | Founded                                                                                         | Core Positioning                                                                             | Strongest Research Fit                                                                                                                                                   | Typical Review Emphasis                                                                                                                              |
| ---------- | ---------------------------------------------------- | ----------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------- |
| ICML       | International Conference on Machine Learning         | Originated in 1980 as the International Workshop on Machine Learning; later developed into ICML | Foundational machine-learning methods, theory, and algorithms                                | Statistical learning, optimization, reinforcement learning, probabilistic methods, generalization, causality, and principled ML algorithms                               | Technical correctness, methodological novelty, rigorous assumptions, theoretical or empirical justification, and broad relevance to machine learning |
| NeurIPS    | Conference on Neural Information Processing Systems  | Founded in 1987                                                                                 | Broad interdisciplinary flagship conference for machine learning and artificial intelligence | Deep learning, ML theory, reinforcement learning, generative models, neuroscience, AI for science, datasets, systems, responsible AI, and interdisciplinary applications | Novelty, significance, technical quality, empirical strength, reproducibility, clarity, and potential impact across a broad research community       |
| ICLR       | International Conference on Learning Representations | First held in 2013                                                                              | Leading venue for representation learning and frontier deep-learning research                | Neural architectures, self-supervised learning, generative models, foundation models, multimodal learning, optimization, and representation learning                     | Originality, conceptual clarity, strong experiments, meaningful ablations, reproducibility, and clear discussion through the OpenReview process      |




<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>







## ICLR

- [2025 - Representation Alignment for Generation: Training Diffusion Transformers Is Easier Than You Think](https://sihyun.me/REPA/), ICLR'25 Oral
- [2026 - Continuous control with deep reinforcement learning(DDPG)](https://patents.google.com/patent/US20170024643A1/en), Test of Time 2026

<br><br><br><br><br><br>



## ICLR Best / Outstanding Papers (2017 - 2026)

| Year     | Representative Best / Outstanding Paper Topics                                                | Representative Authors                                                         | Representative Institutions                                                                |
| -------- | --------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------ |
| **2026** | Transformer theory; Multi-turn LLM reasoning                                                  | Pascal Bergsträßer, Ryan Cotterell, Anthony Widjaja Lin; Philippe Laban et al. | ETH Zurich, University of Zurich, Salesforce AI Research, Purdue University ([ICLR][1]) |
| **2025** | LLM alignment; Fine-tuning dynamics; Model editing                                            | Multiple award-winning teams                                                   | Princeton, CMU, UC Berkeley, Google DeepMind, NUS, Microsoft Research ([ICLR][2])       |
| **2024** | Diffusion models; World models; Long-context models; Vision Transformers; Protein generation  | Darcet et al., Yang et al., Mallat group, others                               | Meta AI, Google DeepMind, NYU, UC Berkeley, MILA                                           |
| **2023** | Text-to-3D; Graph learning; Dense prediction; Embodied AI                                     | Hong et al., He et al., Poole et al.                                           | Google Research, Meta FAIR, KAIST, Peking University, Georgia Tech                         |
| **2022** | Diffusion sampling; Differential privacy; Graph theory; Neural collapse; Meta-learning        | Bao et al., Papernot et al., Donoho et al.                                     | Tsinghua University, Google Research, Stanford University, Meta FAIR                       |
| **2021** | Score-based diffusion; Graph neural simulation; Neural architecture search; Speech generation | Yang Song et al., Battaglia et al.                                             | Stanford University, Google Research, DeepMind, Meta FAIR                                  |
| **2020** | No official Best Paper Award                                                                  | —                                                                              | —                                                                                          |
| **2019** | Lottery Ticket Hypothesis; Ordered Neurons                                                    | Jonathan Frankle, Michael Carbin; Yikang Shen et al.                           | MIT, MILA, Université de Montréal ([ICLR][3])                                              |
| **2018** | Continual Meta-Learning                                                                       | Maruan Al-Shedivat et al.                                                      | OpenAI, UC Berkeley                                                                        |
| **2017** | Generalization theory; Privacy-preserving learning; Deep learning theory                      | Chiyuan Zhang et al., Nicolas Papernot et al.                                  | Google Brain, UC Berkeley, OpenAI                                                          |

[1]: https://blog.iclr.cc/2026/04/23/announcing-the-iclr-2026-outstanding-papers/?utm_source=chatgpt.com "Announcing the ICLR 2026 Outstanding Papers"
[2]: https://blog.iclr.cc/2025/04/22/announcing-the-outstanding-paper-awards-at-iclr-2025/?utm_source=chatgpt.com "Announcing the Outstanding Paper Awards at ICLR 2025"
[3]: https://iclr.cc/Conferences/2019/Awards?utm_source=chatgpt.com "Best Paper Award"



<br><br>

## ICLR Oral Research Topics


| Period        | Dominant Oral Topics                        | Representative Keywords                                                                                                                                                                     |
| ------------- | ------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **2017–2019** | Deep Learning Foundations                   | Generalization, Optimization, Theory, Privacy, Lottery Ticket, RNNs                                                                                                                         |
| **2020–2021** | Representation Learning & Generative Models | Self-Supervised Learning, Diffusion Models, Graph Neural Networks, Neural Simulation, Neural Architecture Search                                                                            |
| **2022–2023** | Foundation Generative Models                | Diffusion, Text-to-3D, Scientific Machine Learning, Protein Modeling, Graph Learning, Embodied AI                                                                                           |
| **2024–2026** | Foundation Models & AI Agents               | Large Language Models, AI Agents, Long-Context Modeling, Alignment, Safety, Model Editing, Vision-Language Models, World Models, Robotics, Transformer Theory, Mechanistic Interpretability |



<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>


## ICML


- [2024 - Some Lessons from Adversarial Machine Learning](https://nicholas.carlini.com/), Alignment, Nicholas Carlini
- [2020 - Are we done with ImageNet?](https://arxiv.org/abs/2006.07159), [Lukas Beyer](https://lucasb.eyer.be/)'s blog

<br><br><br><br><br><br><br><br><br><br>



## NIPS

- [2026 - Scaling](https://scholar.google.com.cu/citations?hl=en&user=2ZxBaA0AAAAJ&view_op=list_works&sortby=pubdate)
- [2026 - Fetch.ai: An Architecture for Modern Multi-Agent Systems](https://arxiv.org/pdf/2510.18699)
- [2026 - SLAM Library](https://gtsam.org/)

<br><br><br><br><br><br><br><br><br><br>






## TMLR, Journal of Machine Learning Research (JMLR)

- [2021 - Sparsity in Deep Learning: Pruning and Growth for Efficient Inference and Training in Neural Networks](https://www.jmlr.org/papers/volume22/21-0366/21-0366.pdf/)



<br><br><br>



## AAAI






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


| Field                          |                                                           Who |            When | What they proposed                               | Why it was proposed / core motivation                                                                                                                                                                           |
| ------------------------------ | ------------------------------------------------------------: | --------------: | ------------------------------------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Early Computer Vision          |                                       **Lawrence G. Roberts** |        **1963** | *Machine Perception of Three-Dimensional Solids* | To make machines infer 3D structure from 2D visual input; this is often treated as one of the earliest foundations of computer vision. ([dspace.mit.edu][1])                                                    |
| CNN / Early Deep Vision        |   **Yann LeCun, Léon Bottou, Yoshua Bengio, Patrick Haffner** |        **1998** | **LeNet-5**                                      | To recognize handwritten digits using convolution, weight sharing, and backpropagation; it showed that neural networks could learn spatial visual features.                                                     |
| Large-scale Deep Vision        |          **Alex Krizhevsky, Ilya Sutskever, Geoffrey Hinton** |        **2012** | **AlexNet**                                      | To scale CNNs to large ImageNet classification using GPUs, ReLU, dropout, and deep convolutional layers; it made deep learning dominant in vision. ([NeurIPS][2])                                         |
| Semantic Segmentation          |             **Jonathan Long, Evan Shelhamer, Trevor Darrell** | **2014 / 2015** | **Fully Convolutional Network, FCN**             | To convert classification CNNs into end-to-end pixel-wise prediction models for semantic segmentation. Their key idea was to make CNNs output dense spatial maps instead of one image-level label. ([arXiv][3]) |
| Biomedical Segmentation        |            **Olaf Ronneberger, Philipp Fischer, Thomas Brox** |        **2015** | **U-Net**                                        | To solve biomedical image segmentation with few labeled samples. U-Net used a contracting path for context and an expanding path for precise localization. ([arXiv][4])                                         |
| Deep Residual Vision           |         **Kaiming He, Xiangyu Zhang, Shaoqing Ren, Jian Sun** | **2015 / 2016** | **ResNet**                                       | To make very deep neural networks easier to train by learning residual functions instead of direct mappings; this addressed optimization degradation in deep networks. ([arXiv][5])                             |
| Object Detection               |         **Shaoqing Ren, Kaiming He, Ross Girshick, Jian Sun** |        **2015** | **Faster R-CNN**                                 | To make object detection faster and more accurate by introducing Region Proposal Networks instead of relying on slow external proposal methods.                                                                 |
| Instance Segmentation          | **Kaiming He, Georgia Gkioxari, Piotr Dollár, Ross Girshick** |        **2017** | **Mask R-CNN**                                   | To extend object detection into instance segmentation by adding a mask prediction branch for each detected object.                                                                                              |
| Vision Transformer             |                                 **Alexey Dosovitskiy et al.** |        **2020** | **ViT, Vision Transformer**                      | To show that pure Transformers can process images as sequences of patches and compete with CNNs when trained at scale. ([arXiv][6])                                                                             |
| Foundation Vision Segmentation |                        **Alexander Kirillov et al., Meta AI** |        **2023** | **Segment Anything Model, SAM**                  | To build a promptable general-purpose segmentation foundation model, enabling masks from clicks, boxes, or text-like prompts across many image domains.                                                         |

[1]: https://dspace.mit.edu/handle/1721.1/11589?utm_source=chatgpt.com "Machine perception of three-dimensional solids"
[2]: https://proceedings.neurips.cc/paper/4824-imagenet-classification-with-deep-convolutional-neural-networks.pdf?utm_source=chatgpt.com "ImageNet Classification with Deep Convolutional Neural ..."
[3]: https://arxiv.org/abs/1411.4038?utm_source=chatgpt.com "Fully Convolutional Networks for Semantic Segmentation"
[4]: https://arxiv.org/abs/1505.04597?utm_source=chatgpt.com "U-Net: Convolutional Networks for Biomedical Image Segmentation"
[5]: https://arxiv.org/abs/1512.03385?utm_source=chatgpt.com "[1512.03385] Deep Residual Learning for Image Recognition - arXiv"
[6]: https://arxiv.org/abs/2010.11929?utm_source=chatgpt.com "An Image is Worth 16x16 Words: Transformers for Image Recognition at Scale"




<br><br><br><br>


## Pre-prints / Readings

- [2026 - Latentlens: Revealing Highly Interpretable Visual Tokens in LLMs](https://huggingface.co/papers/2602.00462)
- [2026 - You Cannot Feed Two Birds with One Score: the Accuracy-Naturalness Tradeoff in Translation](https://arxiv.org/abs/2503.24013)
- [2026 - Google Study Shows Quantum Computer Can Learn From Its Own Errors While It Computes](https://thequantuminsider.com/2026/07/10/google-study-shows-quantum-computer-can-learn-from-its-own-errors-while-it-computes/)



<br><br>









