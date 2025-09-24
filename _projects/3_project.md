---
layout: page
title: Privacy Risks of Personally Identifiable Information in LLMs4Code
description: Causal analysis of heterogeneous PII leakage risks in LLMs for Code
img: assets/img/pii.jpeg
importance: 3
category: work
related_publications: true
---

**Large Language Models for Code (LLMs4Code)** have significantly enhanced developer productivity in real-world software engineering.  
However, their reliance on **open-source repositories (e.g., GitHub)** introduces severe privacy risks, as these repositories contain abundant **Personally Identifiable Information (PII)** such as:

- key  
- username  
- email  
- password  
- name  
- ip address 

Sensitive PII can be memorized during training and later resurfaced during inference, leading to **critical privacy breaches**. Prior studies have shown that commercial code completion models are indeed capable of reproducing sensitive PII, further exacerbating concerns about the trustworthiness and compliance of LLMs4Code in sensitive industries.  

Nonetheless, existing work has largely treated PII as a **homogeneous category**, overlooking the heterogeneous risks posed by different PII types.

---

### 🔎 Research Questions
We ask: **Do different PII types vary in their likelihood of being learned and leaked by LLMs4Code?**  
And further: **Is this relationship causal, driven by training dynamics?**

---

### 🛠️ Methodology
Our study follows a **four-stage pipeline**:

1. **Dataset Construction**  
   Building a high-quality dataset with a diverse set of PII types from real-world repositories.  
   This combines regex-based filters, LLM-assisted judgments, heuristic rules, and human verification.

2. **Model Fine-Tuning**  
   Fine-tuning representative LLMs4Code of **different scales and architectures** to capture cross-family patterns.

3. **Training Dynamics Computation**  
   Measuring model learnability and difficulty on real PII data.

4. **Causal Inference**  
   Formulating a **structural causal model** to estimate the causal effect of learning difficulty on leakage, validated with multiple refutation strategies.

---

### 📊 Results
- Leakage risks vary **significantly** across PII types.  
- **Easy-to-learn instances** (e.g., ip address) → **high leakage risks**.  
- **Hard-to-learn instances** (e.g., key, password) → **lower leakage frequency**.  
- **Ambiguous types** display complex dual effects.  

This provides the **first causal evidence** that leakage risks differ by PII type, offering **actionable insights** for designing **type-aware and learnability-aware defense mechanisms** in LLMs4Code.

---

<div class="row justify-content-sm-center">
  <div class="col-sm-8 mt-3 mt-md-0">
    {% include figure.liquid path="assets/img/pii-leakage.jpeg" title="Causal Graph of PII Leakage Risks" class="img-fluid rounded z-depth-1" %}
  </div>
  <div class="col-sm-4 mt-3 mt-md-0">
    {% include figure.liquid path="assets/img/pii-types.jpeg" title="Examples of PII Types" class="img-fluid rounded z-depth-1" %}
  </div>
</div>
<div class="caption">
  Left: Structural causal model illustrating relationships between training dynamics and PII leakage risks.  
  Right: Representative examples of heterogeneous PII types in real-world repositories.
</div>
