# Awesome Omni Models [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

A curated list of **omni-modal** models: models that understand and/or generate across **text, image, video, audio and speech**. The list covers any-to-any multimodal LLMs, audio-visual understanding models, unified visual understanding and generation models, speech and audio language models, joint audio-video generators, plus the benchmarks and surveys that study them.

Entries within each section are sorted newest first. Dates are the first arXiv version (YYYY-MM), or the dated official release/model card when there is no paper. For API-only entries, release dates were checked against official changelogs; dated snapshots are used when a separate release date is unavailable. Modality shorthand: **T** text, **I** image, **V** video, **A** audio/speech.

**Stats:** 920 model, method & dataset entries · 157 benchmarks · 37 surveys. Last researched: 2026-10-06. Counts are table entries, including related methods and systems.

Contributions are welcome. Please open a PR that adds the paper to the right section in date order, with arXiv and code links.

**AI Usage:** Recent updates are curated using AI Agents such as Claude Code and Codex.

## Contents

- [Any-to-Any Omni Models](#any-to-any-omni-models)
  - [Research & Open Models](#research--open-models)
  - [Proprietary Models (Reports & Model Cards)](#proprietary-models-reports--model-cards)
- [Omni-Modal Understanding (Audio-Visual LLMs)](#omni-modal-understanding-audio-visual-llms)
  - [Models](#models)
  - [Reasoning, RL \& Post-Training](#reasoning-rl--post-training)
- [Unified Visual Understanding \& Generation](#unified-visual-understanding--generation)
  - [Unified Models](#unified-models)
  - [Related: Generation-Centric \& Post-Training Works](#related-generation-centric--post-training-works)
  - [Specialized Unified Models](#specialized-unified-models)
- [Speech \& Audio Language Models](#speech--audio-language-models)
  - [Spoken Dialogue \& Full-Duplex Models](#spoken-dialogue--full-duplex-models)
  - [Unified Audio Generation \& Understanding](#unified-audio-generation--understanding)
  - [Audio Understanding \& Reasoning](#audio-understanding--reasoning)
- [Multimodal Generation (Audio-Video \& Any-to-Any Diffusion)](#multimodal-generation-audio-video--any-to-any-diffusion)
  - [Joint Audio-Video Generation](#joint-audio-video-generation)
  - [Cross-Modal Audio ↔ Video Generation](#cross-modal-audio--video-generation)
  - [Any-to-Any Diffusion Models](#any-to-any-diffusion-models)
  - [Proprietary Audio-Video Generators](#proprietary-audio-video-generators)
- [Efficiency, Tokenization & Serving](#efficiency-tokenization--serving)
  - [Efficiency & Serving](#efficiency--serving)
  - [Unified Tokenizers & Encoders](#unified-tokenizers--encoders)
  - [Datasets & Data Pipelines](#datasets--data-pipelines)
- [Benchmarks](#benchmarks)
  - [Omni-Modal \& Audio-Visual Benchmarks](#omni-modal--audio-visual-benchmarks)
  - [Unified Understanding \& Generation Benchmarks](#unified-understanding--generation-benchmarks)
  - [Audio-Video Generation Benchmarks](#audio-video-generation-benchmarks)
  - [Speech \& Audio Benchmarks](#speech--audio-benchmarks)
- [Surveys](#surveys)
- [Earlier Related Works](#earlier-related-works)
- [Coverage & Search Notes](#coverage--search-notes)

---

## Any-to-Any Omni Models

### Research & Open Models

Includes research systems and open releases. A paper listing does not imply that weights, training data or inference code have been released.

| Date | Model | Paper | Modalities (in → out) | Code |
|:---:|---|---|---|:---:|
| 2026-09 | **Realtime-Venus-Omni** | [Realtime-Venus: A full-duplex interaction system with asynchronous delegation](https://arxiv.org/abs/2609.13814) | Streaming V, A → T, speech; asynchronous agent backend | — |
| 2026-09 | **Qwen3.8-Omni** | [Qwen3.8-Omni: Towards Native Omni-Modal Agents](https://arxiv.org/abs/2609.25611) | T, I, V, A → T (+ speech) | — |
| 2026-08 | **Motion-Omni** | [Motion-Omni: End-to-End Joint Speech and Full-Body Motion for Spoken Dialogue](https://arxiv.org/abs/2609.04250) | Speech, T → T, speech, body motion | [GitHub](https://github.com/step-out/Motion-Omni) |
| 2026-08 | **Ex-Omni-2D** | [Ex-Omni-2D: Expressive Omni-Modal Dialogue Models with Native Visual Presence](https://arxiv.org/abs/2608.10720) | T, I, A → T, speech, avatar video | — |
| 2026-07 | **Wan-Streamer v0.2** | [Wan-Streamer v0.2: Higher Resolution, Same Latency](https://arxiv.org/abs/2607.04443) | T, V, A → T, V, A; higher-resolution streaming interaction | [Project](https://wan-streamer.com/) |
| 2026-06 | **Wan-Streamer v0.1** | [Wan-Streamer v0.1: End-to-end Real-time Interactive Foundation Models](https://arxiv.org/abs/2606.25041) | T, V, A → T, V, A; native streaming duplex interaction | [Project](https://wan-streamer.com/) |
| 2026-06 | **FacePlex** | [FacePlex: Toward Natural Full-Duplex Conversational Avatars](https://arxiv.org/abs/2606.30145) | Speech dialogue → speech, facial motion, rendered avatar | [Project](https://hahminlew.github.io/faceplex) |
| 2026-06 | **DuplexOmni** | [DuplexOmni: Real-Time Listening, Seeing, Thinking, and Speaking for Full-Duplex Interaction](https://arxiv.org/abs/2606.09186) | Streaming V, A → T, speech; full-duplex | — |
| 2026-06 | **DyaPlex** | [DyaPlex: Full-Duplex Speech-Motion Model for Dyadic Interaction](https://arxiv.org/abs/2606.03874) | Speech, motion → speech, motion; full-duplex | — |
| 2026-06 | **Moshi-Face** | [Integrating Facial Generation into Full-Duplex Spoken Dialogue Systems](https://arxiv.org/abs/2606.21970) | Speech, facial expressions → speech, facial motion | — |
| 2026-06 | **Cosmos 3** | [Cosmos 3: Omnimodal World Models for Physical AI](https://arxiv.org/abs/2606.02800) | T, I, V, A, action → T, I, V, A, action | [GitHub](https://github.com/nvidia/cosmos) |
| 2026-05 | **Archon** | [Archon: A Unified Multimodal Model for Holistic Digital Human Generation](https://arxiv.org/abs/2605.30311) | T, A, motion, visual content → digital-human multimodal outputs | [Project](https://zju3dv.github.io/archon/) |
| 2026-05 | **MiniMind-O** | [MiniMind-O Technical Report: An Open Small-Scale Speech-Native Omni Model](https://arxiv.org/abs/2605.03937) | T, speech, I → T, speech | [GitHub](https://github.com/jingyaogong/minimind-o) |
| 2026-04 | **Omni (Context Unrolling)** | [Context Unrolling in Omni Models](https://arxiv.org/abs/2604.21921) | T, I, V, 3D → T, I, V, 3D | — |
| 2026-04 | **MiniCPM-o 4.5** | [MiniCPM-o 4.5: Towards Real-Time Full-Duplex Omni-Modal Interaction](https://arxiv.org/abs/2604.27393) | T, I, V, A → T, speech | [GitHub](https://github.com/OpenBMB/MiniCPM-o) |
| 2026-04 | **Qwen3.5-Omni** | [Qwen3.5-Omni Technical Report](https://arxiv.org/abs/2604.15804) | T, I, V, A → T, speech | — |
| 2026-04 | **Audio-Omni** | [Audio-Omni: Extending Multi-modal Understanding to Versatile Audio Generation and Editing](https://arxiv.org/abs/2604.10708) | T, I, V, A → T, audio (sound/music/speech) | — |
| 2026-03 | **LongCat-Next** | [LongCat-Next: Lexicalizing Modalities as Discrete Tokens](https://arxiv.org/abs/2603.27538) | T, I, A → T, I, speech; discrete autoregression | [GitHub](https://github.com/meituan-longcat/LongCat-Next) |
| 2026-03 | **Dynin-Omni** | [Dynin-Omni: Omnimodal Unified Large Diffusion Language Model](https://arxiv.org/abs/2604.00007) | T, I, V, speech → T, I, speech | [GitHub](https://github.com/AIDASLab/Dynin-Omni) |
| 2026-03 | **Speech-Omni-Lite** | [Speech-Omni-Lite: Portable Speech Interfaces for Vision-Language Models](https://arxiv.org/abs/2603.09627) | T, I, speech → T, speech | — |
| 2026-03 | **Omni-Diffusion** | [Omni-Diffusion: Unified Multimodal Understanding and Generation with Masked Discrete Diffusion](https://arxiv.org/abs/2603.06577) | T, I, speech → T, I, speech | [GitHub](https://github.com/VITA-MLLM/Omni-Diffusion) |
| 2026-02 | **U-Mind** | [U-Mind: A Unified Framework for Real-Time Multimodal Interaction with Audiovisual Generation](https://arxiv.org/abs/2602.23739) | Multimodal dialogue → T, speech, avatar motion/video (pipeline) | — |
| 2026-02 | **A²-LLM** | [A$^2$-LLM: An End-to-end Conversational Audio Avatar Large Language Model](https://arxiv.org/abs/2602.04913) | Conversational audio → speech, 3D facial motion | — |
| 2026-02 | **EmoOmni** | [EmoOmni: Bridging Emotional Understanding and Expression in Omni-Modal LLMs](https://arxiv.org/abs/2602.21900) | T, I/V, A → T, speech | — |
| 2026-02 | **Ming-flash-omni 2.0** | [Ming-flash-omni 2.0 (model release)](https://github.com/inclusionAI/Ming) | T, I, V, A → T, I, speech | [GitHub](https://github.com/inclusionAI/Ming) |
| 2026-02 | **Ex-Omni** | [Ex-Omni: Enabling 3D Facial Animation Generation for Omni-modal Large Language Models](https://arxiv.org/abs/2602.07106) | T, I, A → T, speech, 3D face | — |
| 2026-02 | **ERNIE 5.0** | [ERNIE 5.0 Technical Report](https://arxiv.org/abs/2602.04705) | T, I, V, A → T, I, V, A | — |
| 2026-01 | **AR-Omni** | [AR-Omni: A Unified Autoregressive Model for Any-to-Any Generation](https://arxiv.org/abs/2601.17761) | T, I, speech → T, I, speech | — |
| 2026-01 | **HyperCLOVA X 8B Omni** | [HyperCLOVA X 8B Omni](https://arxiv.org/abs/2601.01792) | T, A, V → T, A, V | — |
| 2025-12 | **JavisGPT** | [JavisGPT: A Unified Multi-modal LLM for Sounding-Video Comprehension and Generation](https://arxiv.org/abs/2512.22905) | T, V, A → T, sounding video | [GitHub](https://github.com/JavisVerse/JavisGPT) |
| 2025-11 | **Uni-MoE-2.0-Omni** | [Uni-MoE-2.0-Omni: Scaling Language-Centric Omnimodal Large Model with Advanced MoE, Training and Data](https://arxiv.org/abs/2511.12609) | T, I, V, A → T, I, speech | [GitHub](https://github.com/HITsz-TMG/Uni-MoE) |
| 2025-10 | **LongCat-Flash-Omni** | [LongCat-Flash-Omni Technical Report](https://arxiv.org/abs/2511.00279) | T, I, V, A → T, speech | [GitHub](https://github.com/meituan-longcat/LongCat-Flash-Omni) |
| 2025-10 | **Ming-Flash-Omni** | [Ming-Flash-Omni: A Sparse, Unified Architecture for Multimodal Perception and Generation](https://arxiv.org/abs/2510.24821) | T, I, V, A → T, I, speech | [GitHub](https://github.com/inclusionAI/Ming) |
| 2025-10 | **RoboOmni** | [RoboOmni: Proactive Robot Manipulation in Omni-modal Context](https://arxiv.org/abs/2510.23763) | V, speech, sound → speech, action | [GitHub](https://github.com/OpenMOSS/RoboOmni) |
| 2025-10 | **VITA-E** | [VITA-E: Natural Embodied Interaction with Concurrent Seeing, Hearing, Speaking, and Acting](https://arxiv.org/abs/2510.21817) | V, speech → speech, action | [GitHub](https://github.com/Tencent/VITA/tree/VITA-E) |
| 2025-10 | **InteractiveOmni** | [InteractiveOmni: A Unified Omni-modal Model for Audio-Visual Multi-turn Dialogue](https://arxiv.org/abs/2510.13747) | T, I, V, A → T, speech | [GitHub](https://github.com/SenseTime-FVG/InteractiveOmni) |
| 2025-10 | **NExT-OMNI** | [NExT-OMNI: Towards Any-to-Any Omnimodal Foundation Models with Discrete Flow Matching](https://arxiv.org/abs/2510.13721) | T, I, V, A → T, I, A | — |
| 2025-09 | **MGM-Omni** | [MGM-Omni: Scaling Omni LLMs to Personalized Long-Horizon Speech](https://arxiv.org/abs/2509.25131) | T, I, V, A → T, speech | [GitHub](https://github.com/dvlab-research/MGM-Omni) |
| 2025-09 | **X-Streamer** | [X-Streamer: Unified Human World Modeling with Audiovisual Interaction](https://arxiv.org/abs/2509.21574) | T, speech, V → T, speech, talking video | — |
| 2025-09 | **Qwen3-Omni** | [Qwen3-Omni Technical Report](https://arxiv.org/abs/2509.17765) | T, I, V, A → T, speech | [GitHub](https://github.com/QwenLM/Qwen3-Omni) |
| 2025-06 | **Stream-Omni** | [Stream-Omni: Simultaneous Multimodal Interactions with Large Language-Vision-Speech Model](https://arxiv.org/abs/2506.13642) | T, I/V, speech → T, speech | [GitHub](https://github.com/ictnlp/Stream-Omni) |
| 2025-06 | **Ming-Omni** | [Ming-Omni: A Unified Multimodal Model for Perception and Generation](https://arxiv.org/abs/2506.09344) | T, I, V, A → T, I, speech | [GitHub](https://github.com/inclusionAI/Ming) |
| 2025-06 | **RoboEgo (FLM-Ego)** | [RoboEgo System Card: An Omnimodal Model with Native Full Duplexity](https://arxiv.org/abs/2506.01934) | V, A, T → T, speech (full-duplex) | — |
| 2025-03 | **Qwen2.5-Omni** | [Qwen2.5-Omni Technical Report](https://arxiv.org/abs/2503.20215) | T, I, V, A → T, speech | [GitHub](https://github.com/QwenLM/Qwen2.5-Omni) |
| 2025-03 | **MoshiVis** | [Vision-Speech Models: Teaching Speech Models to Converse about Images](https://arxiv.org/abs/2503.15633) | I, speech → T, speech | [GitHub](https://github.com/kyutai-labs/moshivis) |
| 2025-03 | **ViSpeak** | [ViSpeak: Visual Instruction Feedback in Streaming Videos](https://arxiv.org/abs/2503.12769) | V, A, T → T, speech | [GitHub](https://github.com/HumanMLLM/ViSpeak) |
| 2025-02 | **Nexus-O** | [Nexus: An Omni-Perceptive And -Interactive Model for Language, Audio, And Vision](https://arxiv.org/abs/2503.01879) | T, I, V, A → T, speech | [GitHub](https://github.com/HiThink-Research/NEXUS-O) |
| 2025-02 | **M2-omni** | [M2-omni: Advancing Omni-MLLM for Comprehensive Modality Support with Competitive Performance](https://arxiv.org/abs/2502.18778) | T, I, V, A → T, I, A | — |
| 2025-02 | **Ola** | [Ola: Pushing the Frontiers of Omni-Modal Language Model with Progressive Modality Alignment](https://arxiv.org/abs/2502.04328) | T, I, V, A → T, speech | [GitHub](https://github.com/Ola-Omni/Ola) |
| 2025-01 | **Baichuan-Omni-1.5** | [Baichuan-Omni-1.5 Technical Report](https://arxiv.org/abs/2501.15368) | T, I, V, A → T, speech | [GitHub](https://github.com/baichuan-inc/Baichuan-Omni-1.5) |
| 2025-01 | **MiniCPM-o 2.6** | [MiniCPM-o 2.6: A GPT-4o Level MLLM for Vision, Speech, and Multimodal Live Streaming on Your Phone (blog)](https://openbmb.notion.site/MiniCPM-o-2-6-A-GPT-4o-Level-MLLM-for-Vision-Speech-and-Multimodal-Live-Streaming-on-Your-Phone-185ede1b7a558042b5d5e45e6b237da9) | T, I, V, A → T, speech | [GitHub](https://github.com/OpenBMB/MiniCPM-o) |
| 2025-01 | **OpenOmni** | [OpenOmni: Advancing Open-Source Omnimodal Large Language Models with Progressive Multimodal Alignment and Real-Time Self-Aware Emotional Speech Synthesis](https://arxiv.org/abs/2501.04561) | T, I, speech → T, speech | [GitHub](https://github.com/RainBowLuoCS/OpenOmni) |
| 2025-01 | **VITA-1.5** | [VITA-1.5: Towards GPT-4o Level Real-Time Vision and Speech Interaction](https://arxiv.org/abs/2501.01957) | T, I, V, speech → T, speech | [GitHub](https://github.com/VITA-MLLM/VITA) |
| 2024-12 | **Lyra** | [Lyra: An Efficient and Speech-Centric Framework for Omni-Cognition](https://arxiv.org/abs/2412.09501) | T, I, V, A → T, speech | [GitHub](https://github.com/dvlab-research/Lyra) |
| 2024-12 | **IXC2.5-OmniLive** | [InternLM-XComposer2.5-OmniLive: A Comprehensive Multimodal System for Long-term Streaming Video and Audio Interactions](https://arxiv.org/abs/2412.09596) | V, A → T, speech | [GitHub](https://github.com/InternLM/InternLM-XComposer) |
| 2024-12 | **MuMu-LLaMA** | [MuMu-LLaMA: Multi-modal Music Understanding and Generation via Large Language Models](https://arxiv.org/abs/2412.06660) | T, I, V, music → T, music | [GitHub](https://github.com/shansongliu/MuMu-LLaMA) |
| 2024-11 | **SOLAMI** | [SOLAMI: Social Vision-Language-Action Modeling for Immersive Interaction with 3D Autonomous Characters](https://arxiv.org/abs/2412.00174) | speech, motion → speech, 3D motion | — |
| 2024-11 | **Spider** | [Spider: Any-to-Many Multimodal LLM](https://arxiv.org/abs/2411.09439) | T, I, V, A → T, I, V, A | [GitHub](https://github.com/Layjins/Spider) |
| 2024-11 | **Omni 4.5B SLM** | [Towards Multi-Modal Mastery: A 4.5B Parameter Truly Multi-Modal Small Language Model](https://arxiv.org/abs/2411.05903) | T, I, V, A → multiple | — |
| 2024-10 | **Mini-Omni2** | [Mini-Omni2: Towards Open-source GPT-4o with Vision, Speech and Duplex Capabilities](https://arxiv.org/abs/2410.11190) | T, I, speech → T, speech | [GitHub](https://github.com/gpt-omni/mini-omni2) |
| 2024-09 | **EMOVA** | [EMOVA: Empowering Language Models to See, Hear and Speak with Vivid Emotions](https://arxiv.org/abs/2409.18042) | T, I, speech → T, speech | [GitHub](https://github.com/emova-ollm/EMOVA) |
| 2024-09 | **MIO** | [MIO: A Foundation Model on Multimodal Tokens](https://arxiv.org/abs/2409.17692) | T, I, V, speech → T, I, V, speech | [GitHub](https://github.com/MIO-Team/MIO) |
| 2024-08 | **VITA** | [VITA: Towards Open-Source Interactive Omni Multimodal LLM](https://arxiv.org/abs/2408.05211) | T, I, V, A → T (speech via TTS) | [GitHub](https://github.com/VITA-MLLM/VITA) |
| 2024-08 | **UnifiedMLLM** | [UnifiedMLLM: Enabling Unified Representation for Multi-modal Multi-tasks With Large Language Model](https://arxiv.org/abs/2408.02503) | T, I, V, A → T, I, V, A (via experts) | [GitHub](https://github.com/lzw-lzw/UnifiedMLLM) |
| 2024-06 | **EmpathyEar** | [EmpathyEar: An Open-source Avatar Multimodal Empathetic Chatbot](https://arxiv.org/abs/2406.15177) | T, A, V → T, speech, talking face | [GitHub](https://github.com/scofield7419/EmpathyEar) |
| 2024-05 | **X-VILA** | [X-VILA: Cross-Modality Alignment for Large Language Model](https://arxiv.org/abs/2405.19335) | T, I, V, A → T, I, V, A | — |
| 2024-05 | **C3LLM** | [C3LLM: Conditional Multimodal Content Generation Using Large Language Models](https://arxiv.org/abs/2405.16136) | T, V, A → T, A | — |
| 2024-04 | **WorldGPT** | [WorldGPT: Empowering LLM as Multimodal World Model](https://arxiv.org/abs/2404.18202) | T, I, V, A → T, I, V, A | [GitHub](https://github.com/DCDmllm/WorldGPT) |
| 2024-02 | **AnyGPT** | [AnyGPT: Unified Multimodal LLM with Discrete Sequence Modeling](https://arxiv.org/abs/2402.12226) | T, I, speech, music → T, I, speech, music | [GitHub](https://github.com/OpenMOSS/AnyGPT) |
| 2024-01 | **ModaVerse** | [ModaVerse: Efficiently Transforming Modalities with LLMs](https://arxiv.org/abs/2401.06395) | T, I, V, A → T, I, V, A | [GitHub](https://github.com/xinke-wang/ModaVerse) |
| 2023-12 | **Unified-IO 2** | [Unified-IO 2: Scaling Autoregressive Multimodal Models with Vision, Language, Audio, and Action](https://arxiv.org/abs/2312.17172) | T, I, V, A, action → T, I, A, action | [GitHub](https://github.com/allenai/unified-io-2) |
| 2023-12 | **VideoPoet** | [VideoPoet: A Large Language Model for Zero-Shot Video Generation](https://arxiv.org/abs/2312.14125) | T, I, V, A → V, A | — |
| 2023-11 | **CoDi-2** | [CoDi-2: In-Context, Interleaved, and Interactive Any-to-Any Generation](https://arxiv.org/abs/2311.18775) | T, I, A → T, I, A | [GitHub](https://github.com/microsoft/i-Code/tree/main/CoDi-2) |
| 2023-11 | **M2UGen** | [M2UGen: Multi-modal Music Understanding and Generation with the Power of Large Language Models](https://arxiv.org/abs/2311.11255) | T, I, V, music → T, music | [GitHub](https://github.com/shansongliu/M2UGen) |
| 2023-11 | **TEAL** | [TEAL: Tokenize and Embed ALL for Multi-modal Large Language Models](https://arxiv.org/abs/2311.04589) | T, I, A → T, I | — |
| 2023-09 | **NExT-GPT** | [NExT-GPT: Any-to-Any Multimodal LLM](https://arxiv.org/abs/2309.05519) | T, I, V, A → T, I, V, A | [GitHub](https://github.com/NExT-GPT/NExT-GPT) |
| 2022-06 | **Unified-IO** | [Unified-IO: A Unified Model for Vision, Language, and Multi-Modal Tasks](https://arxiv.org/abs/2206.08916) | T, I → T, I | [GitHub](https://github.com/allenai/unified-io-inference) |

### Proprietary Models (Reports & Model Cards)

| Date | Model | Paper | Modalities (in → out) | Code |
|:---:|---|---|---|:---:|
| 2026-09 | **MiMo-V2.6 Pro / Flash / Pro-Ultraspeed** | [MiMo-V2.6 series (official release and changelog)](https://mimo.mi.com/docs/en-US/updates/model#2026-09-22-mimo-v2-6-series-release) | Omni-modal reasoning and agent execution; see variant documentation | — |
| 2026-09 | **Gemini 3.8 Live / Live Extended Thinking** | [Gemini 3.8 Audio (official model card)](https://deepmind.google/models/model-cards/gemini-3-8-audio/) | T, I, V, A → T, speech; optional Live Avatar adds V | — |
| 2026-09 | **Gemini 3.8 Flash** | [Gemini 3.8 Flash (official model card)](https://deepmind.google/models/model-cards/gemini-3-8-flash/) | T, I, V, A → T | — |
| 2026-08 | **Gemini 3.7 Flash** | [Gemini 3.7 Flash (official model card)](https://deepmind.google/models/model-cards/gemini-3-7-flash/) | T, I, V, A → T | — |
| 2026-07 | **Gemini 3.5 Flash-Lite** | [Gemini 3.5 Flash-Lite (official model card)](https://deepmind.google/models/model-cards/gemini-3-5-flash-lite/) | T, I, V, A → T | — |
| 2026-07 | **Gemini 3.6 Flash** | [Gemini 3.6 Flash (official model card)](https://deepmind.google/models/model-cards/gemini-3-6-flash/) | T, I, V, A → T | — |
| 2026-05 | **Gemini 3.5 Flash** | [Gemini 3.5 Flash (official model card)](https://deepmind.google/models/model-cards/gemini-3-5-flash/) | T, I, V, A → T | — |
| 2026-04 | **MiMo-V2.5** | [MiMo-V2.5 (official release and changelog)](https://mimo.mi.com/docs/en-US/updates/model#2026-04-23-mimo-v2-5-released) | T, I, V, A → T, tool calls | — |
| 2026-03 | **MiMo-V2-Omni** | [MiMo-V2-Omni (official release and changelog)](https://mimo.mi.com/docs/en-US/updates/model#2026-03-18-mimo-v2-omni-release) | T, I, V, A → T, tool calls | — |
| 2026-03 | **Gemini 3.1 Flash Live** | [Gemini 3.1 Flash Audio (official model card)](https://deepmind.google/models/model-cards/gemini-3-1-flash-audio/) | T, I, V, A → T, speech | — |
| 2026-03 | **Gemini 3.1 Flash-Lite** | [Gemini 3.1 Flash-Lite (official model card)](https://deepmind.google/models/model-cards/gemini-3-1-flash-lite/) | T, I, V, A → T | — |
| 2026-02 | **Gemini 3.1 Pro** | [Gemini 3.1 Pro (official model card)](https://deepmind.google/models/model-cards/gemini-3-1-pro/) | T, I, V, A → T | — |
| 2025-12 | **Gemini 3 Flash** | [Gemini 3 Flash (official model card)](https://deepmind.google/models/model-cards/gemini-3-flash/) | T, I, V, A → T | — |
| 2025-11 | **Gemini 3 Pro** | [Gemini 3 Pro (official model card)](https://deepmind.google/models/model-cards/gemini-3-pro/) | T, I, V, A → T | — |
| 2025-07 | **Gemini 2.5** | [Gemini 2.5: Pushing the Frontier with Advanced Reasoning, Multimodality, Long Context, and Next Generation Agentic Capabilities](https://arxiv.org/abs/2507.06261) | T, I, V, A → T, native audio | — |
| 2025-03 | **GPT-4o Image Generation** | [Addendum to GPT-4o System Card: Native image generation](https://cdn.openai.com/11998be9-5319-4302-bfbf-1167e093f1fb/Native_Image_Generation_System_Card.pdf) | T, I → I | — |
| 2024-10 | **GPT-4o** | [GPT-4o System Card](https://arxiv.org/abs/2410.21276) | T, I, V, A → T, A, I | — |
| 2023-12 | **Gemini 1.0** | [Gemini: A Family of Highly Capable Multimodal Models](https://arxiv.org/abs/2312.11805) | T, I, V, A → T | — |

## Omni-Modal Understanding (Audio-Visual LLMs)

### Models

| Date | Model | Paper | Modalities (in → out) | Code |
|:---:|---|---|---|:---:|
| 2026-09 | **RAO-Nav** | [RAO-Nav: Probing Omni-Language Models for Zero-shot Semantic Audio-Visual Navigation](https://arxiv.org/abs/2609.32224) | A, V → navigation actions; zero-shot omni-model pipeline | — |
| 2026-09 | **OPERA** | [OPERA: A Unified Omnimodal Progressive Spatio-Temporal Reasoning Agent for Referring Video Segmentation](https://arxiv.org/abs/2609.33338) | T, I, A, V → referring-video segmentation; reasoning agent | — |
| 2026-09 | **OmniFysics-Nano-V2** | [OmniFysics-Nano-V2 Technical Report: Understanding the Physical World Across Modalities](https://arxiv.org/abs/2609.25738) | T, I, V, A → T, speech; physical reasoning | — |
| 2026-09 | **OmniVChat** | [OmniVChat: Synthesizing, Benchmarking, and Training for Native Audio-Visual Dialogue](https://arxiv.org/abs/2609.21465) | A, V → T; dialogue without a text question | — |
| 2026-09 | **OmniEcho** | [OmniEcho: Audio-Visual Spatial Understanding for Omni-Modal Embodied Agents](https://arxiv.org/abs/2609.23407) | Spatial A, V → T, navigation decisions | [GitHub](https://github.com/PKU-VaLuE-Lab/OmniEcho/tree/main) |
| 2026-09 | **SyncRA** | [SyncRA: Learning Temporal Correspondence in Omni-Modal Models](https://arxiv.org/abs/2609.34363) | V, A, T → T | — |
| 2026-09 | **OmniFysics-Captioner** | [OmniFysics-Captioner Technical Report: Grounding Omni-Modal Understanding in the Physical World for Better Captioning](https://arxiv.org/abs/2609.31714) | V, A, T → T | — |
| 2026-08 | **OneEmo** | [OneEmo: A Unified Multimodal Reasoning Model for Emotion Perception, Understanding, and Interaction](https://arxiv.org/abs/2608.06013) | Multimodal inputs → emotion analysis and interaction | [GitHub](https://github.com/waHAHJIAHAO/OneEmo) |
| 2026-08 | **TLive-Omni** | [TLive-Omni: An Omni-Modal Understanding Model for E-Commerce Live Streaming](https://arxiv.org/abs/2608.20958) | V, A, T → T | [GitHub](https://github.com/TaoLiveAIGC/TLive-Omni) |
| 2026-07 | **ThinkOmni** | [ThinkOmni: A Reasoning-Driven Omni-Modal LLM Framework for Audio Forgery Detection and Localization](https://arxiv.org/abs/2607.26553) | A, spectral/semantic cues → forgery detection and localization | [Project](https://beyond0814.github.io/ThinkOmni/) |
| 2026-07 | **Gemma 4 (audio-capable variants)** | [Gemma 4 Technical Report](https://arxiv.org/abs/2607.02770) | T, I, V, A → T; audio support depends on variant | — |
| 2026-07 | **AV-Flamingo** | [Audio-Visual Flamingo: Open Audio-Visual Intelligence for Long and Complex Videos](https://arxiv.org/abs/2607.16107) | I, V, A, T → T | — |
| 2026-07 | **AVSCap** | [AVSCap: Orchestrating Audio-Visual Synergy for Omni-modal Video Captioning](https://arxiv.org/abs/2607.12820) | V, A, T → T | [GitHub](https://github.com/NJU-LINK/AVSCap) |
| 2026-07 | **Robust-Audio Omni** | [Empowering Long-form Omni-modal Understanding with Robust Audio Perception](https://arxiv.org/abs/2607.10299) | V, A, T → T | — |
| 2026-07 | **PadCaptioner** | [Parallelized Autoregressive Decoding for Omni-Modal Dense Video Captioning](https://arxiv.org/abs/2607.02963) | V, A, T → T | [GitHub](https://github.com/showlab/PadCaptioner) |
| 2026-07 | **AV Caption Alignment** | [Temporal and Cross-Modal Alignment for Enhanced Audiovisual Video Captioning](https://arxiv.org/abs/2607.01667) | V, A, T → T | — |
| 2026-06 | **Omni Sentiment Readout** | [Beyond Generative Decoding: Discriminative Hidden-State Readout from a Native Omni-Modal LLM for Multimodal Sentiment Analysis](https://arxiv.org/abs/2606.05713) | T, V, A → sentiment; hidden-state classification | — |
| 2026-06 | **MODF-SIR** | [MODF-SIR: A Multi-agent Omni-modal Distilled Framework for Social Intelligence Reasoning](https://arxiv.org/abs/2606.12018) | Multimodal inputs → social reasoning; distilled agent framework | [GitHub](https://github.com/eeee-sys/MODF-SIR) |
| 2026-06 | **Spatial-Omni** | [Spatial-Omni: Spatial Audio Understanding Integration in Multimodal LLMs via FOA Encoding](https://arxiv.org/abs/2606.10738) | V, spatial A, T → T | — |
| 2026-05 | **Meow-Omni 1** | [Meow-Omni 1: A Multimodal Large Language Model for Feline Ethology](https://arxiv.org/abs/2605.09152) | Feline multimodal observations → behavioral interpretation | — |
| 2026-05 | **Valley3** | [Valley3: Scaling Omni Foundation Models for E-commerce](https://arxiv.org/abs/2605.01278) | T, I, V, A → T; e-commerce tasks | [GitHub](https://github.com/bytedance/Valley) |
| 2026-05 | **StreamOV** | [StreamOV: Streaming Omni-Video Understanding via Evidence-Guided Memory and Response Triggering](https://arxiv.org/abs/2605.25621) | V, A, T → T | — |
| 2026-04 | **ONOTE** | [ONOTE: Hypergraph-Grounded Omnimodal Reasoning for Computational Music Science](https://arxiv.org/abs/2604.20719) | Multimodal music information → grounded reasoning | — |
| 2026-04 | **CLUE (UMUI)** | [Unified Multimodal Uncertain Inference](https://arxiv.org/abs/2604.08701) | T, A, V → calibrated inference probabilities | — |
| 2026-04 | **OmniScript** | [OmniScript: Towards Audio-Visual Script Generation for Long-Form Cinematic Video](https://arxiv.org/abs/2604.11102) | V, A → T; long-video scripts | — |
| 2026-04 | **Nemotron 3 Nano Omni** | [Nemotron 3 Nano Omni: Efficient and Open Multimodal Intelligence](https://arxiv.org/abs/2604.24954) | I, V, A, T → T | — |
| 2026-04 | **Script-a-Video** | [Script-a-Video: Deep Structured Audio-visual Captions via Factorized Streams and Relational Grounding](https://arxiv.org/abs/2604.11244) | V, A, T → T | — |
| 2026-03 | **Omni-MMSI** | [Omni-MMSI: Toward Identity-attributed Social Interaction Understanding](https://arxiv.org/abs/2604.00267) | A, V → T; identity-attributed social understanding | [Project](https://sampson-lee.github.io/omni-mmsi-project-page) |
| 2026-03 | **AV-Unified** | [AV-Unified: A Unified Framework for Audio-visual Scene Understanding](https://arxiv.org/abs/2603.06530) | V, A, T → answers, masks, event labels | — |
| 2026-03 | **Crab+** | [Crab+: A Scalable and Unified Audio-Visual Scene Understanding Model with Explicit Cooperation](https://arxiv.org/abs/2603.04128) | V, A, T → T | — |
| 2026-02 | **GuardReasoner-Omni** | [GuardReasoner-Omni: A Reasoning-based Multi-modal Guardrail for Text, Image, Video, and Audio](https://arxiv.org/abs/2602.03328) | T, I, V, A → moderation decisions and reasoning | — |
| 2026-02 | **OmniFysics** | [OmniFysics: Towards Physical Intelligence Evolution via Omni-Modal Signal Processing and Network Optimization](https://arxiv.org/abs/2602.07064) | T, I, V, A; physical perception and generation | — |
| 2026-02 | **TimeChat-Captioner** | [TimeChat-Captioner: Scripting Multi-Scene Videos with Time-Aware and Structural Audio-Visual Captions](https://arxiv.org/abs/2602.08711) | V, A, T → T | [GitHub](https://github.com/yaolinli/TimeChat-Captioner) |
| 2026-02 | **D-ORCA** | [D-ORCA: Dialogue-Centric Optimization for Robust Audio-Visual Captioning](https://arxiv.org/abs/2602.07960) | V, A, T → T | — |
| 2026-02 | **EgoAVU** | [EgoAVU: Egocentric Audio-Visual Understanding](https://arxiv.org/abs/2602.06139) | V (ego), A, T → T | [GitHub](https://github.com/facebookresearch/EgoAVU) |
| 2026-01 | **MuseAgent-1** | [MuseAgent-1: Interactive Grounded Multimodal Understanding of Music Scores and Performance Audio](https://arxiv.org/abs/2601.11968) | Music scores, performance A → T; tool-assisted grounding | — |
| 2026-01 | **QMAVIS** | [QMAVIS: Long Video-Audio Understanding using Fusion of Large Multimodal Models](https://arxiv.org/abs/2601.06573) | V, A → T; multi-model long-video pipeline | — |
| 2026-01 | **DiaDem** | [DiaDem: Advancing Dialogue Descriptions in Audiovisual Video Captioning for Multimodal Large Language Models](https://arxiv.org/abs/2601.19267) | V, A, T → T | — |
| 2026-01 | **ROMA** | [ROMA: Real-time Omni-Multimodal Assistant with Interactive Streaming Understanding](https://arxiv.org/abs/2601.10323) | V, A, T → T | — |
| 2025-12 | **ChronusOmni** | [ChronusOmni: Improving Time Awareness of Omni Large Language Models](https://arxiv.org/abs/2512.09841) | V, A, T → T | [GitHub](https://github.com/YJCX330/Chronus) |
| 2025-10 | **OmniVinci** | [OmniVinci: Enhancing Architecture and Data for Omni-Modal Understanding LLM](https://arxiv.org/abs/2510.15870) | I, V, A, T → T | [GitHub](https://github.com/NVlabs/OmniVinci) |
| 2025-10 | **Omni-Captioner** | [Omni-Captioner: Data Pipeline, Models, and Benchmark for Omni Detailed Perception](https://arxiv.org/abs/2510.12720) | V, A, T → T | [GitHub](https://github.com/ddlBoJack/Omni-Captioner) |
| 2025-10 | **video-SALMONN S** | [video-SALMONN S: Memory-Enhanced Streaming Audio-Visual LLM](https://arxiv.org/abs/2510.11129) | V, A, T → T | — |
| 2025-10 | **AVoCaDO** | [AVoCaDO: An Audiovisual Video Captioner Driven by Temporal Orchestration](https://arxiv.org/abs/2510.10395) | V, A, T → T | [GitHub](https://github.com/AVoCaDO-Captioner/AVoCaDO) |
| 2025-09 | **WAVE** | [WAVE: Learning Unified & Versatile Audio-Visual Embeddings with Multimodal LLM](https://arxiv.org/abs/2509.21990) | V, A, T → T / embedding | — |
| 2025-07 | **ARC-Hunyuan-Video-7B** | [ARC-Hunyuan-Video-7B: Structured Video Comprehension of Real-World Shorts](https://arxiv.org/abs/2507.20939) | V, A, T → T | [GitHub](https://github.com/TencentARC/ARC-Hunyuan-Video-7B) |
| 2025-07 | **UGC-VideoCaptioner** | [UGC-VideoCaptioner: An Omni UGC Video Detail Caption Model and New Benchmarks](https://arxiv.org/abs/2507.11336) | V, A, T → T | [GitHub](https://github.com/WPR001/UGC_VideoCaptioner) |
| 2025-06 | **video-SALMONN 2** | [video-SALMONN 2: Captioning-Enhanced Audio-Visual Large Language Models](https://arxiv.org/abs/2506.15220) | V, A, T → T | [GitHub](https://github.com/bytedance/video-SALMONN-2) |
| 2025-06 | **SAVVY** | [SAVVY: Spatial Awareness via Audio-Visual LLMs through Seeing and Hearing](https://arxiv.org/abs/2506.05414) | V, spatial A, T → T | [GitHub](https://github.com/shlizee/savvy) |
| 2025-06 | **lm-extend** | [Is Extending Modality The Right Path Towards Omni-Modality?](https://arxiv.org/abs/2506.01872) | I, V, A, T → T | [GitHub](https://github.com/DarthZhu/lm-extend) |
| 2025-05 | **MLLMerging** | [Unifying Multimodal Large Language Model Capabilities and Modalities via Model Merging](https://arxiv.org/abs/2505.19892) | I, V, A, T → T | [GitHub](https://github.com/WalkerWorldPeace/MLLMerging) |
| 2025-05 | **TriSense** | [Watch and Listen: Understanding Audio-Visual-Speech Moments with Multimodal LLM](https://arxiv.org/abs/2505.18110) | V, A, speech, T → T | [GitHub](https://github.com/zinuoli/TriSense) |
| 2025-04 | **Capybara-OMNI** | [Capybara-OMNI: An Efficient Paradigm for Building Omni-Modal Language Models](https://arxiv.org/abs/2504.12315) | I, V, A, T → T | [GitHub](https://github.com/stoney0062/CAPYBARA-OMNI) |
| 2025-04 | **HippoMM** | [HippoMM: Hippocampal-inspired Multimodal Memory for Long Audiovisual Event Understanding](https://arxiv.org/abs/2504.10739) | V, A, T → T | [GitHub](https://github.com/linyueqian/HippoMM) |
| 2025-04 | **TDC-Video** | [Multimodal Long Video Modeling Based on Temporal Dynamic Context](https://arxiv.org/abs/2504.10443) | V, A, T → T | [GitHub](https://github.com/Hoar012/TDC-Video) |
| 2025-04 | **Dolphin** | [Aligned Better, Listen Better for Audio-Visual Large Language Models](https://arxiv.org/abs/2504.02061) | V, A, T → T | — |
| 2025-03 | **PAVE** | [PAVE: Patching and Adapting Video Large Language Models](https://arxiv.org/abs/2503.19794) | V, A (+3D), T → T | [GitHub](https://github.com/dragonlzm/PAVE) |
| 2025-03 | **Crab** | [Crab: A Unified Audio-Visual Scene Understanding Model with Explicit Cooperation](https://arxiv.org/abs/2503.13068) | V, A, T → T | [GitHub](https://github.com/GeWu-Lab/Crab) |
| 2025-03 | **Phi-4-Multimodal** | [Phi-4-Mini Technical Report: Compact yet Powerful Multimodal Language Models via Mixture-of-LoRAs](https://arxiv.org/abs/2503.01743) | I, A, T → T | [GitHub](https://github.com/microsoft/PhiCookBook) |
| 2025-02 | **Self-KD Omni** | [Investigating and Enhancing Vision-Audio Capability in Omnimodal Large Language Models](https://arxiv.org/abs/2503.00059) | I, A, T → T | — |
| 2025-02 | **Megrez-Omni** | [Megrez-Omni Technical Report](https://arxiv.org/abs/2502.15803) | I, A, T → T | [GitHub](https://github.com/infinigence/Infini-Megrez-Omni) |
| 2025-01 | **AffectGPT** | [AffectGPT: A New Dataset, Model, and Benchmark for Emotion Understanding with Multimodal Large Language Models](https://arxiv.org/abs/2501.16566) | V, A, T → T | [GitHub](https://github.com/zeroQiaoba/AffectGPT) |
| 2025-01 | **HumanOmni** | [HumanOmni: A Large Vision-Speech Language Model for Human-Centric Video Understanding](https://arxiv.org/abs/2501.15111) | V, A, T → T | [GitHub](https://github.com/HumanMLLM/HumanOmni) |
| 2025-01 | **Omni-Emotion** | [Omni-Emotion: Extending Video MLLM with Detailed Face and Audio Modeling for Multimodal Emotion Analysis](https://arxiv.org/abs/2501.09502) | V, A, T → T | [GitHub](https://github.com/HumanMLLM/Omni-Emotion) |
| 2025-01 | **LAVCap** | [LAVCap: LLM-based Audio-Visual Captioning using Optimal Transport](https://arxiv.org/abs/2501.09291) | V, A, T → T | — |
| 2024-11 | **SAVEn-Vid** | [SAVEn-Vid: Synergistic Audio-Visual Integration for Enhanced Understanding in Long Video Context](https://arxiv.org/abs/2411.16213) | V, A, T → T | [GitHub](https://github.com/LJungang/SAVEn-Vid) |
| 2024-10 | **OMCAT** | [OMCAT: Omni Context Aware Transformer](https://arxiv.org/abs/2410.12109) | V, A, T → T | — |
| 2024-10 | **Baichuan-Omni** | [Baichuan-Omni Technical Report](https://arxiv.org/abs/2410.08565) | I, V, A, T → T | [GitHub](https://github.com/westlake-baichuan-mllm/bc-omni) |
| 2024-07 | **AV-Grounding Video LLM** | [Audio-visual training for improved grounding in video-text LLMs](https://arxiv.org/abs/2407.15046) | V, A, T → T | — |
| 2024-07 | **Meerkat** | [Meerkat: Audio-Visual Large Language Model for Grounding in Space and Time](https://arxiv.org/abs/2407.01851) | I, A, T → T | [GitHub](https://github.com/schowdhury671/meerkat) |
| 2024-06 | **video-SALMONN** | [video-SALMONN: Speech-Enhanced Audio-Visual Large Language Models](https://arxiv.org/abs/2406.15704) | V, A, speech, T → T | [GitHub](https://github.com/bytedance/SALMONN) |
| 2024-06 | **Emotion-LLaMA** | [Emotion-LLaMA: Multimodal Emotion Recognition and Reasoning with Instruction Tuning](https://arxiv.org/abs/2406.11161) | V, A, T → T | [GitHub](https://github.com/ZebangCheng/Emotion-LLaMA) |
| 2024-06 | **VideoLLaMA 2** | [VideoLLaMA 2: Advancing Spatial-Temporal Modeling and Audio Understanding in Video-LLMs](https://arxiv.org/abs/2406.07476) | V, A, T → T | [GitHub](https://github.com/DAMO-NLP-SG/VideoLLaMA2) |
| 2024-05 | **Uni-MoE** | [Uni-MoE: Scaling Unified Multimodal LLMs with Mixture of Experts](https://arxiv.org/abs/2405.11273) | I, V, A, T → T | [GitHub](https://github.com/HITsz-TMG/UMOE-Scaling-Unified-Multimodal-LLMs) |
| 2024-03 | **AVicuna** | [AVicuna: Audio-Visual LLM with Interleaver and Context-Boundary Alignment for Temporal Referential Dialogue](https://arxiv.org/abs/2403.16276) | V, A, T → T | — |
| 2024-03 | **CAT** | [CAT: Enhancing Multimodal Large Language Model to Answer Questions in Dynamic Audio-Visual Scenarios](https://arxiv.org/abs/2403.04640) | V, A, T → T | [GitHub](https://github.com/rikeilong/Bay-CAT) |
| 2024-02 | **CREMA** | [CREMA: Multimodal Compositional Video Reasoning via Efficient Modular Adaptation and Fusion](https://arxiv.org/abs/2402.05889) | V, A, 3D, T → T | [GitHub](https://github.com/Yui010206/CREMA) |
| 2024-01 | **GroundingGPT (LEGO)** | [LEGO: Language Enhanced Multi-modal Grounding Model](https://arxiv.org/abs/2401.06071) | I, V, A, T → T | [GitHub](https://github.com/lzw-lzw/GroundingGPT) |
| 2023-12 | **AV-LLM** | [Audio-Visual LLM for Video Understanding](https://arxiv.org/abs/2312.06720) | V, A, T → T | — |
| 2023-12 | **OneLLM** | [OneLLM: One Framework to Align All Modalities with Language](https://arxiv.org/abs/2312.03700) | I, V, A, 3D, IMU, … → T | [GitHub](https://github.com/csuhan/OneLLM) |
| 2023-11 | **X-InstructBLIP** | [X-InstructBLIP: A Framework for aligning X-Modal instruction-aware representations to LLMs and Emergent Cross-modal Reasoning](https://arxiv.org/abs/2311.18799) | I, V, A, 3D, T → T | [GitHub](https://github.com/artemisp/LAVIS-XInstructBLIP) |
| 2023-10 | **FAVOR** | [Fine-grained Audio-Visual Joint Representations for Multimodal Large Language Models](https://arxiv.org/abs/2310.05863) | V, A, T → T | [GitHub](https://github.com/BriansIDP/AudioVisualLLM) |
| 2023-09 | **AnyMAL** | [AnyMAL: An Efficient and Scalable Any-Modality Augmented Language Model](https://arxiv.org/abs/2309.16058) | I, V, A, IMU, T → T | — |
| 2023-09 | **ImageBind-LLM** | [ImageBind-LLM: Multi-modality Instruction Tuning](https://arxiv.org/abs/2309.03905) | I, V, A, 3D, T → T | [GitHub](https://github.com/OpenGVLab/LLaMA-Adapter) |
| 2023-07 | **BuboGPT** | [BuboGPT: Enabling Visual Grounding in Multi-Modal LLMs](https://arxiv.org/abs/2307.08581) | I, A, T → T | [GitHub](https://github.com/magic-research/bubogpt) |
| 2023-06 | **Macaw-LLM** | [Macaw-LLM: Multi-Modal Language Modeling with Image, Audio, Video, and Text Integration](https://arxiv.org/abs/2306.09093) | I, V, A, T → T | [GitHub](https://github.com/lyuchenyang/Macaw-LLM) |
| 2023-06 | **Video-LLaMA** | [Video-LLaMA: An Instruction-tuned Audio-Visual Language Model for Video Understanding](https://arxiv.org/abs/2306.02858) | V, A, T → T | [GitHub](https://github.com/DAMO-NLP-SG/Video-LLaMA) |
| 2023-05 | **VAST** | [VAST: A Vision-Audio-Subtitle-Text Omni-Modality Foundation Model and Dataset](https://arxiv.org/abs/2305.18500) | V, A, subtitle, T → T | [GitHub](https://github.com/CASIA-IVA-Lab/VAST) |
| 2023-05 | **PandaGPT** | [PandaGPT: One Model To Instruction-Follow Them All](https://arxiv.org/abs/2305.16355) | I, V, A, 3D, thermal, IMU, T → T | [GitHub](https://github.com/yxuansu/PandaGPT) |
| 2023-05 | **ChatBridge** | [ChatBridge: Bridging Modalities with Large Language Model as a Language Catalyst](https://arxiv.org/abs/2305.16103) | I, V, A, T → T | [GitHub](https://github.com/joez17/ChatBridge) |
| 2023-05 | **X-LLM** | [X-LLM: Bootstrapping Advanced Large Language Models by Treating Multi-Modalities as Foreign Languages](https://arxiv.org/abs/2305.04160) | I, V, speech, T → T | [GitHub](https://github.com/phellonchen/X-LLM) |
| 2023-04 | **VALOR** | [VALOR: Vision-Audio-Language Omni-Perception Pretraining Model and Dataset](https://arxiv.org/abs/2304.08345) | V, A, T → T | [GitHub](https://github.com/CASIA-IVA-Lab/VALOR) |

### Reasoning, RL & Post-Training

| Date | Model | Paper | Modalities (in → out) | Code |
|:---:|---|---|---|:---:|
| 2026-10 | **OmniConfess** | [OmniConfess: Eliciting Token Confessions to Mitigate Omni-Modal Hallucination](https://arxiv.org/abs/2610.02999) | Inference-time hallucination correction across modalities | [GitHub](https://github.com/RongHuiQiang/OmniConfess) |
| 2026-10 | **OmniSeek** | [OmniSeek: Native Tool Integration for Multi-turn Audio-Visual Reasoning](https://arxiv.org/abs/2610.02181) | V, A, T → T | — |
| 2026-10 | **Text-Centric Omni Post-Training** | [Text-Centric Post-Training for Omni-Modal Reasoning](https://arxiv.org/abs/2610.02819) | V, A, T → T | — |
| 2026-09 | **DMC-Repair** | [Seeing What Should Be Heard: Diagnosing and Repairing Cross-Modal Shortcuts in Omni-Modal LLMs](https://arxiv.org/abs/2609.36798) | Diagnosing and correcting reliance on the wrong modality | — |
| 2026-09 | **OmniReasoning** | [OmniReasoning: Pushing the Limits of Audio-Visual Joint Reasoning](https://arxiv.org/abs/2609.39490) | V, A, T → T | [GitHub](https://github.com/PKU-VaLuE-Lab/OmniReasoning) |
| 2026-09 | **OP-CAD** | [OP-CAD: On-Policy Clean-Audio Distillation for Robust Audio-Visual Reasoning](https://arxiv.org/abs/2609.39150) | V, A, T → T | — |
| 2026-09 | **Omni-Streaming Thinking** | [Omni-Streaming Thinking](https://arxiv.org/abs/2609.15128) | V, A, T → T | — |
| 2026-08 | **Modality Fault Lines** | [Modality Fault Lines: Structural Corruptions Reveal Fragile Omni-Modal Reasoning](https://arxiv.org/abs/2608.29278) | Reliability under structured input corruption | — |
| 2026-08 | **Probing–Steering Dissociation** | [Read-Best Is Not Steer-Best: A Probing--Steering Layer Dissociation in Omni-Modal Large Language Models](https://arxiv.org/abs/2609.22135) | Study of layer selection for multimodal interventions | [GitHub](https://github.com/YiboWang2002/Read-Best-Is-Not-Steer-Best) |
| 2026-08 | **Speech-Centric Frozen-VLM Pipeline** | [Training-Free Speech-Centric Omni Understanding with Frozen VLMs](https://arxiv.org/abs/2609.04242) | Adding speech understanding without VLM fine-tuning | — |
| 2026-08 | **CAD** | [CAD: Conflict-Aware Decoding to Mitigate Cross-Modal Hallucinations in Omnimodal Large Language Models](https://arxiv.org/abs/2609.04247) | Inference-time decoding for conflicting modal evidence | — |
| 2026-08 | **ST-Omni-R1** | [Listen, See and Track: Spatio-Temporal Audio-Visual Sound Event Reasoning for Omni-Modal Language Models](https://arxiv.org/abs/2608.09435) | panoramic V, FOA A, T → T | — |
| 2026-07 | **Omni-Decision** | [Omni-Decision: Evidence-Ledger Planning for Omni-Modal Agents](https://arxiv.org/abs/2607.11433) | Evidence-ledger planning for multimodal agents | — |
| 2026-07 | **Audio-Grounded Scaffold Distillation** | [Listen, Do Not Copy: Internalizing Audio-Grounded Scaffold Context for Robust Omni-Model Speech Understanding](https://arxiv.org/abs/2607.21943) | Improving speech understanding with grounded training context | — |
| 2026-07 | **Modality Subspace Activation** | [Diagnosing and Mitigating Perception-Decision Misalignment in Omni-LLMs via Modality Subspace Activation](https://arxiv.org/abs/2608.14655) | Inference-time intervention for perception/decision alignment | — |
| 2026-07 | **OPOD** | [OPOD: On-Policy Omni Distillation](https://arxiv.org/abs/2607.20918) | On-policy distillation for multimodal reasoning | — |
| 2026-07 | **OmniReasoner** | [OmniReasoner: Thinking with Long Audio-Video via Native Tool Use](https://arxiv.org/abs/2607.19339) | V, A, T → T | [GitHub](https://github.com/RockyChen0205/OmniReasoner) |
| 2026-07 | **Light-Omni** | [Light-Omni: Reflex over Reasoning in Agentic Video Understanding with Long-Term Memory](https://arxiv.org/abs/2607.05511) | V, A, T → T | [GitHub](https://github.com/Clare-Nie/Light-Omni) |
| 2026-06 | **CogniRoute** | [CogniRoute: Learning to Route Social Evidence in Omni-Modal Models](https://arxiv.org/abs/2606.20970) | Routing audio-visual evidence for social reasoning | — |
| 2026-06 | **OPPO** | [Omni-Perception Policy Optimization for Multimodal Emotion Reasoning](https://arxiv.org/abs/2606.25325) | V, A, T → T | — |
| 2026-06 | **Native Active Perception** | [Native Active Perception as Reasoning for Omni-Modal Understanding](https://arxiv.org/abs/2606.19341) | V, A, T → T | [GitHub](https://github.com/harryhsing/OmniAgent) |
| 2026-05 | **Senses Wide Shut** | [Senses Wide Shut: A Representation-Action Gap in Omnimodal LLMs](https://arxiv.org/abs/2605.13737) | Study of the gap between representations and actions | — |
| 2026-05 | **Agentic Active Omni Perception** | [Agentic Active Omni-Modal Perception for Multi-Hop Audio-Visual Reasoning](https://arxiv.org/abs/2605.28192) | V, A, T → T | — |
| 2026-05 | **LatentOmni** | [LatentOmni: Rethinking Omni-Modal Understanding via Unified Audio-Visual Latent Reasoning](https://arxiv.org/abs/2605.22012) | V, A, T → T | [GitHub](https://github.com/yfanDai/LatentOmni) |
| 2026-05 | **OmniClean Post-Training** | [Boosting Omni-Modal Language Models: Staged Post-Training with Visually Debiased Evaluation](https://arxiv.org/abs/2605.12034) | V, A, T → T | — |
| 2026-05 | **Separate First, Fuse Later** | [Separate First, Fuse Later: Mitigating Cross-Modal Interference in Audio-Visual LLMs Reasoning with Modality-Specific Chain-of-Thought](https://arxiv.org/abs/2605.09906) | V, A, T → T | — |
| 2026-04 | **Omnimodal Dataset Distillation** | [Omnimodal Dataset Distillation via High-order Proxy Alignment](https://arxiv.org/abs/2604.10666) | Proxy-based distillation of multimodal training data | — |
| 2026-04 | **Modality Preference Analysis** | [Beyond Text-Dominance: Understanding Modality Preference of Omni-modal Large Language Models](https://arxiv.org/abs/2604.16902) | Study of text dominance in omni reasoning | [GitHub](https://github.com/icip-cas/OmniPreference) |
| 2026-04 | **CrossOmni** | [Cross-Modal Coreference Alignment: Enabling Reliable Information Transfer in Omni-LLMs](https://arxiv.org/abs/2604.05522) | Cross-modal coreference alignment with ICL and post-training | — |
| 2026-04 | **Omni-o3** | [Omni-o3: Deep Nested Omnimodal Deduction for Deliberative Audio-Visual Reasoning](https://arxiv.org/abs/2604.24191) | V, A, T → T | — |
| 2026-04 | **AVRT** | [AVRT: Audio-Visual Reasoning Transfer through Single-Modality Teachers](https://arxiv.org/abs/2604.16617) | V, A, T → T | — |
| 2026-04 | **Chain of Modality** | [Chain of Modality: From Static Fusion to Dynamic Orchestration in Omni-MLLMs](https://arxiv.org/abs/2604.14520) | V, A, T → T | — |
| 2026-04 | **Audio-Contrastive PO** | [Don't Let the Video Speak: Audio-Contrastive Preference Optimization for Audio-Visual Language Models](https://arxiv.org/abs/2604.14129) | V, A, T → T | — |
| 2026-04 | **OmniJigsaw** | [OmniJigsaw: Enhancing Omni-Modal Reasoning via Modality-Orchestrated Reordering](https://arxiv.org/abs/2604.08209) | V, A, T → T | [GitHub](https://github.com/aim-uofa/OmniJigsaw) |
| 2026-03 | **OmniTrace** | [OmniTrace: A Unified Framework for Generation-Time Attribution in Omni-Modal LLMs](https://arxiv.org/abs/2604.13073) | Attribution of generated outputs to multimodal evidence | — |
| 2026-03 | **SarcasmMiner** | [SarcasmMiner: A Dual-Track Post-Training Framework for Robust Audio-Visual Sarcasm Reasoning](https://arxiv.org/abs/2603.05275) | Audio-visual sarcasm reasoning through post-training | — |
| 2026-03 | **MoD-DPO** | [MoD-DPO: Towards Mitigating Cross-modal Hallucinations in Omni LLMs using Modality Decoupled Preference Optimization](https://arxiv.org/abs/2603.03192) | V, A, T → T | — |
| 2026-02 | **Omni-Safety** | [Omni-Safety under Cross-Modality Conflict: Vulnerabilities, Dynamics Mechanisms and Efficient Alignment](https://arxiv.org/abs/2602.10161) | Safety alignment when modalities carry conflicting instructions | [GitHub](https://github.com/zhrli324/omni-safety-research) |
| 2026-02 | **ThinkOmni** | [ThinkOmni: Lifting Textual Reasoning to Omni-modal Scenarios via Guidance Decoding](https://arxiv.org/abs/2602.23306) | V, A, T → T | — |
| 2026-02 | **OmniGAIA / OmniAtlas** | [OmniGAIA: Towards Native Omni-Modal AI Agents](https://arxiv.org/abs/2602.22897) | I, V, A, T → T | [GitHub](https://github.com/RUC-NLPIR/OmniGAIA) |
| 2026-02 | **AVERE** | [AVERE: Improving Audiovisual Emotion Reasoning with Preference Optimization](https://arxiv.org/abs/2602.07054) | V, A, T → T | — |
| 2026-02 | **OmniVideo-R1** | [OmniVideo-R1: Reinforcing Audio-visual Reasoning with Query Intention and Modality Attention](https://arxiv.org/abs/2602.05847) | V, A, T → T | — |
| 2026-02 | **OmniRAG-Agent** | [OmniRAG-Agent: Agentic Omnimodal Reasoning for Low-Resource Long Audio-Video Question Answering](https://arxiv.org/abs/2602.03707) | V, A, T → T | — |
| 2026-01 | **Omni-RRM** | [Omni-RRM: Advancing Omni Reward Modeling via Automatic Rubric-Grounded Preference Synthesis](https://arxiv.org/abs/2602.00846) | Rubric-based reward modeling for omni responses | [Project](https://tmfk418.github.io/Omni-RRM) |
| 2026-01 | **AV-Evidence Emotion Reasoning** | [Integrating Fine-Grained Audio-Visual Evidence for Robust Multimodal Emotion Reasoning](https://arxiv.org/abs/2601.18321) | V, A, T → T | — |
| 2025-12 | **OmniAgent** | [OmniAgent: Audio-Guided Active Perception Agent for Omnimodal Audio-Video Understanding](https://arxiv.org/abs/2512.23646) | V, A, T → T | — |
| 2025-12 | **Omni-AutoThink** | [Omni-AutoThink: Adaptive Multimodal Reasoning via Reinforcement Learning](https://arxiv.org/abs/2512.03783) | V, A, T → T | [GitHub](https://github.com/yangdongchao/Omni-AutoThink) |
| 2025-11 | **R-AVST** | [R-AVST: Empowering Video-LLMs with Fine-Grained Spatio-Temporal Reasoning in Complex Audio-Visual Scenarios](https://arxiv.org/abs/2511.16901) | V, A, T → T | — |
| 2025-11 | **Agent-Omni** | [Agent-Omni: Test-Time Multimodal Reasoning via Model Coordination for Understanding Anything](https://arxiv.org/abs/2511.02834) | I, V, A, T → T | — |
| 2025-10 | **AV-Master** | [AV-Master: Dual-Path Comprehensive Perception Makes Better Audio-Visual Question Answering](https://arxiv.org/abs/2510.18346) | V, A, T → T | — |
| 2025-09 | **SightSound-R1** | [SightSound-R1: Cross-Modal Reasoning Distillation from Vision to Audio Language Models](https://arxiv.org/abs/2509.15661) | V, A, T → T | — |
| 2025-09 | **CogGuide** | [CogGuide: Human-Like Guidance for Zero-Shot Omni-Modal Reasoning](https://arxiv.org/abs/2509.06641) | V, A, T → T | — |
| 2025-08 | **OmniDPO** | [OmniDPO: A Preference Optimization Framework to Address Omni-Modal Hallucination](https://arxiv.org/abs/2509.00723) | V, A, T → T | — |
| 2025-08 | **AVATAR** | [AVATAR: Reinforcement Learning to See, Hear, and Reason Over Video](https://arxiv.org/abs/2508.03100) | V, A, T → T | — |
| 2025-06 | **HumanOmniV2** | [HumanOmniV2: From Understanding to Omni-Modal Reasoning with Context](https://arxiv.org/abs/2506.21277) | V, A, T → T | [GitHub](https://github.com/HumanMLLM/HumanOmniV2) |
| 2025-06 | **AV-Reasoner** | [AV-Reasoner: Improving and Benchmarking Clue-Grounded Audio-Visual Counting for MLLMs](https://arxiv.org/abs/2506.05328) | V, A, T → T | [GitHub](https://github.com/AV-Reasoner/AV-Reasoner) |
| 2025-05 | **Omni-R1** | [Omni-R1: Reinforcement Learning for Omnimodal Reasoning via Two-System Collaboration](https://arxiv.org/abs/2505.20256) | V, A, T → T | [GitHub](https://github.com/aim-uofa/Omni-R1) |
| 2025-05 | **Fork-Merge Decoding** | [Fork-Merge Decoding: Enhancing Multimodal Understanding in Audio-Visual Large Language Models](https://arxiv.org/abs/2505.20873) | V, A, T → T | — |
| 2025-05 | **AVCD** | [AVCD: Mitigating Hallucinations in Audio-Visual Large Language Models through Contrastive Decoding](https://arxiv.org/abs/2505.20862) | V, A, T → T | — |
| 2025-05 | **EchoInk-R1** | [EchoInk-R1: Exploring Audio-Visual Reasoning in Multimodal LLMs via Reinforcement Learning](https://arxiv.org/abs/2505.04623) | I, A, T → T | [GitHub](https://github.com/HarryHsing/EchoInk) |
| 2025-03 | **AURELIA** | [Aurelia: Test-time Reasoning Distillation in Audio-Visual LLMs](https://arxiv.org/abs/2503.23219) | V, A, T → T | — |
| 2025-03 | **OmniVox** | [OmniVox: Zero-Shot Emotion Recognition with Omni-LLMs](https://arxiv.org/abs/2503.21480) | V, A, T → T | — |
| 2025-03 | **R1-Omni** | [R1-Omni: Explainable Omni-Multimodal Emotion Recognition with Reinforcement Learning](https://arxiv.org/abs/2503.05379) | V, A, T → T | [GitHub](https://github.com/HumanMLLM/R1-Omni) |
| 2025-02 | **video-SALMONN-o1** | [video-SALMONN-o1: Reasoning-enhanced Audio-visual Large Language Model](https://arxiv.org/abs/2502.11775) | V, A, T → T | [GitHub](https://github.com/BriansIDP/video-SALMONN-o1) |
| 2024-12 | **AV-EPO** | [Empathetic Response in Audio-Visual Conversations Using Emotion Preference Optimization and MambaCompressor](https://arxiv.org/abs/2412.17572) | V, A, T → T | — |
| 2024-10 | **video-SALMONN MrDPO** | [Enhancing Multimodal LLM for Detailed and Accurate Video Captioning using Multi-Round Preference Optimization](https://arxiv.org/abs/2410.06682) | V, A, T → T | — |

## Unified Visual Understanding & Generation

### Unified Models

| Date | Model | Paper | Paradigm | Code |
|:---:|---|---|---|:---:|
| 2026-10 | **Nano Banana 2.1** | [Nano Banana 2.1 (official model card)](https://deepmind.google/models/model-cards/nano-banana-2-1/) | Proprietary; T, I → I (text output also supported by Flash Image variants) | — |
| 2026-10 | **Gestalt** | [Gestalt: Large Multimodal Interplay Model](https://arxiv.org/abs/2610.00576) | Discrete Diffusion | — |
| 2026-09 | **PixelUMM** | [PixelUMM: Encoder-Free Unified Image and Video Understanding and Generation](https://arxiv.org/abs/2609.38597) | AR+Diffusion | — |
| 2026-09 | **SenseNova-U1.5** | [SenseNova-U1.5: Towards Native Unified Visual Intelligence](https://arxiv.org/abs/2609.11929) | AR+Diffusion | [GitHub](https://github.com/OpenSenseNova/SenseNova-U1) |
| 2026-08 | **Object-Uni** | [Object-Uni: A Unified Model for Object-Centric Spatial Understanding and Controllable Generation](https://arxiv.org/abs/2608.22757) | Object pose understanding and controllable image generation | — |
| 2026-07 | **Argus-Unified** | [Argus-Unified: Towards A Compact and Economical Unified Model for Image Understanding and Generation](https://arxiv.org/abs/2607.25527) | AR | — |
| 2026-07 | **Boogu-Image-0.1** | [Boogu-Image-0.1: Boosting Open Agentic Multimodal Generation via Understanding under a Minimal Budget](https://arxiv.org/abs/2607.13125) | AR+Diffusion | [GitHub](https://github.com/Boogu-Project/Boogu-Image) |
| 2026-07 | **Gen4U** | [Gen4U: Unifying Video Generation and Understanding via Diffusion](https://arxiv.org/abs/2607.06856) | Diffusion | — |
| 2026-06 | **Gemini 3.1 Flash-Lite Image** | [Gemini 3.1 Flash-Lite Image (official model card)](https://deepmind.google/models/model-cards/gemini-3-1-flash-lite-image/) | Proprietary; T, I → I (text output also supported by Flash Image variants) | — |
| 2026-06 | **ABACUS** | [ABACUS: Adapting Unified Foundation Model for Bridging Image Count Understanding and Generation](https://arxiv.org/abs/2606.23835) | Object/crowd counting and count-controlled image generation | [Project](https://mondalanindya.github.io/pages/ABACUS) |
| 2026-06 | **UniGP** | [UniGP: Taming Diffusion Transformer for Prior-Preserved Unified Generation and Perception](https://arxiv.org/abs/2606.30332) | Diffusion transformer for controllable generation and dense perception | — |
| 2026-06 | **SPAR** | [SPAR: Semantic-Pixel Self-Alignment and Adaptive Routing for Unified Multimodal Models](https://arxiv.org/abs/2606.23041) | Semantic/pixel alignment with adaptive routing | — |
| 2026-06 | **ILLUME-X** | [Illuminating Unified Multimodal Model for Free-form Interleaved Text-Image Generation](https://arxiv.org/abs/2606.30054) | Free-form interleaved text-image generation | — |
| 2026-06 | **Vega** | [Bridging Video Understanding and Generation in a Unified Framework](https://arxiv.org/abs/2606.31326) | AR+Diffusion | — |
| 2026-06 | **UniAR** | [Unified Multimodal Autoregressive Modeling with Shared Context-Visual Tokenizer is Key to Unification](https://arxiv.org/abs/2606.18249) | AR | — |
| 2026-06 | **UniDDT** | [UniDDT: Unifying Multimodal Understanding and Generation with Decoupled Diffusion Transformer](https://arxiv.org/abs/2606.16255) | Diffusion | — |
| 2026-06 | **HYDRA-X** | [HYDRA-X: Native Unified Multimodal Models with Holistic Visual Tokenizers](https://arxiv.org/abs/2606.13289) | AR+Diffusion | — |
| 2026-05 | **Lance** | [Lance: Unified Multimodal Modeling by Multi-Task Synergy](https://arxiv.org/abs/2605.18678) | AR+Diffusion | [GitHub](https://github.com/bytedance/Lance) |
| 2026-05 | **SenseNova-U1** | [SenseNova-U1: Unifying Multimodal Understanding and Generation with NEO-unify Architecture](https://arxiv.org/abs/2605.12500) | AR+Diffusion | [GitHub](https://github.com/OpenSenseNova/SenseNova-U1) |
| 2026-05 | **STARFlow2** | [STARFlow2: Bridging Language Models and Normalizing Flows for Unified Multimodal Generation](https://arxiv.org/abs/2605.08029) | AR+Diffusion | — |
| 2026-05 | **JoyAI-Image** | [JoyAI-Image: Awaking Spatial Intelligence in Unified Multimodal Understanding and Generation](https://arxiv.org/abs/2605.04128) | AR+Diffusion | [GitHub](https://github.com/jd-opensource/JoyAI-Image) |
| 2026-05 | **Mamoda2.5** | [Mamoda2.5: Enhancing Unified Multimodal Model with DiT-MoE](https://arxiv.org/abs/2605.02641) | AR+Diffusion | — |
| 2026-04 | **Tuna-2** | [Tuna-2: Pixel Embeddings Beat Vision Encoders for Multimodal Understanding and Generation](https://arxiv.org/abs/2604.24763) | AR+Diffusion | — |
| 2026-04 | **LLaDA2.0-Uni** | [LLaDA2.0-Uni: Unifying Multimodal Understanding and Generation with Diffusion Large Language Model](https://arxiv.org/abs/2604.20796) | Discrete Diffusion | [GitHub](https://github.com/inclusionAI/LLaDA2.0-Uni) |
| 2026-04 | **Uni-ViGU** | [Uni-ViGU: Towards Unified Video Generation and Understanding via A Diffusion-Based Video Generator](https://arxiv.org/abs/2604.08121) | Diffusion | — |
| 2026-03 | **EchoGen** | [EchoGen: Cycle-Consistent Learning for Unified Layout-Image Generation and Understanding](https://arxiv.org/abs/2603.18001) | Layout-conditioned synthesis and image grounding | — |
| 2026-03 | **LLaDA-o** | [LLaDA-o: An Effective and Length-Adaptive Omni Diffusion Model](https://arxiv.org/abs/2603.01068) | Discrete text diffusion + continuous image diffusion | [GitHub](https://github.com/ML-GSAI/LLaDA-o) |
| 2026-03 | **HYDRA** | [HYDRA: Unifying Multi-modal Generation and Understanding via Representation-Harmonized Tokenization](https://arxiv.org/abs/2603.15228) | AR+Diffusion | — |
| 2026-03 | **Cheers** | [Cheers: Decoupling Patch Details from Semantic Representations Enables Unified Multimodal Comprehension and Generation](https://arxiv.org/abs/2603.12793) | AR+Diffusion | — |
| 2026-03 | **UniCom** | [UniCom: Unified Multimodal Modeling via Compressed Continuous Semantic Representations](https://arxiv.org/abs/2603.10702) | AR+Diffusion | — |
| 2026-03 | **InternVL-U** | [InternVL-U: Democratizing Unified Multimodal Models for Understanding, Reasoning, Generation and Editing](https://arxiv.org/abs/2603.09877) | AR+Diffusion | [GitHub](https://github.com/OpenGVLab/InternVL-U) |
| 2026-03 | **Wallaroo** | [A Simple Baseline for Unifying Understanding, Generation, and Editing via Vanilla Next-token Prediction](https://arxiv.org/abs/2603.04980) | AR | [GitHub](https://github.com/JiePKU/Wallaroo) |
| 2026-02 | **Gemini 3.1 Flash Image (Nano Banana 2)** | [Gemini 3.1 Flash Image (Nano Banana 2) (official model card)](https://deepmind.google/models/model-cards/gemini-3-1-flash-image/) | Proprietary; T, I → I (text output also supported by Flash Image variants) | — |
| 2026-02 | **Mobile-O** | [Mobile-O: Unified Multimodal Understanding and Generation on Mobile Device](https://arxiv.org/abs/2602.20161) | AR+Diffusion | — |
| 2026-02 | **UniWeTok** | [UniWeTok: An Unified Binary Tokenizer with Codebook Size 2^128 for Unified Multimodal Large Language Model](https://arxiv.org/abs/2602.14178) | AR | — |
| 2026-02 | **LaViDa-R1** | [LaViDa-R1: Advancing Reasoning for Unified Multimodal Diffusion Language Models](https://arxiv.org/abs/2602.14147) | Discrete Diffusion | — |
| 2026-02 | **DeepGen 1.0** | [DeepGen 1.0: A Lightweight Unified Multimodal Model for Advancing Image Generation and Editing](https://arxiv.org/abs/2602.12205) | AR+Diffusion | — |
| 2026-01 | **OmniPersona** | [Unified Personalized Understanding, Generating and Editing](https://arxiv.org/abs/2601.06965) | Personalized understanding, generation and editing | — |
| 2026-01 | **UM-Text** | [UM-Text: A Unified Multimodal Model for Image Understanding and Visual Text Editing](https://arxiv.org/abs/2601.08321) | Image understanding and visual text editing | — |
| 2026-01 | **NextFlow** | [NextFlow: Unified Sequential Modeling Activates Multimodal Understanding and Generation](https://arxiv.org/abs/2601.02204) | AR | [GitHub](https://github.com/ByteVisionLab/NextFlow) |
| 2025-12 | **STAR** | [STAR: STacked AutoRegressive Scheme for Unified Multimodal Learning](https://arxiv.org/abs/2512.13752) | AR | — |
| 2025-12 | **EMMA** | [EMMA: Efficient Multimodal Understanding, Generation, and Editing with a Unified Architecture](https://arxiv.org/abs/2512.04810) | AR+Diffusion | [GitHub](https://github.com/umm-emma/emma) |
| 2025-12 | **TUNA** | [TUNA: Taming Unified Visual Representations for Native Unified Multimodal Models](https://arxiv.org/abs/2512.02014) | AR+Diffusion | [GitHub](https://github.com/wren93/tuna) |
| 2025-11 | **Gemini 3 Pro Image (Nano Banana Pro)** | [Gemini 3 Pro Image (Nano Banana Pro) (official model card)](https://deepmind.google/models/model-cards/gemini-3-pro-image/) | Proprietary; T, I → I (text output also supported by Flash Image variants) | — |
| 2025-11 | **HBridge** | [HBridge: H-Shape Bridging of Heterogeneous Experts for Unified Multimodal Understanding and Generation](https://arxiv.org/abs/2511.20520) | AR+Diffusion | — |
| 2025-11 | **MammothModa2** | [MammothModa2: A Unified AR-Diffusion Framework for Multimodal Understanding and Generation](https://arxiv.org/abs/2511.18262) | AR+Diffusion | [GitHub](https://github.com/bytedance/mammothmoda) |
| 2025-11 | **UniModel** | [UniModel: A Visual-Only Framework for Unified Multimodal Understanding and Generation](https://arxiv.org/abs/2511.16917) | Diffusion | — |
| 2025-11 | **UniGen-1.5** | [UniGen-1.5: Enhancing Image Generation and Editing through Reward Unification in Reinforcement Learning](https://arxiv.org/abs/2511.14760) | AR | — |
| 2025-11 | **MMaDA-Parallel** | [MMaDA-Parallel: Multimodal Large Diffusion Language Models for Thinking-Aware Editing and Generation](https://arxiv.org/abs/2511.09611) | Discrete Diffusion | [GitHub](https://github.com/tyfeld/MMaDA-Parallel) |
| 2025-10 | **ThinkMorph** | [ThinkMorph: Emergent Properties in Multimodal Interleaved Chain-of-Thought Reasoning](https://arxiv.org/abs/2510.27492) | AR+Diffusion | — |
| 2025-10 | **Emu3.5** | [Emu3.5: Native Multimodal Models are World Learners](https://arxiv.org/abs/2510.26583) | AR | [GitHub](https://github.com/baaivision/Emu3.5) |
| 2025-10 | **LightFusion** | [LightFusion: A Light-weighted, Double Fusion Framework for Unified Multimodal Understanding and Generation](https://arxiv.org/abs/2510.22946) | AR+Diffusion | [GitHub](https://github.com/shubhamsonivfx/LightFusion) |
| 2025-10 | **BLIP3o-NEXT** | [BLIP3o-NEXT: Next Frontier of Native Image Generation](https://arxiv.org/abs/2510.15857) | AR+Diffusion | [GitHub](https://github.com/JiuhaiChen/BLIP3o) |
| 2025-10 | **UniVideo** | [UniVideo: Unified Understanding, Generation, and Editing for Videos](https://arxiv.org/abs/2510.08377) | AR+Diffusion | — |
| 2025-10 | **Ming-UniVision** | [Ming-UniVision: Joint Image Understanding and Generation with a Unified Continuous Tokenizer](https://arxiv.org/abs/2510.06590) | AR | [GitHub](https://github.com/inclusionAI/Ming-UniVision) |
| 2025-10 | **Lumina-DiMOO** | [Lumina-DiMOO: An Omni Diffusion Large Language Model for Multi-Modal Generation and Understanding](https://arxiv.org/abs/2510.06308) | Discrete Diffusion | [GitHub](https://github.com/Alpha-VLLM/Lumina-DiMOO) |
| 2025-09 | **UniVid** | [UniVid: The Open-Source Unified Video Model](https://arxiv.org/abs/2509.24200) | Video understanding and generation with AR + diffusion | [GitHub](https://github.com/AIGeeksGroup/UniVid) |
| 2025-09 | **Query-Kontext** | [Query-Kontext: An Unified Multimodal Model for Image Generation and Editing](https://arxiv.org/abs/2509.26641) | AR+Diffusion | — |
| 2025-09 | **Uni-X** | [Uni-X: Mitigating Modality Conflict with a Two-End-Separated Architecture for Unified Multimodal Models](https://arxiv.org/abs/2509.24365) | AR | [GitHub](https://github.com/CURRENTF/Uni-X) |
| 2025-09 | **HunyuanImage 3.0** | [HunyuanImage 3.0 Technical Report](https://arxiv.org/abs/2509.23951) | AR+Diffusion | [GitHub](https://github.com/Tencent-Hunyuan/HunyuanImage-3.0) |
| 2025-09 | **Lavida-O** | [Lavida-O: Elastic Large Masked Diffusion Models for Unified Multimodal Understanding and Generation](https://arxiv.org/abs/2509.19244) | Discrete Diffusion | [GitHub](https://github.com/jacklishufan/LaViDa-O) |
| 2025-09 | **OmniBridge** | [OmniBridge: Unified Multimodal Understanding, Generation, and Retrieval via Latent Space Alignment](https://arxiv.org/abs/2509.19018) | AR+Diffusion | [GitHub](https://github.com/xiao-xt/OmniBridge) |
| 2025-09 | **Manzano** | [MANZANO: A Simple and Scalable Unified Multimodal Model with a Hybrid Vision Tokenizer](https://arxiv.org/abs/2509.16197) | AR+Diffusion | — |
| 2025-09 | **UAE** | [Unified Multimodal Models as Auto-Encoders](https://arxiv.org/abs/2509.09666) | AR+Diffusion | — |
| 2025-09 | **UniPic 2.0** | [Skywork UniPic 2.0: Building Kontext Model with Online RL for Unified Multimodal Model](https://arxiv.org/abs/2509.04548) | AR+Diffusion | [GitHub](https://github.com/SkyworkAI/UniPic) |
| 2025-09 | **OneCAT** | [OneCAT: Decoder-Only Auto-Regressive Model for Unified Understanding and Generation](https://arxiv.org/abs/2509.03498) | AR | [GitHub](https://github.com/onecat-ai/OneCAT) |
| 2025-08 | **Gemini 2.5 Flash Image (Nano Banana)** | [Gemini image generation/editing release](https://blog.google/products-and-platforms/products/gemini/updated-image-editing-model/) | Proprietary; text/image-conditioned generation and conversational editing | — |
| 2025-08 | **TBAC-UniImage** | [TBAC-UniImage: Unified Understanding and Generation by Ladder-Side Diffusion Tuning](https://arxiv.org/abs/2508.08098) | AR+Diffusion | [GitHub](https://github.com/DruryXu/TBAC-UniImage) |
| 2025-08 | **Bifrost-1** | [Bifrost-1: Bridging Multimodal LLMs and Diffusion Models with Patch-level CLIP Latents](https://arxiv.org/abs/2508.05954) | AR+Diffusion | [GitHub](https://github.com/HL-hanlin/Bifrost-1) |
| 2025-08 | **Uni-CoT** | [Uni-cot: Towards Unified Chain-of-Thought Reasoning Across Text and Vision](https://arxiv.org/abs/2508.05606) | AR+Diffusion | [GitHub](https://github.com/Fr0zenCrane/UniCoT) |
| 2025-08 | **Skywork UniPic** | [Skywork UniPic: Unified Autoregressive Modeling for Visual Understanding and Generation](https://arxiv.org/abs/2508.03320) | AR | [GitHub](https://github.com/SkyworkAI/UniPic) |
| 2025-07 | **UniLIP** | [UniLiP: Adapting CLIP for Unified Multimodal Understanding, Generation and Editing](https://arxiv.org/abs/2507.23278) | AR+Diffusion | [GitHub](https://github.com/nnnth/UniLIP) |
| 2025-07 | **X-Omni** | [X-Omni: Reinforcement Learning Makes Discrete Autoregressive Image Generative Models Great Again](https://arxiv.org/abs/2507.22058) | AR | [GitHub](https://github.com/X-Omni-Team/X-Omni) |
| 2025-07 | **Omni-Video** | [Omni-Video: Democratizing Unified Video Understanding and Generation](https://arxiv.org/abs/2507.06119) | AR+Diffusion | — |
| 2025-06 | **Ovis-U1** | [Ovis-U1 Technical Report](https://arxiv.org/abs/2506.23044) | AR+Diffusion | [GitHub](https://github.com/AIDC-AI/Ovis-U1) |
| 2025-06 | **UniCode2** | [UniCode²: Cascaded Large-scale Codebooks for Unified Multimodal Understanding and Generation](https://arxiv.org/abs/2506.20214) | AR | — |
| 2025-06 | **Tar** | [Vision as a Dialect: Unifying Visual Understanding and Generation via Text-Aligned Representations](https://arxiv.org/abs/2506.18898) | AR | [GitHub](https://github.com/csuhan/Tar) |
| 2025-06 | **OmniGen2** | [OmniGen2: Towards Instruction-Aligned Multimodal Generation](https://arxiv.org/abs/2506.18871) | AR+Diffusion | [GitHub](https://github.com/VectorSpaceLab/OmniGen2) |
| 2025-06 | **UniFork** | [UniFork: Exploring Modality Alignment for Unified Multimodal Understanding and Generation](https://arxiv.org/abs/2506.17202) | AR | [GitHub](https://github.com/tliby/UniFork) |
| 2025-06 | **Show-o2** | [Show-o2: Improved Native Unified Multimodal Models](https://arxiv.org/abs/2506.15564) | AR+Diffusion | [GitHub](https://github.com/showlab/Show-o) |
| 2025-06 | **Pisces** | [Pisces: An Auto-regressive Foundation Model for Image Understanding and Generation](https://arxiv.org/abs/2506.10395) | AR+Diffusion | — |
| 2025-06 | **LaTtE-Flow** | [LaTtE-Flow: Layerwise Timestep-Expert Flow-based Transformer](https://arxiv.org/abs/2506.06952) | AR+Diffusion | — |
| 2025-06 | **UniWorld-V1** | [UniWorld-V1: High-Resolution Semantic Encoders for Unified Visual Understanding and Generation](https://arxiv.org/abs/2506.03147) | AR+Diffusion | [GitHub](https://github.com/PKU-YuanGroup/UniWorld-V1) |
| 2025-06 | **HaploOmni** | [HaploOmni: Unified Single Transformer for Multimodal Video Understanding and Generation](https://arxiv.org/abs/2506.02975) | AR+Diffusion | [GitHub](https://github.com/Tencent/HaploVLM) |
| 2025-05 | **OpenUni** | [OpenUni: A Simple Baseline for Unified Multimodal Understanding and Generation](https://arxiv.org/abs/2505.23661) | AR+Diffusion | [GitHub](https://github.com/wusize/OpenUni) |
| 2025-05 | **Muddit** | [Muddit: Liberating Generation Beyond Text-to-Image with a Unified Discrete Diffusion Model](https://arxiv.org/abs/2505.23606) | Discrete Diffusion | [GitHub](https://github.com/M-E-AGI-Lab/Muddit) |
| 2025-05 | **FUDOKI** | [FUDOKI: Discrete Flow-based Unified Understanding and Generation via Kinetic-Optimal Velocities](https://arxiv.org/abs/2505.20147) | Discrete Diffusion | — |
| 2025-05 | **MMaDA** | [MMaDA: Multimodal Large Diffusion Language Models](https://arxiv.org/abs/2505.15809) | Discrete Diffusion | [GitHub](https://github.com/Gen-Verse/MMaDA) |
| 2025-05 | **BAGEL** | [Emerging Properties in Unified Multimodal Pretraining](https://arxiv.org/abs/2505.14683) | AR+Diffusion | [GitHub](https://github.com/bytedance-seed/BAGEL) |
| 2025-05 | **UniGen** | [UniGen: Enhanced Training & Test-Time Strategies for Unified Multimodal Understanding and Generation](https://arxiv.org/abs/2505.14682) | AR | — |
| 2025-05 | **MindOmni** | [MindOmni: Unleashing Reasoning Generation in Vision Language Models with RGPO](https://arxiv.org/abs/2505.13031) | AR+Diffusion | [GitHub](https://github.com/TencentARC/MindOmni) |
| 2025-05 | **BLIP3-o** | [BLIP3-o: A Family of Fully Open Unified Multimodal Models-Architecture, Training and Dataset](https://arxiv.org/abs/2505.09568) | AR+Diffusion | [GitHub](https://github.com/JiuhaiChen/BLIP3o) |
| 2025-05 | **Selftok** | [Selftok: Discrete Visual Tokens of Autoregression, by Diffusion, and for Reasoning](https://arxiv.org/abs/2505.07538) | AR | [GitHub](https://github.com/selftok-team/SelftokTokenizer) |
| 2025-05 | **Mogao** | [Mogao: An Omni Foundation Model for Interleaved Multi-Modal Generation](https://arxiv.org/abs/2505.05472) | AR+Diffusion | — |
| 2025-05 | **TokLIP** | [TokLIP: Marry Visual Tokens to CLIP for Multimodal Comprehension and Generation](https://arxiv.org/abs/2505.05422) | AR | [GitHub](https://github.com/TencentARC/TokLIP) |
| 2025-05 | **Ming-Lite-Uni** | [Ming-Lite-Uni: Advancements in Unified Architecture for Natural Multimodal Interaction](https://arxiv.org/abs/2505.02471) | AR+Diffusion | [GitHub](https://github.com/inclusionAI/Ming) |
| 2025-04 | **Nexus-Gen** | [Nexus-Gen: Unified Image Understanding, Generation, and Editing via Prefilled Autoregression in Shared Embedding Space](https://arxiv.org/abs/2504.21356) | AR+Diffusion | [GitHub](https://github.com/modelscope/Nexus-Gen) |
| 2025-04 | **X-Fusion** | [X-Fusion: Introducing New Modality to Frozen Large Language Models](https://arxiv.org/abs/2504.20996) | AR+Diffusion | — |
| 2025-04 | **MetaQuery** | [Transfer between Modalities with MetaQueries](https://arxiv.org/abs/2504.06256) | AR+Diffusion | — |
| 2025-04 | **UniToken** | [UniToken: Harmonizing Multimodal Understanding and Generation through Unified Visual Encoding](https://arxiv.org/abs/2504.04423) | AR | [GitHub](https://github.com/SxJyJay/UniToken) |
| 2025-04 | **VARGPT-v1.1** | [VARGPT-v1.1: Improve Visual Autoregressive Large Unified Model via Iterative Instruction Tuning and Reinforcement Learning](https://arxiv.org/abs/2504.02949) | AR | [GitHub](https://github.com/VARGPT-family/VARGPT-v1.1) |
| 2025-04 | **ILLUME+** | [ILLUME+: Illuminating Unified MLLM with Dual Visual Tokenization and Diffusion Refinement](https://arxiv.org/abs/2504.01934) | AR+Diffusion | [GitHub](https://github.com/illume-unified-mllm/ILLUME_plus) |
| 2025-03 | **Harmon** | [Harmonizing Visual Representations for Unified Multimodal Understanding and Generation](https://arxiv.org/abs/2503.21979) | AR | [GitHub](https://github.com/wusize/Harmon) |
| 2025-03 | **UGen** | [UGen: Unified Autoregressive Multimodal Model with Progressive Vocabulary Learning](https://arxiv.org/abs/2503.21193) | AR | — |
| 2025-03 | **UniDisc** | [Unified Multimodal Discrete Diffusion](https://arxiv.org/abs/2503.20853) | Discrete Diffusion | [GitHub](https://github.com/alexanderswerdlow/unidisc) |
| 2025-03 | **MMGen** | [MMGen: Unified Multi-modal Image Generation and Understanding in One Go](https://arxiv.org/abs/2503.20644) | Diffusion | [GitHub](https://github.com/jiepengwang/MMGen) |
| 2025-03 | **DualToken** | [DualToken: Towards Unifying Visual Understanding and Generation with Dual Visual Vocabularies](https://arxiv.org/abs/2503.14324) | AR | [GitHub](https://github.com/songweii/dualtoken) |
| 2025-03 | **UniFluid** | [Unified Autoregressive Visual Generation and Understanding with Continuous Tokens](https://arxiv.org/abs/2503.13436) | AR | — |
| 2025-03 | **OmniMamba** | [OmniMamba: Efficient and Unified Multimodal Understanding and Generation via State Space Models](https://arxiv.org/abs/2503.08686) | AR | [GitHub](https://github.com/hustvl/OmniMamba) |
| 2025-03 | **ARMOR** | [ARMOR: Empowering Multimodal Understanding Model with Interleaved Multimodal Generation Capability](https://arxiv.org/abs/2503.06542) | AR | [GitHub](https://github.com/finyorko/armor) |
| 2025-03 | **WeGen** | [WeGen: A Unified Model for Interactive Multimodal Generation as We Chat](https://arxiv.org/abs/2503.01115) | AR+Diffusion | [GitHub](https://github.com/hzphzp/WeGen) |
| 2025-02 | **UniTok** | [UniTok: A Unified Tokenizer for Visual Generation and Understanding](https://arxiv.org/abs/2502.20321) | AR | [GitHub](https://github.com/FoundationVision/UniTok) |
| 2025-02 | **HermesFlow** | [HermesFlow: Seamlessly Closing the Gap in Multimodal Understanding and Generation](https://arxiv.org/abs/2502.12148) | AR+Discrete Diffusion | [GitHub](https://github.com/Gen-Verse/HermesFlow) |
| 2025-02 | **UniMoD** | [UniMoD: Efficient Unified Multimodal Transformers with Mixture-of-Depths](https://arxiv.org/abs/2502.06474) | AR | [GitHub](https://github.com/showlab/UniMoD) |
| 2025-02 | **UniCMs (Show-o Turbo)** | [UniCMs: A Unified Consistency Model For Efficient Multimodal Generation and Understanding](https://arxiv.org/abs/2502.05415) | AR+Discrete Diffusion | [GitHub](https://github.com/zhijie-group/UniCMs) |
| 2025-02 | **QLIP** | [QLIP: Text-Aligned Visual Tokenization Unifies Auto-Regressive Multimodal Understanding and Generation](https://arxiv.org/abs/2502.05178) | AR | [GitHub](https://github.com/NVlabs/QLIP) |
| 2025-01 | **Janus-Pro** | [Janus-Pro: Unified Multimodal Understanding and Generation with Data and Model Scaling](https://arxiv.org/abs/2501.17811) | AR | [GitHub](https://github.com/deepseek-ai/Janus) |
| 2025-01 | **VARGPT** | [VARGPT: Unified Understanding and Generation in a Visual Autoregressive Multimodal Large Language Model](https://arxiv.org/abs/2501.12327) | AR | [GitHub](https://github.com/VARGPT-family/VARGPT) |
| 2025-01 | **D-DiT (Dual Diffusion)** | [Dual Diffusion for Unified Image Generation and Understanding](https://arxiv.org/abs/2501.00289) | Diffusion | [GitHub](https://github.com/zijieli-Jlee/Dual-Diffusion) |
| 2024-12 | **Vitron** | [Vitron: A Unified Pixel-level Vision LLM for Understanding, Generating, Segmenting, Editing](https://arxiv.org/abs/2412.19806) | AR+Diffusion | [GitHub](https://github.com/SkyworkAI/Vitron) |
| 2024-12 | **LMFusion** | [LMFusion: Adapting Pretrained Language Models for Multimodal Generation](https://arxiv.org/abs/2412.15188) | AR+Diffusion | — |
| 2024-12 | **MetaMorph** | [MetaMorph: Multimodal Understanding and Generation via Instruction Tuning](https://arxiv.org/abs/2412.14164) | AR+Diffusion | [GitHub](https://github.com/facebookresearch/metamorph) |
| 2024-12 | **SynerGen-VL** | [SynerGen-VL: Towards Synergistic Image Understanding and Generation with Vision Experts and Token Folding](https://arxiv.org/abs/2412.09604) | AR | — |
| 2024-12 | **LatentLM** | [Multimodal Latent Language Modeling with Next-Token Diffusion](https://arxiv.org/abs/2412.08635) | AR+Diffusion | — |
| 2024-12 | **ILLUME** | [ILLUME: Illuminating Your LLMs to See, Draw, and Self-Enhance](https://arxiv.org/abs/2412.06673) | AR+Diffusion | — |
| 2024-12 | **Divot** | [Divot: Diffusion Powers Video Tokenizer for Comprehension and Generation](https://arxiv.org/abs/2412.04432) | AR+Diffusion | [GitHub](https://github.com/TencentARC/Divot) |
| 2024-12 | **Liquid** | [Liquid: Language Models are Scalable and Unified Multi-modal Generators](https://arxiv.org/abs/2412.04332) | AR | [GitHub](https://github.com/FoundationVision/Liquid) |
| 2024-12 | **TokenFlow** | [TokenFlow: Unified Image Tokenizer for Multimodal Understanding and Generation](https://arxiv.org/abs/2412.03069) | AR | [GitHub](https://github.com/ByteFlow-AI/TokenFlow) |
| 2024-12 | **Orthus** | [Orthus: Autoregressive Interleaved Image-Text Generation with Modality-Specific Heads](https://arxiv.org/abs/2412.00127) | AR+Diffusion | [GitHub](https://github.com/zhijie-group/Orthus) |
| 2024-11 | **JetFormer** | [JetFormer: An Autoregressive Generative Model of Raw Images and Text](https://arxiv.org/abs/2411.19722) | AR | [GitHub](https://github.com/google-research/big_vision) |
| 2024-11 | **MUSE-VL** | [MUSE-VL: Modeling Unified VLM through Semantic Discrete Encoding](https://arxiv.org/abs/2411.17762) | AR | — |
| 2024-11 | **JanusFlow** | [JanusFlow: Harmonizing Autoregression and Rectified Flow for Unified Multimodal Understanding and Generation](https://arxiv.org/abs/2411.07975) | AR+Diffusion | [GitHub](https://github.com/deepseek-ai/Janus) |
| 2024-11 | **MoT** | [Mixture-of-Transformers: A Sparse and Scalable Architecture for Multi-Modal Foundation Models](https://arxiv.org/abs/2411.04996) | AR+Diffusion | — |
| 2024-10 | **PUMA** | [PUMA: Empowering Unified MLLM with Multi-granular Visual Generation](https://arxiv.org/abs/2410.13861) | AR+Diffusion | [GitHub](https://github.com/rongyaofang/PUMA) |
| 2024-10 | **Janus** | [Janus: Decoupling Visual Encoding for Unified Multimodal Understanding and Generation](https://arxiv.org/abs/2410.13848) | AR | [GitHub](https://github.com/deepseek-ai/Janus) |
| 2024-10 | **MMAR** | [MMAR: Towards Lossless Multi-Modal Auto-Regressive Probabilistic Modeling](https://arxiv.org/abs/2410.10798) | AR+Diffusion | — |
| 2024-09 | **Emu3** | [Emu3: Next-Token Prediction is All You Need](https://arxiv.org/abs/2409.18869) | AR | [GitHub](https://github.com/baaivision/Emu3) |
| 2024-09 | **MonoFormer** | [MonoFormer: One Transformer for Both Diffusion and Autoregression](https://arxiv.org/abs/2409.16280) | AR+Diffusion | [GitHub](https://github.com/MonoFormer/MonoFormer) |
| 2024-09 | **VILA-U** | [VILA-U: a Unified Foundation Model Integrating Visual Understanding and Generation](https://arxiv.org/abs/2409.04429) | AR | [GitHub](https://github.com/mit-han-lab/vila-u) |
| 2024-08 | **Show-o** | [Show-o: One Single Transformer to Unify Multimodal Understanding and Generation](https://arxiv.org/abs/2408.12528) | AR+Discrete Diffusion | [GitHub](https://github.com/showlab/Show-o) |
| 2024-08 | **Transfusion** | [Transfusion: Predict the Next Token and Diffuse Images with One Multi-Modal Model](https://arxiv.org/abs/2408.11039) | AR+Diffusion | [GitHub](https://github.com/lucidrains/transfusion-pytorch) |
| 2024-08 | **Lumina-mGPT** | [Lumina-mGPT: Illuminate Flexible Photorealistic Text-to-Image Generation with Multimodal Generative Pretraining](https://arxiv.org/abs/2408.02657) | AR | [GitHub](https://github.com/Alpha-VLLM/Lumina-mGPT) |
| 2024-07 | **SEED-Story** | [SEED-Story: Multimodal Long Story Generation with Large Language Model](https://arxiv.org/abs/2407.08683) | AR+Diffusion | [GitHub](https://github.com/TencentARC/SEED-Story) |
| 2024-07 | **ANOLE** | [ANOLE: An Open, Autoregressive, Native Large Multimodal Models for Interleaved Image-Text Generation](https://arxiv.org/abs/2407.06135) | AR | [GitHub](https://github.com/GAIR-NLP/anole) |
| 2024-05 | **Chameleon** | [Chameleon: Mixed-Modal Early-Fusion Foundation Models](https://arxiv.org/abs/2405.09818) | AR | [GitHub](https://github.com/facebookresearch/chameleon) |
| 2024-05 | **Morph-Tokens** | [Auto-Encoding Morph-Tokens for Multimodal LLM](https://arxiv.org/abs/2405.01926) | AR+Diffusion | [GitHub](https://github.com/DCDmllm/MorphTokens) |
| 2024-04 | **SEED-X** | [SEED-X: Multimodal Models with Unified Multi-granularity Comprehension and Generation](https://arxiv.org/abs/2404.14396) | AR+Diffusion | [GitHub](https://github.com/AILab-CVC/SEED-X) |
| 2024-02 | **LWM** | [World Model on Million-Length Video And Language With Blockwise RingAttention](https://arxiv.org/abs/2402.08268) | AR | [GitHub](https://github.com/LargeWorldModel/LWM) |
| 2024-02 | **Video-LaVIT** | [Video-LaVIT: Unified Video-Language Pre-training with Decoupled Visual-Motional Tokenization](https://arxiv.org/abs/2402.03161) | AR+Diffusion | [GitHub](https://github.com/jy0205/LaVIT) |
| 2024-01 | **MM-Interleaved** | [MM-Interleaved: Interleaved Image-Text Generative Modeling via Multi-modal Feature Synchronizer](https://arxiv.org/abs/2401.10208) | AR+Diffusion | [GitHub](https://github.com/OpenGVLab/MM-Interleaved) |
| 2023-12 | **Emu2** | [Generative Multimodal Models are In-Context Learners](https://arxiv.org/abs/2312.13286) | AR+Diffusion | [GitHub](https://github.com/baaivision/Emu) |
| 2023-12 | **VL-GPT** | [VL-GPT: A Generative Pre-trained Transformer for Vision and Language Understanding and Generation](https://arxiv.org/abs/2312.09251) | AR+Diffusion | [GitHub](https://github.com/AILab-CVC/VL-GPT) |
| 2023-10 | **MiniGPT-5** | [MiniGPT-5: Interleaved Vision-and-Language Generation via Generative Vokens](https://arxiv.org/abs/2310.02239) | AR+Diffusion | [GitHub](https://github.com/eric-ai-lab/MiniGPT-5) |
| 2023-10 | **SEED-LLaMA** | [Making LLaMA SEE and Draw with SEED Tokenizer](https://arxiv.org/abs/2310.01218) | AR+Diffusion | [GitHub](https://github.com/AILab-CVC/SEED) |
| 2023-09 | **DreamLLM** | [DreamLLM: Synergistic Multimodal Comprehension and Creation](https://arxiv.org/abs/2309.11499) | AR+Diffusion | [GitHub](https://github.com/RunpeiDong/DreamLLM) |
| 2023-09 | **LaVIT** | [Unified Language-Vision Pretraining in LLM with Dynamic Discrete Visual Tokenization](https://arxiv.org/abs/2309.04669) | AR+Diffusion | [GitHub](https://github.com/jy0205/LaVIT) |
| 2023-09 | **CM3Leon** | [Scaling Autoregressive Multi-Modal Models: Pretraining and Instruction Tuning](https://arxiv.org/abs/2309.02591) | AR | — |
| 2023-07 | **SEED** | [Planting a SEED of Vision in Large Language Model](https://arxiv.org/abs/2307.08041) | AR+Diffusion | [GitHub](https://github.com/AILab-CVC/SEED) |
| 2023-07 | **Emu** | [Emu: Generative Pretraining in Multimodality](https://arxiv.org/abs/2307.05222) | AR+Diffusion | [GitHub](https://github.com/baaivision/Emu) |
| 2023-05 | **GILL** | [Generating Images with Multimodal Language Models](https://arxiv.org/abs/2305.17216) | AR+Diffusion | [GitHub](https://github.com/kohjingyu/gill) |

### Related: Generation-Centric & Post-Training Works

| Date | Model | Paper | Paradigm | Code |
|:---:|---|---|---|:---:|
| 2026-10 | **RSI** | [Recursive Self-Improvement in Unified Multimodal Models](https://arxiv.org/abs/2610.03002) | Self-improvement using execution-verified synthetic supervision | — |
| 2026-09 | **GPT-Image-2.5 Flare** | [GPT-Image-2.5 Flare (official model documentation)](https://developers.openai.com/api/docs/models/gpt-image-2.5-flare) | Proprietary; T, I → I; generation and editing | — |
| 2026-09 | **GPT-Image-2.5 Sunburst** | [GPT-Image-2.5 Sunburst (official model documentation)](https://developers.openai.com/api/docs/models/gpt-image-2.5-sunburst) | Proprietary; T, I → I; generation and editing | — |
| 2026-09 | **Omni-IO Skills** | [Omni-IO Skills: Harnessing Your Agent Omni-Native](https://arxiv.org/abs/2609.31847) | Tool-based multimodal production harness for agents | [GitHub](https://github.com/any2any-mllm/Omni-IO-Skill) |
| 2026-09 | **LynnReal-Omni** | [LynnReal-Omni: Native multi-modal Video Generation for Agentic Visual Workflows](https://arxiv.org/abs/2609.15863) | Agentic video generation with multimodal references | — |
| 2026-09 | **Uni-LaDiR** | [Uni-LaDiR: Latent Diffusion Unifies Multimodal Reasoning](https://arxiv.org/abs/2609.19878) | Latent diffusion for multimodal reasoning | — |
| 2026-09 | **Understanding–Generation Synergy** | [Uncovering Understanding-Generation Synergy in Native Unified Multimodal Models: From Representation, Task to System](https://arxiv.org/abs/2609.01607) | Representation, task and system analyses | — |
| 2026-09 | **GGF** | [Dreaming in Flow: Generative Grounding Feedback for Self-Evolving Unified Multimodal Models](https://arxiv.org/abs/2609.08282) | Self-evolution using generation-grounding feedback | — |
| 2026-09 | **GRIDUMM** | [Does Gradient Conflict Predict the Understanding--Generation Trade-off? A Controlled Audit of Conflict-Metric Validity in Unified Multimodal Models](https://arxiv.org/abs/2609.38465) | Controlled study of gradient-conflict measurements | — |
| 2026-09 | **Position-Aware Modulation** | [Beyond Layers: Position-Resolved Gradient Conflict and Position-Aware Modulation for Unified Multimodal Models](https://arxiv.org/abs/2609.38485) | Controlling conflicts between understanding and generation gradients | — |
| 2026-09 | **MATE** | [Mutually Adversarial Self-Training with Evolving Data for Unified Multimodal Models](https://arxiv.org/abs/2609.36224) | Adversarial self-training with evolving examples | — |
| 2026-09 | **UMM-Reflection** | [Learning Native Reflection in Unified Models with Interleaved Reinforcement Learning](https://arxiv.org/abs/2609.35767) | Interleaved reinforcement learning for reflection | — |
| 2026-09 | **Puffin-World** | [Puffin-World: Scaling a Unified Multimodal Model with Native 3D World States](https://arxiv.org/abs/2609.04196) | ? | — |
| 2026-08 | **Visual Shortcut Interventions** | [Intervention, Not Shared Latents: Blocking Visual Shortcuts in Audio-Video Generation](https://arxiv.org/abs/2609.22361) | Causal analysis of audio dependence on generated video | — |
| 2026-08 | **EditStream** | [EditStream: A Unified Autoregressive Framework for Interactive Video Generation and Editing](https://arxiv.org/abs/2608.21424) | Interactive autoregressive video generation/editing | [Project](https://real-time-video-research.github.io/editstream/) |
| 2026-08 | **PosterText** | [PosterText: Towards Unified Visual Text Generation and Editing for E-commerce Poster](https://arxiv.org/abs/2608.16289) | Poster generation with editable visual-text patches | — |
| 2026-08 | **Swift-Image** | [Exploring the Performance Frontier of Compact Unified Image Generation Models](https://arxiv.org/abs/2608.20334) | Compact text-to-image and single/multi-image editing model | — |
| 2026-08 | **Vorch-IR** | [Vorch-IR: Long-Form Unified Multimodal Identity Replacement Video Generation](https://arxiv.org/abs/2608.05648) | Long-video identity replacement | [Project](https://vorch-project.github.io/Vorch-IR-project/) |
| 2026-08 | **ToolArtist** | [ToolArtist: Tool-Using Unified Multimodal Models for Agentic Image Generation](https://arxiv.org/abs/2608.04436) | Tool-assisted agentic image generation | — |
| 2026-08 | **C3-UniMM** | [C3-UniMM: Causal Cycle-Consistent Unified Multimodal Modeling via Super Alignment and Shared Decoding Space](https://arxiv.org/abs/2608.28603) | ? | — |
| 2026-08 | **SPARGen** | [SPARGen: Unifying Spatial Perception and Reasoning through Native Multimodal Generation](https://arxiv.org/abs/2608.14138) | ? | — |
| 2026-07 | **SymbOmni** | [SymbOmni: Evolving Agentic Omni Models via Symbolic Concept Learning](https://arxiv.org/abs/2607.12042) | Agentic learning of symbolic visual concepts | — |
| 2026-07 | **CMA** | [Cognitive-structured Multimodal Agent for Multimodal Understanding, Generation, and Editing](https://arxiv.org/abs/2607.08497) | Agent framework for understanding, generation and editing | [GitHub](https://github.com/caseclose/cma-harness) |
| 2026-07 | **AdaViG** | [Model Guides You How to Draw: Adaptive Visual Gating for Unified Multimodal Reasoning](https://arxiv.org/abs/2607.10004) | Adaptive visual gating during reasoning | — |
| 2026-07 | **U&G Transferability** | [Transferability Between Understanding and Generation in Unified Multimodal Models](https://arxiv.org/abs/2607.04423) | Controlled study of transfer between understanding and generation | [Project](https://cvlab-kaist.github.io/UMM_Transferability/) |
| 2026-07 | **SenseNova-Vision** | [Vision as Unified Multimodal Generation](https://arxiv.org/abs/2607.06560) | ? | — |
| 2026-07 | **Rosetta** | [Rosetta: Composable Native Multimodal Pretraining](https://arxiv.org/abs/2607.00293) | ? | — |
| 2026-06 | **Unified Visual Safety Regulator** | [Unified Safe In-context Image Generation in Multimodal Diffusion Transformers via Restricting Unsafe Information Flows](https://arxiv.org/abs/2606.06875) | Inference-time control of unsafe visual conditioning | [GitHub](https://github.com/deng12yx/UVR) |
| 2026-06 | **UniCanvas** | [UniCanvas: A Diffusion-base Unified Model for Text-in-Image Joint Generation](https://arxiv.org/abs/2606.04264) | Diffusion-based text-in-image joint generation | — |
| 2026-06 | **TIDE** | [TIDE: Task-Isolated Diffusion for Unified Video Editing and Generation](https://arxiv.org/abs/2606.08260) | Separating task conditions in video generation/editing | [Project](https://LittleWork123.github.io/tide) |
| 2026-06 | **CineOrchestra** | [CineOrchestra: Unified Entity-Centric Conditioning for Cinematic Video Generation](https://arxiv.org/abs/2606.13768) | Entity, event and camera control for video synthesis | [Project](https://snap-research.github.io/CineOrchestra) |
| 2026-06 | **Orchestra-o1** | [Orchestra-o1: Omnimodal Agent Orchestration](https://arxiv.org/abs/2606.13707) | Modality-aware orchestration of specialist agents | — |
| 2026-06 | **Pareto LoRA** | [Pareto LoRA: Mitigating Modality Imbalance in Unified Multimodal Models via Pareto-Optimal Gradient Integration](https://arxiv.org/abs/2606.17296) | Balancing modality gradients during adaptation | — |
| 2026-06 | **Visual-OPSD** | [Visual-OPSD: Cross-Modal On-Policy Self-Distillation for Efficient Unified Multimodal Reasoning](https://arxiv.org/abs/2606.18974) | On-policy cross-modal self-distillation | — |
| 2026-06 | **Ask, Solve, Generate** | [Ask, Solve, Generate: Self-Evolving Unified Multimodal Understanding and Generation via Self-Consistency Rewards](https://arxiv.org/abs/2606.27376) | Self-evolution with consistency-based rewards | — |
| 2026-06 | **COMPASS** | [COMPASS: Grounding Composition-Intent Guidance in Unified Multimodal Models](https://arxiv.org/abs/2606.28696) | Composition-aware guidance from recognition | — |
| 2026-05 | **Images in Sentences** | [Images in Sentences: Scaling Interleaved Instructions for Unified Visual Generation](https://arxiv.org/abs/2605.12305) | Interleaved instruction data for visual generation | — |
| 2026-05 | **Latent Action Control** | [Latent Action Control for Reasoning-Guided Unified Image Generation](https://arxiv.org/abs/2605.16961) | Reasoning-guided control of visual synthesis | — |
| 2026-05 | **UniVidX** | [UniVidX: A Unified Multimodal Framework for Versatile Video Generation via Diffusion Priors](https://arxiv.org/abs/2605.00658) | Diffusion priors for multiple video generation tasks | [Project](https://houyuanchen111.github.io/UniVidX.github.io/) |
| 2026-05 | **UNO** | [Steering Visual Generation in Unified Multimodal Models with Understanding Supervision](https://arxiv.org/abs/2605.05781) | Understanding-based supervision for visual generation | — |
| 2026-05 | **UniPath** | [UniPath: Adaptive Coordination of Understanding and Generation for Unified Multimodal Reasoning](https://arxiv.org/abs/2605.11400) | Coordinating understanding and generation during reasoning | [GitHub](https://github.com/AIFrontierLab/TorchUMM/tree/main/src/umm/post_training/unipath) |
| 2026-05 | **Interleaved Visual Reasoner** | [Breaking Dual Bottlenecks: Evolving Unified Multimodal Models into Self-Adaptive Interleaved Visual Reasoners](https://arxiv.org/abs/2605.14709) | Adaptive planning of visual reasoning steps | [GitHub](https://github.com/WeChatCV/Interleaved_Visual_Reasoner) |
| 2026-05 | **LatentUMM** | [LatentUMM: Dual Latent Alignment for Unified Multimodal Models](https://arxiv.org/abs/2605.17766) | Aligning understanding and generation latent spaces | [GitHub](https://github.com/AIFrontierLab/TorchUMM/tree/main/src/umm/post_training/LatentUMM) |
| 2026-05 | **SGT** | [Semantic Generative Tuning for Unified Multimodal Models](https://arxiv.org/abs/2605.18714) | Semantic generative tuning with visual supervision | [Project](https://song2yu.github.io/SGT/) |
| 2026-05 | **DIVA** | [DIVA: Harnessing the Representation Divergence in Unified Multimodal Models for Mutual Reinforcement](https://arxiv.org/abs/2605.25328) | Using representation differences to improve both tasks | [GitHub](https://github.com/Jayyy-H/DIVA) |
| 2026-04 | **Wan 2.7 Image / Image-Pro** | [Wan 2.7 Image (official release)](https://www.alibabacloud.com/en/press-room/alibaba-unveils-wan2-7-redefining-personalized-and) | Proprietary; text/image-conditioned synthesis and editing | — |
| 2026-04 | **GPT-Image-2** | [GPT-Image-2 (official model documentation)](https://developers.openai.com/api/docs/models/gpt-image-2) | Proprietary; T, I → I; generation and editing | — |
| 2026-04 | **OmniShow** | [OmniShow: Unifying Multimodal Conditions for Human-Object Interaction Video Generation](https://arxiv.org/abs/2604.11804) | Multimodal conditions for human-object interaction video generation | [Project](https://correr-zhou.github.io/OmniShow/) |
| 2026-04 | **SmartPhotoCrafter** | [SmartPhotoCrafter: Unified Reasoning, Generation and Optimization for Automatic Photographic Image Editing](https://arxiv.org/abs/2604.19587) | Reasoning-based automatic photographic editing | [GitHub](https://github.com/vivoCameraResearch/SmartPhotoCrafter) |
| 2026-04 | **UniGenDet** | [UniGenDet: A Unified Generative-Discriminative Framework for Co-Evolutionary Image Generation and Generated Image Detection](https://arxiv.org/abs/2604.21904) | Joint image generation and synthetic-image detection | [GitHub](https://github.com/Zhangyr2022/UniGenDet) |
| 2026-04 | **SpatialFusion** | [SpatialFusion: Endowing Unified Image Generation with Intrinsic 3D Geometric Awareness](https://arxiv.org/abs/2604.26341) | Geometric grounding for unified image generation | — |
| 2026-04 | **CLEAR** | [CLEAR: Unlocking Generative Potential for Degraded Image Understanding in Unified Multimodal Models](https://arxiv.org/abs/2604.04780) | Using generation to understand degraded images | — |
| 2026-04 | **UniRect-CoT** | [UniRect-CoT: Enhancing Generation in Unified Multimodal Models via Reflective Rectification with Inherent Understanding](https://arxiv.org/abs/2604.13540) | Generation refinement using reflective reasoning | — |
| 2026-03 | **Qwen-Image 2.0 / 2.0-Pro (March snapshot)** | [Qwen-Image 2.0 (official model-release log)](https://www.alibabacloud.com/help/en/model-studio/newly-released-models) | Text/image-conditioned synthesis and editing; dated March 3 snapshot | — |
| 2026-03 | **DreamVideo-Omni** | [DreamVideo-Omni: Omni-Motion Controlled Multi-Subject Video Customization with Latent Identity Reinforcement Learning](https://arxiv.org/abs/2603.12257) | Visual-only video customization with identity and motion controls | — |
| 2026-03 | **Long-Horizon Context Curation** | [How Long Can Unified Multimodal Models Generate Images Reliably? Taming Long-Horizon Interleaved Image Generation via Context Curation](https://arxiv.org/abs/2603.07540) | Maintaining reliability in interleaved image generation | — |
| 2026-03 | **LaDe** | [LaDe: Unified Multi-Layered Graphic Media Generation and Decomposition](https://arxiv.org/abs/2603.17965) | Generation and decomposition of layered graphic media | — |
| 2026-03 | **UniGRPO** | [UniGRPO: Unified Policy Optimization for Reasoning-Driven Visual Generation](https://arxiv.org/abs/2603.23500) | Policy optimization across text reasoning and image synthesis | — |
| 2026-03 | **OmniWeaving** | [OmniWeaving: Towards Unified Video Generation with Free-form Composition and Reasoning](https://arxiv.org/abs/2603.24458) | Video generation with multimodal composition and reasoning | [GitHub](https://github.com/Tencent-Hunyuan/OmniWeaving) |
| 2026-03 | **DreamLite** | [DreamLite: A Lightweight On-Device Unified Model for Image Generation and Editing](https://arxiv.org/abs/2603.28713) | Compact image generation and editing on local devices | [Project](https://carlofkl.github.io/dreamlite/) |
| 2026-03 | **Understanding-Driven Intrinsic Rewards** | [Learning to Generate via Understanding: Understanding-Driven Intrinsic Rewarding for Unified Multimodal Models](https://arxiv.org/abs/2603.06043) | Understanding-based feedback for generation | — |
| 2026-03 | **Interleaved GRPO** | [Towards Unified Multimodal Interleaved Generation via Group Relative Policy Optimization](https://arxiv.org/abs/2603.09538) | Reinforcement learning for interleaved generation | — |
| 2026-03 | **Meta-TTRL** | [Meta-TTRL: A Metacognitive Framework for Self-Improving Test-Time Reinforcement Learning in Unified Multimodal Models](https://arxiv.org/abs/2603.15724) | Self-improvement with test-time reinforcement learning | — |
| 2026-03 | **SeGroS** | [Enhancing Alignment for Unified Multimodal Models via Semantically-Grounded Supervision](https://arxiv.org/abs/2603.19807) | Semantically grounded supervision for alignment | — |
| 2026-03 | **Unify-Agent** | [Unify-Agent: A Unified Multimodal Agent for World-Grounded Image Synthesis](https://arxiv.org/abs/2603.29620) | Agent framework for grounded image synthesis | [GitHub](https://github.com/shawn0728/Unify-Agent) |
| 2026-02 | **Kling Image 3.0 / Image 3.0 Omni** | [Kling AI 3.0 (official release)](https://ir.kuaishou.com/news-releases/news-release-details/kling-ai-launches-30-model-ushering-era-where-everyone-can-be) | Proprietary; visual generation with reference controls | — |
| 2026-02 | **UniReason 1.0** | [UniReason 1.0: A Unified Reasoning Framework for World Knowledge Aligned Image Generation and Editing](https://arxiv.org/abs/2602.02437) | Reasoning and visual refinement for image generation/editing | — |
| 2026-02 | **Continual-NExT** | [Continual-NExT: A Unified Comprehension And Generation Continual Learning Framework](https://arxiv.org/abs/2602.18055) | Continual learning for joint comprehension and generation | — |
| 2026-02 | **CoLoGen** | [CoLoGen: Progressive Learning of Concept-Localization Duality for Unified Image Generation](https://arxiv.org/abs/2602.22150) | Reconciling semantic and spatial controls in image synthesis | — |
| 2026-02 | **Omni-Video 2** | [Omni-Video 2: Scaling MLLM-Conditioned Diffusion for Unified Video Generation and Editing](https://arxiv.org/abs/2602.08820) | MLLM-conditioned diffusion for video generation/editing | [Project](https://howellyoung-s.github.io/Omni-Video2-project/) |
| 2026-02 | **Tele-Omni** | [Tele-Omni: a Unified Multimodal Framework for Video Generation and Editing](https://arxiv.org/abs/2602.09609) | Unified video generation and editing | — |
| 2026-01 | **Unified Thinker** | [Unified Thinker: A General Reasoning Modular Core for Image Generation](https://arxiv.org/abs/2601.03127) | Modular planning for reasoning-intensive image generation | — |
| 2026-01 | **Weakness-Targeted Post-Training** | [Unified Text-Image Generation with Weakness-Targeted Post-Training](https://arxiv.org/abs/2601.04339) | Learning automatic transitions between text and image output | — |
| 2026-01 | **VINO** | [VINO: A Unified Visual Generator with Interleaved OmniModal Context](https://arxiv.org/abs/2601.02358) | Interleaved multimodal conditioning for visual generation | [Project](https://sotamak1r.github.io/VINO-web/) |
| 2026-01 | **CoM-DAD** | [Bridging the Discrete-Continuous Gap: Unified Multimodal Generation via Coupled Manifold Discrete Absorbing Diffusion](https://arxiv.org/abs/2601.04056) | Coupled discrete and continuous diffusion for generation | — |
| 2026-01 | **UniMRG** | [Generation Enhances Understanding in Unified Multimodal Models via Multi-Representation Generation](https://arxiv.org/abs/2601.21406) | Auxiliary reconstruction, depth and segmentation generation | [GitHub](https://github.com/Sugewud/UniMRG) |
| 2026-01 | **UniCorn** | [UniCorn: Towards Self-Improving Unified Multimodal Models through Self-Generated Supervision](https://arxiv.org/abs/2601.03193) | Self-training with model-generated supervision | — |
| 2025-12 | **GPT-Image-1.5** | [GPT-Image-1.5 (official model documentation)](https://developers.openai.com/api/docs/models/gpt-image-1.5) | Proprietary; T, I → I; generation and editing | — |
| 2025-11 | **AIA** | [AIA: Rethinking Architecture Decoupling Strategy In Unified Multimodal Model](https://arxiv.org/abs/2511.22663) | ? | [GitHub](https://github.com/zhengdian1/AIA) |
| 2025-10 | **UniWorld-V2** | [Uniworld-V2: Reinforce Image Editing with Diffusion Negative-aware Finetuning and MLLM Implicit Feedback](https://arxiv.org/abs/2510.16888) | AR+Diffusion | [GitHub](https://github.com/PKU-YuanGroup/UniWorld) |
| 2025-09 | **UiG** | [Understanding-in-Generation: Reinforcing Generative Capability of Unified Model via Infusing Understanding into Generation](https://arxiv.org/abs/2509.18639) | Understanding signals integrated into generation | [GitHub](https://github.com/QC-LY/UiG) |
| 2025-09 | **RecA** | [Reconstruction Alignment Improves Unified Multimodal Models](https://arxiv.org/abs/2509.07295) | - | [GitHub](https://github.com/HorizonWind2004/reconstruction-alignment) |
| 2025-08 | **NextStep-1** | [NextStep-1: Toward Autoregressive Image Generation with Continuous Tokens at Scale](https://arxiv.org/abs/2508.10711) | AR | [GitHub](https://github.com/stepfun-ai/NextStep-1) |
| 2025-08 | **Qwen-Image** | [Qwen-Image Technical Report](https://arxiv.org/abs/2508.02324) | Diffusion | [GitHub](https://github.com/QwenLM/Qwen-Image) |
| 2025-07 | **Lumina-mGPT 2.0** | [Lumina-mGPT 2.0: Stand-Alone AutoRegressive Image Modeling](https://arxiv.org/abs/2507.17801) | AR | [GitHub](https://github.com/Alpha-VLLM/Lumina-mGPT-2.0) |
| 2025-04 | **GPT-Image-1** | [GPT-Image-1 (official model documentation)](https://developers.openai.com/api/docs/models/gpt-image-1) | Proprietary; T, I → I; generation and editing | — |
| 2024-09 | **OmniGen** | [OmniGen: Unified Image Generation](https://arxiv.org/abs/2409.11340) | Diffusion | [GitHub](https://github.com/VectorSpaceLab/OmniGen) |
| 2024-03 | **Mini-Gemini** | [Mini-Gemini: Mining the Potential of Multi-modality Vision Language Models](https://arxiv.org/abs/2403.18814) | AR+Diffusion | [GitHub](https://github.com/dvlab-research/MGM) |

### Specialized Unified Models

| Date | Model / Work | Paper | Focus | Code / Project |
|:---:|---|---|---|:---:|
| 2026-09 | **Open-UniMo** | [Open-UniMo: Towards Unified Motion-Language Understanding and Generation in the Open World](https://arxiv.org/abs/2609.14615) | Open-world motion-language understanding and generation | — |
| 2026-09 | **MIRA** | [MIRA: Real-Time Full-Duplex Human-Robot Interaction for Embodied Companions](https://arxiv.org/abs/2609.24547) | Full-duplex speech interaction with interruptible robot motion | — |
| 2026-09 | **MachEmbodied-U0** | [MachEmbodied-U0: Unified Understanding and Generation Model for Embodied Intelligence](https://arxiv.org/abs/2609.25627) | Embodied understanding, generation, dynamics and actions | [GitHub](https://github.com/MachEmbodied/ME-U0) |
| 2026-09 | **Dynin-Robotics** | [Dynin-Robotics: Omnimodal Unified Diffusion Vision-Language-Action Model](https://arxiv.org/abs/2609.13053) | Diffusion-based vision-language-action modeling | — |
| 2026-08 | **Hunyuan3D-Buffalo 1.0** | [Hunyuan3D-Buffalo 1.0: A Unified Multimodal Model for Scalable 3D Generation, Understanding, and Editing](https://arxiv.org/abs/2608.02711) | 3D generation, understanding and editing | [Project](https://tencent-hunyuan.github.io/Hunyuan3D-Buffalo1.0/) |
| 2026-07 | **ELSA3D** | [ELSA3D: Elastic Semantic Anchoring for Unified 3D Understanding and Generation](https://arxiv.org/abs/2607.06565) | Joint language and multiscale 3D modeling | — |
| 2026-07 | **MUGEN** | [MUGEN: A Unified Framework for Efficient Motion Understanding and Generation](https://arxiv.org/abs/2607.27581) | Efficient continuous motion-language understanding/generation | — |
| 2026-07 | **WorldBagel** | [WorldBagel: Uncovering the Power of Unified Multimodal Models for Vision-Language-Action-World Modeling](https://arxiv.org/abs/2607.03461) | Vision-language-action modeling with generated future observations | — |
| 2026-07 | **S1-Omni** | [S1-Omni: A Unified Multimodal Reasoning Model for Scientific Understanding, Prediction, and Generation](https://arxiv.org/abs/2607.15686) | Scientific understanding, prediction and generation across domain modalities | — |
| 2026-06 | **OMG** | [OMG: Omni-Modal Motion Generation for Generalist Humanoid Control](https://arxiv.org/abs/2606.10340) | Multimodal conditioning for humanoid motion synthesis | [Project](https://tsinghua-mars-lab.github.io/OMG/) |
| 2026-06 | **UniTac** | [UniTac: A Unified Multimodal Model for Cross-Sensor Tactile Understanding and Generation](https://arxiv.org/abs/2606.31451) | Cross-sensor tactile understanding and generation | — |
| 2026-06 | **iFLYTEK-Embodied-Omni** | [iFLYTEK-Embodied-Omni Technical Report](https://arxiv.org/abs/2607.02542) | Vision, language and actions in an embodied foundation model | — |
| 2026-06 | **S1-Omni-Image** | [S1-Omni-Image: A Unified Model for Scientific Image Understanding, Generation, and Editing](https://arxiv.org/abs/2606.24441) | Scientific image understanding, generation and editing | — |
| 2026-05 | **X-OmniClaw** | [X-OmniClaw Technical Report: A Unified Mobile Agent for Multimodal Understanding and Interaction](https://arxiv.org/abs/2605.05765) | Mobile multimodal agent for understanding and interaction | — |
| 2026-05 | **Pelican-Unify 1.0** | [Pelican-Unify 1.0: A Unified Embodied Intelligence Model for Understanding, Reasoning, Imagination and Action](https://arxiv.org/abs/2605.15153) | Embodied understanding, reasoning, imagination and actions | — |
| 2026-05 | **EVA01** | [EVA01: Unified Native 3D Understanding and Generation via Mixture-of-Transformers](https://arxiv.org/abs/2605.16745) | Native 3D understanding and generation with mixture-of-transformers | — |
| 2026-04 | **IAD-Unify** | [IAD-Unify: A Region-Grounded Unified Model for Industrial Anomaly Segmentation, Understanding, and Generation](https://arxiv.org/abs/2604.12440) | Industrial defect segmentation, explanation and generation | — |
| 2026-03 | **UniMotion** | [UniMotion: A Unified Framework for Motion-Text-Vision Understanding and Generation](https://arxiv.org/abs/2603.22282) | Joint motion, text and RGB-image understanding/generation | — |
| 2026-03 | **MMaDA-VLA** | [MMaDA-VLA: Large Diffusion Vision-Language-Action Model with Unified Multi-Modal Instruction and Generation](https://arxiv.org/abs/2603.25406) | Joint denoising of goal observations and robot actions | [Project](https://yliu-cs.github.io/MMaDA-VLA) |
| 2026-02 | **PnP-U3D** | [PnP-U3D: Plug-and-Play 3D Framework Bridging Autoregression and Diffusion for Unified Understanding and Generation](https://arxiv.org/abs/2602.03533) | Combining autoregression and diffusion for 3D U&G | [Project](https://cyw-3d.github.io/PnP-U3D/) |
| 2026-02 | **LLaMo** | [LLaMo: Scaling Pretrained Language Models for Unified Motion Understanding and Generation with Continuous Autoregressive Tokens](https://arxiv.org/abs/2602.12370) | Continuous autoregressive motion-language modeling | [Project](https://kunkun0w0.github.io/project/LLaMo/) |
| 2026-02 | **MoRL** | [MoRL: Reinforced Reasoning for Unified Motion Understanding and Generation](https://arxiv.org/abs/2602.14534) | Motion reasoning and generation with reinforcement learning | [GitHub](https://github.com/AIGeeksGroup/MoRL) |
| 2026-01 | **UniMo** | [UniMo: Unified Motion Generation and Understanding with Chain of Thought](https://arxiv.org/abs/2601.12126) | Motion-language understanding and generation with reasoning | — |
| 2026-01 | **Uni-RS** | [Uni-RS: A Spatially Faithful Unified Understanding and Generation Model for Remote Sensing](https://arxiv.org/abs/2601.17673) | Remote-sensing image understanding and spatially controlled generation | — |

---

## Speech & Audio Language Models

### Spoken Dialogue & Full-Duplex Models

| Date | Model | Paper | Type | Code |
|:---:|---|---|---|:---:|
| 2026-09 | **GPT-Live 1** | [GPT-Live 1 (official model documentation)](https://developers.openai.com/api/docs/models/gpt-live-1) | A, T → A, T; full-duplex front end with backend delegation | — |
| 2026-09 | **PALS** | [Psychoacoustically Aligned Latent Smoothing for Adversarial Robustness of Full-Duplex Speech-to-Speech Dialogue Models](https://arxiv.org/abs/2609.27378) | Latent smoothing against acoustic adversarial attacks | — |
| 2026-09 | **Decoupled Turn-Taking Data** | [Decoupling Turn-Taking from Semantics: A Decoupled Data Approach for Finite-State-Machine-Based Full-Duplex Dialogue](https://arxiv.org/abs/2609.03321) | Separate training of conversational timing and semantics | [GitHub](https://github.com/Liyht/def-fsm) |
| 2026-09 | **AV-STE** | [Noise Adaptive Streaming Audio-Visual Speech Token Enhancement for Robust Full-Duplex Spoken Dialogue Models](https://arxiv.org/abs/2609.08390) | Lip-video-assisted restoration of streaming speech tokens | — |
| 2026-09 | **Spurious-Onset Mitigation** | [Causal Analysis and Mitigation of Spurious Onsets in Full-Duplex Speech LLMs](https://arxiv.org/abs/2609.13445) | Analysis and control of speech during user silence | [GitHub](https://github.com/KentoNishi/icassp27-spurious-onsets) |
| 2026-09 | **FD-VAD** | [FD-VAD: Semantic Endpoint Detection for Streaming Full-Duplex Speech](https://arxiv.org/abs/2609.35791) | Streaming semantic endpoint decisions directly from audio | — |
| 2026-09 | **Voice-Light** | [Voice-Light: A Full-Duplex Cascaded Voice Agent with Causal Turn-Taking and Speculative Generation](https://arxiv.org/abs/2609.20995) | Cascaded duplex agent with speculative generation and playback control | [GitHub](https://github.com/BertilBraun/Voice-Light) |
| 2026-09 | **AdaptDuplex** | [AdaptDuplex: from static to adaptive full-duplex spoken dialogue](https://arxiv.org/abs/2609.29217) | Adaptive duplex interaction built on Qwen3-Omni | — |
| 2026-09 | **Backchannel Control Head** | [Controlling Backchannels in Streamable Full-duplex Models](https://arxiv.org/abs/2609.29418) | Controllable acknowledgments during simultaneous listening/speaking | — |
| 2026-09 | **HiThink Turn** | [HiThink Turn: An Intent-Aware Turn-Taking Control Module for Full-Duplex Dialogue](https://arxiv.org/abs/2609.34096) | Streaming prediction of turn state and response intent | — |
| 2026-09 | **SALMONN-duo** | [SALMONN-duo: Adaptive Dual-System Coordination for Full-Duplex Voice Agents](https://arxiv.org/abs/2609.34247) | Duplex speech front end with asynchronous reasoning/tool backend | — |
| 2026-09 | **CharDuplex** | [CharDuplex: Building Character-Consistent Full-Duplex Spoken Dialogue Models](https://arxiv.org/abs/2609.34461) | Persona-conditioned full-duplex speech dialogue | — |
| 2026-09 | **Self-Listening** | [What Did I Just Say? Self-Listening for Full-Duplex Speech Models](https://arxiv.org/abs/2609.05592) | Tracking spoken output to handle interruptions | — |
| 2026-09 | **TASTE2** | [TASTE2: Text-Aligned Speech Modeling and Deployment toward Full-Duplex Voice Interaction](https://arxiv.org/abs/2609.08956) | Text-aligned speech modeling for duplex interaction | — |
| 2026-09 | **Streaming User Transcription** | [Enabling Streaming User Transcription in Full-Duplex Speech-to-Speech Models](https://arxiv.org/abs/2609.15759) | Adding streaming ASR to speech-to-speech dialogue | — |
| 2026-09 | **Frontend–Backend Tool Calls** | [A frontend-backend architecture for tool calls in full-duplex speech models](https://arxiv.org/abs/2609.19334) | Architecture for tools in full-duplex dialogue | — |
| 2026-09 | **NemotronLabs VoiceChat** | [NemotronLabs VoiceChat: An Open Full-duplex Speech-to-Speech Model with Tool Calling Capabilities](https://arxiv.org/abs/2609.21967) | Full-duplex speech dialogue with tool calls | — |
| 2026-09 | **Context Spanning** | [Context Spanning: A Communication Framework for Full-Duplex Speech Models and External LLM Backends](https://arxiv.org/abs/2609.33443) | Connecting full-duplex speech models to external LLM backends | — |
| 2026-09 | **MultiTalk** | [MultiTalk: Scaling Full-Duplex Speech Models to Long, Multi-Party, Bilingual Conversation](https://arxiv.org/abs/2609.36903) | Full-duplex, multi-party bilingual speech dialogue | — |
| 2026-08 | **Gemini 3.5 Live Translate / Transcribe / Transcribe Live** | [Gemini 3.5 Audio (official model card)](https://deepmind.google/models/model-cards/gemini-3-5-audio/) | A, T → T; Live Translate also outputs speech | — |
| 2026-08 | **LPS-TC** | [Enabling Proactive Spoken Turns via a Generalized Style-Aware Full-Duplex Framework](https://arxiv.org/abs/2608.28630) | Style-aware controller for proactive speech turns | — |
| 2026-08 | **TurnFSM** | [TurnFSM for Full-Duplex Dialogue System: Internalizing State-Machine Logic for Streaming Semantic Voice Activity Detection and Utterance-Level Rejection](https://arxiv.org/abs/2609.04240) | Streaming turn control as learned state transitions | — |
| 2026-08 | **PACE** | [PACE: A Playback-Aligned Context Engine for LLM-Based Full-Duplex Voice Dialogue](https://arxiv.org/abs/2608.07631) | Dialogue context synchronized to audible playback | — |
| 2026-08 | **JoyAI-Talker** | [JoyAI-Talker: Full-Duplex Speech Interactive Large Model Built for Empathetic Voice Agents](https://arxiv.org/abs/2608.01119) | Full-duplex empathetic voice interaction | — |
| 2026-07 | **Qwen-Audio 3.0 Realtime Flash** | [Qwen-Audio 3.0 Realtime Flash (official model-release log)](https://www.alibabacloud.com/help/en/model-studio/newly-released-models) | Proprietary low-latency duplex speech dialogue | — |
| 2026-07 | **GPT-Realtime-2.1 Mini** | [GPT-Realtime-2.1 Mini (official model documentation)](https://developers.openai.com/api/docs/models/gpt-realtime-2.1-mini) | T, I, A → T, speech; distilled reasoning model | — |
| 2026-07 | **GPT-Realtime-2.1** | [GPT-Realtime-2.1 (official model documentation)](https://developers.openai.com/api/docs/models/gpt-realtime-2.1) | T, I, A → T, speech; reasoning and tools | — |
| 2026-07 | **DuplexPO** | [Decoupling Conversational Dynamics in Full-Duplex Spoken Models through Reinforcement Learning](https://arxiv.org/abs/2607.07148) | Reinforcement learning separating timing from response content | — |
| 2026-07 | **SimulS2ST-Omni** | [SimulS2ST-Omni: Data-Efficient Streaming Speech-to-Speech Translation via Explicit Trajectory Supervision](https://arxiv.org/abs/2607.19810) | Streaming speech-to-speech translation | — |
| 2026-07 | **Lychee-FD** | [Hierarchical Acoustic-Semantic Modeling: Modality Separation and Semantic Coherence for Full-Duplex SLMs](https://arxiv.org/abs/2607.06540) | Full-duplex | — |
| 2026-06 | **IRAF** | [IRAF: Interference-Resilient Adaptive Fusion for Noise-Robust End-to-End Full-Duplex Spoken Dialogue Systems](https://arxiv.org/abs/2606.06559) | Adaptive user-audio fusion under interference | — |
| 2026-06 | **State-Inertia Steering** | [Overcoming State Inertia in Full-Duplex Spoken Language Models via Activation Steering](https://arxiv.org/abs/2606.11386) | Activation interventions for immediate interruption comprehension | — |
| 2026-06 | **BayLing-Duplex** | [BayLing-Duplex: Native Full-Duplex Speech Dialogue with a Single Autoregressive LLM](https://arxiv.org/abs/2606.14528) | Single-LLM autoregressive full-duplex dialogue | [GitHub](https://github.com/BayLing-Models/BayLing-Duplex) |
| 2026-06 | **Multi-Faceted Interactivity Alignment** | [Multi-Faceted Interactivity Alignment in Full-Duplex Speech Models](https://arxiv.org/abs/2606.11167) | Full-duplex | — |
| 2026-05 | **GPT-Realtime-Translate** | [GPT-Realtime-Translate (official model documentation)](https://developers.openai.com/api/docs/models/gpt-realtime-translate) | Streaming A → translated speech and transcripts | — |
| 2026-05 | **GPT-Realtime-2** | [GPT-Realtime-2 (official model documentation)](https://developers.openai.com/api/docs/models/gpt-realtime-2) | T, I, A → T, speech; configurable reasoning | — |
| 2026-05 | **PersonaKit** | [PersonaKit (PK): A Plug-and-Play Platform for User Testing Diverse Roles in Full-Duplex Dialogue](https://arxiv.org/abs/2605.06007) | Platform for user testing of duplex dialogue roles | — |
| 2026-05 | **User-Stream Routing Study** | [How Should LLMs Listen While Speaking? A Study of User-Stream Routing in Full-Duplex Spoken Dialogue](https://arxiv.org/abs/2605.10199) | Input routing while a speech model is speaking | — |
| 2026-05 | **Duplex Synchronization Study** | [Synchronization and Turn-Taking in Full-Duplex Speech Dialogue Models](https://arxiv.org/abs/2605.20356) | Analysis of synchronization and turn-taking behavior | — |
| 2026-05 | **Listen-Write-Speak (LWS)** | [Liberating LLM Capabilities in Full-Duplex Speech Models](https://arxiv.org/abs/2606.07547) | Separate listening, text writing and speaking channels | — |
| 2026-05 | **DuplexSLA** | [DuplexSLA: A Full-Duplex Spoken Language Model with Synchronized Speech, Language, and Action](https://arxiv.org/abs/2605.20755) | Full-duplex | [GitHub](https://github.com/hyzhang24/DuplexSLA) |
| 2026-04 | **Human-1** | [Human-1 by Josh Talks: A Full-Duplex Conversational Modeling Framework in Hindi using Real-World Conversations](https://arxiv.org/abs/2604.23295) | Hindi full-duplex conversational modeling | — |
| 2026-04 | **ASPIRin** | [ASPIRin: Action Space Projection for Interactivity-Optimized Reinforcement Learning in Full-Duplex Speech Language Models](https://arxiv.org/abs/2604.10065) | Reinforcement learning for turn-taking behavior | — |
| 2026-04 | **MoshiRAG** | [MoshiRAG: Asynchronous Knowledge Retrieval for Full-Duplex Speech Language Models](https://arxiv.org/abs/2604.12928) | Asynchronous retrieval during full-duplex speech dialogue | — |
| 2026-04 | **UAF** | [UAF: A Unified Audio Front-end LLM for Full-Duplex Speech Interaction](https://arxiv.org/abs/2604.19221) | Audio front end for full-duplex speech interaction | — |
| 2026-03 | **Privacy-Preserving Duplex Dialogue** | [Privacy-Preserving End-to-End Full-Duplex Speech Dialogue Models](https://arxiv.org/abs/2603.08179) | Privacy-aware end-to-end spoken interaction | — |
| 2026-03 | **DuplexCascade** | [DuplexCascade: Full-Duplex Speech-to-Speech Dialogue with VAD-Free Cascaded ASR-LLM-TTS Pipeline and Micro-Turn Optimization](https://arxiv.org/abs/2603.09180) | Cascaded ASR–LLM–TTS duplex interaction with micro-turn control | — |
| 2026-03 | **JAL-Turn** | [JAL-Turn: Joint Acoustic-Linguistic Modeling for Real-Time and Robust Turn-Taking Detection in Full-Duplex Spoken Dialogue Systems](https://arxiv.org/abs/2603.26515) | Acoustic and linguistic cues for turn-taking detection | — |
| 2026-03 | **SoulX-Duplug** | [SoulX-Duplug: Plug-and-Play Streaming State Prediction Module for Realtime Full-Duplex Speech Conversation](https://arxiv.org/abs/2603.14877) | Streaming state prediction for duplex conversation | — |
| 2026-03 | **FLAIR** | [The Silent Thought: Modeling Internal Cognition in Full-Duplex Spoken Dialogue Models via Latent Reasoning](https://arxiv.org/abs/2603.17837) | Latent internal reasoning during full-duplex dialogue | — |
| 2026-02 | **GPT-Realtime-1.5** | [GPT-Realtime-1.5 (official model documentation)](https://developers.openai.com/api/docs/models/gpt-realtime-1.5) | T, I, A → T, speech; real-time voice interaction | — |
| 2026-02 | **S-MARC** | [S-MARC: Causal Streaming Reasoning for Full-Duplex Conversational Behavior Modeling](https://arxiv.org/abs/2602.11065) | Streaming reasoning about conversational behavior | — |
| 2026-02 | **Covo-Audio** | [Covo-Audio Technical Report](https://arxiv.org/abs/2602.09823) | Spoken dialogue | [GitHub](https://github.com/Tencent/Covo-Audio) |
| 2026-01 | **Unit-Based Duplex Agent** | [Unit-Based Agent for Semi-Cascaded Full-Duplex Dialogue Systems](https://arxiv.org/abs/2601.20230) | Semi-cascaded dialogue organized into interaction units | [GitHub](https://github.com/yu-haoyuan/fd-badcat) |
| 2026-01 | **PersonaPlex** | [PersonaPlex: Voice and Role Control for Full Duplex Conversational Speech Models](https://arxiv.org/abs/2602.06053) | Full-duplex | [GitHub](https://github.com/NVIDIA/personaplex) |
| 2026-01 | **F-Actor** | [F-Actor: Controllable Conversational Behaviour in Full-Duplex Models](https://arxiv.org/abs/2601.11329) | Full-duplex | — |
| 2025-12 | **Fun-Audio-Chat** | [Fun-Audio-Chat Technical Report](https://arxiv.org/abs/2512.20156) | Spoken dialogue | [GitHub](https://github.com/FunAudioLLM/Fun-Audio-Chat) |
| 2025-11 | **LFM2-Audio** | [LFM2 Technical Report](https://arxiv.org/abs/2511.23404) | Spoken dialogue | [GitHub](https://github.com/Liquid4All/liquid-audio) |
| 2025-10 | **UltraVoice** | [UltraVoice: Scaling Fine-Grained Style-Controlled Speech Conversations for Spoken Dialogue Models](https://arxiv.org/abs/2510.22588) | Spoken dialogue | [GitHub](https://github.com/bigai-nlco/UltraVoice) |
| 2025-10 | **MOSS-Speech** | [MOSS-Speech: Towards True Speech-to-Speech Models Without Text Guidance](https://arxiv.org/abs/2510.00499) | Spoken dialogue | [GitHub](https://github.com/OpenMOSS/MOSS-Speech) |
| 2025-09 | **EchoX** | [EchoX: Towards Mitigating Acoustic-Semantic Gap via Echo Training for Speech-to-Speech LLMs](https://arxiv.org/abs/2509.09174) | Spoken dialogue | [GitHub](https://github.com/FreedomIntelligence/EchoX) |
| 2025-09 | **FLM-Audio** | [FLM-Audio: Natural Monologues Improves Native Full-Duplex Chatbots via Dual Training](https://arxiv.org/abs/2509.02521) | Full-duplex | [GitHub](https://github.com/cofe-ai/flm-audio) |
| 2025-08 | **GPT-Realtime** | [GPT-Realtime (official model documentation)](https://developers.openai.com/api/docs/models/gpt-realtime) | T, I, A → T, speech; historical GA model | — |
| 2025-08 | **Mini-Omni-Reasoner** | [Mini-Omni-Reasoner: Token-Level Thinking-in-Speaking in Large Speech Models](https://arxiv.org/abs/2508.15827) | Spoken dialogue | [GitHub](https://github.com/xzf-thu/Mini-Omni-Reasoner) |
| 2025-08 | **OSUM-EChat** | [OSUM-EChat: Enhancing End-to-End Empathetic Spoken Chatbot via Understanding-Driven Spoken Dialogue](https://arxiv.org/abs/2508.09600) | Spoken dialogue | [GitHub](https://github.com/ASLP-lab/OSUM) |
| 2025-08 | **TurnGuide** | [TurnGuide: Enhancing Meaningful Full Duplex Spoken Interactions via Dynamic Turn-Level Text-Speech Interleaving](https://arxiv.org/abs/2508.07375) | Full-duplex | [GitHub](https://github.com/dreamtheater123/TurnGuide) |
| 2025-07 | **GOAT-SLM** | [GOAT-SLM: A Spoken Language Model with Paralinguistic and Speaker Characteristic Awareness](https://arxiv.org/abs/2507.18119) | Spoken dialogue | — |
| 2025-07 | **Seed LiveInterpret 2.0** | [Seed LiveInterpret 2.0: End-to-end Simultaneous Speech-to-speech Translation with Your Voice](https://arxiv.org/abs/2507.17527) | Simultaneous S2ST | — |
| 2025-07 | **Step-Audio 2** | [Step-Audio 2 Technical Report](https://arxiv.org/abs/2507.16632) | Spoken dialogue | [GitHub](https://github.com/stepfun-ai/Step-Audio2) |
| 2025-07 | **OpenS2S** | [OpenS2S: Advancing Fully Open-Source End-to-End Empathetic Large Speech Language Model](https://arxiv.org/abs/2507.05177) | Spoken dialogue | [GitHub](https://github.com/CASIA-LM/OpenS2S) |
| 2025-06 | **DeepOmni (DeepTalk)** | [DeepOmni: Towards Seamless and Smart Speech Interaction with Adaptive Modality-Specific MoE](https://arxiv.org/abs/2506.21864) | Spoken dialogue | — |
| 2025-06 | **Aligning SDMs from User Interactions** | [Aligning Spoken Dialogue Models from User Interactions](https://arxiv.org/abs/2506.21463) | Full-duplex | — |
| 2025-06 | **DrVoice** | [DrVoice: Parallel Speech-Text Voice Conversation Model via Dual-Resolution Speech Representations](https://arxiv.org/abs/2506.09349) | Spoken dialogue | — |
| 2025-06 | **Step-Audio-AQAA** | [Step-Audio-AQAA: a Fully End-to-End Expressive Large Audio Language Model](https://arxiv.org/abs/2506.08967) | Spoken dialogue | — |
| 2025-06 | **NTPP** | [NTPP: Generative Speech Language Modeling for Dual-Channel Spoken Dialogue via Next-Token-Pair Prediction](https://arxiv.org/abs/2506.00975) | Full-duplex | — |
| 2025-05 | **SALMONN-omni (standalone)** | [SALMONN-omni: A Standalone Speech LLM without Codec Injection for Full-duplex Conversation](https://arxiv.org/abs/2505.17060) | Full-duplex | [GitHub](https://github.com/bytedance/SALMONN) |
| 2025-05 | **VITA-Audio** | [VITA-Audio: Fast Interleaved Cross-Modal Token Generation for Efficient Large Speech-Language Model](https://arxiv.org/abs/2505.03739) | Spoken dialogue | [GitHub](https://github.com/VITA-MLLM/VITA-Audio) |
| 2025-05 | **Voila** | [Voila: Voice-Language Foundation Models for Real-Time Autonomous Interaction and Voice Role-Play](https://arxiv.org/abs/2505.02707) | Full-duplex | [GitHub](https://github.com/maitrix-org/Voila) |
| 2025-05 | **LLaMA-Omni2** | [LLaMA-Omni2: LLM-based Real-time Spoken Chatbot with Autoregressive Streaming Speech Synthesis](https://arxiv.org/abs/2505.02625) | Spoken dialogue | [GitHub](https://github.com/ictnlp/LLaMA-Omni2) |
| 2025-04 | **TASTE** | [TASTE: Text-Aligned Speech Tokenization and Embedding for Spoken Language Modeling](https://arxiv.org/abs/2504.07053) | Spoken dialogue | [GitHub](https://github.com/mtkresearch/TASTE-SpokenLM) |
| 2025-04 | **VocalNet** | [VocalNet: Speech LLM with Multi-Token Prediction for Faster and High-Quality Generation](https://arxiv.org/abs/2504.04060) | Spoken dialogue | [GitHub](https://github.com/SJTU-OmniAgent/VocalNet) |
| 2025-03 | **Sesame CSM** | [Conversational Speech Model (no paper)](https://github.com/SesameAILabs/csm) | Spoken dialogue | [GitHub](https://github.com/SesameAILabs/csm) |
| 2025-02 | **Baichuan-Audio** | [Baichuan-Audio: A Unified Framework for End-to-End Speech Interaction](https://arxiv.org/abs/2502.17239) | Spoken dialogue | [GitHub](https://github.com/baichuan-inc/Baichuan-Audio) |
| 2025-02 | **FlexDuo** | [FlexDuo: A Pluggable System for Enabling Full-Duplex Capabilities in Speech Dialogue Systems](https://arxiv.org/abs/2502.13472) | Full-duplex | — |
| 2025-02 | **DuplexMamba** | [DuplexMamba: Enhancing Real-time Speech Conversations with Duplex and Streaming Capabilities](https://arxiv.org/abs/2502.11123) | Full-duplex | — |
| 2025-02 | **Step-Audio** | [Step-Audio: Unified Understanding and Generation in Intelligent Speech Interaction](https://arxiv.org/abs/2502.11946) | Spoken dialogue | [GitHub](https://github.com/stepfun-ai/Step-Audio) |
| 2025-02 | **Hibiki** | [High-Fidelity Simultaneous Speech-To-Speech Translation](https://arxiv.org/abs/2502.03382) | Simultaneous S2ST | [GitHub](https://github.com/kyutai-labs/hibiki) |
| 2025-01 | **LUCY** | [LUCY: Linguistic Understanding and Control Yielding Early Stage of Her](https://arxiv.org/abs/2501.16327) | Spoken dialogue | [GitHub](https://github.com/VITA-MLLM/LUCY) |
| 2025-01 | **SpeechGPT 2.0-preview** | [SpeechGPT 2.0-preview (no paper)](https://github.com/OpenMOSS/SpeechGPT-2.0-preview) | Spoken dialogue | [GitHub](https://github.com/OpenMOSS/SpeechGPT-2.0-preview) |
| 2025-01 | **MinMo** | [MinMo: A Multimodal Large Language Model for Seamless Voice Interaction](https://arxiv.org/abs/2501.06282) | Full-duplex | — |
| 2024-12 | **SLAM-Omni** | [SLAM-Omni: Timbre-Controllable Voice Interaction System with Single-Stage Training](https://arxiv.org/abs/2412.15649) | Spoken dialogue | [GitHub](https://github.com/X-LANCE/SLAM-LLM/tree/main/examples/s2s) |
| 2024-12 | **Typhoon2-Audio** | [Typhoon 2: A Family of Open Text and Multimodal Thai Large Language Models](https://arxiv.org/abs/2412.13702) | Spoken dialogue | [GitHub](https://github.com/scb-10x/typhoon2-audio) |
| 2024-12 | **Flow-Omni** | [Continuous Speech Tokens Makes LLMs Robust Multi-Modality Learners](https://arxiv.org/abs/2412.04917) | Spoken dialogue | — |
| 2024-12 | **GLM-4-Voice** | [GLM-4-Voice: Towards Intelligent and Human-Like End-to-End Spoken Chatbot](https://arxiv.org/abs/2412.02612) | Spoken dialogue | [GitHub](https://github.com/zai-org/GLM-4-Voice) |
| 2024-11 | **SALMONN-omni** | [SALMONN-omni: A Codec-free LLM for Full-duplex Speech Understanding and Generation](https://arxiv.org/abs/2411.18138) | Full-duplex | [GitHub](https://github.com/bytedance/SALMONN) |
| 2024-11 | **Freeze-Omni** | [Freeze-Omni: A Smart and Low Latency Speech-to-speech Dialogue Model with Frozen LLM](https://arxiv.org/abs/2411.00774) | Spoken dialogue | [GitHub](https://github.com/VITA-MLLM/Freeze-Omni) |
| 2024-11 | **Westlake-Omni** | [Westlake-Omni (no paper)](https://github.com/xinchen-ai/Westlake-Omni) | Spoken dialogue | [GitHub](https://github.com/xinchen-ai/Westlake-Omni) |
| 2024-11 | **Hertz-dev** | [hertz-dev: open-source full-duplex audio base model (no paper)](https://github.com/Standard-Intelligence/hertz-dev) | Full-duplex | [GitHub](https://github.com/Standard-Intelligence/hertz-dev) |
| 2024-10 | **OmniFlatten** | [OmniFlatten: An End-to-end GPT Model for Seamless Voice Conversation](https://arxiv.org/abs/2410.17799) | Full-duplex | — |
| 2024-10 | **Ichigo** | [Ichigo: Mixed-Modal Early-Fusion Realtime Voice Assistant](https://arxiv.org/abs/2410.15316) | Spoken dialogue | [GitHub](https://github.com/homebrewltd/ichigo) |
| 2024-10 | **IntrinsicVoice** | [IntrinsicVoice: Empowering LLMs with Intrinsic Real-time Voice Interaction Abilities](https://arxiv.org/abs/2410.08035) | Spoken dialogue | — |
| 2024-10 | **MooER-Omni** | [MooER (no paper)](https://github.com/MooreThreads/MooER) | Spoken dialogue | [GitHub](https://github.com/MooreThreads/MooER) |
| 2024-09 | **Moshi** | [Moshi: a speech-text foundation model for real-time dialogue](https://arxiv.org/abs/2410.00037) | Full-duplex | [GitHub](https://github.com/kyutai-labs/moshi) |
| 2024-09 | **SyncLLM** | [Beyond Turn-Based Interfaces: Synchronous LLMs as Full-Duplex Dialogue Agents](https://arxiv.org/abs/2409.15594) | Full-duplex | — |
| 2024-09 | **LLaMA-Omni** | [LLaMA-Omni: Seamless Speech Interaction with Large Language Models](https://arxiv.org/abs/2409.06666) | Spoken dialogue | [GitHub](https://github.com/ictnlp/LLaMA-Omni) |
| 2024-08 | **Mini-Omni** | [Mini-Omni: Language Models Can Hear, Talk While Thinking in Streaming](https://arxiv.org/abs/2408.16725) | Spoken dialogue | [GitHub](https://github.com/gpt-omni/mini-omni) |
| 2024-08 | **LSLM** | [Language Model Can Listen While Speaking](https://arxiv.org/abs/2408.02622) | Full-duplex | — |
| 2024-06 | **RTTL-DG (MiniCPM-Duplex)** | [Beyond the Turn-Based Game: Enabling Real-Time Conversations with Duplex Models](https://arxiv.org/abs/2406.15718) | Full-duplex | — |
| 2024-06 | **PSLM** | [PSLM: Parallel Generation of Text and Speech with LLMs for Low-Latency Spoken Dialogue Systems](https://arxiv.org/abs/2406.12428) | Spoken dialogue | — |
| 2024-06 | **BLSP-Emo** | [BLSP-Emo: Towards Empathetic Large Speech-Language Models](https://arxiv.org/abs/2406.03872) | Spoken dialogue | [GitHub](https://github.com/cwang621/blsp-emo) |
| 2024-02 | **USDM** | [Paralinguistics-Aware Speech-Empowered Large Language Models for Natural Conversation](https://arxiv.org/abs/2402.05706) | Spoken dialogue | — |
| 2023-12 | **E-chat** | [E-chat: Emotion-sensitive Spoken Dialogue System with Large Language Models](https://arxiv.org/abs/2401.00475) | Spoken dialogue | — |
| 2023-12 | **ParalinGPT** | [Paralinguistics-Enhanced Large Language Modeling of Spoken Dialogue](https://arxiv.org/abs/2312.15316) | Spoken dialogue | — |
| 2023-10 | **Parrot** | [Autoregressive Spoken Dialogue Language Modeling with Decoder-only Transformers](https://openreview.net/forum?id=Ttndg2Jl5F) | Full-duplex | — |
| 2023-05 | **Spectron** | [Spoken Question Answering and Speech Continuation Using Spectrogram-Powered LLM](https://arxiv.org/abs/2305.15255) | Spoken dialogue | — |
| 2023-05 | **SpeechGPT** | [SpeechGPT: Empowering Large Language Models with Intrinsic Cross-Modal Conversational Abilities](https://arxiv.org/abs/2305.11000) | Spoken dialogue | [GitHub](https://github.com/0nutation/SpeechGPT) |

### Unified Audio Generation & Understanding

| Date | Model | Paper | Type | Code |
|:---:|---|---|---|:---:|
| 2026-09 | **Alignment-Free Text-Audiobox** | [Alignment-Free Text-Audiobox for Voice Dubbing and Full-Duplex Dialogue Synthesis](https://arxiv.org/abs/2609.03992) | Voice dubbing and overlapping dialogue synthesis | — |
| 2026-09 | **AURA** | [AURA: Unified Multimodal Framework for Conversational Music Editing](https://arxiv.org/abs/2609.14344) | Conversational music editing with multimodal context | — |
| 2026-08 | **SwanTale** | [SwanTale: Unified Multi-Speaker Speech and Audio Generation for Instruct and Zero-Shot Tasks](https://arxiv.org/abs/2608.02023) | Multi-speaker speech and sound generation | [Project](https://swanaigc.github.io/#swantale) |
| 2026-08 | **FireRedTTS3** | [FireRedTTS3: Unified Speech Generation and Editing with Semantically Enriched Speech Representations](https://arxiv.org/abs/2608.17492) | Instruction-driven speech generation and editing | [GitHub](https://github.com/FireRedTeam/FireRedTTS3) |
| 2026-08 | **SonicWeave** | [SonicWeave: Chunk-Routed Mixture-of-Experts for Unified Audio Scene Generation](https://arxiv.org/abs/2608.09571) | Mixture-of-experts audio scene generation | [Project](https://caiyunrui.github.io/SonicWeave) |
| 2026-08 | **MiDashengLM-Gen** | [MiDashengLM-Gen: Unified Audio Scene Generation via LLM-Driven Autoregressive Flow Matching](https://arxiv.org/abs/2608.11804) | LLM-conditioned generation of mixed audio scenes | [GitHub](https://github.com/xiaomi-research/midashenglm-gen) |
| 2026-08 | **FireRedAudio** | [FireRedAudio: A General-Purpose Audio Language Model with Decoupled Continuous Representations for Understanding and Generation](https://arxiv.org/abs/2608.24168) | General audio understanding and generation | [GitHub](https://github.com/FireRedTeam/FireRedAudio) |
| 2026-06 | **UniVoice** | [UniVoice: A Unified Model for Speech and Singing Voice Generation](https://arxiv.org/abs/2606.05852) | Speech and singing synthesis with factorized controls | — |
| 2026-06 | **UniSinger** | [Towards Unified Song Generation and Singing Voice Conversion with Accompaniment Co-Generation](https://arxiv.org/abs/2606.07015) | Song generation, singing voice conversion and accompaniment | — |
| 2026-06 | **AudioWeave** | [Unified Audio Generation and Editing via Joint Condition Modeling and Progressive Training](https://arxiv.org/abs/2606.16435) | Shared conditioning for audio generation and editing | — |
| 2026-06 | **UAT** | [UAT: Unified Audio-Text Diffusion for Audio Generation, Editing, and Captioning](https://arxiv.org/abs/2606.04939) | Audio-text diffusion for generation, editing and captioning | — |
| 2026-06 | **AudioCALM** | [AudioCALM: Continuous Autoregressive Language Modeling for Universal Audio Generation](https://arxiv.org/abs/2606.23080) | Continuous autoregressive universal audio generation | — |
| 2026-05 | **UNISON (sound generation/editing)** | [UNISON: A Unified Sound Generation and Editing Framework via Deep LLM Fusion](https://arxiv.org/abs/2605.31530) | LLM-conditioned sound generation and editing | — |
| 2026-05 | **StepAudio 2.5** | [StepAudio 2.5 Technical Report](https://arxiv.org/abs/2605.23463) | Speech understanding, synthesis and real-time interaction | — |
| 2026-05 | **Dasheng AudioGen** | [Dasheng AudioGen: A Unified Model for Generating Coherent Audio Scenes from Text](https://arxiv.org/abs/2605.27838) | Text-conditioned coherent audio scene generation | [Project](https://nieeim.github.io/Dasheng-AudioGen-Web/) |
| 2026-04 | **CapTalk** | [CapTalk: Unified Voice Design for Single-Utterance and Dialogue Speech Generation](https://arxiv.org/abs/2604.08363) | Caption-conditioned voice design for utterances and dialogues | — |
| 2026-04 | **UniSonate** | [UniSonate: A Unified Model for Speech, Music, and Sound Effect Generation with Text Instructions](https://arxiv.org/abs/2604.22209) | Text-instructed speech, music and sound-effect generation | [Project](https://qiangchunyu.github.io/UniSonate/) |
| 2026-02 | **GPT-Audio-1.5** | [GPT-Audio-1.5 (official model documentation)](https://developers.openai.com/api/docs/models/gpt-audio-1.5) | T, A → T, A; audio chat | — |
| 2026-02 | **UniAudio 2.0** | [UniAudio 2.0: A Unified Audio Language Model with Text-Aligned Factorized Audio Tokenization](https://arxiv.org/abs/2602.04683) | Unified audio model with text-aligned factorized tokens | — |
| 2026-02 | **AudioChat** | [AudioChat: Unified Audio Storytelling, Editing, and Understanding with Transfusion Forcing](https://arxiv.org/abs/2602.17097) | Audio understanding, storytelling and editing | [Project](https://wanchichen.github.io/audiochat/) |
| 2025-12 | **MiMo-Audio** | [MiMo-Audio: Audio Language Models are Few-Shot Learners](https://arxiv.org/abs/2512.23808) | Unified audio gen + understanding | [GitHub](https://github.com/XiaomiMiMo/MiMo-Audio) |
| 2025-11 | **Step-Audio-EditX** | [Step-Audio-EditX Technical Report](https://arxiv.org/abs/2511.03601) | Speech editing | [GitHub](https://github.com/stepfun-ai/Step-Audio-EditX) |
| 2025-10 | **Ming-UniAudio** | [Ming-UniAudio: Speech LLM for Joint Understanding, Generation and Editing with Unified Representation](https://arxiv.org/abs/2511.05516) | Unified audio gen + understanding | [GitHub](https://github.com/inclusionAI/Ming-UniAudio) |
| 2025-09 | **Llama-Mimi** | [Llama-Mimi: Exploring the Limits of Flattened Speech Language Modeling](https://arxiv.org/abs/2509.14882) | Speech LM | [GitHub](https://github.com/llm-jp/llama-mimi) |
| 2025-08 | **GPT-Audio** | [GPT-Audio (official model documentation)](https://developers.openai.com/api/docs/models/gpt-audio) | T, A → T, A; historical GA audio chat | — |
| 2025-06 | **OpusLM** | [OpusLM: A Family of Open Unified Speech Language Models](https://arxiv.org/abs/2506.17611) | Unified speech LM | — |
| 2025-04 | **Kimi-Audio** | [Kimi-Audio Technical Report](https://arxiv.org/abs/2504.18425) | Unified audio gen + understanding | [GitHub](https://github.com/MoonshotAI/Kimi-Audio) |
| 2025-04 | **EmoVoice** | [EmoVoice: LLM-based Emotional Text-To-Speech Model with Freestyle Text Prompting](https://arxiv.org/abs/2504.12867) | LLM-based TTS | — |
| 2025-02 | **Slamming** | [Slamming: Training a Speech Language Model on One GPU in a Day](https://arxiv.org/abs/2502.15814) | Speech LM | [GitHub](https://github.com/slp-rl/slamkit) |
| 2024-11 | **GLM-4-Voice Pretraining** | [Scaling Speech-Text Pre-training with Synthetic Interleaved Data](https://arxiv.org/abs/2411.17607) | Speech-text pretraining | — |
| 2024-06 | **UniAudio 1.5** | [UniAudio 1.5: Large Language Model-driven Audio Codec is A Few-shot Audio Task Learner](https://arxiv.org/abs/2406.10056) | Unified audio gen + understanding | [GitHub](https://github.com/yangdongchao/LLM-Codec) |
| 2024-02 | **Spirit LM** | [Spirit LM: Interleaved Spoken and Written Language Model](https://arxiv.org/abs/2402.05755) | Interleaved speech-text LM | [GitHub](https://github.com/facebookresearch/spiritlm) |
| 2024-01 | **SpeechGPT-Gen** | [SpeechGPT-Gen: Scaling Chain-of-Information Speech Generation](https://arxiv.org/abs/2401.13527) | Speech generation | [GitHub](https://github.com/0nutation/SpeechGPT) |
| 2023-10 | **LauraGPT** | [LauraGPT: Listen, Attend, Understand, and Regenerate Audio with GPT](https://arxiv.org/abs/2310.04673) | Unified audio gen + understanding | — |
| 2023-10 | **UniAudio** | [UniAudio: An Audio Foundation Model Toward Universal Audio Generation](https://arxiv.org/abs/2310.00704) | Universal audio generation | [GitHub](https://github.com/yangdongchao/UniAudio) |
| 2023-06 | **AudioPaLM** | [AudioPaLM: A Large Language Model That Can Speak and Listen](https://arxiv.org/abs/2306.12925) | Unified speech gen + understanding | — |
| 2023-05 | **VioLA** | [VioLA: Unified Codec Language Models for Speech Recognition, Synthesis, and Translation](https://arxiv.org/abs/2305.16107) | Unified codec LM | — |
| 2023-04 | **AudioGPT** | [AudioGPT: Understanding and Generating Speech, Music, Sound, and Talking Head](https://arxiv.org/abs/2304.12995) | LLM + audio tools | [GitHub](https://github.com/AIGC-Audio/AudioGPT) |

### Audio Understanding & Reasoning

| Date | Model | Paper | Type | Code |
|:---:|---|---|---|:---:|
| 2026-10 | **SEA-LM** | [SEA-LM: Egocentric Spatial Audio Understanding for Wearable Microphone Arrays](https://arxiv.org/abs/2610.05610) | Spatial audio perception with wearable microphone arrays | — |
| 2026-09 | **ParA-LLM** | [ParA-LLM: A Unified Approach to Paralinguistic and Acoustic Speech Understanding](https://arxiv.org/abs/2609.22771) | Paralinguistic and acoustic speech understanding | [Project](https://nishitanand.github.io/paralinguistic-understanding-llm/) |
| 2026-09 | **Samsone** | [Samsone: A Family of Open Small Audio Language Models for On-Device Inference](https://arxiv.org/abs/2609.21666) | Small audio language models for local inference | — |
| 2026-09 | **EvoAudio** | [EvoAudio: Recursive Self-Improvement for Audio Understanding](https://arxiv.org/abs/2609.27389) | Self-improvement for audio understanding | — |
| 2026-09 | **Mizar** | [Mizar: A 159M-Parameter Audio-Language Model for Audio Understanding](https://arxiv.org/abs/2609.28344) | 159M-parameter audio-language understanding model | [GitHub](https://github.com/KaiyangLi1992/Mizar_159M) |
| 2026-09 | **SAIL** | [SAIL: Spatial Audio Intelligence with Large Language Models via Disentangled Acoustic-Spatial Encoding and Dual-Stream Q-Former](https://arxiv.org/abs/2609.34347) | Separating acoustic content and spatial information | — |
| 2026-07 | **DETECT-3B-Omni** | [DETECT-3B-Omni is Agnostic of Content and Demographics](https://arxiv.org/abs/2607.03418) | Audio deepfake detection; content/demographic robustness study | — |
| 2026-07 | **Dual-BEATs** | [Dual-BEATs: Unlocking Zero-Shot Stereo Audio Perception in Audio Large Language Models via Dithering](https://arxiv.org/abs/2607.08800) | Stereo perception for audio language models | — |
| 2026-07 | **GigaChat Audio** | [GigaChat Audio: Time-aware Large Audio Language Model](https://arxiv.org/abs/2607.10387) | Long-audio understanding with timestamp grounding | — |
| 2026-06 | **AuRA** | [AuRA: Internalizing Audio Understanding into LLMs as LoRA](https://arxiv.org/abs/2606.11033) | LoRA-based audio understanding inside an LLM | — |
| 2026-06 | **EChO-Agent** | [EChO-Agent: Evidence Chain Orchestration Agent for Audio Reasoning](https://arxiv.org/abs/2606.15141) | Agentic reasoning with chains of audio evidence | — |
| 2026-06 | **MOSS-Audio** | [MOSS-Audio Technical Report](https://arxiv.org/abs/2606.01802) | Audio understanding | [GitHub](https://github.com/OpenMOSS/MOSS-Audio) |
| 2026-05 | **SpeakerLLM** | [SpeakerLLM: A Speaker-Specialized Audio-LLM for Speaker Understanding and Verification Reasoning](https://arxiv.org/abs/2605.15044) | Speaker understanding and verification reasoning | — |
| 2026-05 | **PlanRAG-Audio** | [PlanRAG-Audio: Planning and Retrieval Augmented Generation for Long-form Audio Understanding](https://arxiv.org/abs/2605.20414) | Planning and retrieval for long-audio understanding | — |
| 2026-05 | **Audio-Mind** | [Audio-Mind: An Auditable Agentic Framework for Audio Understanding](https://arxiv.org/abs/2605.28480) | Agent framework with inspectable audio reasoning | — |
| 2026-05 | **TextPro-SLM** | [Minimizing Modality Gap from the Input Side: Your Speech LLM Can Be a Prosody-Aware Text LLM](https://arxiv.org/abs/2605.05927) | Speech understanding | — |
| 2026-04 | **SpotSound** | [SpotSound: Enhancing Large Audio-Language Models with Fine-Grained Temporal Grounding](https://arxiv.org/abs/2604.13023) | Fine-grained temporal audio grounding | [Project](https://loiesun.github.io/spotsound/) |
| 2026-04 | **Audio-DeepThinker** | [Audio-DeepThinker: Progressive Reasoning-Aware Reinforcement Learning for High-Quality Chain-of-Thought Emergence in Audio Language Models](https://arxiv.org/abs/2604.18187) | Progressive reinforcement learning for audio reasoning | — |
| 2026-04 | **LAT-Audio** | [Listening with Time: Precise Temporal Awareness for Long-Form Audio Understanding](https://arxiv.org/abs/2604.22245) | Temporal grounding for long-form audio | [GitHub](https://github.com/alanshaoTT/LAT-Audio-Repo) |
| 2026-04 | **Audio-Cogito** | [Audio-Cogito: Towards Deep Audio Reasoning in Large Audio Language Models](https://arxiv.org/abs/2604.12527) | Audio reasoning | — |
| 2026-04 | **Audio Flamingo Next** | [Audio Flamingo Next: Next-Generation Open Audio-Language Models for Speech, Sound, and Music](https://arxiv.org/abs/2604.10905) | Audio understanding | [GitHub](https://github.com/NVIDIA/audio-flamingo) |
| 2026-03 | **ALARM** | [ALARM: Audio-Language Alignment for Reasoning Models](https://arxiv.org/abs/2603.09556) | Audio-language alignment for reasoning | — |
| 2026-03 | **EvA** | [EvA: An Evidence-First Audio Understanding Paradigm for LALMs](https://arxiv.org/abs/2603.27667) | Audio understanding with explicit evidence preservation | [Project](https://satsuki2486441738.github.io/EvA/) |
| 2026-02 | **AudioRouter** | [AudioRouter: Data Efficient Audio Understanding via RL based Dual Reasoning](https://arxiv.org/abs/2602.10439) | Routing between audio reasoning paths | — |
| 2026-02 | **Echo** | [Echo: Towards Advanced Audio Comprehension via Audio-Interleaved Reasoning](https://arxiv.org/abs/2602.11909) | Reasoning with interleaved audio evidence | [GitHub](https://github.com/wdqqdw/Echo) |
| 2026-01 | **Speech-Hands** | [Speech-Hands: A Self-Reflection Voice Agentic Approach to Speech Recognition and Audio Reasoning with Omni Perception](https://arxiv.org/abs/2601.09413) | Self-reflecting voice agent for recognition and audio reasoning | [GitHub](https://github.com/YukinoWan/Speech-Hands) |
| 2026-01 | **CORD** | [CORD: Bridging the Audio-Text Reasoning Gap via Weighted On-policy Cross-modal Distillation](https://arxiv.org/abs/2601.16547) | Cross-modal distillation of audio-text reasoning | — |
| 2026-01 | **PhaseCoder** | [PhaseCoder: Microphone Geometry-Agnostic Spatial Audio Understanding for Multimodal LLMs](https://arxiv.org/abs/2601.21124) | Spatial audio encoding across microphone geometries | — |
| 2026-01 | **DIFFA-2** | [DIFFA-2: A Practical Diffusion Large Language Model for General Audio Understanding](https://arxiv.org/abs/2601.23161) | Diffusion language modeling for general audio understanding | [GitHub](https://github.com/NKU-HLT/DIFFA.git) |
| 2026-01 | **Qwen3-ASR** | [Qwen3-ASR Technical Report](https://arxiv.org/abs/2601.21337) | ASR | [GitHub](https://github.com/QwenLM/Qwen3-ASR) |
| 2026-01 | **VibeVoice-ASR** | [VIBEVOICE-ASR Technical Report](https://arxiv.org/abs/2601.18184) | ASR | [GitHub](https://github.com/microsoft/VibeVoice) |
| 2025-11 | **Step-Audio-R1** | [Step-Audio-R1 Technical Report](https://arxiv.org/abs/2511.15848) | Audio reasoning | [GitHub](https://github.com/stepfun-ai/Step-Audio-R1) |
| 2025-11 | **Music Flamingo** | [Music Flamingo: Scaling Music Understanding in Audio Language Models](https://arxiv.org/abs/2511.10289) | Music understanding | [GitHub](https://github.com/NVIDIA/audio-flamingo) |
| 2025-08 | **Audio Flamingo Sound-CoT** | [Audio Flamingo Sound-CoT Technical Report: Improving Chain-of-Thought Reasoning in Sound Understanding](https://arxiv.org/abs/2508.11818) | Audio reasoning | [GitHub](https://github.com/NVIDIA/audio-flamingo) |
| 2025-08 | **Audio-Thinker** | [Audio-Thinker: Guiding Audio Language Model When and How to Think via Reinforcement Learning](https://arxiv.org/abs/2508.08039) | Audio reasoning | — |
| 2025-07 | **Voxtral** | [Voxtral](https://arxiv.org/abs/2507.13264) | Speech understanding | — |
| 2025-07 | **Audio Flamingo 3** | [Audio Flamingo 3: Advancing Audio Intelligence with Fully Open Large Audio Language Models](https://arxiv.org/abs/2507.08128) | Audio understanding | [GitHub](https://github.com/NVIDIA/audio-flamingo) |
| 2025-07 | **DeSTA2.5-Audio** | [DeSTA2.5-Audio: Toward General-Purpose Large Audio Language Model with Self-Generated Cross-Modal Alignment](https://arxiv.org/abs/2507.02768) | Audio understanding | [GitHub](https://github.com/kehanlu/DeSTA2.5-Audio) |
| 2025-05 | **Granite-speech** | [Granite-speech: open-source speech-aware LLMs with strong English ASR capabilities](https://arxiv.org/abs/2505.08699) | ASR / speech understanding | [GitHub](https://github.com/ibm-granite/granite-speech-models) |
| 2025-03 | **R1-AQA** | [Reinforcement Learning Outperforms Supervised Fine-Tuning: A Case Study on Audio Question Answering](https://arxiv.org/abs/2503.11197) | Audio reasoning | — |
| 2025-03 | **Mellow** | [Mellow: a small audio language model for reasoning](https://arxiv.org/abs/2503.08540) | Audio reasoning | — |
| 2025-03 | **Audio Flamingo 2** | [Audio Flamingo 2: An Audio-Language Model with Long-Audio Understanding and Expert Reasoning Abilities](https://arxiv.org/abs/2503.03983) | Audio understanding | [GitHub](https://github.com/NVIDIA/audio-flamingo) |
| 2025-03 | **Audio-Reasoner** | [Audio-Reasoner: Improving Reasoning Capability in Large Audio Language Models](https://arxiv.org/abs/2503.02318) | Audio reasoning | [GitHub](https://github.com/xzf-thu/Audio-Reasoner) |
| 2025-02 | **Soundwave** | [Soundwave: Less is More for Speech-Text Alignment in LLMs](https://arxiv.org/abs/2502.12900) | Speech understanding | [GitHub](https://github.com/FreedomIntelligence/Soundwave) |
| 2025-01 | **OSUM** | [OSUM: Advancing Open Speech Understanding Models with Limited Resources in Academia](https://arxiv.org/abs/2501.13306) | Speech understanding | [GitHub](https://github.com/ASLP-lab/OSUM) |
| 2024-12 | **MERaLiON-AudioLLM** | [MERaLiON-AudioLLM: Bridging Audio and Language with Large Language Models](https://arxiv.org/abs/2412.09818) | Audio understanding | — |
| 2024-10 | **VoiceTextBlender** | [VoiceTextBlender: Augmenting Large Language Models with Speech Capabilities via Single-Stage Joint Speech-Text Supervised Fine-Tuning](https://arxiv.org/abs/2410.17485) | Speech understanding | — |
| 2024-10 | **DiVA** | [Distilling an End-to-End Voice Assistant Without Instruction Training Data](https://arxiv.org/abs/2410.02678) | Speech understanding | — |
| 2024-09 | **DeSTA2** | [DeSTA2: Developing Instruction-Following Speech Language Model Without Speech Instruction-Tuning Data](https://arxiv.org/abs/2409.20007) | Speech understanding | [GitHub](https://github.com/kehanlu/DeSTA2) |
| 2024-08 | **Ultravox** | [Ultravox (no paper)](https://github.com/fixie-ai/ultravox) | Speech understanding | [GitHub](https://github.com/fixie-ai/ultravox) |
| 2024-07 | **Qwen2-Audio** | [Qwen2-Audio Technical Report](https://arxiv.org/abs/2407.10759) | Audio understanding | [GitHub](https://github.com/QwenLM/Qwen2-Audio) |
| 2024-06 | **GAMA** | [GAMA: A Large Audio-Language Model with Advanced Audio Understanding and Complex Reasoning Abilities](https://arxiv.org/abs/2406.11768) | Audio understanding | [GitHub](https://github.com/Sreyan88/GAMA) |
| 2024-05 | **SpeechVerse** | [SpeechVerse: A Large-scale Generalizable Audio Language Model](https://arxiv.org/abs/2405.08295) | Audio understanding | — |
| 2024-03 | **WavLLM** | [WavLLM: Towards Robust and Adaptive Speech Large Language Model](https://arxiv.org/abs/2404.00656) | Speech understanding | [GitHub](https://github.com/microsoft/SpeechT5/tree/main/WavLLM) |
| 2024-02 | **Audio Flamingo** | [Audio Flamingo: A Novel Audio Language Model with Few-Shot Learning and Dialogue Abilities](https://arxiv.org/abs/2402.01831) | Audio understanding | [GitHub](https://github.com/NVIDIA/audio-flamingo) |
| 2023-11 | **Qwen-Audio** | [Qwen-Audio: Advancing Universal Audio Understanding via Unified Large-Scale Audio-Language Models](https://arxiv.org/abs/2311.07919) | Audio understanding | [GitHub](https://github.com/QwenLM/Qwen-Audio) |
| 2023-11 | **AudioChatLlama** | [AudioChatLlama: Towards General-Purpose Speech Abilities for LLMs](https://arxiv.org/abs/2311.06753) | Speech understanding | — |
| 2023-10 | **SALMONN** | [SALMONN: Towards Generic Hearing Abilities for Large Language Models](https://arxiv.org/abs/2310.13289) | Audio understanding | [GitHub](https://github.com/bytedance/SALMONN) |
| 2023-09 | **LTU-AS** | [Joint Audio and Speech Understanding](https://arxiv.org/abs/2309.14405) | Audio understanding | [GitHub](https://github.com/YuanGongND/ltu) |
| 2023-09 | **BLSP** | [BLSP: Bootstrapping Language-Speech Pre-training via Behavior Alignment of Continuation Writing](https://arxiv.org/abs/2309.00916) | Speech understanding | [GitHub](https://github.com/cwang621/blsp) |
| 2023-08 | **LLaSM** | [LLaSM: Large Language and Speech Model](https://arxiv.org/abs/2308.15930) | Speech understanding | [GitHub](https://github.com/LinkSoul-AI/LLaSM) |
| 2023-05 | **Pengi** | [Pengi: An Audio Language Model for Audio Tasks](https://arxiv.org/abs/2305.11834) | Audio understanding | [GitHub](https://github.com/microsoft/Pengi) |
| 2023-05 | **LTU** | [Listen, Think, and Understand](https://arxiv.org/abs/2305.10790) | Audio understanding | [GitHub](https://github.com/YuanGongND/ltu) |

## Multimodal Generation (Audio-Video & Any-to-Any Diffusion)

### Joint Audio-Video Generation

| Date | Model | Paper | Modalities (in → out) | Code |
|:---:|---|---|---|:---:|
| 2026-09 | **TimeSteer** | [TimeSteer: Inference-Time Speech Scheduling in Joint Audio-Visual Diffusion Models](https://arxiv.org/abs/2609.01277) | Speech schedule → synchronized V, A (inference control) | — |
| 2026-09 | **Temporal Context Routing** | [The Missing Temporal Link: Temporal Context Routing for Script-Driven Audio-Video Generation](https://arxiv.org/abs/2609.02367) | Script, timing context → V, A | — |
| 2026-09 | **AV-GRPO** | [AV-GRPO: Modality-Anchored Decoupling Diffusion Reinforcement Learning for Joint Audio-Video Generation](https://arxiv.org/abs/2609.29816) | Joint V, A generation post-training | [GitHub](https://github.com/zhiyuxu03/AV-GRPO) |
| 2026-09 | **Soundwich** | [Soundwich: Video Generation with Layered and Controllable Audio](https://arxiv.org/abs/2610.00691) | T, references → V, separately controllable audio layers | [GitHub](https://github.com/CodyNing/Soundwich) |
| 2026-09 | **Encore** | [Encore: Infinite Audio-Video Generation with Adaptive Signal Routing](https://arxiv.org/abs/2609.04249) | A ↔ V (infinite length) | [GitHub](https://github.com/shaohua-pan/Encore) |
| 2026-08 | **OmniVR** | [OmniVR: Audio-Video Conditional Generation for Archival Footage Restoration](https://arxiv.org/abs/2608.04224) | Degraded V, A → restored V, A | [Project](https://xin1u.github.io/OminiVR_PAGE/) |
| 2026-08 | **Vorch-Human** | [Vorch-Human: Unified Multi-Task Human-Centric Generation via Long-Horizon Continuation](https://arxiv.org/abs/2609.26117) | Multimodal conditions → human-centric V, A | [Project](https://vorch-project.github.io/Vorch-Human-Project/) |
| 2026-08 | **Vorch-Streamer** | [Vorch-Streamer: Extending Human Audio-Visual Generation to Real-Time Long-Form Streaming](https://arxiv.org/abs/2608.05663) | Multimodal context → long streaming V, A | [Project](https://vorch-project.github.io/Vorch-Streamer-project/) |
| 2026-08 | **Vorch-Omni** | [Vorch-Omni: Multi-Task Orchestration of Sight and Sound](https://arxiv.org/abs/2608.05803) | T, I, V, A → V, A; generation and editing | [Project](https://vorch-project.github.io/Vorch-Omni-project/) |
| 2026-08 | **Omni-LiveAvatar** | [Omni-LiveAvatar: Minute-Level Real-Time Streaming Joint Audio-Video Avatar Generation](https://arxiv.org/abs/2608.13602) | Multimodal context → streaming avatar V, A | [GitHub](https://github.com/Aoko955/Omni-LiveAvatar) |
| 2026-08 | **DreamX-Creator** | [DreamX-Creator: Democratizing Native Audio-Video Generation at 2K Resolution](https://arxiv.org/abs/2608.31106) | T + first frame → V + A | [GitHub](https://github.com/AMAP-ML/DreamX-Creator) |
| 2026-08 | **JoyAI-Echo-1.5** | [Long-Horizon Audio-Visual Generation for Persistent Stories and Interactive Worlds](https://arxiv.org/abs/2608.23383) | T (+ camera) → long V + A | [Project](https://echo-team-joy-future-academy-jd.github.io/Echo-1.5-Page/) |
| 2026-08 | **EchoWM** | [EchoWM: Open and Enterable Omnimodal World Models](https://arxiv.org/abs/2608.23189) | T + actions → V + sound + music + speech | — |
| 2026-07 | **MiniMax-H3 / H3-Base** | [MiniMax H3 (official launch)](https://www.minimax.io/blog/minimax-h3) | T, I, V, A → V, stereo A; H3-Base weights released August 3 | [Weights / Model card](https://huggingface.co/MiniMaxAI/MiniMax-H3) |
| 2026-07 | **OmniMate** | [OmniMate: Open-Ended Real-Time Streaming Audio-Visual Generation for Interactive Avatars](https://arxiv.org/abs/2607.23023) | Multimodal context → streaming avatar V, A | — |
| 2026-07 | **TaoMate** | [TaoMate: Anchor-Guided Memory Bridging Evolving and Reference States for Real-Time Audio-Video Digital Human Generation](https://arxiv.org/abs/2607.24359) | References, context → streaming digital-human V, A | [Project](https://taoliveaigc.github.io/TaoMate) |
| 2026-07 | **Ripple** | [Ripple: Real-Time Streaming Audio-Video Generation With Cross-Modal Recurrent Memory](https://arxiv.org/abs/2607.26818) | Multimodal context → real-time V, A | — |
| 2026-06 | **Adaptive Reward Weighting** | [Inference-Time Scaling for Joint Audio-Video Generation](https://arxiv.org/abs/2606.03183) | Joint V, A generation; test-time scaling | [Project](https://jung-jaemin.github.io/ITS-AVGen-Proj) |
| 2026-06 | **UnityShots** | [UnityShots: Memory-Driven Multi-Shot Audio-Video Generation with Boundary-Aware Gating](https://arxiv.org/abs/2606.21661) | T, context → multi-shot V, A | [Project](https://jackailab.github.io/Projects/UnityShots) |
| 2026-06 | **MAVIN** | [MAVIN: Multi-Shot Audio-Visual Generation with Customized Narrative Control](https://arxiv.org/abs/2606.29473) | Narrative instructions → multi-shot V, A | — |
| 2026-06 | **AVTok** | [AVTok: 1D Unified Tokenization for Holistic Audio-Video Generation](https://arxiv.org/abs/2606.30811) | A ↔ V, joint AV | [GitHub](https://github.com/HKUST-LongGroup/AVTok) |
| 2026-06 | **MaineCoon** | [MaineCoon: Pursuing A Real-Time Audio-Visual Social World Model](https://arxiv.org/abs/2606.17800) | T / interaction → V + A (real-time) | [GitHub](https://github.com/catnip-ai-tech/MaineCoon) |
| 2026-05 | **StreamChar** | [StreamChar: Long-Horizon Streaming Character Audio-Video Generation with Decoupled Orchestration](https://arxiv.org/abs/2605.25659) | Character context → long streaming V, A | — |
| 2026-05 | **Unison (AV generation)** | [Unison: Harmonizing Motion, Speech, and Sound for Human-Centric Audio-Video Generation](https://arxiv.org/abs/2605.08729) | T, references → human-centric V, speech, sound | — |
| 2026-05 | **SpongeBob** | [SpongeBob: Sync-Aware Harmonious Audio-Visual Generative Editing](https://arxiv.org/abs/2605.25193) | V, A, editing instructions → edited V, A | [Project](https://hy-spongebob.github.io/) |
| 2026-05 | **NAVA** | [Native Audio-Visual Alignment for Generation](https://arxiv.org/abs/2605.30073) | T (+ timbre ref) → V + A | [GitHub](https://github.com/ernie-research/NAVA) |
| 2026-05 | **Baton** | [Baton: Explicit Semantic Blueprints for Joint Video-Audio Generation](https://arxiv.org/abs/2605.25195) | T → V + A | — |
| 2026-05 | **Omni-Customizer** | [Omni-Customizer: End-to-End MultiModal Customization for Joint Audio-Video Generation](https://arxiv.org/abs/2605.17488) | T + ref I + ref A → V + A | — |
| 2026-05 | **OmniNFT** | [OmniNFT: Modality-wise Omni Diffusion Reinforcement for Joint Audio-Video Generation](https://arxiv.org/abs/2605.12480) | T → V + A (RL) | [GitHub](https://github.com/zghhui/OmniNFT) |
| 2026-05 | **SyncDPO** | [SyncDPO: Enhancing Temporal Synchronization in Video-Audio Joint Generation via Preference Learning](https://arxiv.org/abs/2605.12179) | T → V + A (DPO) | [Project](https://syncdpo.github.io/syncdpo/) |
| 2026-04 | **Tora3** | [Tora3: Trajectory-Guided Audio-Video Generation with Physical Coherence](https://arxiv.org/abs/2604.09057) | T, motion trajectories → V, A | [Project](https://ali-videoai.github.io/tora3_page) |
| 2026-04 | **Hallo-Live** | [Hallo-Live: Real-Time Streaming Joint Audio-Video Avatar Generation with Asynchronous Dual-Stream and Human-Centric Preference Distillation](https://arxiv.org/abs/2604.23632) | Context → real-time avatar V, A | — |
| 2026-04 | **Mutual Forcing** | [Mutual Forcing: Dual-Mode Self-Evolution for Fast Autoregressive Audio-Video Character Generation](https://arxiv.org/abs/2604.25819) | Context → autoregressive character V, A | — |
| 2026-04 | **Talker-T2AV** | [Talker-T2AV: Joint Talking Audio-Video Generation with Autoregressive Diffusion Modeling](https://arxiv.org/abs/2604.23586) | T → talking V + speech | [GitHub](https://github.com/zhenye234/Talker-T2AV) |
| 2026-04 | **MMControl** | [MMControl: Unified Multi-Modal Control for Joint Audio-Video Generation](https://arxiv.org/abs/2604.19679) | T + ref I/A/depth/pose → V + A | [GitHub](https://github.com/aim-uofa/MMControl) |
| 2026-03 | **UniTalking** | [UniTalking: A Unified Audio-Video Framework for Talking Portrait Generation](https://arxiv.org/abs/2603.01418) | Multimodal conditioning → talking-portrait V, A | — |
| 2026-03 | **Identity-as-Presence** | [Identity as Presence: Towards Appearance and Voice Personalized Joint Audio-Video Generation](https://arxiv.org/abs/2603.17889) | Appearance, voice references → personalized V, A | [Project](https://chen-yingjie.github.io/projects/Identity-as-Presence) |
| 2026-03 | **Cross-Modal Context Learning** | [Improving Joint Audio-Video Generation with Cross-Modal Context Learning](https://arxiv.org/abs/2603.18600) | Cross-modal context → joint V, A | — |
| 2026-03 | **daVinci-MagiHuman** | [Speed by Simplicity: A Single-Stream Architecture for Fast Audio-Video Generative Foundation Model](https://arxiv.org/abs/2603.21986) | T (+ I) → V + A | [GitHub](https://github.com/GAIR-NLP/daVinci-MagiHuman) |
| 2026-03 | **OmniForcing** | [OmniForcing: Unleashing Real-time Joint Audio-Visual Generation](https://arxiv.org/abs/2603.11647) | T → V + A (real-time) | [GitHub](https://github.com/OmniForcing/OmniForcing) |
| 2026-02 | **LTX-2.3** | [LTX-2.3 (official release)](https://ltx.io/blog/ltx-2-3-release) | T, I, V, A → synchronized V, A | [Weights / Model card](https://huggingface.co/Lightricks/LTX-2.3) |
| 2026-02 | **DreamID-Omni** | [DreamID-Omni: Unified Framework for Controllable Human-Centric Audio-Video Generation](https://arxiv.org/abs/2602.12160) | Multimodal references → controllable human-centric V, A | [Project](https://guoxu1233.github.io/DreamID-Omni/) |
| 2026-02 | **SkyReels-V4** | [SkyReels-V4: Multi-modal Video-Audio Generation, Inpainting and Editing model](https://arxiv.org/abs/2602.21818) | T/I/V/A → V + A | — |
| 2026-02 | **JavisDiT++** | [JavisDiT++: Unified Modeling and Optimization for Joint Audio-Video Generation](https://arxiv.org/abs/2602.19163) | T → V + A | [GitHub](https://github.com/JavisVerse/JavisDiT) |
| 2026-02 | **OmniCustom** | [OmniCustom: Sync Audio-Video Customization Via Joint Audio-Video Generation Model](https://arxiv.org/abs/2602.12304) | T + ref I + ref A → V + A | [GitHub](https://github.com/OmniCustom-project/OmniCustom) |
| 2026-02 | **MOVA** | [MOVA: Towards Scalable and Synchronized Video-Audio Generation](https://arxiv.org/abs/2602.08794) | I + T → V + A | [GitHub](https://github.com/OpenMOSS/MOVA) |
| 2026-02 | **ALIVE** | [ALIVE: Animate Your World with Lifelike Audio-Video Generation](https://arxiv.org/abs/2602.08682) | T / ref I → V + A | [GitHub](https://github.com/FoundationVision/Alive) |
| 2026-01 | **JUST-DUB-IT** | [JUST-DUB-IT: Video Dubbing via Joint Audio-Visual Diffusion](https://arxiv.org/abs/2601.22143) | V + A + T → dubbed V + A | [GitHub](https://github.com/justdubit/just-dub-it) |
| 2026-01 | **Apollo (Klear)** | [Apollo: Unified Multi-Task Audio-Video Joint Generation](https://arxiv.org/abs/2601.04151) | T/I → V + A, T2V, T2A | — |
| 2026-01 | **LTX-2** | [LTX-2: Efficient Joint Audio-Visual Foundation Model](https://arxiv.org/abs/2601.03233) | T/I/A/V → V + A | [GitHub](https://github.com/Lightricks/LTX-2) |
| 2026-01 | **MM-Sonate** | [MM-Sonate: Multimodal Controllable Audio-Video Generation with Zero-Shot Voice Cloning](https://arxiv.org/abs/2601.01568) | T + ref voice → V + A | — |
| 2025-12 | **JoVA** | [JoVA: Unified Multimodal Learning for Joint Video-Audio Generation and Editing](https://arxiv.org/abs/2512.13677) | T/V/A → V + A | [GitHub](https://github.com/Visual-AI/JoVA) |
| 2025-11 | **AV-CDiT** | [Audio-Visual World Models: Learning Physically Grounded Multisensory Dynamics](https://arxiv.org/abs/2512.00883) | AV obs + action → future V + A | — |
| 2025-11 | **Harmony** | [Harmony: Harmonizing Audio and Video Generation through Cross-Task Synergy](https://arxiv.org/abs/2511.21579) | T2AV, A2V, V2A | [GitHub](https://github.com/sjtuplayer/Harmony) |
| 2025-11 | **UniAVGen** | [UniAVGen: Unified Audio and Video Generation with Asymmetric Cross-Modal Interactions](https://arxiv.org/abs/2511.03334) | T/I/A/V → V + A | [GitHub](https://github.com/MCG-NJU/UniAVGen) |
| 2025-10 | **BridgeDiT** | [Taming Text-to-Sounding Video Generation via Advanced Modality Condition and Interaction](https://arxiv.org/abs/2510.03117) | T → V + A | [GitHub](https://github.com/guankaisi/BridgeDiT) |
| 2025-10 | **Ovi** | [Ovi: Twin Backbone Cross-Modal Fusion for Audio-Video Generation](https://arxiv.org/abs/2510.01284) | T (+ I) → V + A | [GitHub](https://github.com/character-ai/Ovi) |
| 2025-09 | **UniVerse-1** | [UniVerse-1: Unified Audio-Video Generation via Stitching of Experts](https://arxiv.org/abs/2509.06155) | T (+ I) → V + A | [GitHub](https://github.com/Dorniwang/UniVerse-1-code) |
| 2025-04 | **OmniTalker** | [OmniTalker: One-shot Real-time Text-Driven Talking Audio-Video Generation With Multimodal Style Mimicking](https://arxiv.org/abs/2504.02433) | T + ref V → talking V + speech | [GitHub](https://github.com/HumanAIGC/omnitalker) |
| 2025-03 | **JavisDiT** | [JavisDiT: Joint Audio-Video Diffusion Transformer with Hierarchical Spatio-Temporal Prior Synchronization](https://arxiv.org/abs/2503.23377) | T → V + A | [GitHub](https://github.com/JavisVerse/JavisDiT) |
| 2025-03 | **R-FLAV** | [RFLAV: Rolling Flow matching for infinite Audio Video generation](https://arxiv.org/abs/2503.08307) | → V + A (infinite) | [GitHub](https://github.com/ErgastiAlex/R-FLAV) |
| 2025-02 | **UniForm** | [UniForm: A Unified Multi-Task Diffusion Transformer for Audio-Video Generation](https://arxiv.org/abs/2502.03897) | T2AV, V2A, A2V | — |
| 2024-12 | **SyncFlow** | [SyncFlow: Toward Temporally Aligned Joint Audio-Video Generation from Text](https://arxiv.org/abs/2412.15220) | T → V + A | — |
| 2024-12 | **AV-Link** | [AV-Link: Temporally-Aligned Diffusion Features for Cross-Modal Audio-Video Generation](https://arxiv.org/abs/2412.15191) | V → A, A → V | [GitHub](https://github.com/snap-research/AVLink) |
| 2024-09 | **SVG-Baseline** | [A Simple but Strong Baseline for Sounding Video Generation: Effective Adaptation of Audio and Video Diffusion Models for Joint Generation](https://arxiv.org/abs/2409.17550) | → V + A | [GitHub](https://github.com/SonyResearch/SVG_baseline) |
| 2024-06 | **AV-DiT** | [AV-DiT: Efficient Audio-Visual Diffusion Transformer for Joint Audio and Video Generation](https://arxiv.org/abs/2406.07686) | → V + A | — |
| 2024-05 | **MMDisCo** | [MMDisCo: Multi-Modal Discriminator-Guided Cooperative Diffusion for Joint Audio and Video Generation](https://arxiv.org/abs/2405.17842) | (T) → V + A | [GitHub](https://github.com/SonyResearch/MMDisCo) |
| 2024-05 | **Visual Echoes** | [Visual Echoes: A Simple Unified Transformer for Audio-Visual Generation](https://arxiv.org/abs/2405.14598) | I ↔ A, joint I + A | — |
| 2024-04 | **TAVDiffusion** | [TAVGBench: Benchmarking Text to Audible-Video Generation](https://arxiv.org/abs/2404.14381) | T → V + A | [GitHub](https://github.com/OpenNLPLab/TAVGBench) |
| 2024-02 | **Seeing and Hearing** | [Seeing and Hearing: Open-domain Visual-Audio Generation with Diffusion Latent Aligners](https://arxiv.org/abs/2402.17723) | T2AV, V2A, A2V, I2A | [GitHub](https://github.com/yzxing87/Seeing-and-Hearing) |
| 2022-12 | **MM-Diffusion** | [MM-Diffusion: Learning Multi-Modal Diffusion Models for Joint Audio and Video Generation](https://arxiv.org/abs/2212.09478) | → V + A; zero-shot V2A | [GitHub](https://github.com/researchmm/MM-Diffusion) |

### Cross-Modal Audio ↔ Video Generation

| Date | Model | Paper | Modalities (in → out) | Code |
|:---:|---|---|---|:---:|
| 2026-06 | **AudioX-Turbo** | [AudioX-Turbo: A Unified Framework for Efficient Anything-to-Audio Generation](https://arxiv.org/abs/2606.12555) | T, I, V → A | [Project](https://zeyuet.github.io/AudioX-Turbo/) |
| 2026-06 | **FoleyGenEx** | [FoleyGenEx: Unified Video-to-Audio Generation with Multi-Modal Control, Temporal Alignment, and Semantic Precision](https://arxiv.org/abs/2606.14049) | V, multimodal controls → A | [Project](https://foleygenex.github.io/FoleyGenEx) |
| 2026-06 | **Foley-Omni** | [Foley-Omni: A Unified Multimodal Generation Model from Task-Level Audio Synthesis to Complete Video Soundtrack Generation](https://arxiv.org/abs/2606.03672) | V + T → speech + SFX + music | — |
| 2026-04 | **ControlFoley** | [ControlFoley: Unified and Controllable Video-to-Audio Generation with Cross-Modal Conflict Handling](https://arxiv.org/abs/2604.15086) | V, T, reference A → controlled A | [GitHub](https://github.com/xiaomi-research/controlfoley) |
| 2026-03 | **V2A-DPO** | [V2A-DPO: Omni-Preference Optimization for Video-to-Audio Generation](https://arxiv.org/abs/2603.11089) | V → A; preference optimization | — |
| 2026-03 | **Foley-Flow** | [Foley-Flow: Coordinated Video-to-Audio Generation with Masked Audio-Visual Alignment and Dynamic Conditional Flows](https://arxiv.org/abs/2603.08126) | V → aligned A | — |
| 2026-02 | **Echoes Over Time** | [Echoes Over Time: Unlocking Length Generalization in Video-to-Audio Generation Models](https://arxiv.org/abs/2602.20981) | V → A; extrapolation to longer sequences | — |
| 2026-01 | **JoyStreamer (JoyAvatar)** | [JoyStreamer: Unlocking Highly Expressive Avatars via Harmonized Text-Audio Conditioning](https://arxiv.org/abs/2602.00702) | T, A → expressive avatar V | [Project](https://joystreamer.github.io/) |
| 2026-01 | **Omni2Sound** | [Omni2Sound: Towards Unified Video-Text-to-Audio Generation](https://arxiv.org/abs/2601.02731) | V + T → A | — |
| 2025-12 | **DreamFoley** | [DreamFoley: Scalable VLMs for High-Fidelity Video-to-Audio Generation](https://arxiv.org/abs/2512.06022) | V + T → A | — |
| 2025-11 | **PrismAudio** | [PrismAudio: Decomposed Chain-of-Thoughts and Multi-dimensional Rewards for Video-to-Audio Generation](https://arxiv.org/abs/2511.18833) | V → A | — |
| 2025-08 | **OmniHuman-1.5** | [OmniHuman-1.5: Instilling an Active Mind in Avatars via Cognitive Simulation](https://arxiv.org/abs/2508.19209) | I + A + T → V | — |
| 2025-08 | **Wan-S2V** | [Wan-S2V: Audio-Driven Cinematic Video Generation](https://arxiv.org/abs/2508.18621) | A + I + T → V | [GitHub](https://github.com/Wan-Video/Wan2.2) |
| 2025-08 | **HunyuanVideo-Foley** | [HunyuanVideo-Foley: Multimodal Diffusion with Representation Alignment for High-Fidelity Foley Audio Generation](https://arxiv.org/abs/2508.16930) | V + T → A | [GitHub](https://github.com/Tencent-Hunyuan/HunyuanVideo-Foley) |
| 2025-08 | **AudioGen-Omni** | [AudioGen-Omni: A Unified Multimodal Diffusion Transformer for Video-Synchronized Audio, Speech, and Song Generation](https://arxiv.org/abs/2508.00733) | V + T/lyrics → audio / speech / song | [GitHub](https://github.com/ciyou2/AudioGen-Omni) |
| 2025-06 | **JAM-Flow** | [JAM-Flow: Joint Audio-Motion Synthesis with Flow Matching](https://arxiv.org/abs/2506.23552) | T/A/motion → facial motion + speech | — |
| 2025-06 | **ThinkSound** | [ThinkSound: Chain-of-Thought Reasoning in Multimodal Large Language Models for Audio Generation and Editing](https://arxiv.org/abs/2506.21448) | V + T → A | [GitHub](https://github.com/QwenAudio/ThinkSound) |
| 2025-06 | **Kling-Foley** | [Kling-Foley: Multimodal Diffusion Transformer for High-Quality Video-to-Audio Generation](https://arxiv.org/abs/2506.19774) | V + T → A | [GitHub](https://github.com/klingfoley/Kling-Foley) |
| 2025-03 | **AudioX** | [AudioX: A Unified Framework for Anything-to-Audio Generation](https://arxiv.org/abs/2503.10522) | T/V/I/A → audio + music | [GitHub](https://github.com/ZeyueT/AudioX) |
| 2025-02 | **OmniHuman-1** | [OmniHuman-1: Rethinking the Scaling-Up of One-Stage Conditioned Human Animation Models](https://arxiv.org/abs/2502.01061) | I + A/V/pose → V | — |
| 2024-12 | **MMAudio** | [MMAudio: Taming Multimodal Joint Training for High-Quality Video-to-Audio Synthesis](https://arxiv.org/abs/2412.15322) | V + T → A | [GitHub](https://github.com/hkchengrex/MMAudio) |

### Any-to-Any Diffusion Models

| Date | Model | Paper | Modalities (in → out) | Code |
|:---:|---|---|---|:---:|
| 2026-06 | **MUNI** | [MUNI: Multimodal Unified Latent Diffusion for Coherent Any-to-Any Generation](https://arxiv.org/abs/2606.16408) | any-to-any (T, I, A) | [GitHub](https://github.com/KAIST-Visual-AI-Group/MUNI) |
| 2025-12 | **FlowBind** | [FlowBind: Efficient Any-to-Any Generation with Bidirectional Flows](https://arxiv.org/abs/2512.15420) | any-to-any (T, I, A) | [GitHub](https://github.com/yeonwoo378/flowbind) |
| 2024-12 | **OmniFlow** | [OmniFlow: Any-to-Any Generation with Multi-Modal Rectified Flows](https://arxiv.org/abs/2412.01169) | any-to-any (T, I, A) | [GitHub](https://github.com/jacklishufan/OmniFlows) |
| 2024-10 | **UniMuMo** | [UniMuMo: Unified Text, Music and Motion Generation](https://arxiv.org/abs/2410.04534) | any-to-any (T, music, motion) | — |
| 2024-06 | **4M-21** | [4M-21: An Any-to-Any Vision Model for Tens of Tasks and Modalities](https://arxiv.org/abs/2406.09406) | any-to-any (21 vision modalities) | [GitHub](https://github.com/apple/ml-4m) |
| 2024-05 | **Lumina-T2X** | [Lumina-T2X: Transforming Text into Any Modality, Resolution, and Duration via Flow-based Large Diffusion Transformers](https://arxiv.org/abs/2405.05945) | T → I / V / 3D / A | [GitHub](https://github.com/Alpha-VLLM/Lumina-T2X) |
| 2023-12 | **4M** | [4M: Massively Multimodal Masked Modeling](https://arxiv.org/abs/2312.06647) | any-to-any (vision modalities) | [GitHub](https://github.com/apple/ml-4m) |
| 2023-11 | **C3Net** | [C3Net: Compound Conditioned ControlNet for Multimodal Content Generation](https://arxiv.org/abs/2311.17951) | T, I, A → I/A | — |
| 2023-06 | **MMLD** | [Multi-modal Latent Diffusion](https://arxiv.org/abs/2306.04445) | any-to-any (latent diffusion) | — |
| 2023-05 | **CoDi** | [Any-to-Any Generation via Composable Diffusion](https://arxiv.org/abs/2305.11846) | any-to-any (T, I, V, A) | [GitHub](https://github.com/microsoft/i-Code/tree/main/i-Code-V3) |

### Proprietary Audio-Video Generators

| Date | Model | Paper | Modalities (in → out) | Code |
|:---:|---|---|---|:---:|
| 2026-08 | **Wan 3.0 Video / Video-Prime** | [Wan 3.0 (official model-release log)](https://www.alibabacloud.com/help/en/model-studio/newly-released-models) | T, I, V, A → V, A; reference-based generation and editing | — |
| 2026-08 | **Gemini Omni 1.1 Flash** | [Gemini Omni 1.1 Flash (official release)](https://blog.google/innovation-and-ai/technology/developers-tools/build-with-gemini-omni-1-1-flash/) | T, I, V, A → V, A; video generation/editing/extension | — |
| 2026-06 | **HappyHorse 1.1** | [HappyHorse 1.1 (official model-release log)](https://www.alibabacloud.com/help/en/model-studio/newly-released-models) | T, I, references → V, A; text/image/reference variants | — |
| 2026-05 | **Gemini Omni Flash** | [Gemini Omni (official launch)](https://blog.google/innovation-and-ai/products/gemini-app/next-evolution-gemini-app/) | T, I, V, A → V, A | [Model card](https://deepmind.google/models/model-cards/gemini-omni-flash/) |
| 2026-04 | **HappyHorse 1.0** | [HappyHorse 1.0 (official model-release log)](https://www.alibabacloud.com/help/en/model-studio/newly-released-models) | T, I, references → V, A; generation and editing | — |
| 2026-04 | **Wan 2.7 T2V / I2V / R2V / VideoEdit** | [Wan 2.7 (official model-release log)](https://www.alibabacloud.com/help/en/model-studio/newly-released-models) | T, I, V, A → V, A; task-dependent conditioning | — |
| 2026-04 | **Veo 3.1 Lite** | [Veo 3.1 Lite (official model card)](https://deepmind.google/models/model-cards/veo-3-1-lite/) | T, I → V, A | — |
| 2026-04 | **Seedance 2.0** | [Seedance 2.0: Advancing Video Generation for World Complexity](https://arxiv.org/abs/2604.14148) | T + I + A + V → V + A | — |
| 2026-02 | **Kling Video 3.0 / Video 3.0 Omni** | [Kling AI 3.0 (official release)](https://ir.kuaishou.com/news-releases/news-release-details/kling-ai-launches-30-model-ushering-era-where-everyone-can-be) | T, I, V, A → V, A; reference and storyboard controls | [Guide](https://kling.ai/quickstart/klingai-video-3-omni-model-user-guide) |
| 2025-12 | **Wan 2.6 T2V / I2V / R2V** | [Wan 2.6 (official release)](https://www.alibabacloud.com/en/press-room/alibaba-unveils-wan2-6-series-enabling-everyone) | T, I, reference V/A → V, A; multi-shot generation | — |
| 2025-12 | **Seedance 1.5 pro** | [Seedance 1.5 pro: A Native Audio-Visual Joint Generation Foundation Model](https://arxiv.org/abs/2512.13507) | T/I → V + A | — |
| 2025-12 | **Kling 2.6** | [Kling AI Video 2.6: simultaneous audio-visual generation (press release)](https://www.nasdaq.com/press-release/kling-ai-launches-video-26-model-simultaneous-audio-visual-generation-capability) | T/I → V + A | — |
| 2025-10 | **Veo 3.1 / Veo 3.1 Fast** | [Veo 3.1 (official release)](https://developers.googleblog.com/en/introducing-veo-3-1-and-new-creative-capabilities-in-the-gemini-api/) | T, I, V (extension) → V, A | — |
| 2025-09 | **Sora 2** | [Sora 2 System Card](https://openai.com/index/sora-2-system-card/) | T/I → V + A | — |
| 2025-09 | **Wan 2.5 (preview)** | [Wan 2.5: native audio-visual generation](https://wan.video/) | T/I → V + A | — |
| 2025-05 | **Veo 3** | [Veo 3 Tech Report](https://storage.googleapis.com/deepmind-media/veo/Veo-3-Tech-Report.pdf) | T/I → V + A | — |
| 2024-10 | **Movie Gen** | [Movie Gen: A Cast of Media Foundation Models](https://arxiv.org/abs/2410.13720) | T/I → V; V + T → A | — |

## Efficiency, Tokenization & Serving

These works improve the representation, runtime, tooling or training data of omni and unified models. They are listed separately from foundation models.

### Efficiency & Serving

| Date | Model / Work | Paper | Focus | Code / Project |
|:---:|---|---|---|:---:|
| 2026-09 | **Composable Omni Evaluation** | [A Composable Evaluation System for Reproducible Omni-Modal Foundation Model Evaluation](https://arxiv.org/abs/2609.01315) | Reproducible modular evaluation system | [GitHub](https://github.com/naver-ai/omni-evaluator) |
| 2026-09 | **Acoustic-to-Text KV Compression** | [Acoustic-to-Text KV Compression for Full-Duplex Speech Models](https://arxiv.org/abs/2609.31224) | Replacing older acoustic cache states with transcript memory | — |
| 2026-09 | **OmniKVQuant** | [OmniKVQuant: KV Cache Quantization for Omni-LLMs](https://arxiv.org/abs/2609.11582) | Quantization of omni-model KV caches | [GitHub](https://github.com/kaistmm/OmniKVQuant) |
| 2026-09 | **UniCache** | [UniCache: Task- and Type-Aware KV Cache Compression for Unified Multimodal Models](https://arxiv.org/abs/2609.32831) | Task-aware cache compression for unified models | — |
| 2026-09 | **OmniTide** | [OmniTide: Co-Designing Algorithms and Systems for Efficient On-Device Omni-LLM Streaming](https://arxiv.org/abs/2609.34653) | Algorithms and systems for on-device streaming | — |
| 2026-09 | **OmniRoute** | [OmniRoute: Mapping Temporal Semantic Evidence to Audio-Visual Token Budgets for Efficient Omnimodal Large Language Models](https://arxiv.org/abs/2609.37052) | Temporal evidence-based allocation of audio-visual token budgets | — |
| 2026-08 | **HorizonServe** | [HorizonServe: Coordinating Request Scheduling with GPU Sharing for Omni-Model Serving](https://arxiv.org/abs/2608.01785) | Request scheduling and GPU sharing for omni serving | — |
| 2026-08 | **OmniPack** | [OmniPack: Unified Token Compression for Efficient Omni-modal Large Language Models](https://arxiv.org/abs/2608.03812) | Compression of multimodal input tokens | — |
| 2026-08 | **A-PACK** | [Deferred Audio Pruning with Local Audio-Visual Dynamics for Omni-LLMs](https://arxiv.org/abs/2608.08794) | Delayed audio-token pruning using local audio-visual dynamics | — |
| 2026-08 | **Omni2LoRA** | [Omni2LoRA: Coherence-Preserving Parametric Memory for Efficient Omni Language Models](https://arxiv.org/abs/2608.09227) | Parametric memory for multimodal coherence | — |
| 2026-07 | **vLLM Audio Pipeline** | [An Efficient vLLM-Based Inference Pipeline for Unified Audio Understanding and Generation](https://arxiv.org/abs/2607.02119) | Efficient serving of speech understanding and generation | — |
| 2026-07 | **OmniFocus** | [OmniFocus: Query-Guided Modality-Balanced Token Compression for Omni-Modal Large Language Models](https://arxiv.org/abs/2607.03050) | Query-guided compression with modality balancing | — |
| 2026-07 | **ReMo** | [Out of Sight, Still in Mind: Token Compression for Omni-LLMs](https://arxiv.org/abs/2607.21179) | Preserving omitted-token information during compression | — |
| 2026-07 | **OmniScope** | [OmniScope: Modality-Decoupled Token Compression for Omnimodal Large Language Models](https://arxiv.org/abs/2607.23193) | Modality-specific token compression | [GitHub](https://github.com/MAC-AutoML/OmniScope) |
| 2026-07 | **Omni-Prune** | [Omni-Prune: Query-Aware Unified Token Pruning for Efficient Omnimodal Large Language Models](https://arxiv.org/abs/2607.23445) | Query-dependent pruning across modalities | [GitHub](https://github.com/kimberlyii/Omni-Prune) |
| 2026-06 | **MorphoQuant** | [MorphoQuant: Modality-Aware Quantization for Omni-modal Large Language Models](https://arxiv.org/abs/2606.04349) | Post-training quantization across modalities | — |
| 2026-06 | **LiveServe** | [LiveServe: Interaction-Aware Serving for Real-Time Omni-Modal LLMs](https://arxiv.org/abs/2606.22983) | Serving adapted to real-time conversational interactions | — |
| 2026-06 | **Omni-Flow** | [Omni-Flow: A Unified Workflow Orchestration and Distributed KV Cache Sharing Framework for Multimodal Inference](https://arxiv.org/abs/2606.31093) | Distributed multimodal workflows with shared KV caches | — |
| 2026-06 | **AVOC** | [AVOC: Enhancing Hour-Level Audio-Video Understanding in Omni-Modal LLMs via Retrieval-Inspired Token Compression](https://arxiv.org/abs/2606.24286) | Retrieval-inspired compression for hour-long audio-video | — |
| 2026-05 | **MegaScale-Omni** | [MegaScale-Omni: A Hyper-Scale, Workload-Resilient System for MultiModal LLM Training in Production](https://arxiv.org/abs/2605.08962) | Large-scale multimodal training system | — |
| 2026-05 | **SEATS** | [Stage-adaptive Token Selection for Efficient Omni-modal LLMs](https://arxiv.org/abs/2605.20035) | Input-token selection adapted to model stage | [GitHub](https://github.com/xxayt/SEATS) |
| 2026-05 | **ContextGuard** | [Keep What Audio Cannot Say: Context-Preserving Token Pruning for Omni-LLMs](https://arxiv.org/abs/2605.11605) | Preserving visual information not recoverable from audio | — |
| 2026-05 | **OmniRefine** | [OmniRefine: Alignment-Aware Cooperative Compression for Efficient Omnimodal Large Language Models](https://arxiv.org/abs/2605.12056) | Compression that accounts for cross-modal alignment | — |
| 2026-05 | **OmniDrop** | [OmniDrop: Layer-wise Token Pruning for Omni-modal LLMs via Query-Guidance](https://arxiv.org/abs/2605.14458) | Layer-by-layer query-guided pruning | — |
| 2026-05 | **OmniSelect** | [OmniSelect: Dynamic Modality-Aware Token Compression for Efficient Omni-modal Large Language Models](https://arxiv.org/abs/2605.18041) | Dynamic selection of modality-specific tokens | — |
| 2026-05 | **O-MARC** | [O-MARC: Omni Memory-Augmented Compression Distillation for Efficient Video Understanding](https://arxiv.org/abs/2605.26584) | Distillation with compressed multimodal memory | — |
| 2026-05 | **OmniMem** | [OmniMem: Perturbation-aware Memory Compression for Streaming Audio-Visual LLMs](https://arxiv.org/abs/2606.07577) | Streaming memory compression resistant to perturbations | [GitHub](https://github.com/bytedance/SALMONN/tree/omni_mem) |
| 2026-04 | **Relax** | [Relax: An Asynchronous Reinforcement Learning Engine for Omni-Modal Post-Training at Scale](https://arxiv.org/abs/2604.11554) | Asynchronous reinforcement-learning infrastructure | [GitHub](https://github.com/rednote-ai/Relax) |
| 2026-04 | **TorchUMM** | [TorchUMM: A Unified Multimodal Model Codebase for Evaluation, Analysis, and Post-training](https://arxiv.org/abs/2604.10784) | Evaluation, analysis and post-training codebase | [GitHub](https://github.com/AIFrontierLab/TorchUMM) |
| 2026-03 | **BiGain** | [BiGain: Unified Token Compression for Joint Generation and Classification](https://arxiv.org/abs/2603.12240) | Compression preserving generation and classification behavior | [GitHub](https://github.com/Greenoso/BiGain) |
| 2026-03 | **Omni Attention-Sink Analysis** | [On the Nature of Attention Sink that Shapes Decoding Strategy in Omni-LLMs](https://arxiv.org/abs/2603.14337) | Attention structure and its implications for decoding | — |
| 2026-03 | **DASH** | [DASH: Dynamic Audio-Driven Semantic Chunking for Efficient Omnimodal Token Compression](https://arxiv.org/abs/2603.15685) | Audio-conditioned chunking for token compression | [GitHub](https://github.com/laychou666/DASH) |
| 2026-03 | **UniCompress** | [UniCompress: Token Compression for Unified Vision-Language Understanding and Generation](https://arxiv.org/abs/2603.11320) | Token compression for visual understanding and generation | — |
| 2026-02 | **vLLM-Omni** | [vLLM-Omni: Fully Disaggregated Serving for Any-to-Any Multimodal Models](https://arxiv.org/abs/2602.02204) | Disaggregated serving of multimodal generation stages | [GitHub](https://github.com/vllm-project/vllm-omni) |
| 2026-02 | **OmniSIFT** | [OmniSIFT: Modality-Asymmetric Token Compression for Efficient Omni-modal Large Language Models](https://arxiv.org/abs/2602.04804) | Asymmetric compression across modalities | [GitHub](https://github.com/dingyue772/OmniSIFT) |
| 2026-01 | **FastAV** | [FastAV: Efficient Token Pruning for Audio-Visual Large Language Model Inference](https://arxiv.org/abs/2601.13143) | Audio-visual token pruning at inference time | — |

### Unified Tokenizers & Encoders

| Date | Model / Work | Paper | Focus | Code / Project |
|:---:|---|---|---|:---:|
| 2026-07 | **OmniVAE** | [OmniVAE: An Audio-Video VAE with Cross-Modal Alignment for Joint Generation](https://arxiv.org/abs/2607.23855) | Aligned audio-video latent representations for generation | — |
| 2026-05 | **Semantic-Dictionary Codebooks** | [Learning from Semantic Dictionaries: Discriminative Codebook Contrastive Learning for Unified Visual Representation and Generation](https://arxiv.org/abs/2605.25012) | Visual token learning for discriminative and generative tasks | — |
| 2026-04 | **Speech VAE Distillation Study** | [On the Distillation Loss Functions of Speech VAE for Unified Reconstruction, Understanding, and Generation](https://arxiv.org/abs/2604.12383) | Audio latent alignment for reconstruction, understanding and generation | — |
| 2026-03 | **EvoTok** | [EvoTok: A Unified Image Tokenizer via Residual Latent Evolution for Visual Understanding and Generation](https://arxiv.org/abs/2603.12108) | Image tokenizer with residual latent refinement | — |
| 2026-02 | **DashengTokenizer** | [DashengTokenizer: One layer is enough for unified audio understanding and generation](https://arxiv.org/abs/2602.23765) | Continuous audio tokens shared by understanding and generation | — |
| 2026-02 | **Omni-C** | [Omni-C: Compressing Heterogeneous Modalities into a Single Dense Encoder](https://arxiv.org/abs/2603.05528) | Single dense encoder for heterogeneous modalities | — |
| 2026-01 | **OpenVision 3** | [OpenVision 3: A Family of Unified Visual Encoder for Both Understanding and Generation](https://arxiv.org/abs/2601.15369) | Shared visual encoders for understanding and generation | — |
| 2025-03 | **SemHiTok** | [SemHiTok: A Unified Image Tokenizer via Semantic-Guided Hierarchical Codebook for Multimodal Understanding and Generation](https://arxiv.org/abs/2503.06764) | Hierarchical image tokens for understanding and generation | — |

---

### Datasets & Data Pipelines

| Date | Model / Work | Paper | Focus | Code / Project |
|:---:|---|---|---|:---:|
| 2026-09 | **ConversationalVoice** | [ConversationalVoice: Full-Duplex Speech Data from Real Conversations through Source-Faithful Reconstruction and Conversation-Grounded Expansion](https://arxiv.org/abs/2609.08147) | Conversation-grounded data for duplex speech models | — |
| 2026-09 | **DuplexDrama** | [DuplexDrama: A Synthesized Dialogue Dataset with Scenarios, Full-Duplex Behaviors, Expressive Speech, and Sound Events](https://arxiv.org/abs/2609.12872) | Synthetic scenarios with duplex speech behaviors and sound events | [Project](https://dunjie5465.github.io/duplexdrama-demo/) |
| 2026-07 | **DuplexChat** | [DuplexChat: Constructing Speaker-Separated Full-Duplex Dialogue Speech at Scale for Spoken Dialogue Language Modeling](https://arxiv.org/abs/2607.04941) | Large-scale speaker-separated dialogue data | — |
| 2026-06 | **CineDance-1M / CineBench** | [CineDance: Towards Next-Generation Multi-Shot Long-Form Cinematic Audio-Video Generation](https://arxiv.org/abs/2606.09639) | Multi-shot audio-video training data and narrative evaluation | [Project](https://aliothchen.github.io/projects/CineDance/) |
| 2026-06 | **OmniVideo-100K** | [OmniVideo-100K: A Dataset for Audio-Visual Reasoning through Structured Scripts and Evidence Chains](https://arxiv.org/abs/2606.14702) | Audio-visual reasoning data with scripts and evidence chains | [GitHub](https://github.com/MiG-NJU/OmniVideo-100K) |
| 2026-04 | **DialogueSidon** | [DialogueSidon: Recovering Full-Duplex Dialogue Tracks from In-the-Wild Dialogue Audio](https://arxiv.org/abs/2604.09344) | Recovering overlapping dialogue tracks from recordings | — |
| 2026-03 | **Sommelier** | [Sommelier: Scalable Open Multi-turn Audio Pre-processing for Full-duplex Speech Language Models](https://arxiv.org/abs/2603.25750) | Audio preprocessing for multi-turn duplex dialogue | — |

---

## Benchmarks

### Omni-Modal & Audio-Visual Benchmarks

| Date | Model | Paper | Evaluates | Code |
|:---:|---|---|---|:---:|
| 2026-09 | **Tri-PvP** | [Tri-PvP: Exposing Modality Bias in Omni-Modal Large Language Models through Perceptual-Propositional Evidence Conflicts](https://arxiv.org/abs/2609.06011) | Conflicting perceptual and propositional evidence across three modalities | — |
| 2026-09 | **Omni Demand Understanding** | [Omni Demand Understanding: A Benchmark for Contextual User-Intent Inference in Multimodal Interaction](https://arxiv.org/abs/2609.21392) | Inferring contextual user intent from multimodal interactions | — |
| 2026-09 | **AVTrace** | [AVTrace: Diagnosing Audio-Visual Temporal Reasoning in Omni Models](https://arxiv.org/abs/2609.19991) | Audio-visual temporal reasoning diagnostics | — |
| 2026-09 | **Video-HolmesV2** | [Video-HolmesV2: Can MLLMs Reason with Spatio-Temporal Audio-Visual Evidence in Long Videos?](https://arxiv.org/abs/2609.17248) | Long-video reasoning grounded in spatial and temporal evidence | — |
| 2026-08 | **C³PO** | [C$^3$PO: Evaluating Cross-Modal Composition and Counterfactual Performance in Omnimodal Models](https://arxiv.org/abs/2608.05381) | Composition and counterfactual reasoning across modalities | — |
| 2026-08 | **OmniAssistBench** | [OmniAssistBench: Assistant-style Interaction Benchmark for Omni-LLMs](https://arxiv.org/abs/2608.21360) | Assistant-style multimodal interactions | [Project](https://xianyunsun.github.io/OmniAssistBench/) |
| 2026-08 | **MMI** | [Modality Maturity Index: A benchmark for assessing multimodal capabilities of omni models](https://arxiv.org/abs/2608.26317) | Any-to-any I/O across text/image/audio/video/document; right output modality | — |
| 2026-06 | **OmniHalluc-L** | [OmniHalluc-L: Counterfactual Benchmarking and Modality-Perturbation Reliability Calibration for Long-Form Omni Hallucination](https://arxiv.org/abs/2606.03614) | Long-context hallucinations and modality perturbations | — |
| 2026-06 | **OmniCap-IF** | [OmniCap-IF: Benchmarking and Improving Instruction Following Abilities for Omni-Video Captioning](https://arxiv.org/abs/2606.08572) | Instruction following in audio-visual video captioning | — |
| 2026-06 | **AVI-Bench** | [AVI-Bench: Toward Human-like Audio-Visual Intelligence of Omni-MLLMs](https://arxiv.org/abs/2606.07643) | Audio-visual perception, understanding, reasoning | [Project](https://fudancvl.github.io/AVI-Bench/) |
| 2026-05 | **Omni-Fake** | [Omni-Fake: Benchmarking Unified Multimodal Social Media Deepfake Detection](https://arxiv.org/abs/2605.01638) | Multimodal social-media deepfake detection | [Project](https://tianxiao1201.github.io/omni-fake-project-page/) |
| 2026-05 | **Omni-Persona** | [Omni-Persona: Systematic Benchmarking and Improving Omnimodal Personalization](https://arxiv.org/abs/2605.09996) | Multimodal personalization | [GitHub](https://github.com/oyt9306/Omni-Persona) |
| 2026-05 | **OmniInteract** | [OmniInteract: Benchmarking Real-World Streaming Interaction for Real-Time Omnimodal Assistants](https://arxiv.org/abs/2605.26485) | Streaming interaction in real-world assistant scenarios | [GitHub](https://github.com/Lucky-Lance/OmniInteract) |
| 2026-05 | **VideoFDB** | [VideoFDB: Evaluating Full-Duplex Vision-Speech Capabilities in Conversational Agents](https://arxiv.org/abs/2605.30256) | Full-duplex vision-speech interaction | — |
| 2026-05 | **TOBench** | [TOBench: A Task-Oriented Omni-Modal Benchmark for Real-World Tool-Using Agents](https://arxiv.org/abs/2605.16909) | Task completion with multimodal inputs and tools | [GitHub](https://github.com/Pi3AI/TOBench) |
| 2026-05 | **Omni-DuplexEval** | [Omni-DuplexEval: Evaluating Real-time Duplex Omni-modal Interaction](https://arxiv.org/abs/2605.17360) | Real-time full-duplex multimodal interaction | — |
| 2026-05 | **OmniPro** | [OmniPro: A Comprehensive Benchmark for Omni-Proactive Streaming Video Understanding](https://arxiv.org/abs/2605.18577) | Proactive interaction with streaming video | [Project](https://ruixiangzhao.github.io/OmniPro) |
| 2026-05 | **VideoOdyssey** | [VideoOdyssey: A Benchmark for Ultra-Long-Context and Omni-Modal Video Understanding](https://arxiv.org/abs/2605.22907) | Ultra-long-context audio-visual understanding | — |
| 2026-05 | **Omni-DeepSearch** | [Omni-DeepSearch: A Benchmark for Audio-Driven Omni-Modal Deep Search](https://arxiv.org/abs/2605.08762) | Agentic deep search from audio queries | — |
| 2026-05 | **TraceAV-Bench** | [TraceAV-Bench: Benchmarking Multi-Hop Trajectory Reasoning over Long Audio-Visual Videos](https://arxiv.org/abs/2605.07593) | Multi-hop reasoning over long AV videos | — |
| 2026-04 | **Demographic/Linguistic Bias Evaluation** | [Demographic and Linguistic Bias Evaluation in Omnimodal Language Models](https://arxiv.org/abs/2604.10014) | Bias measurements for omni language models | — |
| 2026-04 | **MCBench** | [MCBench: A Multicontext Safety Assessment Benchmark for Omni Large Language Models](https://arxiv.org/abs/2606.05177) | Safety assessment across multimodal contexts | — |
| 2026-04 | **AVID** | [AVID: A Benchmark for Omni-Modal Audio-Visual Inconsistency Understanding via Agent-Driven Construction](https://arxiv.org/abs/2604.13593) | Audio-visual inconsistency detection and reasoning | — |
| 2026-03 | **MMOU** | [MMOU: A Massive Multi-Task Omni Understanding and Reasoning Benchmark for Long and Complex Real-World Videos](https://arxiv.org/abs/2603.14145) | Multitask understanding of complex long videos | — |
| 2026-03 | **SocialOmni** | [SocialOmni: Benchmarking Audio-Visual Social Interactivity in Omni Models](https://arxiv.org/abs/2603.16859) | Social interaction using audio and visual cues | [GitHub](https://github.com/MAC-AutoML/SocialOmni) |
| 2026-03 | **OMD-Bench** | [Omni-Modal Dissonance Benchmark: Systematically Breaking Modality Consensus to Probe Robustness and Calibrated Abstention](https://arxiv.org/abs/2603.27187) | Robustness under conflicting modalities | — |
| 2026-03 | **LVOmniBench** | [LVOmniBench: Pioneering Long Audio-Video Understanding Evaluation for Omnimodal LLMs](https://arxiv.org/abs/2603.19217) | Long (10–90 min) audio-video understanding | [GitHub](https://github.com/KD-TAO/LVOmniBench) |
| 2026-03 | **UniM** | [UniM: A Unified Any-to-Any Interleaved Multimodal Benchmark](https://arxiv.org/abs/2603.05075) | Any-to-any interleaved U&G over 7 modalities | [GitHub](https://github.com/liyanlin06/UniM) |
| 2026-01 | **AEQ-Bench** | [AEQ-Bench: Measuring Empathy of Omni-Modal Large Models](https://arxiv.org/abs/2601.10513) | Empathy in omni-model responses | — |
| 2026-01 | **LiViBench** | [LiViBench: An Omnimodal Benchmark for Interactive Livestream Video Understanding](https://arxiv.org/abs/2601.15016) | Interactive livestream understanding | — |
| 2026-01 | **SONIC-O1** | [SONIC-O1: A Real-World Benchmark for Evaluating Multimodal Large Language Models on Audio-Video Understanding](https://arxiv.org/abs/2601.21666) | Real-world audio-video understanding | [Project](https://vectorinstitute.github.io/sonic-o1/) |
| 2026-01 | **PhoStream** | [PhoStream: Benchmarking Real-World Streaming for Omnimodal Assistants in Mobile Scenarios](https://arxiv.org/abs/2601.22575) | Mobile streaming assistant scenarios | [GitHub](https://github.com/Lucky-Lance/PhoStream) |
| 2026-01 | **FutureOmni** | [FutureOmni: Evaluating Future Forecasting from Omni-Modal Context for Multimodal LLMs](https://arxiv.org/abs/2601.13836) | Forecasting future events from AV context | [GitHub](https://github.com/OpenMOSS/FutureOmni) |
| 2025-12 | **JointAVBench** | [JointAVBench: A Benchmark for Joint Audio-Visual Reasoning Evaluation](https://arxiv.org/abs/2512.12772) | Strictly joint AV reasoning | — |
| 2025-12 | **FysicsWorld** | [FysicsWorld: A Unified Full-Modality Benchmark for Any-to-Any Understanding, Generation, and Reasoning](https://arxiv.org/abs/2512.12756) | Any-to-any over image, video, audio, text | [GitHub](https://github.com/Fysics-AI/FysicsWorld) |
| 2025-10 | **UNO-Bench** | [UNO-Bench: A Unified Benchmark for Exploring the Compositional Law Between Uni-modal and Omni-modal in Omni Models](https://arxiv.org/abs/2510.18915) | Uni-modal vs. omni-modal abilities | [GitHub](https://github.com/meituan-longcat/UNO-Bench) |
| 2025-10 | **XModBench** | [XModBench: Benchmarking Cross-Modal Capabilities and Consistency in Omni-Language Models](https://arxiv.org/abs/2510.15148) | Cross-modal consistency across A/V/T | [GitHub](https://github.com/XingruiWang/XModBench) |
| 2025-10 | **OmniVideoBench** | [OmniVideoBench: Towards Audio-Visual Understanding Evaluation for Omni MLLMs](https://arxiv.org/abs/2510.10689) | Audio-visual video reasoning | [GitHub](https://github.com/NJU-LINK/OmniVideoBench) |
| 2025-08 | **Omni-SafetyBench** | [Omni-SafetyBench: A Benchmark for Safety Evaluation of Audio-Visual Large Language Models](https://arxiv.org/abs/2508.07173) | Safety of omni LLMs | — |
| 2025-06 | **IntentBench** | [HumanOmniV2: From Understanding to Omni-Modal Reasoning with Context](https://arxiv.org/abs/2506.21277) | Human intent/emotion from video + audio | [GitHub](https://github.com/HumanMLLM/HumanOmniV2) |
| 2025-06 | **OmniEval** | [OmniEval: A Benchmark for Evaluating Omni-modal Models with Visual, Auditory, and Textual Inputs](https://arxiv.org/abs/2506.20960) | AV-text collaboration incl. grounding | [Project](https://omnieval-benchmark.github.io/) |
| 2025-06 | **CG-AV-Counting** | [AV-Reasoner: Improving and Benchmarking Clue-Grounded Audio-Visual Counting for MLLMs](https://arxiv.org/abs/2506.05328) | Clue-grounded AV counting | [GitHub](https://github.com/AV-Reasoner/AV-Reasoner) |
| 2025-05 | **Video-Holmes** | [Video-Holmes: Can MLLM Think Like Holmes for Complex Video Reasoning?](https://arxiv.org/abs/2505.21374) | Complex multi-clue video reasoning | [GitHub](https://github.com/TencentARC/Video-Holmes) |
| 2025-05 | **Daily-Omni** | [Daily-Omni: Towards Audio-Visual Reasoning with Temporal Alignment across Modalities](https://arxiv.org/abs/2505.17862) | AV QA with cross-modal temporal alignment | [GitHub](https://github.com/Lliar-liar/Daily-Omni) |
| 2025-05 | **General-Bench** | [On Path to Multimodal Generalist: General-Level and General-Bench](https://arxiv.org/abs/2505.04620) | 700+ tasks, comprehension + generation synergy | [HF](https://huggingface.co/datasets/General-Level/General-Bench-Openset) |
| 2025-03 | **OmniMMI** | [OmniMMI: A Comprehensive Multi-modal Interaction Benchmark in Streaming Video Contexts](https://arxiv.org/abs/2503.22952) | Streaming/proactive interaction | [GitHub](https://github.com/OmniMMI/OmniMMI) |
| 2025-03 | **AVUT** | [Audio-centric Video Understanding Benchmark without Text Shortcut](https://arxiv.org/abs/2503.19951) | Audio-centric video understanding | [GitHub](https://github.com/lark-png/AVUT) |
| 2025-03 | **Judge Anything** | [Judge Anything: MLLM as a Judge Across Any Modality](https://arxiv.org/abs/2503.17489) | Any-to-any tasks + MLLM-as-judge | [GitHub](https://github.com/URRealHero/JudgeAnything) |
| 2025-02 | **WorldSense** | [WorldSense: Evaluating Real-world Omnimodal Understanding for Multimodal LLMs](https://arxiv.org/abs/2502.04326) | Real-world AV-text video understanding | [GitHub](https://github.com/JaaackHongggg/WorldSense) |
| 2025-01 | **AVTrustBench** | [AVTrustBench: Assessing and Enhancing Reliability and Robustness in Audio-Visual LLMs](https://arxiv.org/abs/2501.02135) | Robustness of AV-LLMs | — |
| 2024-12 | **AV-Odyssey** | [AV-Odyssey Bench: Can Your Multimodal LLMs Really Understand Audio-Visual Information?](https://arxiv.org/abs/2412.02611) | 4,555 AV problems | [GitHub](https://github.com/AV-Odyssey/AV-Odyssey) |
| 2024-11 | **LongVALE** | [LongVALE: Vision-Audio-Language-Event Benchmark Towards Time-Aware Omni-Modal Perception of Long Videos](https://arxiv.org/abs/2411.19772) | Time-aware omni event understanding | [GitHub](https://github.com/ttgeng233/LongVALE) |
| 2024-10 | **AVHBench** | [AVHBench: A Cross-Modal Hallucination Benchmark for Audio-Visual Large Language Models](https://arxiv.org/abs/2410.18325) | Cross-modal hallucination | [GitHub](https://github.com/kaist-ami/AVHBench) |
| 2024-10 | **MixEval-X** | [MixEval-X: Any-to-Any Evaluations from Real-World Data Mixtures](https://arxiv.org/abs/2410.13754) | Any-to-any evaluation | [GitHub](https://github.com/JinjieNi/MixEval-X) |
| 2024-10 | **OmnixR** | [OmnixR: Evaluating Omni-modality Language Models on Reasoning across Modalities](https://arxiv.org/abs/2410.12219) | Cross-modal reasoning | — |
| 2024-09 | **OmniBench** | [OmniBench: Towards The Future of Universal Omni-Language Models](https://arxiv.org/abs/2409.15272) | Tri-modal (image + audio + text) reasoning | [GitHub](https://github.com/multimodal-art-projection/OmniBench) |

### Unified Understanding & Generation Benchmarks

| Date | Model | Paper | Evaluates | Code |
|:---:|---|---|---|:---:|
| 2026-09 | **OmniHallu** | [OmniHallu: Unified Hallucination Detection for Cross-Modal Comprehension and Generation in Multimodal Large Language Models](https://arxiv.org/abs/2609.11244) | Cross-modal hallucinations in comprehension and generation | — |
| 2026-09 | **UFO / UFO-Bench** | [UFO: Chain-of-Evaluation for Omni-Condition Alignment in Multi-Modal Image Generation](https://arxiv.org/abs/2609.12397) | Evaluation of simultaneous alignment to multimodal image conditions | — |
| 2026-09 | **Omni-StoryBench** | [What Comes Next? Omni-StoryBench for Evaluating Story-Grounded Omnimodal Generation](https://arxiv.org/abs/2609.37317) | Story-conditioned generation across modalities | — |
| 2026-08 | **VGAU-Diag** | [When Does Visual Generation Help Visual Understanding in Unified Multimodal Models?](https://arxiv.org/abs/2608.22174) | When visual generation assists understanding | — |
| 2026-08 | **OmniPhys** | [OmniPhys: A Unified Multimodal Benchmark for Physics Understanding and Generation from Chinese Educational Corpora](https://arxiv.org/abs/2608.25398) | Physics understanding and generation | [GitHub](https://github.com/ECNU-RAIL/OmniPhys-EMNLP2026) |
| 2026-06 | **Unison** | [Unison: Benchmarking Unified Multimodal Models via Synergistic Understanding and Generation](https://arxiv.org/abs/2606.26984) | U&G synergy in UMMs | [GitHub](https://github.com/FudanCVL/Unison) |
| 2026-06 | **IMUG-Bench** | [IMUG-Bench: Benchmarking Unified Multimodal Models on Interleaved Understanding and Generation](https://arxiv.org/abs/2606.09169) | Multi-turn interleaved image-text dialogue | [HF](https://huggingface.co/datasets/ccccEsion/IMUG-Bench) |
| 2026-05 | **VCG-Bench** | [VCG-Bench: Towards A Unified Visual-Centric Benchmark for Structured Generation and Editing](https://arxiv.org/abs/2605.15677) | Structured visual generation and editing | — |
| 2026-04 | **Uni-SafeBench** | [Does Unification Come at a Cost? Uni-SafeBench: A Safety Benchmark for Unified Multimodal Large Models](https://arxiv.org/abs/2604.00547) | Safety of unified understanding/generation models | — |
| 2026-04 | **XTC-Bench** | [Beyond Accuracy: Benchmarking Cross-Task Consistency in Unified Multimodal Models](https://arxiv.org/abs/2604.25072) | Consistency between visual understanding and generation | — |
| 2026-03 | **UniG2U-Bench** | [UniG2U-Bench: Do Unified Models Advance Multimodal Understanding?](https://arxiv.org/abs/2603.03241) | Understanding gains from unified generation | — |
| 2026-03 | **UniSAFE** | [UniSAFE: A Comprehensive Benchmark for Safety Evaluation of Unified Multimodal Models](https://arxiv.org/abs/2603.17476) | Safety evaluation across unified-model tasks | [GitHub](https://github.com/segyulee/UniSAFE) |
| 2026-02 | **VGUBench** | [Can Unified Generation and Understanding Models Maintain Semantic Equivalence Across Different Output Modalities?](https://arxiv.org/abs/2602.23711) | Semantic agreement between textual and visual outputs | — |
| 2026-02 | **UReason** | [UReason: Benchmarking Reasoning-to-Generation Alignment in Unified Multimodal Models](https://arxiv.org/abs/2602.08336) | Alignment between reasoning and generated outputs | — |
| 2026-02 | **MICON-Bench** | [MICON-Bench: Benchmarking and Enhancing Multi-Image Context Image Generation in Unified Multimodal Models](https://arxiv.org/abs/2602.19497) | Generation using multiple contextual images | [GitHub](https://github.com/Angusliuuu/MICON-Bench) |
| 2026-02 | **GapEval** | [Quantifying the Gap between Understanding and Generation within Unified Multimodal Models](https://arxiv.org/abs/2602.02140) | U↔G bidirectional consistency | — |
| 2026-01 | **UEval** | [UEval: A Benchmark for Unified Multimodal Generation](https://arxiv.org/abs/2601.22155) | Evaluation of unified multimodal generation | — |
| 2026-01 | **Omni-Bench** | [Omni-R1: Towards the Unified Generative Paradigm for Multimodal Reasoning](https://arxiv.org/abs/2601.09536) | Unified generative multimodal reasoning | [GitHub](https://github.com/ModalityDance/Omni-R1) |
| 2025-12 | **UmniBench** | [UmniBench: Unified Understand and Generation Model Oriented Omni-dimensional Benchmark](https://arxiv.org/abs/2512.17196) | Understanding, generation, editing in one pass | [Project](https://umnibench.github.io/) |
| 2025-12 | **VABench** | [VABench: A Comprehensive Benchmark for Audio-Video Generation](https://arxiv.org/abs/2512.09299) | Joint audio-video generation | [GitHub](https://github.com/tanABCC/VABench) |
| 2025-11 | **UniSandbox** | [Does Understanding Inform Generation in Unified Multimodal Models? From Analysis to Path Forward](https://arxiv.org/abs/2511.20561) | Probing how understanding affects generation | — |
| 2025-10 | **Uni-MMMU** | [Uni-MMMU: A Massive Multi-discipline Multimodal Unified Benchmark](https://arxiv.org/abs/2510.13759) | Generation-understanding synergy | [GitHub](https://github.com/Vchitect/Uni-MMMU) |
| 2025-09 | **RealUnify** | [RealUnify: Do Unified Models Truly Benefit from Unification? A Comprehensive Benchmark](https://arxiv.org/abs/2509.24897) | Whether U helps G and vice versa | [GitHub](https://github.com/FrankYang-17/RealUnify) |
| 2025-09 | **Unified-Bench** | [Unified Multimodal Models as Auto-Encoders](https://arxiv.org/abs/2509.09666) | Unification degree via I2T→T2I reconstruction | [GitHub](https://github.com/PKU-YuanGroup/UAE) |
| 2025-08 | **T2I-ReasonBench** | [T2I-ReasonBench: Benchmarking Reasoning-Informed Text-to-Image Generation](https://arxiv.org/abs/2508.17472) | Reasoning-informed T2I | [GitHub](https://github.com/KaiyueSun98/T2I-ReasonBench) |
| 2025-05 | **OmniGenBench** | [OmniGenBench: A Benchmark for Omnipotent Multimodal Generation across 50+ Tasks](https://arxiv.org/abs/2505.18775) | Instruction-following generation | [GitHub](https://github.com/emilia113/OmniGenBench) |
| 2025-05 | **MMMG** | [MMMG: a Comprehensive and Reliable Benchmark for Multitask Multimodal Generation](https://arxiv.org/abs/2505.17613) | Image, audio, interleaved generation | [GitHub](https://github.com/yaojh18/MMMG) |
| 2025-05 | **UniEval** | [UniEval: Unified Holistic Evaluation for Unified Multimodal Understanding and Generation](https://arxiv.org/abs/2505.10483) | UniBench + UniScore | [GitHub](https://github.com/xmed-lab/UniEval) |
| 2025-04 | **MME-Unify** | [MME-Unify: A Comprehensive Benchmark for Unified Multimodal Understanding and Generation Models](https://arxiv.org/abs/2504.03641) | U, G and mixed-modality generation | [GitHub](https://github.com/MME-Benchmarks/MME-Unify) |
| 2025-03 | **WISE** | [WISE: A World Knowledge-Informed Semantic Evaluation for Text-to-Image Generation](https://arxiv.org/abs/2503.07265) | World-knowledge T2I | [GitHub](https://github.com/PKU-YuanGroup/WISE) |
| 2024-11 | **OpenING** | [OpenING: A Comprehensive Benchmark for Judging Open-ended Interleaved Image-Text Generation](https://arxiv.org/abs/2411.18499) | Open-ended interleaved generation | [GitHub](https://github.com/LanceZPF/OpenING) |
| 2024-11 | **ISG-Bench** | [Interleaved Scene Graphs for Interleaved Text-and-Image Generation Assessment](https://arxiv.org/abs/2411.17188) | Interleaved text-image generation | [GitHub](https://github.com/Dongping-Chen/ISG) |
| 2024-10 | **MMIE** | [MMIE: Massive Multimodal Interleaved Comprehension Benchmark for Large Vision-Language Models](https://arxiv.org/abs/2410.10139) | Interleaved comprehension and generation | [GitHub](https://github.com/Lillianwei-h/MMIE) |

### Audio-Video Generation Benchmarks

| Date | Model / Work | Paper | Focus | Code / Project |
|:---:|---|---|---|:---:|
| 2026-09 | **AV-SafetyBench** | [AV-SafetyBench: A Safety Benchmark for Text-to-Audio-Video Generation](https://arxiv.org/abs/2609.06991) | Safety of text-conditioned joint audio-video generation | — |
| 2026-09 | **CutCraft** | [Beyond Coherence: Benchmarking Professional Editing-Technique Execution in Multi-Shot Audio-Video Generation](https://arxiv.org/abs/2609.08275) | Execution of professional editing techniques in multi-shot generation | [GitHub](https://github.com/AlibabaResearch/cut-craft-bench) |
| 2026-09 | **OmniVBench** | [OmniVBench: A Benchmark and Large-Scale Dataset for Omni Reference-to-Video Generation](https://arxiv.org/abs/2609.22069) | Generation from multiple kinds of reference input | — |
| 2026-09 | **ORAV** | [ORAV: Benchmarking Audio-Video Generation from Multimodal Contexts](https://arxiv.org/abs/2609.34843) | Audio-video generation conditioned on multimodal context | — |
| 2026-08 | **Multi2AV-Safety** | [Multi2AV-Safety: Benchmarking Safety in Multimodal-to-Audio-Video Generation](https://arxiv.org/abs/2608.26535) | Safety of multimodal-conditioned audio-video generation | — |
| 2026-08 | **StreamAV-Bench** | [StreamAV-Bench: A Comprehensive Benchmark for Streaming Audio-Video Generation](https://arxiv.org/abs/2608.26336) | Streaming joint audio-video generation | — |
| 2026-07 | **Reference-Free Omni AV Evaluator** | [Beyond Time Shifts: Adapting Omni-LLM as a Reference-Free Evaluator for Generative Audio-Visual Models](https://arxiv.org/abs/2607.09091) | Audio-video generation evaluation without a target reference | — |
| 2026-07 | **MultiRef-Compass** | [MultiRef-Compass: Towards Comprehensive Evaluation of Multi-Reference-to-Audio-Video Generation](https://arxiv.org/abs/2607.14189) | Multiple-reference audio-video generation | — |
| 2026-05 | **Joint-AV Physics Evaluation** | [Do Joint Audio-Video Generation Models Understand Physics?](https://arxiv.org/abs/2605.07061) | Physical consistency of generated audio and video | — |
| 2026-05 | **MTAVG-Bench 2.0** | [MTAVG-Bench 2.0: Diagnosing Failure Modes of Cinematic Expressiveness in Multi-Talker Audio-Video Generation](https://arxiv.org/abs/2605.28035) | Cinematic expression in multi-speaker dialogue generation | — |
| 2026-05 | **MSAVBench** | [MSAVBench: Towards Comprehensive and Reliable Evaluation of Multi-Shot Audio-Video Generation](https://arxiv.org/abs/2605.20183) | Multi-shot audio-video generation | [GitHub](https://github.com/ali-vilab/MSAVBench) |
| 2026-05 | **AVBench** | [AVBench: Human-Aligned and Automated Evaluation Benchmark for Audio-Video Generative Models](https://arxiv.org/abs/2605.24652) | Human and automated assessment of joint audio-video outputs | — |
| 2026-05 | **LongAV-Compass** | [LongAV-Compass: Towards Unified Evaluation of Minute-Scale Audio-Visual Generation Across T2AV, I2AV, and V2AV](https://arxiv.org/abs/2605.26244) | Minute-scale audio-video generation | — |
| 2026-04 | **AVGen-Bench** | [AVGen-Bench: A Task-Driven Benchmark for Multi-Granular Evaluation of Text-to-Audio-Video Generation](https://arxiv.org/abs/2604.08540) | Task-based evaluation of text-to-audio-video generation | — |
| 2026-02 | **Omni-Judge** | [Omni-Judge: Can Omni-LLMs Serve as Human-Aligned Judges for Text-Conditioned Audio-Video Generation?](https://arxiv.org/abs/2602.01623) | Human-aligned evaluation with omni language models | — |
| 2026-01 | **MTAVG-Bench** | [MTAVG-Bench: A Diagnostic Benchmark for Multi-Talker Dialogue-Centric Audio-Video Generation](https://arxiv.org/abs/2602.00607) | Multiple-speaker dialogue in generated audio-video | — |

### Speech & Audio Benchmarks

| Date | Model | Paper | Evaluates | Code |
|:---:|---|---|---|:---:|
| 2026-09 | **Floor-Self-Selection Study** | [Full-Duplex Speech Models Take the Floor When Asked, Not When Needed](https://arxiv.org/abs/2609.19596) | Whether models initiate speech when useful | — |
| 2026-09 | **DuplexSpeechBench-IFEval** | [DuplexSpeechBench-IFEval: Evaluating Implicit Instruction Following in Full-Duplex Voice Agents](https://arxiv.org/abs/2609.03423) | Implicit instruction following in duplex voice interaction | — |
| 2026-09 | **DuplexJail** | [DuplexJail: Spoken Interruption Attacks on Full-Duplex Speech Models](https://arxiv.org/abs/2609.09420) | Safety under timed spoken interruption attacks | — |
| 2026-09 | **Duplex Cue** | [Continue, Adapt, or Yield: In-Turn Adaptation to Overlapping Speech in Full-Duplex Agents](https://arxiv.org/abs/2609.13117) | Adapting to listener contributions while speaking | — |
| 2026-09 | **TACT** | [Neither Silence nor Overlap Is Failure: Intent-Conditioned Evaluation of Turn-Taking in Full-Duplex Spoken Dialogue Models](https://arxiv.org/abs/2609.27372) | Turn-taking scored according to conversational intent | — |
| 2026-09 | **Duplex-MPE** | [Duplex-MPE: Benchmarking Multi-Party Interaction in Full-Duplex Dialogue](https://arxiv.org/abs/2609.31948) | Appropriate participation in multi-party speech interaction | [Project](https://step-out.github.io/Duplex-MPE-Page/) |
| 2026-09 | **APEX-Voice** | [APEX-Voice: Can Voice Agents Complete Professional Workflows Through Full-Duplex Interaction](https://arxiv.org/abs/2609.34973) | Professional workflow completion through duplex voice interaction | — |
| 2026-09 | **TAG-Bench** | [TAG-Bench: Benchmarking Temporal Audio Grounding in Large Audio Language Models](https://arxiv.org/abs/2609.01542) | Temporal grounding of audio events | — |
| 2026-09 | **AudioICL-Bench** | [AudioICL-Bench: A Benchmark for Large Audio Language Model In-Context Learning](https://arxiv.org/abs/2609.11252) | In-context learning with audio examples | — |
| 2026-09 | **MuLA-Bench** | [MuLA-Bench: A Multilingual Long-Form Audio Understanding Benchmark via Multi-Tier Auditing](https://arxiv.org/abs/2609.23416) | Multilingual long-audio understanding | — |
| 2026-09 | **MISHAP-Bench** | [MISHAP-Bench: A Hallucination Benchmark for Large Audio-Language Models](https://arxiv.org/abs/2609.33893) | Hallucination in audio-language understanding | — |
| 2026-09 | **LateIntent-Bench** | [When Intent Arrives Late: A Benchmark for Full-Duplex Speech Models under Delayed Intent Revelation](https://arxiv.org/abs/2610.00272) | Intent revealed after a full-duplex response starts | — |
| 2026-09 | **IndicFDB** | [IndicFDB: Benchmarking Full-Duplex Voice Agents across Indian Languages](https://arxiv.org/abs/2609.31967) | Full-duplex voice interaction in Indian languages | — |
| 2026-09 | **DuplexAct-Bench** | [DuplexAct-Bench: Broadening Full-Duplex Speech Evaluation toward Proactive Interaction across Diverse Behavioral Requirements](https://arxiv.org/abs/2609.39446) | Proactive behavior in full-duplex interaction | — |
| 2026-09 | **French-FD-Bench** | [From Metrics to Natural Dialogue: French Full-Duplex Benchmark for Spoken Dialogue Models](https://arxiv.org/abs/2609.10765) | French full-duplex dialogue | — |
| 2026-08 | **MRMAD** | [MRMAD: A Multi-Round Multi-Audio Benchmark for Evaluating Acoustic Degradation Perception in Large Audio-Language Models](https://arxiv.org/abs/2608.22236) | Perception of acoustic degradation across dialogue turns | [GitHub](https://github.com/Bose/MRMAD) |
| 2026-07 | **M3-DuplexBench** | [M3-DuplexBench: A Multi-Turn, Multilingual, Multidomain Benchmark for Full-Duplex Spoken Dialogue Models](https://arxiv.org/abs/2607.29125) | Multi-turn, multilingual and multidomain speech interaction | — |
| 2026-07 | **TORUS** | [TORUS: A Test of Rendering-Understanding Self-Coherence for Unified Audio Models](https://arxiv.org/abs/2607.28896) | Consistency between audio generation and understanding | — |
| 2026-07 | **RW-Voice-EQ Bench** | [RW-Voice-EQ Bench: A Real World Benchmark for Evaluating Voice AI Systems](https://arxiv.org/abs/2607.14846) | Real-world voice AI | — |
| 2026-07 | **SPEARBench** | [SPEARBench: A Benchmark for Naturalness Evaluation in Streaming Speech-to-Speech Language Models](https://arxiv.org/abs/2607.05365) | Naturalness of streaming S2S | [Project](https://thomasthebaud.github.io/SPEAR-benchmark-website/) |
| 2026-05 | **Instruct-FD** | [Instruct-FD: Can Your Full-Duplex Speech System Follow Turn-Taking Instructions?](https://arxiv.org/abs/2607.20460) | Turn-management instruction following | — |
| 2026-05 | **VoiceGiraffe** | [VoiceGiraffe: A Benchmark for Extreme Long-Context Audio-Language Understanding](https://arxiv.org/abs/2605.27976) | Very long audio-language contexts | — |
| 2026-04 | **HumDial 2026 Study** | [Full-Duplex Interaction in Spoken Dialogue Systems: A Comprehensive Study from the ICASSP 2026 HumDial Challenge](https://arxiv.org/abs/2604.21406) | Comparative study of full-duplex dialogue systems | — |
| 2026-04 | **Full-Duplex-Bench-v3** | [Full-Duplex-Bench-v3: Benchmarking Tool Use for Full-Duplex Voice Agents Under Real-World Disfluency](https://arxiv.org/abs/2604.04847) | Tool use with realistic speech disfluency | [Project](https://daniellin94144.github.io/FDB-v3-demo) |
| 2026-04 | **EchoChain** | [EchoChain: A Full-Duplex Benchmark for State-Update Reasoning Under Interruptions](https://arxiv.org/abs/2604.16456) | State updates under conversational interruptions | — |
| 2026-04 | **HalluAudio** | [HalluAudio: A Comprehensive Benchmark for Hallucination Detection in Large Audio-Language Models](https://arxiv.org/abs/2604.19300) | Audio-language hallucination detection | — |
| 2026-03 | **τ-Voice** | [$\tau$-Voice: Benchmarking Full-Duplex Voice Agents on Real-World Domains](https://arxiv.org/abs/2603.13686) | Voice-agent tasks in real-world domains | — |
| 2026-03 | **DEAF** | [DEAF: A Benchmark for Diagnostic Evaluation of Acoustic Faithfulness in Audio Language Models](https://arxiv.org/abs/2603.18048) | Faithfulness to acoustic evidence | — |
| 2026-03 | **OmniACBench** | [OmniACBench: A Benchmark for Evaluating Context-Grounded Acoustic Control in Omni-Modal Models](https://arxiv.org/abs/2603.23938) | Context-dependent control of speech acoustics | — |
| 2026-01 | **ChronosAudio** | [ChronosAudio: A Comprehensive Long-Audio Benchmark for Evaluating Audio-Large Language Models](https://arxiv.org/abs/2601.04876) | Long-audio understanding | — |
| 2026-01 | **HumDial** | [The ICASSP 2026 HumDial Challenge: Benchmarking Human-like Spoken Dialogue Systems in the LLM Era](https://arxiv.org/abs/2601.05564) | Emotional intelligence + full-duplex | — |
| 2025-11 | **MTR-DuplexBench** | [MTR-DuplexBench: Towards a Comprehensive Evaluation of Multi-Round Conversations for Full-Duplex Speech Language Models](https://arxiv.org/abs/2511.10262) | Multi-round full-duplex | [GitHub](https://github.com/ZhangHe0918/MTR-DuplexBench) |
| 2025-10 | **Full-Duplex-Bench-v2** | [Full-Duplex-Bench-v2: A Multi-Turn Evaluation Framework for Duplex Dialogue Systems with an Automated Examiner](https://arxiv.org/abs/2510.07838) | Multi-turn full-duplex | [GitHub](https://github.com/DanielLin94144/Full-Duplex-Bench) |
| 2025-10 | **AudioMarathon** | [AudioMarathon: A Comprehensive Benchmark for Long-Context Audio Understanding and Efficiency in Audio LLMs](https://arxiv.org/abs/2510.07293) | Long-form audio understanding | [GitHub](https://github.com/DabDans/AudioMarathon) |
| 2025-08 | **MTalk-Bench** | [MTalk-Bench: Evaluating Speech-to-Speech Models in Multi-Turn Dialogues via Arena-style and Rubrics Protocols](https://arxiv.org/abs/2508.18240) | Multi-turn S2S dialogue | [GitHub](https://github.com/FreedomIntelligence/MTalk-Bench) |
| 2025-08 | **MMAU-Pro** | [MMAU-Pro: A Challenging and Comprehensive Benchmark for Holistic Evaluation of Audio General Intelligence](https://arxiv.org/abs/2508.13992) | 49 audio skills | [Project](https://sonalkum.github.io/mmau-pro) |
| 2025-08 | **SpeechR** | [SpeechR: A Benchmark for Speech Reasoning in Large Audio-Language Models](https://arxiv.org/abs/2508.02018) | Speech reasoning | — |
| 2025-06 | **MMSU** | [MMSU: A Massive Multi-task Spoken Language Understanding and Reasoning Benchmark](https://arxiv.org/abs/2506.04779) | Spoken understanding/reasoning | [GitHub](https://github.com/dingdongwang/MMSU) |
| 2025-05 | **VocalBench** | [VocalBench: Benchmarking the Vocal Conversational Abilities for Speech Interaction Models](https://arxiv.org/abs/2505.15727) | Speech interaction models | [GitHub](https://github.com/SJTU-OmniAgent/VocalBench) |
| 2025-05 | **SAKURA** | [SAKURA: On the Multi-hop Reasoning of Large Audio-Language Models Based on Speech and Audio Information](https://arxiv.org/abs/2505.13237) | Multi-hop audio reasoning | [GitHub](https://github.com/b08202033/SAKURA) |
| 2025-05 | **MMAR** | [MMAR: A Challenging Benchmark for Deep Reasoning in Speech, Audio, Music, and Their Mix](https://arxiv.org/abs/2505.13032) | Deep audio reasoning | [GitHub](https://github.com/ddlBoJack/MMAR) |
| 2025-03 | **S2S-Arena** | [S2S-Arena: Evaluating Paralinguistic Instruction Following in Speech-to-Speech Models](https://arxiv.org/abs/2503.05085) | Paralinguistic S2S | [GitHub](https://github.com/FreedomIntelligence/S2S-Arena) |
| 2025-03 | **Full-Duplex-Bench** | [Full-Duplex-Bench: A Benchmark to Evaluate Full-duplex Spoken Dialogue Models on Turn-taking Capabilities](https://arxiv.org/abs/2503.04721) | Turn-taking, interruption | [GitHub](https://github.com/DanielLin94144/Full-Duplex-Bench) |
| 2025-02 | **URO-Bench** | [URO-Bench: Towards Comprehensive Evaluation for End-to-End Spoken Dialogue Models](https://arxiv.org/abs/2502.17810) | End-to-end spoken dialogue | [GitHub](https://github.com/Ruiqi-Yan/URO-Bench) |
| 2025-01 | **VoxEval** | [VoxEval: Benchmarking the Knowledge Understanding Capabilities of End-to-End Spoken Language Models](https://arxiv.org/abs/2501.04962) | Speech-in/speech-out knowledge QA | [GitHub](https://github.com/dreamtheater123/VoxEval) |
| 2024-11 | **Dynamic-SUPERB Phase-2** | [Dynamic-SUPERB Phase-2: A Collaboratively Expanding Benchmark for Measuring the Capabilities of Spoken Language Models with 180 Tasks](https://arxiv.org/abs/2411.05361) | 180 speech/music/audio tasks | [GitHub](https://github.com/dynamic-superb/dynamic-superb) |
| 2024-10 | **MMAU** | [MMAU: A Massive Multi-Task Audio Understanding and Reasoning Benchmark](https://arxiv.org/abs/2410.19168) | Speech, sound, music QA | [GitHub](https://github.com/Sakshi113/MMAU) |
| 2024-10 | **VoiceBench** | [VoiceBench: Benchmarking LLM-Based Voice Assistants](https://arxiv.org/abs/2410.17196) | Spoken instructions | [GitHub](https://github.com/MatthewCYM/VoiceBench) |
| 2024-06 | **AudioBench** | [AudioBench: A Universal Benchmark for Audio Large Language Models](https://arxiv.org/abs/2406.16020) | Speech, scene, paralinguistics | [GitHub](https://github.com/AudioLLMs/AudioBench) |
| 2024-06 | **SD-Eval** | [SD-Eval: A Benchmark Dataset for Spoken Dialogue Understanding Beyond Words](https://arxiv.org/abs/2406.13340) | Paralinguistic spoken dialogue | [GitHub](https://github.com/amphionspace/SD-Eval) |
| 2024-02 | **AIR-Bench** | [AIR-Bench: Benchmarking Large Audio-Language Models via Generative Comprehension](https://arxiv.org/abs/2402.07729) | Audio understanding | [GitHub](https://github.com/OFA-Sys/AIR-Bench) |
| 2023-09 | **Dynamic-SUPERB** | [Dynamic-SUPERB: Towards A Dynamic, Collaborative, and Comprehensive Instruction-Tuning Benchmark for Speech](https://arxiv.org/abs/2309.09510) | Instruction-based speech evaluation | [GitHub](https://github.com/dynamic-superb/dynamic-superb) |

## Surveys

| Date | Model | Paper | Scope | Code |
|:---:|---|---|---|:---:|
| 2026-09 | **Joint/Cross-Modal AV Taxonomy** | [Joint and Cross-Modal Video-Audio Generation and Editing: A Unified Formulation and Design Taxonomy](https://arxiv.org/abs/2609.34381) | Audio-video generation/editing: task definitions and design choices | — |
| 2026-07 | **Unified MLLM Survey** | [Towards Unified Multimodal Large Language Models: A survey (ACL 2026 Findings)](https://aclanthology.org/2026.findings-acl.1853/) | Unified MLLMs | — |
| 2026-06 | **Full-Duplex Survey** | [A Survey of Full-Duplex Spoken Dialogue Systems: Architectural Hierarchy, Interaction Ontology, and Decision State Machine](https://arxiv.org/abs/2606.19453) | Full-duplex SDS | [GitHub](https://github.com/DuplexLM/DuplexSurvey) |
| 2026-05 | **NMM Roadmap** | [Toward Native Multimodal Modeling: A Roadmap](https://arxiv.org/abs/2605.25343) | Native multi-to-multi modeling | — |
| 2026-05 | **LALM Trustworthiness** | [A Survey of Large Audio Language Models: Generalization, Trustworthiness, and Outlook](https://arxiv.org/abs/2605.20266) | Large audio LMs | [GitHub](https://github.com/Kwwwww74/Awesome-Trustworthy-AudioLLMs) |
| 2026-05 | **Audio-Visual Intelligence** | [Audio-Visual Intelligence in Large Foundation Models](https://arxiv.org/abs/2605.04045) | AV understanding, generation, interaction | [GitHub](https://github.com/JavisVerse/Awesome-AVI) |
| 2025-09 | **FD-SLM Survey** | [From Turn-Taking to Synchronous Dialogue: A Survey of Full-Duplex Spoken Language Models](https://arxiv.org/abs/2509.14515) | Full-duplex SLMs | — |
| 2025-07 | **Discrete Tokenization** | [Discrete Tokenization for Multimodal LLMs: A Comprehensive Survey](https://arxiv.org/abs/2507.22920) | Discrete tokenizers | [GitHub](https://github.com/jindongli-Ai/LLM-Discrete-Tokenization-Survey) |
| 2025-06 | **Multimodal Generative Models** | [A Survey of Generative Categories and Techniques in Multimodal Generative Models](https://arxiv.org/abs/2506.10016) | Multimodal generation | — |
| 2025-05 | **LALM Evaluation** | [Towards Holistic Evaluation of Large Audio-Language Models: A Comprehensive Survey](https://arxiv.org/abs/2505.15957) | LALM benchmarks | [GitHub](https://github.com/ckyang1124/LALM-Evaluation-Survey) |
| 2025-05 | **Large Multimodal Reasoning Models** | [Perception, Reason, Think, and Plan: A Survey on Large Multimodal Reasoning Models](https://arxiv.org/abs/2505.04921) | Multimodal reasoning incl. omni | [GitHub](https://github.com/HITsz-TMG/Awesome-Large-Multimodal-Reasoning-Models) |
| 2025-05 | **Unified Multimodal Models** | [Unified Multimodal Understanding and Generation Models: Advances, Challenges, and Opportunities](https://arxiv.org/abs/2505.02567) | Unified U&G models | [GitHub](https://github.com/AIDC-AI/Awesome-Unified-Multimodal-Models) |
| 2025-04 | **Spoken LM Landscape** | [On The Landscape of Spoken Language Models: A Comprehensive Survey](https://arxiv.org/abs/2504.08528) | Spoken LMs | — |
| 2025-03 | **World Simulator** | [Simulating the Real World: A Unified Survey of Multimodal Generative Models](https://arxiv.org/abs/2503.04641) | 2D/video/3D/4D generation | [GitHub](https://github.com/ALEEEHU/World-Simulator) |
| 2025-02 | **Discrete Tokenizers** | [From Principles to Applications: A Comprehensive Survey of Discrete Tokenizers in Generation, Comprehension, Recommendation, and Information Retrieval](https://arxiv.org/abs/2502.12448) | Discrete tokenizers | — |
| 2025-02 | **Discrete Speech Tokens** | [Recent Advances in Discrete Speech Tokens: A Review](https://arxiv.org/abs/2502.06490) | Speech tokens | — |
| 2024-12 | **Multimodal NTP** | [Next Token Prediction Towards Multimodal Intelligence: A Comprehensive Survey](https://arxiv.org/abs/2412.18619) | Multimodal next-token prediction | [GitHub](https://github.com/LMM101/Awesome-Multimodal-Next-Token-Prediction) |
| 2024-12 | **Omni-MLLM Survey** | [From Specific-MLLMs to Omni-MLLMs: A Survey on MLLMs Aligned with Multi-modalities](https://arxiv.org/abs/2412.11694) | Omni-MLLMs | [GitHub](https://github.com/threegold116/Awesome-Omni-MLLMs) |
| 2024-11 | **MME-Survey** | [MME-Survey: A Comprehensive Survey on Evaluation of Multimodal LLMs](https://arxiv.org/abs/2411.15296) | MLLM evaluation | [GitHub](https://github.com/BradyFU/Awesome-Multimodal-Large-Language-Models) |
| 2024-11 | **WavChat** | [WavChat: A Survey of Spoken Dialogue Models](https://arxiv.org/abs/2411.13577) | Spoken dialogue models | [GitHub](https://github.com/jishengpeng/WavChat) |
| 2024-11 | **AR Models in Vision** | [Autoregressive Models in Vision: A Survey](https://arxiv.org/abs/2411.05902) | Visual autoregressive models | [GitHub](https://github.com/ChaofanTao/Autoregressive-Models-in-Vision-Survey) |
| 2024-10 | **Speech LLMs for Understanding** | [A Survey on Speech Large Language Models for Understanding](https://arxiv.org/abs/2410.18908) | Speech LLMs | — |
| 2024-10 | **SpeechLM Survey** | [Recent Advances in Speech Language Models: A Survey](https://arxiv.org/abs/2410.03751) | Speech LMs | [GitHub](https://github.com/dreamtheater123/Awesome-SpeechLM-Survey) |
| 2024-09 | **Multimodal Benchmarks** | [A Survey on Multimodal Benchmarks: In the Era of Large AI Models](https://arxiv.org/abs/2409.18142) | Multimodal benchmarks | — |
| 2024-06 | **Fairness & Bias** | [Fairness and Bias in Multimodal AI: A Survey](https://arxiv.org/abs/2406.19097) | Fairness | — |
| 2024-05 | **LLMs Meet Multimodal Generation** | [LLMs Meet Multimodal Generation and Editing: A Survey](https://arxiv.org/abs/2405.19334) | LLM-based multimodal generation | [GitHub](https://github.com/YingqingHe/Awesome-LLMs-meet-Multimodal-Generation) |
| 2024-05 | **Evolution of MM Architectures** | [The Evolution of Multimodal Model Architectures](https://arxiv.org/abs/2405.17927) | Architecture taxonomy incl. any-to-any | — |
| 2024-05 | **Efficient MLLMs** | [Efficient Multimodal Large Language Models: A Survey](https://arxiv.org/abs/2405.10739) | Efficient MLLMs | [GitHub](https://github.com/lijiannuist/Efficient-Multimodal-LLMs-Survey) |
| 2024-04 | **MLLM Hallucination** | [Hallucination of Multimodal Large Language Models: A Survey](https://arxiv.org/abs/2404.18930) | Hallucination | — |
| 2024-02 | **(R)Evolution of MLLMs** | [The (R)Evolution of Multimodal Large Language Models: A Survey](https://arxiv.org/abs/2402.12451) | MLLMs | — |
| 2024-01 | **MM-LLMs** | [MM-LLMs: Recent Advances in MultiModal Large Language Models](https://arxiv.org/abs/2401.13601) | MM-LLM taxonomy incl. any-to-any | — |
| 2024-01 | **MLLM Reasoning** | [Exploring the Reasoning Abilities of Multimodal Large Language Models (MLLMs): A Comprehensive Survey on Emerging Trends in Multimodal Reasoning](https://arxiv.org/abs/2401.06805) | Multimodal reasoning | — |
| 2023-12 | **Brain-Conditional Synthesis** | [Brain-Conditional Multimodal Synthesis: A Survey and Taxonomy](https://arxiv.org/abs/2401.00430) | Brain-conditional generation | — |
| 2023-11 | **MLLM Survey (Wu et al.)** | [Multimodal Large Language Models: A Survey](https://arxiv.org/abs/2311.13165) | MLLMs | — |
| 2023-09 | **Multimodal Foundation Models** | [Multimodal Foundation Models: From Specialists to General-Purpose Assistants](https://arxiv.org/abs/2309.10020) | Multimodal foundation models | — |
| 2023-08 | **Sparks of Large Audio Models** | [Sparks of Large Audio Models: A Survey and Outlook](https://arxiv.org/abs/2308.12792) | Large audio models | [GitHub](https://github.com/EmulationAI/awesome-large-audio-models) |
| 2023-06 | **MLLM Survey (Yin et al.)** | [A Survey on Multimodal Large Language Models](https://arxiv.org/abs/2306.13549) | MLLMs | [GitHub](https://github.com/BradyFU/Awesome-Multimodal-Large-Language-Models) |

## Earlier Related Works

| Date | Model | Paper | Modalities (in → out) | Code |
|:---:|---|---|---|:---:|
| 2024-06 | **GenLLaVA** | [Generative Visual Instruction Tuning](https://arxiv.org/abs/2406.11262) | T, I → T, I | — |
| 2023-11 | **ChatIllusion** | [ChatIllusion: Efficient-Aligning Interleaved Generation Ability with Visual Instruction Model](https://arxiv.org/abs/2311.17963) | T, I → T, I | — |
| 2023-10 | **MiniDALLE-3** | [MiniDALLE-3: Interactive Text to Image by Prompting Large Language Models](https://arxiv.org/abs/2310.07653) | T → T, I | — |
| 2023-10 | **EasyGen** | [EasyGen: Easing Multimodal Generation with BiDiffuser and LLMs](https://arxiv.org/abs/2310.08949) | T, I → T, I | — |
| 2023-09 | **VideoDirectorGPT** | [VideoDirectorGPT: Consistent Multi-scene Video Generation via LLM-Guided Planning](https://arxiv.org/abs/2309.15091) | T → V | — |
| 2023-01 | **FROMAGe** | [Grounding Language Models to Images for Multimodal Inputs and Outputs](https://arxiv.org/abs/2301.13823) | T, I → T, I (retrieval) | — |
| 2018-02 | **CMCGAN** | [CMCGAN: A Uniform Framework for Cross-Modal Visual-Audio Mutual Generation](https://ojs.aaai.org/index.php/AAAI/article/download/12329/12188) | I ↔ A | — |
| 2017-10 | **Deep Cross-Modal AV Generation** | [Deep Cross-Modal Audio-Visual Generation](https://dl.acm.org/doi/10.1145/3126686.3126723) | I ↔ A | — |

## Coverage & Search Notes

The October 6, 2026 expansion searched arXiv metadata and paper pages, official model cards, release announcements, [OpenAI’s API changelog](https://developers.openai.com/api/docs/changelog), [Google DeepMind’s model cards](https://deepmind.google/models/model-cards/), [Xiaomi’s model-release log](https://mimo.mi.com/docs/en-US/updates/model) and author repositories. It covers audio-visual understanding, native multimodal generation, unified visual models, speech/audio models, joint audio-video generation, relevant post-training and efficiency methods, and their benchmarks. Specialized 3D, scientific and embodied unified models are marked separately. A visual-only unified model or an audio-only model should not be read as supporting every modality.

Discovery included searches for omni/omnimodal, unified understanding and generation, audio-visual/audio-video, full-duplex, audio language modeling and audio reasoning, plus cross-checks against [Awesome Unified Multimodal Models](https://github.com/AIDC-AI/Awesome-Unified-Multimodal-Models), [Awesome Omni MLLMs](https://github.com/threegold116/Awesome-Omni-MLLMs), [Awesome AVI](https://github.com/JavisVerse/Awesome-AVI) and [WavChat](https://github.com/jishengpeng/WavChat). New paper entries were checked against their primary arXiv records; discovery lists are not used as substitutes for paper references.

The main search window was January 1–October 6, 2026, with earlier missing works added through citation and repository cross-checks. Every added entry has a paper or official release reference. Code/project links are included when supplied by the primary source; **—** means no such link was recorded, rather than a claim that none exists. The additions are source-checked; inherited entries have not all been re-audited. This is a broad literature catalogue, not a guarantee that every relevant publication or unpublished model is indexed.
