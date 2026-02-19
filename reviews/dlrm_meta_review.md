# Deep Learning Recommendation Model (DLRM) — Meta (Facebook)

**Source**: Facebook AI, arXiv:1906.00091

## One-page evaluator review

### Problem
Industrial recommenders must combine dense numerical features with extremely high-cardinality sparse categorical features. Prior deep models struggled to scale embedding interactions efficiently while keeping inference latency acceptable.

### Core idea
DLRM separates **dense** and **sparse** feature processing. Sparse categorical features are embedded and then combined with dense features through an explicit *feature interaction* operation (dot products), followed by a top MLP.

### Architecture highlights
- **Bottom MLP**: Processes dense numerical features.
- **Embedding tables**: One per sparse feature, trained jointly.
- **Feature interaction layer**: Computes pairwise dot products between embeddings and dense outputs.
- **Top MLP**: Learns higher-order interactions.

### Results
DLRM demonstrated strong accuracy–latency tradeoffs on production-scale tasks and became a reference architecture for both research and industry benchmarks (e.g., MLPerf).

### Strengths
- Conceptually simple and modular
- Clear separation of dense vs sparse modeling
- Highly influential; easy to optimize and scale incrementally

### Weaknesses / limitations
- Embedding tables dominate memory and system cost
- Interaction layer is fixed (pairwise dots only)
- Does not address system-level issues like collisions or consistency

### Relevance to recsys trends
DLRM represents the *model-centric era* of recommender design. Later systems (e.g., Google Monolith) keep DLRM-like cores but shift innovation toward embedding infrastructure, consistency, and lifecycle management.

### Takeaways
DLRM is less about novelty today and more about being the stable baseline that modern system-level papers react against or extend.
