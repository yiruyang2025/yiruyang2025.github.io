---
layout: page
title: 2026 - Master Thesis - Symphony Music
description: Continuous Tokenization from Transformer, Jyrki, AI Center
img: assets/img/4.jpg
importance: 7
category: work
related_publications: true
---

<br>




## References 1

- [2015 - BiternionNets: continuous head orientation from discrete labels](https://x.com/giffmana/status/2059356284525195308?s=20)
- [2025 - Who Invented Transformer Neural Networks?](https://people.idsia.ch/~juergen/who-invented-transformer-neural-networks.html)
- [1960 - A new approach to linear filtering and prediction problems](https://cds.cern.ch/record/434680), Kalman, R E
- 📍 [2021 - A Mathematical Framework for Transformer Circuits](https://transformer-circuits.pub/2021/framework/index.html), Anthropic
- [2026 - Do Value Vectors in Deep Layers Need Context from the 📍 Residual Stream?](https://x.com/giffmana/status/2060633524487487972?s=46&t=1tqSPaJVuc_ns2oTMZs8EQ), [2](https://x.com/hemuyu0327/status/2060779481032450309?s=46&t=1tqSPaJVuc_ns2oTMZs8EQ), AI/ML
- [2026 - Looping Transformers for Multi-View 3D Reconstruction](https://x.com/tobiasfischer11/status/2060825255640256661?s=46&t=1tqSPaJVuc_ns2oTMZs8EQ), [2](https://research.nvidia.com/labs/dvl/projects/dvlt/) Vision Task, Zan Gojcic (*Nvidia Zurich)



<br><br><br><br><br><br><br><br>



## Arts

<br>

## Audio (Symphony Music Generation)

- [📍 Viola the Bird](https://artsandculture.google.com/experiment/viola-the-bird/nAEJVwNkp-FnrQ?hl=en), Google Arts & Culture
- [🇨🇭Bird Sounds Swiss](https://bird-song.ch/)


- []


<br><br><br><br><br><br><br><br><br><br>


## Pinao



- [Keith Jarrett - Over the Rainbow (Tokyo 1984) [Restored]](https://www.youtube.com/watch?v=AyLQGDIrGcI&list=WL)



<br><br><br><br><br><br><br><br><br><br>


## Violin


<br><br><br><br><br><br><br><br><br><br>



## Cello






<br><br><br><br><br><br><br><br><br><br>


<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>



## Techniques

<br>

## Tokenization



|  Year | Method                                                  | Core Mechanism                                                                                 | Key Contribution                                                                                                         | Paradigm Shift                                                                |
| ----: | ------------------------------------------------------- | ---------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------ | ----------------------------------------------------------------------------- |
|  1994 | **Byte Pair Encoding (BPE, original)**                  | Data compression by repeatedly replacing the most frequent adjacent symbol pair                | Introduced BPE as a generic compression algorithm, later repurposed for subword tokenization                             | From explicit symbols to frequency-driven compression                         |
| 1990s | **Rule-based / WordPunct tokenization**                 | Deterministic splitting using whitespace, punctuation, and hand-written rules                  | Provided simple and interpretable preprocessing for early NLP pipelines                                                  | Language-specific linguistic heuristics                                       |
|  2012 | **Dictionary-based segmentation**                       | Lexicon lookup and morphological rules, especially for languages without whitespace boundaries | Enabled practical CJK segmentation through curated dictionaries and statistical heuristics, e.g. Jieba-style pipelines   | From universal whitespace splitting to language-specific segmentation         |
|  2015 | **Subword BPE**                                         | Iterative frequency-based merging of character or symbol pairs                                 | Adapted BPE to neural machine translation, reducing the out-of-vocabulary problem by representing rare words as subwords | From word-level vocabularies to open-vocabulary subwords                      |
|  2016 | **WordPiece**                                           | Greedy subword construction guided by likelihood improvement                                   | Used in Google NMT and later BERT-style models; selects subword units that better explain the training corpus            | From frequency-only merging to likelihood-aware vocabulary learning           |
|  2018 | **SentencePiece**                                       | Language-agnostic tokenization directly from raw text                                          | Removed the need for external pre-tokenization; treats whitespace as a normal symbol and supports multilingual pipelines | From preprocessing-dependent tokenization to raw-text tokenization            |
|  2018 | **Unigram Language Model tokenization**                 | Probabilistic subword model with vocabulary pruning based on likelihood                        | Learns a distribution over possible segmentations and supports subword regularization through sampling                   | From deterministic segmentation to probabilistic tokenization                 |
|  2019 | **Byte-level BPE**                                      | BPE over byte sequences rather than Unicode characters                                         | Used in GPT-2; guarantees full coverage of arbitrary text without unknown tokens                                         | From Unicode/token coverage issues to universal byte-level coverage           |
|  2021 | **High-performance BPE implementations, e.g. tiktoken** | Optimized byte-level BPE encoding and decoding                                                 | Improved tokenization throughput and latency for large-scale training and inference systems                              | From tokenization as preprocessing to tokenization as systems infrastructure  |
| 2024+ | **Tokenizer-free / byte-level modeling**                | Direct modeling of bytes, patches, or low-level discrete streams                               | Attempts to remove fixed token boundaries and reduce information loss introduced by handcrafted tokenizers               | From compressed symbolic units to end-to-end learned sequence representations |


<br>


| Stage                              | Dominant Assumption                                                  | Failure Mode                                                                        | Representative Methods                                   |
| ---------------------------------- | -------------------------------------------------------------------- | ----------------------------------------------------------------------------------- | -------------------------------------------------------- |
| **Rule-based tokenization**        | Words are linguistically separable units                             | Fails on OOV words, morphology, multilingual text, and scripts without whitespace   | WordPunct, whitespace splitting, dictionary segmentation |
| **Subword tokenization**           | Frequent character patterns form reusable semantic units             | Still imposes fixed segmentation and can fragment rare or multilingual terms poorly | BPE, WordPiece, Unigram LM                               |
| **Language-agnostic tokenization** | Raw text should be processed without language-specific preprocessing | Vocabulary learning still depends on corpus statistics and tokenizer design         | SentencePiece, byte-level BPE                            |
| **Systems-optimized tokenization** | Tokenization must be fast enough for large-scale deployment          | Compression efficiency and semantic granularity may conflict                        | tiktoken-style optimized BPE                             |
| **Tokenizer-free modeling**        | Token boundaries should be learned or avoided entirely               | Longer sequences increase compute cost and make modeling harder                     | byte-level LMs, patch/byte sequence models               |








<br><br><br><br><br><br><br><br><br><br>
<br><br><br><br><br>

<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>





<br><br><br><br><br><br><br>

## References 2

- [2026 - Anny-One Dataset](https://europe.naverlabs.com/research/human-centric-computer-vision/anny-one/)
- [2023 - PaLM-E: An Embodied Multimodal Language Model](https://palm-e.github.io/)

<br><br>
