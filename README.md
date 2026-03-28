# DL Sprint 4.0 – Bengali Long-Form ASR & Speaker Diarization

This repository contains the notebooks and code developed as part of **DL Sprint 4.0**, organized by **Bangladesh University of Engineering and Technology (BUET)** for **BUET CSE Fest 2026**.

The project focuses on building a system for **automatic speech recognition (ASR)** and **speaker diarization** on **long-form Bengali audio**. The goal is to handle real-world recordings such as lectures, interviews, and conversations that often contain **noise, background music, multiple speakers, and irregular pauses**.

---

# Task Overview

The objective was to develop a framework capable of processing long-form Bengali audio for:

**1. Long-Form Bengali ASR**

Converting spoken long-form audio into written transcripts.

**2. Speaker Diarization**

Segmenting audio by speaker identity and determining **who spoke when**.

---

# Methodology (Brief)

### Long-Form Speech Recognition

We designed a pipeline for long audio transcription:

* **Demucs** vocal separation to isolate speech from background music and noise
* **Silero VAD** for detecting speech segments
* **Context-aware windowing (~20 seconds)** to maintain sentence continuity during transcription
* **Fine-tuned Whisper-Medium (Bengali)** for decoding speech segments
* Segment merging and **text normalization** to generate the final transcript

### Speaker Diarization

We explored both **training-free pipelines** and **fine-tuned neural segmentation approaches**:

* **ECAPA-TDNN** speaker embeddings
* Spectral clustering and VBx refinement for clustering-based diarization
* Fine-tuned **pyannote segmentation model** for improved speaker boundary detection

The fine-tuned segmentation model achieved the **lowest diarization error rate (DER)** among the tested approaches.

---

# Evaluation Metrics

* **WER (Word Error Rate)** for ASR performance
* **DER (Diarization Error Rate)** for speaker diarization

---

# Paper

For complete implementation details, system architecture, and experimental results, please refer to the system description paper here: https://arxiv.org/abs/2602.21183
