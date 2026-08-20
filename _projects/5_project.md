---
layout: page
title: Offline Evaluation Infrastructure for Multi-Turn On-Call Agents
description: Trace-to-causal-graph evaluation and a real-device execution harness for agent-generated remediation workflows
importance: 4
category: work
related_publications: false
---

**May 2026 – Aug 2026** · Software Engineer Intern, AI Infrastructure — **ByteDance**, San Jose, CA

On-call agents are hard to evaluate: their work is **multi-turn**, the correct action depends on system state, and the only ground truth lives in messy production traces. This project built the offline evaluation infrastructure that makes such agents measurable before they touch a live system.

---

### 🛠️ What I Built

1. **Trace-to-Causal-Graph Evaluation Framework**
   Production on-call traces are converted into **causal graphs** that capture which turns actually caused a resolution, rather than scoring the conversation as a flat transcript. Evaluated against this framework, the agent under test achieved **35% higher conversion success** than a Claude-based baseline.

2. **Real-Device Rendering & Execution Harness**
   Extended the agent infrastructure so that agent-generated **remediation workflows are rendered and executed on real devices**, giving end-to-end, verifiable evaluation in realistic application environments instead of mocked stubs.

3. **LLM-Driven Data Synthesis Pipeline**
   Sanitized production data is used to **emulate software engineer interactions**, generating **1,000 evaluation-ready test cases** and removing the bottleneck of hand-authored scenarios.

---

### 📊 Impact

- Turned a qualitative "does the agent seem helpful?" review into a reproducible offline benchmark with a causal notion of success.
- Closed the sim-to-real gap for remediation workflows via verifiable on-device execution.
- Scaled evaluation coverage from a handful of hand-written scenarios to **1,000 synthesized cases**.

---

**Tech Stack:** Agent Evaluation, ReAct, MCP, LangGraph, LangSmith, Python, Go, Kubernetes, Docker
