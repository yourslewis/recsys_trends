# FAISS: A Library for Efficient Similarity Search and Clustering — Meta (Facebook)

**Source**: Johnson et al., Facebook AI Research, arXiv:1702.08734

## One-page evaluator review

### Problem
Large-scale recommender systems require fast similarity search over millions to billions of vectors. Exact nearest neighbor search is computationally infeasible at this scale.

### Core idea
FAISS provides a **modular library of approximate nearest neighbor (ANN) algorithms**, combining vector quantization, inverted indexes, and GPU acceleration to enable scalable similarity search.

### Architecture highlights
- **Indexing structures**: IVF, PQ, OPQ for memory–accuracy tradeoffs.
- **GPU acceleration**: Massive speedups for training and querying.
- **Composable design**: Mix-and-match components per workload.

### Results
FAISS achieves strong recall–latency tradeoffs across benchmarks and becomes a foundational ANN tool across industry and research.

### Strengths
- Extremely flexible and widely adopted
- Strong performance on GPUs
- Forms the backbone of many retrieval systems

### Weaknesses / limitations
- Requires careful tuning
- Provides primitives, not end-to-end recsys solutions

### Relevance to recsys trends
FAISS is Meta’s counterpart to Google’s ScaNN: **retrieval infrastructure as a competitive lever**. It underpins both single- and multi-interest retrieval models.

### Takeaways
High-quality ANN infrastructure is a prerequisite for modern recommender gains, enabling increasingly expressive retrieval models.
