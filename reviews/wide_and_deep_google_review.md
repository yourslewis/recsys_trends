# Wide & Deep Learning for Recommender Systems — Google

**Source**: Cheng et al., Google, arXiv:1606.07792 (Wide & Deep)

## One-page evaluator review

### Problem
Linear models with engineered feature crosses generalize poorly, while deep models generalize well but can struggle to memorize sparse, idiosyncratic patterns important for recommendation.

### Core idea
Wide & Deep combines a **wide (linear) model** for memorization with a **deep neural network** for generalization, trained jointly to capture both explicit rules and implicit patterns.

### Architecture highlights
- **Wide component**: Linear model with cross-product features.
- **Deep component**: Feed-forward neural network over embeddings and dense features.
- **Joint training**: Shared loss enables complementary learning.

### Results
Demonstrated significant gains on Google Play app recommendations and became a foundational production architecture.

### Strengths
- Simple, interpretable hybrid design
- Strong empirical gains at the time
- Influenced a decade of recsys architectures

### Weaknesses / limitations
- Manual feature crosses remain brittle
- Embedding and system issues abstracted away
- Superseded by more automated interaction models (DCN, DLRM)

### Relevance to recsys trends
Wide & Deep establishes the *hybrid modeling* lineage that evolves into DCN, DLRM, and modern two-tower systems. It anchors the early model-centric era preceding system-heavy work like Monolith.

### Takeaways
The paper’s lasting impact lies in framing recommendation as a balance between memorization and generalization—an idea still visible in modern architectures.
