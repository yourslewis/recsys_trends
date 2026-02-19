# Hard Negative Mining for Neural Retrieval — Google

**Source**: Google, arXiv:2005.09347

## One-page evaluator review

### Problem
Neural retrieval models trained with random or popularity-based negatives learn weak decision boundaries. As models scale, negative quality—not model capacity—becomes the dominant limiter of recall.

### Core idea
The paper introduces **hard negative mining** for large-scale neural retrieval, iteratively sampling negatives that are highly ranked by the current model but incorrect. This sharpens the embedding space without requiring full-softmax training.

### Architecture highlights
- **Two-tower retrieval model**: User and item encoders trained with dot-product similarity.
- **Iterative mining loop**: Periodically refreshes hard negatives using ANN search.
- **Scalable training**: Maintains feasibility at large corpus sizes.

### Results
Hard-negative-trained models significantly outperform those trained with random negatives, especially at high recall thresholds, and transfer gains to downstream ranking.

### Strengths
- Directly targets the retrieval bottleneck
- Orthogonal to model architecture
- Strong empirical gains

### Weaknesses / limitations
- More complex training pipeline
- Requires stable ANN infrastructure

### Relevance to recsys trends
This work aligns Google with ByteDance’s later emphasis on **training signal quality** (hierarchical negatives), while remaining compatible with Google’s infra-first stack (ScaNN, Monolith).

### Takeaways
As retrieval matures, better negatives rival bigger models in impact.
