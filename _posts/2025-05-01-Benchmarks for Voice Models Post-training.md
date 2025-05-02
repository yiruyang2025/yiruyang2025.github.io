---
layout: post
title: Benchmarks for Voice Models Post-training - 25
date: 2025-05-01
description: 🥥
categories: AI/ML
thumbnail: assets/img/9.jpg
images:
  lightbox2: true
  photoswipe: true
  spotlight: true
  venobox: true
---

Welcome ✨!  

This one is actually a little bit difficult for me to write, with aging, my short-term memory is no longer as good as it used to be :)<br><br>


# 1.Introduction<br><br>

Let's discuss the main benchmarking metrics used in current industry practice.<br><br><br><br>



# 2. Recent Benchmark Frameworks

## 2.1 Evaluation Metrics for Text-to-Speech (TTS)

| Year | Metric | Description | Typical Range |
|------|--------|-------------|---------------|
| 1996 | **MOS** (Mean Opinion Score) | ITU subjective naturalness & intelligibility test | 1–5 (↑ better) |
| 2001 | **PESQ** | Full-reference perceptual quality score (ITU P.862) | –0.5–4.5 (↑) |
| 2011 | **STOI** | Short-Time Objective Intelligibility predictor | 0–1 (↑) |
| 2004 | **MCD** | Mel-Cepstral Distortion (spectral distance) | <6 dB (↓) |
| 2003 | **F<sub>0</sub> RMSE** | Pitch-contour root-mean-square error | lower = better |
| 2019 | **MOSNet** | DNN that predicts MOS from speech | 1–5 (predicted) |
| 2020 | **DNSMOS** | No-reference MOS for noisy/enhanced speech | 1–5 (↑) |
| 2021 | **NISQA** | Multidimensional quality assessment via self-attention | 1–5 (↑) |
| 2023 | **VoiceMOS (Zero-shot)** | Out-of-domain MOS prediction challenge metric | 1–5 (↑) |
| 2024 | **MOSA-Net** | Multi-objective no-reference (quality + intelligibility + distortion) | metric-specific (↑) |
| 2024 | **DNSMOS-Pro** | Lightweight on-device variant of DNSMOS | 1–5 (↑) |


<br><br><br><br>

## 2.2 Evaluation Metrics for Voice Conversion (VC)

| Year | Metric | Description | Typical Range |
|------|--------|-------------|---------------|
| 1996 | **MOS** | Naturalness of converted speech | 1–5 (↑) |
| 2004 | **MCD** | Spectral distance between source & target | <6 dB (↓) |
| 2010 | **Speaker-ID Accuracy** | Listener/ASV target-speaker identification | 0–100 % (↑) |
| 2011 | **STOI / WER** | Intelligibility after conversion | metric-specific (↑) |
| 2018 | **x-vector Cos Sim.** | Cosine of deep speaker embeddings | 0–1 (↑) |
| 2019 | **ASV t-DCF / EER** | Spoof-aware ASV error from ASVspoof’19 | 0–1 (↓) |
| 2023 | **G-MOS** | Cross-domain crowd MOS (VoiceMOS’23) | 1–5 (↑) |
| 2024 | **SASV-EER** | Joint speaker-&-spoof error rate (SASV Challenge) | 0–1 (↓) |

<br><br><br><br>

## 2.3 Speech-to-Speech Translation (S2ST) Benchmarks

| Year | Metric | Description | Typical Range |
|------|--------|-------------|---------------|
| 1996 | **MOS** | Naturalness of translated speech | 1–5 (↑) |
| 2010 | **Speaker-ID Accuracy** | Identity retention across languages | 0–100 % (↑) |
| 2018 | **x-vector Cos Sim.** | Speaker-embedding match after translation | 0–1 (↑) |
| 2023 | **ASR-BLEU** | BLEU on ASR transcripts of output speech | 0–100 (↑) |
| 2024 | **BLASER 2.0** | Reference-free cross-modal quality metric | 0–1 (↑) |
| 2004 | **Spectral Distortion** | Frequency-content preservation | lower = better |



<br><br><br><br>


# 3.Specific Evaluation Frameworks for Disabled Users<br><br><br><br>















