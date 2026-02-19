# Hierarchical Negative Sampling for Large-Scale Recommendation — ByteDance

**Source**: ByteDance, arXiv:2209.07498

## One-page evaluator review

### Problem
Two-tower and retrieval-based recommenders rely heavily on negative sampling during training. Uniform or simple heuristic sampling produces easy negatives, leading to weak decision boundaries and poor recall at scale.

### Core idea
The paper proposes **hierarchical negative sampling**, where negatives are drawn from progressively harder buckets (e.g., popular, semantically similar, or high-score candidates), approximating full-softmax training while remaining scalable.

### Architecture highlights
- **Two-tower retrieval backbone**: User and item encoders trained with dot-product similarity.
- **Hierarchical sampler**: Multi-stage negative pools with increasing hardness.
- **Adaptive training**: Sampling strategy evolves with model maturity.

### Results
On ByteDance-scale datasets, hierarchical negative sampling significantly improves retrieval recall and downstream ranking metrics compared to uniform or popularity-based sampling.

### Strengths
- Directly targets retrieval quality
- Infrastructure-friendly (no serving change)
- Complements multi-interest models like MIND/ComiRec

### Weaknesses / limitations
- More complex training pipeline
- Requires careful sampler calibration
- Does not address embedding freshness or consistency

### Relevance to recsys trends
This work shows ByteDance optimizing the **training dynamics** of retrieval models rather than rebuilding serving infrastructure. It contrasts with Google’s focus on correctness (Monolith) and ANN rigor (ScaNN).

### Takeaways
When infrastructure is stable, improving training signals (better negatives) becomes a powerful and cost-effective lever.
