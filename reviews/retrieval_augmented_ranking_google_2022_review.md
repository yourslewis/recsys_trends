# Retrieval-Augmented Ranking Models for Recommendation — Google

**Source**: Google, arXiv:2205.09629

## One-page evaluator review

### Problem
Ranking models operate on a limited candidate set. When retrieval recall is imperfect, ranking quality saturates regardless of model complexity. Tight coupling between retrieval and ranking is required to unlock further gains.

### Core idea
The paper proposes **retrieval-augmented ranking**, where ranking models explicitly incorporate retrieval signals (candidate embeddings, retrieval scores, neighborhood context) rather than treating retrieval as a black box.

### Architecture highlights
- **Two-stage pipeline retained**: Retrieval followed by ranking.
- **Augmented features**: Ranking model consumes retrieval embeddings and scores.
- **Joint optimization signals**: Better alignment between stages.

### Results
Google reports consistent gains over decoupled pipelines, particularly in regimes where retrieval recall is the bottleneck.

### Strengths
- Pragmatic improvement to a ubiquitous architecture
- Preserves scalability while improving effectiveness
- Compatible with ScaNN and Monolith-style infra

### Weaknesses / limitations
- Still bounded by retrieval candidate quality
- Adds feature and training complexity

### Relevance to recsys trends
This work represents a **middle path** between pure modeling and pure systems: architectural glue that extracts more value from existing infrastructure investments.

### Takeaways
As pipelines mature, progress increasingly comes from tightening interfaces between components rather than replacing them.
