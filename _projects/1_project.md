---
layout: page
title: Evading Membership Inference in Code LLMs via Semantically Equivalent Transformations
description: Investigating how will the semantically equivalent code transformation impact the training result of LLMs4Code
img: assets/img/llm2.jpeg
importance: 1
category: work
related_publications: true
---
The success of **Large Language Models for Code (LLMs4Code)** relies on vast amounts of code data, including **public open-source repositories** (e.g., GitHub) and **private, confidential company code**. This raises concerns about **intellectual property compliance** and the potential **unauthorized use of license-restricted code**.  

**Membership Inference (MI)** techniques have been proposed to detect such unauthorized usage. However, their effectiveness can be undermined by **semantically equivalent code transformation (SECT) rules**, which modify code syntax while preserving semantics.

---

### 🔎 Research Questions
- How does each transformation rule impact membership inference? 
- How do combined transformation rules impact membership inference?
- To what extent does each transformation rule impact the success of MI?

---

### 🛠️ Methodology
We conducted a **systematic investigation** across multiple transformation rules, evaluating their effect on MI detection:

1. Applied **SECT rules** (e.g., `RenameVariable`, control-flow rewrites, syntactic variations).  
2. Fine-tuned LLMs on transformed datasets and measured **accuracy & MI success rates**.  
3. Conducted **causal analysis** to validate which transformations directly influence MI effectiveness.

---

### 📊 Key Findings
- **Model accuracy** drops by only **1.5% at worst** per transformation rule, showing that transformed datasets remain strong substitutes for fine-tuning.  
- **RenameVariable** rule reduces MI success by **10.19%**, making it the most effective transformation in obscuring restricted code presence.  
- **Causal analysis** confirms that variable renaming has the **strongest causal effect** in disrupting MI detection.  
- **Combining multiple rules** does **not** further reduce MI effectiveness beyond single-rule transformations.  

---

**Tech Stack:** Python, Java, PyTorch, Hugging Face, GitHub, CUDA  

<div class="row">
  <div class="col-sm mt-3 mt-md-0">
    {% include figure.liquid loading="eager" path="assets/img/llm1.jpeg" title="An example where a membership inference method successfully predicted membership before transformation but failed after transformation." class="img-fluid rounded z-depth-1" %}
  </div>
</div>

<div class="caption">
  Examples of model fine-tuning pipelines.
</div>
