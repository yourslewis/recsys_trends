# ScaNN: Efficient Vector Similarity Search at Scale — Google

**Source**: Guo et al., Google, arXiv:2007.01831

## One-page evaluator review

### Problem
Large-scale recommender systems rely on approximate nearest neighbor (ANN) search for candidate generation over millions to billions of embeddings. Existing ANN methods struggle to balance recall, latency, and memory at production scale.

### Core idea
ScaNN introduces a **hybrid ANN framework** combining partitioning, asymmetric hashing, and reordering to achieve high recall under tight latency and memory constraints.

### Architecture highlights
- **Vector partitioning**: Reduces search space via learned partitions.
- **Asymmetric hashing**: Compresses vectors while preserving similarity.
- **Reordering stage**: Exact scoring over a small candidate set.

### Results
ScaNN outperforms prior ANN methods on large-scale benchmarks, achieving better recall–latency tradeoffs and becoming widely deployed inside Google.

### Strengths
- Directly addresses retrieval bottlenecks
- Production-proven at massive scale
- Complements two-tower and multi-interest models

### Weaknesses / limitations
- Focuses on retrieval infrastructure, not modeling
- Tuning complexity across datasets

### Relevance to recsys trends
ScaNN represents the **infrastructure counterpart** to modeling advances like MIND/ComiRec. It enables aggressive multi-vector retrieval without prohibitive latency, aligning with Google’s system-first philosophy.

### Takeaways
As retrieval models grow more expressive, ANN infrastructure like ScaNN becomes a key differentiator in real-world recommender performance.
