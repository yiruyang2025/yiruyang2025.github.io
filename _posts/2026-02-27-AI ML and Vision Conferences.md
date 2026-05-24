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


<br><br>



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

**dumb syntax**
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


## Shortest Path Algorithms

| Scenario                                             | Algorithm           | Core Principle                                       | Mathematical Formulation                                                                                       | Time Complexity                  | When to Use                        |
| ---------------------------------------------------- | ------------------- | ---------------------------------------------------- | -------------------------------------------------------------------------------------------------------------- | -------------------------------- | ---------------------------------- |
| Single-source shortest path with negative edges      | Bellman–Ford        | Repeated edge relaxation until convergence           | Relaxation rule: $$d(v) = \min(d(v), d(u) + w(u,v))$$ applied for all edges                                    | $$O(VE)$$                        | Graphs with negative edge weights  |
| Single-source shortest path (optimized Bellman–Ford) | SPFA                | Queue-based relaxation to reduce unnecessary updates | Same relaxation rule: $$d(v) = \min(d(v), d(u) + w(u,v))$$ but only nodes whose distance changed are processed | Average $$O(E)$$ worst $$O(VE)$$ | Sparse graphs with negative edges  |
| All-pairs shortest path (dense graph)                | Floyd–Warshall      | Dynamic programming over intermediate vertices       | Recurrence: $$d_{ij}^{(k)} = \min(d_{ij}^{(k-1)},\ d_{ik}^{(k-1)} + d_{kj}^{(k-1)})$$                          | $$O(V^3)$$                       | Dense graphs or small vertex count |
| All-pairs shortest path (sparse graph)               | Johnson’s Algorithm | Reweight edges to remove negatives then run Dijkstra | Reweight: $$w'(u,v) = w(u,v) + h(u) - h(v)$$ where $$h(v)$$ from Bellman–Ford                                  | $$O(VE + V^2 \log V)$$           | Sparse graphs with negative edges  |


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



<br>




<br>




<br><br><br><br><br><br><br><br>


## ICLR

- [2025 - Representation Alignment for Generation: Training Diffusion Transformers Is Easier Than You Think](https://sihyun.me/REPA/), ICLR'25 Oral
- [2026 - Continuous control with deep reinforcement learning(DDPG)](https://patents.google.com/patent/US20170024643A1/en), Test of Time 2026

<br><br><br><br><br><br><br><br><br><br>



## ICML


- [2024 - Some Lessons from Adversarial Machine Learning](https://nicholas.carlini.com/), Alignment, Nicholas Carlini
- [2020 - Are we done with ImageNet?](https://arxiv.org/abs/2006.07159), [Lukas Beyer](https://lucasb.eyer.be/)'s blog

<br><br><br><br><br><br><br><br><br><br>



## NIPS

- [2026 - Scaling](https://scholar.google.com.cu/citations?hl=en&user=2ZxBaA0AAAAJ&view_op=list_works&sortby=pubdate)
- [2026 - Fetch.ai: An Architecture for Modern Multi-Agent Systems](https://arxiv.org/pdf/2510.18699)
- [2026 - SLAM Library](https://gtsam.org/)

<br><br><br><br><br><br><br><br><br><br>




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



## Journal of Machine Learning Research (JMLR)

- [2021 - Sparsity in Deep Learning: Pruning and Growth for Efficient Inference and Training in Neural Networks](https://www.jmlr.org/papers/volume22/21-0366/21-0366.pdf/)



<br>





<br><br><br><br><br><br><br><br><br>


## Millennium Prize Problems


| **Problem Name**                               | **Field**                  | **Core Nature**                  | **Fundamental Question**                                                              |
| ---------------------------------------------- | -------------------------- | -------------------------------- | ------------------------------------------------------------------------------------- |
| **Riemann Hypothesis**                         | Number Theory              | Structure of prime numbers       | Do prime numbers follow a hidden regularity? (Primes as the “atoms” of mathematics)   |
| **P vs NP Problem**                            | Computer Science / Logic   | Complexity of computation        | If verifying a solution is easy, is finding it also easy?                             |
| **Navier–Stokes Existence and Smoothness**     | Fluid Dynamics             | Behavior of turbulence           | Do solutions to fluid equations always remain smooth, or can singularities form?      |
| **Yang–Mills Existence and Mass Gap**          | Quantum Physics / Geometry | Origin of mass in quantum fields | Why do elementary particles have mass, and how can this be rigorously explained?      |
| **Hodge Conjecture**                           | Algebraic Geometry         | Structure of geometric spaces    | Can complex geometric objects be decomposed into simpler algebraic components?        |
| **Birch and Swinnerton-Dyer (BSD) Conjecture** | Algebraic Number Theory    | Arithmetic of elliptic curves    | Is there a deep connection between rational points and special values of L-functions? |




<br><br><br><br><br><br><br><br><br>




## ECCV

- [2024 - Oral - Minimalist Vision with Free form Pixels](https://eccv.ecva.net/virtual/2024/oral/147)
- [2022 - Best Papers and 📍 Demo On-device](https://eccv2022.ecva.net/files/2022/10/ECCV22-Awards.pdf)



<br><br><br><br><br>






<br><br><br><br><br>




## CVPR


<br><br><br><br><br><br><br><br><br><br>






## Pre-prints / Readings

- [2026 - Latentlens: Revealing Highly Interpretable Visual Tokens in LLMs](https://huggingface.co/papers/2602.00462)
- [2026 - You Cannot Feed Two Birds with One Score: the Accuracy-Naturalness Tradeoff in Translation](https://arxiv.org/abs/2503.24013)




<br><br><br><br><br><br><br><br><br><br>



