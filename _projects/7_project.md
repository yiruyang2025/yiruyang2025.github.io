---
layout: page
title: 2026 - Important Thesis - Symphonic Music Generation
description: Continuous Tokenization from Transformer, Jyrki, Industry, Arnout (ETH AI Center)
img: assets/img/4.jpg
importance: 7
category: work
related_publications: true
---

<br>




## References 1



- 📍 [2017 - Guetzli: Perceptually Guided JPEG Encoder](https://arxiv.org/pdf/1703.04421), J. Alakuijala
- [2015 - BiternionNets: continuous head orientation from discrete labels](https://x.com/giffmana/status/2059356284525195308?s=20)
- [2025 - Who Invented Transformer Neural Networks?](https://people.idsia.ch/~juergen/who-invented-transformer-neural-networks.html)
- [1960 - A new approach to linear filtering and prediction problems](https://cds.cern.ch/record/434680), Kalman, R E
- 📍 [2021 - A Mathematical Framework for Transformer Circuits](https://transformer-circuits.pub/2021/framework/index.html), Anthropic
- [2026 - Do Value Vectors in Deep Layers Need Context from the Residual Stream?](https://x.com/giffmana/status/2060633524487487972?s=46&t=1tqSPaJVuc_ns2oTMZs8EQ), [2](https://x.com/hemuyu0327/status/2060779481032450309?s=46&t=1tqSPaJVuc_ns2oTMZs8EQ), AI/ML
- [Classic Prediction Models](https://www.linkedin.com/feed/update/urn:li:groupPost:961087-7468905210048884736/?utm_source=share&utm_medium=member_ios&rcm=ACoAAC5vvBgB20VgN9iW9bBoWdHZWq21kkV22wk)
- [2018 - Enabling Factorized Piano Music Modeling and Generation with the MAESTRO Dataset](https://arxiv.org/abs/1810.12247), Google Brain, Deepmind
- [András Schiff](https://www.youtube.com/watch?v=5gTA5q6eqyo&list=PLfo_f-OJyxFhfov3m9Zgypsi4DBJ4bNba)


<br><br><br><br><br><br><br><br>


## Evaluation

| Context                       | Correct Term              |
| ----------------------------- | ------------------------- |
| Image generation              | **FID**                   |
| Audio / music generation      | **FAD**                   |
| General mathematical distance | **Fréchet Distance / FD** |


<br><br><br><br><br><br><br><br>


## Loss for Music Generation

* Music generation requires losses at multiple levels because the model must learn **audio fidelity**, **spectral accuracy**, **temporal coherence**, and **text-music alignment**.

| Loss Type                           | Formula                                                                                                 | Training Stage                                                  | Used In                                                                     | Core Function                                                                                                     |
| ----------------------------------- | ------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------- | --------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------- |
| **Reconstruction Loss**             | ( \mathcal{L}_{rec}=\lVert x-\hat{x}\rVert_1 \quad \text{or} \quad \lVert x-\hat{x}\rVert_2^2 )         | Autoencoder / codec training; supervised reconstruction         | VAE, VQ-VAE, EnCodec, SoundStream, diffusion decoder                        | Reconstructs the original waveform or latent representation and preserves timbre, pitch, and local audio details. |
| **Log-Mel Spectrogram Loss**        | ( \mathcal{L}_{mel}=\lVert \mathrm{Mel}(x)-\mathrm{Mel}(\hat{x})\rVert_1 )                              | Audio decoder / vocoder training                                | HiFi-GAN, diffusion vocoder, neural codec decoder                           | Matches the generated audio to the real audio in the frequency domain, improving perceptual quality.              |
| **Adversarial Loss**                | ( \mathcal{L}_{adv}=-\mathbb{E}[D(\hat{x})] )                                                           | GAN-based waveform or spectrogram generation                    | HiFi-GAN, MusicGen decoder variants, neural vocoders                        | Makes generated music sound more realistic by training a discriminator to distinguish real from generated audio.  |
| **Feature Matching Loss**           | ( \mathcal{L}_{fm}=\sum_l \lVert D_l(x)-D_l(\hat{x})\rVert_1 )                                          | Stable GAN / vocoder training                                   | HiFi-GAN, Multi-Scale / Multi-Period Discriminator systems                  | Matches hidden-layer features between real and generated audio, stabilizing GAN training and improving texture.   |
| **Diffusion Noise Prediction Loss** | ( \mathcal{L}*{diff}=\lVert \epsilon-\epsilon*\theta(z_t,t,c)\rVert_2^2 )                               | Diffusion model training                                        | AudioLDM, Stable Audio, diffusion-based music generation                    | Trains the model to denoise noisy latent or audio representations step by step.                                   |
| **Autoregressive Token Loss**       | ( \mathcal{L}*{AR}=-\sum_t \log p*\theta(y_t \mid y_{<t}, c) )                                          | Token-level sequence modeling                                   | MusicGen, MusicLM-style token models, Transformer decoders                  | Trains the model to predict the next music token, preserving temporal order and musical structure.                |
| **Consistency Loss**                | ( \mathcal{L}*{con}=\mathrm{KL}\left(p*\theta(y_t \mid c),\Vert,p_\theta(y_{t+k} \mid c)\right) )       | Long-sequence training / structure regularization               | Long-form music generation, hierarchical Transformers, diffusion refinement | Prevents rhythm, harmony, and musical form from collapsing over long generations.                                 |
| **CLAP / Contrastive Loss**         | ( \mathcal{L}_{CLAP}=-\log \frac{\exp(\mathrm{sim}(a,t)/\tau)}{\sum_j \exp(\mathrm{sim}(a,t_j)/\tau)} ) | Audio-text pretraining or text-conditioned generation alignment | CLAP, AudioLDM, text-to-music systems                                       | Aligns generated audio with the text prompt, such as “Mozart style,” “cinematic orchestral,” or “jazz piano.”     |

<br>

## Final Objective

A modern music generation model usually combines several losses:

[
\mathcal{L}_{total}
===================

\lambda_{rec}\mathcal{L}*{rec}
+
\lambda*{mel}\mathcal{L}*{mel}
+
\lambda*{adv}\mathcal{L}*{adv}
+
\lambda*{fm}\mathcal{L}*{fm}
+
\lambda*{seq}\mathcal{L}*{AR/diff}
+
\lambda*{align}\mathcal{L}_{CLAP}
]

In practice, different stages use different losses:

| Training Stage                          | Main Losses                                             | Purpose                                                           |
| --------------------------------------- | ------------------------------------------------------- | ----------------------------------------------------------------- |
| **Audio codec / autoencoder training**  | Reconstruction Loss + Log-Mel Loss                      | Learn a compact continuous or discrete audio representation.      |
| **Vocoder / decoder training**          | Log-Mel Loss + Adversarial Loss + Feature Matching Loss | Convert latent or audio tokens back into a high-quality waveform. |
| **Autoregressive music-token training** | Cross-Entropy / Next-Token Loss                         | Learn musical sequence structure over time.                       |
| **Diffusion music generation**          | Noise Prediction Loss                                   | Learn iterative denoising from noise to music.                    |
| **Text-to-music alignment**             | CLAP / Contrastive Loss                                 | Ensure the generated music follows the text prompt.               |
| **Long-form generation refinement**     | Consistency Loss                                        | Maintain rhythm, harmony, and structure across long sequences.    |


<br><br><br><br><br><br><br>



<br>



## Audio (Symphony Music Generation)



- [Viola the Bird](https://artsandculture.google.com/experiment/viola-the-bird/nAEJVwNkp-FnrQ?hl=en)




<br><br><br><br><br><br><br><br><br><br>



## Violin


<br><br><br><br><br><br><br><br><br><br>



## Cello






<br><br><br><br><br><br><br><br><br><br>



## Others



- [Keith Jarrett - Over the Rainbow (Tokyo 1984) [Restored]](https://www.youtube.com/watch?v=AyLQGDIrGcI&list=WL)
- [1851 - Franz Liszt - Campanella](https://www.youtube.com/watch?v=H1Dvg2MxQn8)
- [2019 - Lang Lang – Bach: The Well-Tempered Clavier: Book 1, 1.Prelude C Major, BWV 846]

<br><br><br><br><br><br><br><br><br><br>


<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>




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

- ASL / RSL
- [2023 - PaLM-E: An Embodied Multimodal Language Model](https://palm-e.github.io/)

<br><br>
