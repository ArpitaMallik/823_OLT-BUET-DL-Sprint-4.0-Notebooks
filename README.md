# DL Sprint 4.0 – Bengali Long-Form ASR & Speaker Diarization

This repository contains our implementation for **DL Sprint 4.0**, where we developed a system for **automatic speech recognition (ASR)** and **speaker diarization** on **long-form Bengali audio**.

The project focuses on handling real-world audio such as lectures, interviews, and conversations where recordings may contain **noise, background music, multiple speakers, and irregular pauses**. 

---

# Task Overview

The objective was to build a robust pipeline for:

**1. Long-Form Bengali ASR**

Convert long Bengali speech recordings into text transcripts.

**2. Speaker Diarization**

Segment audio by speaker identity and determine **who spoke when**.

---

# Methodology (Brief)

### Long-Form Speech Recognition

We designed a **training-free ASR pipeline** for long audio:

* **Demucs** vocal separation for removing music and noise
* **Silero VAD** to detect speech segments
* **Context-aware windowing (~20s)** to preserve sentence continuity
* **Fine-tuned Whisper-Medium (Bengali)** for transcription
* Segment merging and **text normalization** for final transcripts 

### Speaker Diarization

We explored both **training-free pipelines** and **fine-tuned neural segmentation**:

* **ECAPA-TDNN** speaker embeddings
* Spectral clustering and VBx refinement for zero-training pipelines
* Fine-tuned **pyannote segmentation model** for improved speaker boundary detection

The fine-tuned neural segmentation model achieved the **lowest diarization error rate (DER)** among our approaches. 

---

# Evaluation Metrics

* **WER (Word Error Rate)** for ASR performance
* **DER (Diarization Error Rate)** for speaker diarization

---

# Paper

For full implementation details and experimental results, see the accompanying system description paper included in this repository.
