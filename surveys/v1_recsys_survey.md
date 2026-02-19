# RecSys V1 Survey — Consolidated Cross‑Validation Summary

## Scope
This document consolidates the **RecSys V1 survey** conclusions derived from cross‑validation across representative V1 architectures and systems, based on detailed paper‑level reviews in `../reviews/`.

Covered models / systems:
- **HSTU**
- **OneRec V1 / V2**
- **TIGER**
- **PLUM**

The goal is not exhaustive coverage, but to distill *shared design patterns, validated gains, and structural limits* observed across V1‑era recommenders.

---

## Methodology (Cross‑Validation)
Rather than treating each paper independently, we evaluated them along shared axes:

- **User modeling paradigm** (sequence‑centric vs feature‑centric)
- **Context length & representation**
- **Pretraining / foundation reuse**
- **Retrieval vs ranking unification**
- **Serving feasibility & system cost**

Each conclusion below is supported by multiple independent implementations or empirical results, reducing single‑paper bias.

---

## Key Cross‑Validated Findings

### 1. Convergence toward unified, sequence‑centric recommenders
Across HSTU, OneRec, TIGER, and PLUM, there is a clear convergence toward:

- Long user behavior sequences as the *primary signal*
- Unified architectures spanning retrieval and ranking
- Reduced reliance on hand‑engineered features

Sequence modeling (Transformers or Transformer‑like blocks) consistently dominates classical multi‑tower or feature‑heavy designs.

---

### 2. User modeling and pretraining drive most of the gains
Performance improvements attributed to "new architectures" are, in most cases, dominated by:

- Better **user representation learning**
- Larger‑scale **pretraining on behavioral sequences**
- Transfer from shared or foundation‑style encoders

Architectural novelty alone contributes marginal gains without strong user modeling.

---

### 3. OneRec‑style unification is the most stable V1 pattern
Among evaluated systems:

- **OneRec V1/V2** shows the cleanest end‑to‑end unification
- Retrieval and ranking collapse into a single scoring space
- Training and inference pipelines are simpler and more stable

This pattern generalizes well across domains, suggesting it as a canonical V1 design.

---

### 4. Generative recommenders are emerging, not dominant (V1)
While generative or LLM‑style approaches appear in late V1 work:

- They are **not yet competitive** in latency‑sensitive production settings
- Gains are inconsistent without heavy distillation or hybridization
- Most success still comes from discriminative, sequence‑based models

Generative methods should be viewed as *V2‑era candidates*, not V1 replacements.

---

## Big Picture Summary

**V1 recommenders converge, they do not diversify.**

The dominant trajectory is:

> Unified → long‑context → sequence‑centric → pretrained

Rather than many competing paradigms, V1 collapses into a small number of stable design choices, with user modeling quality explaining most observed improvements.

---

## Limitations
- Focused on industrial‑scale systems; academic long‑tail work not fully covered
- Does not deeply evaluate cold‑start or fairness dimensions
- Assumes access to large‑scale behavior logs

---

## Outlook Toward V2
Open questions moving beyond V1:

- How far can sequence length scale before diminishing returns?
- Can generative models replace discriminative scoring *without* latency collapse?
- What is the right abstraction boundary between foundation models and RecSys heads?

These questions define the transition from **V1 consolidation** to **V2 exploration**.

---

*This file materializes the previously generated RecSys V1 cross‑validation summary that existed only as a conversational result.*
