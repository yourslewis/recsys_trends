# Sampling-Bias-Corrected Neural Modeling for Large Corpus Retrieval — Google

**Source**: Yi et al., Google, arXiv:2104.07567

## One-page evaluator review

### Problem
Two-tower retrieval models are trained with sampled negatives, introducing **sampling bias** that misaligns training objectives with full-corpus retrieval metrics. This gap degrades recall and ranking quality at scale.

### Core idea
The paper proposes **bias-corrected loss formulations** for neural retrieval that explicitly account for negative sampling distributions, aligning training with true softmax over large corpora.

### Architecture highlights
- **Two-tower retrieval**: Separate user and item encoders with dot-product scoring.
- **Bias correction terms**: Adjust logits or losses based on sampling probabilities.
- **Scalable training**: Retains sampled negatives while approximating full softmax behavior.

### Results
Across large-scale Google datasets, bias-corrected objectives significantly improve retrieval recall and downstream ranking performance with minimal serving overhead.

### Strengths
- Directly addresses a core theoretical–practical gap
- Drop-in improvement for existing two-tower systems
- Strong empirical validation

### Weaknesses / limitations
- Requires accurate estimation of sampling distributions
- Does not address embedding freshness or serving consistency

### Relevance to recsys trends
This work strengthens the **retrieval stage** of the two-stage paradigm, complementing system papers (Monolith) and modeling advances (DLRM, DCNv2). It shows that careful objective design still yields meaningful gains.

### Takeaways
Even in mature stacks, principled fixes to long-standing approximations can unlock measurable improvements without architectural overhaul.
