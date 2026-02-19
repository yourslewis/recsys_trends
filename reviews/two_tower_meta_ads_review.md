# Two-Tower Models for Ads and Recommendations — Meta

**Source**: Meta (Facebook), arXiv:2103.00020

## One-page evaluator review

### Problem
Retrieval systems for ads and recommendations must score user–item pairs at massive scale. Monolithic models are too slow for candidate generation over millions of items.

### Core idea
Two-tower (dual-encoder) models learn **separate user and item embeddings** optimized for dot-product similarity, enabling efficient ANN-based retrieval while preserving personalization.

### Architecture highlights
- **User tower**: Encodes user context and behavior.
- **Item tower**: Encodes item features.
- **Similarity scoring**: Dot product or cosine similarity.
- **ANN retrieval**: Scales candidate generation to large corpora.

### Results
Meta reports strong performance for ads retrieval and recommendation tasks, with substantial latency and throughput benefits compared to cross-encoder models.

### Strengths
- Clean separation of retrieval and ranking
- Infrastructure-friendly and scalable
- Compatible with FAISS-style ANN backends

### Weaknesses / limitations
- Expressiveness limited to embedding similarity
- Requires downstream ranking for fine-grained personalization

### Relevance to recsys trends
Two-tower models form the **retrieval backbone** across Meta, Google, and ByteDance systems. Differences arise in how much modeling complexity (multi-interest, Transformers) or system rigor (Monolith, ScaNN) is layered on top.

### Takeaways
Retrieval simplicity plus strong infrastructure remains a winning combination; innovation increasingly shifts to what surrounds the two towers.
