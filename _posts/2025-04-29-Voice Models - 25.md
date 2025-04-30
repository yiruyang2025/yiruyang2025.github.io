---
layout: post
title: Voice Models - 25
date: 2025-04-29
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

Let's start with Hearing Assistance<br><br><br><br>

# 0. Some Background Knowledge<br><br>


Voice models are AI systems that process or generate human speech.Core AI Techniques used are listed as below:

| Technique                   | Purpose                                                             |
|----------------------------|----------------------------------------------------------------------|
| **RNN / LSTM**             | Early sequence modeling in ASR & TTS                                 |
| **CNNs**                   | Feature extraction from spectrograms                                 | 
| **Transformers**           | Parallel processing, great for long-range speech dependencies        |
| **Diffusion Models**       | High-quality, controllable generation (recent TTS trend)             |
| **Self-supervised Pretraining** | Efficient training on large unlabeled datasets                  |

<br><br><br><br>

Core Evolution of Voice Models:

| Year | Milestone                        | Model / Paper                                                     |
|------|----------------------------------|-------------------------------------------------------------------|
| 2014 | End-to-end ASR                   | DeepSpeech ([Hannun et al.](https://arxiv.org/abs/1412.5567))     |
| 2017 | Tacotron (neural TTS)            | Tacotron ([Wang et al.](https://arxiv.org/abs/1703.10135))        |
| 2019 | Real-time voice synthesis        | FastSpeech ([Ren et al.](https://arxiv.org/abs/1905.09263))       |
| 2020 | Self-supervised speech learning  | wav2vec 2.0 ([Baevski et al.](https://arxiv.org/abs/2006.11477))  |
| 2021 | Multilingual speech models       | Whisper (OpenAI, 2022)                                            |
| 2023–2024 | Diffusion-based TTS         | FastDiff ([Huang et al.](https://arxiv.org/abs/2305.10973))       |

<br><br><br><br>

# 1. Latest Models in Industry<br><br>

**1.1 Google Sound Amplifier, 2019**
  - [Sound Amplifier](https://play.google.com/store/apps/details?id=com.google.android.accessibility.soundamplifier)
  - [AudioEffect API](https://developer.android.com/reference/android/media/audiofx/AudioEffect)<br><br>
 
**1.2 Rogervoice, 2014**
  - [Rogervoice](https://rogervoice.com/)
  - [GitHub repository](https://github.com/rogervoice)<br><br>

**1.3 Pedius, 2013**
  - [Pedius](https://www.pedius.org/zh/zhuye/)<br><br><br><br>



# 2. Model Training and The Key Challenges<br><br>

**2.1 Pre-training with text**

- 2023. [Spirit LM: Interleaved Spoken and Written Language Model](https://arxiv.org/abs/2402.05755)
- 2024. [OpenAI - Navigating the Challenges and Opportunities of Synthetic Voices](https://openai.com/index/navigating-the-challenges-and-opportunities-of-synthetic-voices/)
- 2023. [Toward Joint Language Modeling for Speech Units and Text](https://arxiv.org/abs/2310.08715)
- 2022. [Dialogue GSLM](https://arxiv.org/abs/2203.16502)<br><br><br><br>


**2.2 Challenges in the Post-Training**<br><br><br><br>




# 3. ✨Possible Improvements to the Foundation Models / During Fine-tuning📍<br><br><br><br>


**3.1 Catastrophic Forgetting**

- 2024. [Scaling Laws for Forgetting When Fine-Tuning Large Language Models](https://arxiv.org/abs/2401.05605)
- 2023. [An Empirical Study of Catastrophic Forgetting in Large Language Models During Continual Fine-tuning](https://arxiv.org/abs/2308.08747)
- 2024. [LoRA Learns Less and Forgets Less](https://arxiv.org/abs/2405.09673)<br><br><br><br>

**Possible Solutions🪨 - Stone Age of AI**

- ✨2018. [The Natural Language Decathlon: Multitask Learning as Question Answering](https://arxiv.org/abs/1806.08730)<br><br><br><br>



**3.2 Safety Alignment**

- 2024. [Safety-Tuned LLaMAs: Lessons From Improving the Safety of Large Language Models that Follow Instructions](https://arxiv.org/abs/2309.07875)<br><br><br><br>


**3.3 -**

- 2024. [Dynamic-SUPERB Phase-2: A Collaboratively Expanding Benchmark for Measuring the Capabilities of Spoken Language Models with 180 Tasks
](https://arxiv.org/abs/2411.05361)<br><br><br><br>



# 4. Recent Technical Advances<br><br>

- 2023. [Speak, Read and Prompt: High-Fidelity Text-to-Speech with Minimal Supervision](https://direct.mit.edu/tacl/article/doi/10.1162/tacl_a_00618/118854)
- 2014, [Deep Speech: Scaling up end-to-end speech recognition](https://arxiv.org/abs/1412.5567)<br><br><br><br>




# 5. Products for Disabled People<br><br><br><br>







# 6. Speech Processing Labs<br><br><br><br>




# 7. Others<br><br>

**7.1 ASR: Automatic Speech Recognition**
  - [Whisper - OpenAI](https://github.com/openai/whisper)


**7.2 TTS: Text-to-Speech**
  - [Tacotron2 - Google](https://github.com/Rayhane-mamah/Tacotron-2)


**7.3 Voice Cloning / Real-Time TTS**
  - [ElevenLabs](https://elevenlabs.io/)
  - [Real-Time Voice Cloning](https://github.com/CorentinJ/Real-Time-Voice-Cloning)


**7.4 Emotion & Multi-speaker TTS**
  - [ChatTTS - 中英对话](https://github.com/2noise/ChatTTS)
  - [OpenVoice](https://github.com/myshell-ai/OpenVoice)

**7.5 Audio Agents**
  - [GPT-4 Turbo with Audio](https://openai.com/gpt-4-turbo/)
  - [FunAudioLLM](https://github.com/FunAudioLLM)  <br><br><br><br>



# References

- Hung-yi Lee - [yyds - hopefully one day also in English](https://www.youtube.com/watch?v=Z6b5-77EfGk&t=1453s)<br><br><br><br>




