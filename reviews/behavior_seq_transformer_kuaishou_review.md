# Behavior Sequence Transformer for Recommendation — Kuaishou

**Source**: Zhou et al., Kuaishou, arXiv:1905.06874

## One-page evaluator review

### Problem
Short-video platforms must model rapidly evolving user interests from long, noisy behavior sequences. Traditional pooling or RNN-based methods struggle to capture long-range dependencies and interest shifts.

### Core idea
The paper introduces a **Transformer-based behavior sequence encoder** that models user interaction histories with self-attention, enabling flexible weighting of past behaviors when generating user representations for recommendation.

### Architecture highlights
- **Behavior embeddings**: Encode user actions (watch, like, etc.) with positional/context signals.
- **Self-attention layers**: Capture long-range dependencies and interest transitions.
- **User representation**: Attention-pooled sequence output fed into downstream ranking models.

### Results
On large-scale Kuaishou datasets, the Transformer-based model outperforms RNN and CNN baselines in offline metrics and delivers online engagement gains.

### Strengths
- Early industrial adoption of Transformers in recsys
- Well-suited to high-churn, short-video consumption patterns
- Conceptually extensible to multi-interest modeling

### Weaknesses / limitations
- Computationally heavier than simple pooling/RNNs
- Embedding and attention scalability constraints not deeply discussed
- Focuses on modeling, not system-level infrastructure

### Relevance to recsys trends
This paper signals ByteDance/Kuaishou-style emphasis on **sequence modeling and interest dynamics**, complementing Google’s system-heavy work and Meta’s model-centric DLRM lineage.

### Takeaways
Transformer encoders become natural fits for short-video recommendation, shifting innovation toward modeling user dynamics while largely reusing existing retrieval–ranking stacks.
