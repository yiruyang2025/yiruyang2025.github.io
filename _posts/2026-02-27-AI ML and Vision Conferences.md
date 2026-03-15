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

| Pattern                  | Mathematical Form               | Time Complexity   | Core Data Structure                | Explanation                                  |
| ------------------------ | ------------------------------- | ----------------- | ---------------------------------- | -------------------------------------------- |
| Constant operation       | (c)                             | (O(1))            | Array / Variable                   | Execution time does not depend on input size |
| Single loop              | (\sum_{i=1}^{n} 1)              | (O(n))            | Array / List                       | One iteration per element                    |
| Nested loops             | (\sum_{i=1}^{n}\sum_{j=1}^{n}1) | (O(n^2))          | Matrix / 2D Array                  | Two loops over the same range                |
| Triangular loops         | (\sum_{i=1}^{n}\sum_{j=1}^{i}1) | (O(n^2))          | Array / Matrix                     | Inner loop grows with outer loop             |
| Logarithmic loop         | (n / 2^k = 1)                   | (O(\log n))       | Binary Search Tree / Sorted Array  | Halving each step (binary search)            |
| Exponential growth loop  | (2^k = n)                       | (O(\log n))       | Binary Tree                        | Doubling until reaching (n)                  |
| Divide and conquer       | (T(n)=T(n/2)+O(1))              | (O(\log n))       | Binary Tree                        | Recursive halving with constant work         |
| Binary search recurrence | (T(n)=T(n/2)+c)                 | (O(\log n))       | Sorted Array                       | Search in half of the array                  |
| Linear recursion         | (T(n)=T(n-1)+O(1))              | (O(n))            | Recursion Stack                    | Decrease problem size by 1 each step         |
| Merge sort recurrence    | (T(n)=2T(n/2)+O(n))             | (O(n\log n))      | Array / Merge Tree                 | Two subproblems plus merge cost              |
| Master theorem case 1    | (T(n)=aT(n/b)+O(n^c),\ a<b^c)   | (O(n^c))          | Recursive Tree                     | Work dominated by combine step               |
| Master theorem case 2    | (T(n)=aT(n/b)+O(n^c),\ a=b^c)   | (O(n^c\log n))    | Recursive Tree                     | Balanced recursion                           |
| Master theorem case 3    | (T(n)=aT(n/b)+O(n^c),\ a>b^c)   | (O(n^{\log_b a})) | Recursive Tree                     | Work dominated by recursion                  |
| Two-pointer technique    | (\sum_{i=1}^{n}1)               | (O(n))            | Array                              | Each pointer moves at most (n) times         |
| Sliding window           | (2n) operations                 | (O(n))            | Array / Queue                      | Each element enters and leaves window once   |
| Prefix sum construction  | (\sum_{i=1}^{n}1)               | (O(n))            | Array                              | Build cumulative array                       |
| Hash table operations    | average (1)                     | (O(1))            | Hash Table                         | Expected constant time lookup                |
| BFS / DFS                | (V+E)                           | (O(V+E))          | Graph (Adjacency List)             | Each vertex and edge visited once            |
| Dijkstra (heap)          | (E\log V)                       | (O(E\log V))      | Graph + Priority Queue (Heap)      | Priority queue operations                    |
| Union-Find (amortized)   | (\alpha(n))                     | (O(\alpha(n)))    | Disjoint Set Union                 | Inverse Ackermann function                   |
| Subset enumeration       | (2^n)                           | (O(2^n))          | Bitmask / Recursion Tree           | Each element chosen or not                   |
| Permutations             | (n!)                            | (O(n!))           | Recursion Tree                     | All orderings explored                       |
| Bitmask DP               | (n \cdot 2^n)                   | (O(n2^n))         | Bitmask / DP Table                 | DP over subsets                              |
| Floyd–Warshall           | (n^3)                           | (O(n^3))          | Matrix (Adjacency Matrix)          | Triple nested loops                          |
| Segment tree query       | (\log n)                        | (O(\log n))       | Segment Tree                       | Height of tree                               |
| Fenwick tree operations  | (\log n)                        | (O(\log n))       | Fenwick Tree (Binary Indexed Tree) | Binary indexed tree updates                  |


<br>




<br>


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


