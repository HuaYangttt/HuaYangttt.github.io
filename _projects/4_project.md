---
layout: page
title: GDPR-Compliant Code LLM Alignment & Multi-Agent Detection
description: Aligning code LLMs with GDPR compliance preferences via DPO and a Generator–Challenger–Judge agent framework
importance: 3
category: work
related_publications: false
---

**Jan 2026 – May 2026**

Privacy regulations such as the **GDPR** impose concrete obligations on the code that ships in production — consent handling, data minimization, the right to erasure, retention limits. Yet **Large Language Models for Code (LLMs4Code)** are trained on open-source repositories where such obligations are inconsistently implemented, so generated code frequently violates them silently.

This project asks whether compliance can be treated as an **alignment target** rather than an afterthought: can a code LLM be trained to *prefer* GDPR-compliant implementations, and can an agent system reliably *detect* violations in real pull requests?

---

### 🛠️ Approach

1. **Preference Data Collection**
   An automated **GitHub PR collection and annotation pipeline** that mines compliance-relevant changes and yields **1,173 labeled GDPR preference samples** (compliant vs. non-compliant pairs).

2. **Generator–Challenger–Judge Multi-Agent Framework**
   A three-role agent design for violation detection:
   - **Generator** proposes candidate GDPR violations in a diff.
   - **Challenger** adversarially attacks each candidate to filter plausible-but-wrong findings.
   - **Judge** adjudicates the surviving findings.

   The framework is backed by **semantic memory** and **self-evolving pattern extraction**, so confirmed violations become reusable detection patterns for later runs.

3. **Preference Alignment**
   Distributed **DPO** training with **Ray** and **vLLM** to align **CodeLlama** with the collected GDPR compliance preferences.

---

### 📊 Results

- Detection accuracy improved from **35% → 65%** with the Generator–Challenger–Judge framework over a single-pass baseline.
- Self-evolving pattern extraction compounds across runs: patterns confirmed by the Judge measurably raise recall on later, unseen PRs.
- DPO alignment shifts CodeLlama's generations toward compliant implementations without a separate rule engine at inference time.

---

**Tech Stack:** Ray, vLLM, DPO, CodeLlama, Multi-Agent Systems, LangGraph, PyTorch, Hugging Face
