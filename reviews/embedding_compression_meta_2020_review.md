# Embedding Compression Techniques for Large-Scale Recommendation Systems — Meta

**Source**: Meta (Facebook), arXiv:2010.11941

## One-page evaluator review

### Problem
Embedding tables dominate memory footprint and serving cost in large-scale recommender systems. As vocabularies grow into billions, naive dense embeddings become economically infeasible.

### Core idea
This paper surveys and evaluates **embedding compression techniques**—including quantization, hashing, low-rank factorization, and pruning—applied to industrial recommender workloads.

### Architecture highlights
- **Quantized embeddings**: Reduce precision to lower memory and bandwidth cost.
- **Hashing & sharing**: Trade collisions for footprint reduction.
- **Low-rank factorization**: Decompose large tables into smaller components.
- **Hybrid strategies**: Combine techniques depending on feature frequency.

### Results
Meta demonstrates substantial memory and cost savings with minimal accuracy loss, enabling deployment of larger models under fixed serving budgets.

### Strengths
- Strong production relevance
- Systematic comparison of techniques
- Direct impact on serving feasibility

### Weaknesses / limitations
- Accepts embedding collisions and approximation
- Less emphasis on consistency or correctness guarantees

### Relevance to recsys trends
Embedding compression reflects Meta’s **cost- and efficiency-driven philosophy**, contrasting with Google Monolith’s collisionless stance and ByteDance’s focus on richer modeling.

### Takeaways
As models scale, memory efficiency becomes a first-class design dimension alongside accuracy and latency.
