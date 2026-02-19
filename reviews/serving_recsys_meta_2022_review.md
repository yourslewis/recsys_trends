# Efficient Serving of Large-Scale Recommendation Models — Meta

**Source**: Meta, arXiv:2205.12112

## One-page evaluator review

### Problem
As recommendation models grow in size and complexity, **serving latency, tail performance, and cost** become dominant constraints. Training gains often fail to translate to production impact without careful serving design.

### Core idea
This paper describes Meta’s **end-to-end serving optimizations** for large-scale recommender models, focusing on model partitioning, caching, hardware utilization, and latency-aware scheduling.

### Architecture highlights
- **Model partitioning**: Separates embedding-heavy and compute-heavy components.
- **Caching strategies**: Reuse hot embeddings and intermediate activations.
- **Hardware-aware serving**: CPU/GPU role separation tuned for recsys workloads.
- **Tail-latency optimization**: Explicit focus on p99 performance.

### Results
Meta reports substantial reductions in serving latency and cost while maintaining model accuracy, enabling deployment of larger and more expressive models.

### Strengths
- Deep production realism
- Focus on tail latency, not averages
- Complements training-side scaling work

### Weaknesses / limitations
- Less emphasis on strong consistency guarantees compared to Google Monolith
- Details tied closely to Meta’s infra stack

### Relevance to recsys trends
This paper positions Meta between Google and ByteDance: **strong serving optimization**, but without fully embracing collisionless or strongly consistent embedding systems.

### Takeaways
Serving efficiency is now as important as model quality; future recommender gains require tight training–serving co-design.
