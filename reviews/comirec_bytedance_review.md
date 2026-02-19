# ComiRec: Controllable Multi-Interest Framework — ByteDance

**Source**: Cen et al., ByteDance, arXiv:2006.05625

## One-page evaluator review

### Problem
Multi-interest user modeling improves recall, but existing methods offer little control over *which* interests are emphasized during retrieval, limiting flexibility across recommendation scenarios.

### Core idea
ComiRec extends multi-interest modeling with **controllable interest extraction**, allowing the system to adjust how user behaviors are clustered into interests via different aggregation operators (e.g., attention, pooling).

### Architecture highlights
- **Behavior encoder**: Encodes user interaction sequences.
- **Interest extraction modules**: Multiple controllable mechanisms to form interest vectors.
- **Multi-vector retrieval**: Candidates retrieved against all interest embeddings.

### Results
ComiRec improves recall and ranking metrics over prior multi-interest baselines (including MIND) on large-scale datasets.

### Strengths
- Generalizes multi-interest modeling
- Flexible control over interest granularity
- Strong empirical improvements

### Weaknesses / limitations
- Additional modeling complexity
- Infrastructure assumptions remain implicit
- Serving cost scales with number of interests

### Relevance to recsys trends
ComiRec reinforces ByteDance’s trajectory: **modeling user intent diversity** is a primary lever, even as system infrastructure is treated as a stable substrate.

### Takeaways
ByteDance doubles down on multi-interest retrieval as a durable advantage in feed-based recommendation.
