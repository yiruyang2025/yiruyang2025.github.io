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
- [2026 - PyViz3D](https://github.com/francisengelmann/PyViz3D)


<br><br><br><br><br><br><br><br><br><br>


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

## O(xx)

| Pattern                  | Mathematical Form                | Time Complexity   | Core Data Structure                | Explanation                                    |
| ------------------------ | -------------------------------- | ----------------- | ---------------------------------- | ---------------------------------------------- |
| Constant operation       | (c)                              | (O(1))            | Array / Variable                   | Execution time does not depend on input size   |
| Single loop              | (\sum_{i=1}^{n} 1)               | (O(n))            | Array / List                       | One iteration per element                      |
| Nested loops             | (\sum_{i=1}^{n}\sum_{j=1}^{n} 1) | (O(n^2))          | Matrix / 2D Array                  | Two loops over the same range                  |
| Triangular loops         | (\sum_{i=1}^{n}\sum_{j=1}^{i} 1) | (O(n^2))          | Array / Matrix                     | Inner loop grows with the outer loop           |
| Logarithmic loop         | ( \frac{n}{2^k} = 1 )            | (O(\log n))       | Binary Search Tree / Sorted Array  | Problem size halves each step (binary search)  |
| Exponential growth loop  | (2^k = n)                        | (O(\log n))       | Binary Tree                        | Value doubles until reaching (n)               |
| Divide and conquer       | (T(n)=T(n/2)+O(1))               | (O(\log n))       | Binary Tree                        | Recursive halving with constant work           |
| Binary search recurrence | (T(n)=T(n/2)+c)                  | (O(\log n))       | Sorted Array                       | Each step searches half of the array           |
| Linear recursion         | (T(n)=T(n-1)+O(1))               | (O(n))            | Recursion Stack                    | Problem size decreases by one each step        |
| Merge sort recurrence    | (T(n)=2T(n/2)+O(n))              | (O(n\log n))      | Array / Merge Tree                 | Two recursive calls plus linear merge          |
| Master theorem case 1    | (T(n)=aT(n/b)+O(n^c),\ a<b^c)    | (O(n^c))          | Recursion Tree                     | Work dominated by the combine step             |
| Master theorem case 2    | (T(n)=aT(n/b)+O(n^c),\ a=b^c)    | (O(n^c\log n))    | Recursion Tree                     | Balanced recursion tree                        |
| Master theorem case 3    | (T(n)=aT(n/b)+O(n^c),\ a>b^c)    | (O(n^{\log_b a})) | Recursion Tree                     | Work dominated by recursive calls              |
| Two-pointer technique    | (\sum_{i=1}^{n} 1)               | (O(n))            | Array                              | Each pointer moves at most (n) times           |
| Sliding window           | (2n) operations                  | (O(n))            | Array / Queue                      | Each element enters and leaves the window once |
| Prefix sum construction  | (\sum_{i=1}^{n} 1)               | (O(n))            | Array                              | Build cumulative prefix array                  |
| Hash table operations    | average (1)                      | (O(1))            | Hash Table                         | Expected constant-time lookup                  |
| BFS / DFS                | (V+E)                            | (O(V+E))          | Graph (Adjacency List)             | Each vertex and edge visited once              |
| Dijkstra (heap)          | (E\log V)                        | (O(E\log V))      | Graph + Priority Queue (Heap)      | Heap operations for extracting minimum         |
| Union-Find (amortized)   | (\alpha(n))                      | (O(\alpha(n)))    | Disjoint Set Union                 | Inverse Ackermann function complexity          |
| Subset enumeration       | (2^n)                            | (O(2^n))          | Bitmask / Recursion Tree           | Each element chosen or skipped                 |
| Permutations             | (n!)                             | (O(n!))           | Recursion Tree                     | Explore all orderings                          |
| Bitmask DP               | (n \cdot 2^n)                    | (O(n2^n))         | Bitmask / DP Table                 | Dynamic programming over subsets               |
| Floyd–Warshall           | (n^3)                            | (O(n^3))          | Matrix (Adjacency Matrix)          | Triple nested loops over vertices              |
| Segment tree query       | (\log n)                         | (O(\log n))       | Segment Tree                       | Height of the tree                             |
| Fenwick tree operations  | (\log n)                         | (O(\log n))       | Fenwick Tree (Binary Indexed Tree) | Binary indexed updates and prefix queries      |

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


<br><br><br><br><br><br><br><br><br>


## ICLR

- [2025 - Representation Alignment for Generation: Training Diffusion Transformers Is Easier Than You Think](https://sihyun.me/REPA/), ICLR'25 Oral

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



<br>














<br><br><br><br><br><br><br><br><br>




## ECCV

- [2024 - Oral - Minimalist Vision with Free form Pixels](https://eccv.ecva.net/virtual/2024/oral/147)
- [2022 - Best Papers](https://eccv2022.ecva.net/files/2022/10/ECCV22-Awards.pdf)



<br><br><br><br><br>






<br><br><br><br><br>




## CVPR


<br><br><br><br><br><br><br><br><br><br>






## Pre-prints / Readings

- [2026 - Latentlens: Revealing Highly Interpretable Visual Tokens in LLMs](https://huggingface.co/papers/2602.00462)
- [2026 - You Cannot Feed Two Birds with One Score: the Accuracy-Naturalness Tradeoff in Translation](https://arxiv.org/abs/2503.24013)




<br><br><br><br><br><br><br><br><br><br>


