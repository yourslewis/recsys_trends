# Practical Lessons from Predicting Clicks on Ads at Facebook — Meta

**Source**: He et al., Facebook, arXiv:1412.3102

## One-page evaluator review

### Problem
Predicting ad click-through rate (CTR) at Facebook scale involves extremely sparse features, massive data volume, and tight latency constraints. Academic models often fail under these practical conditions.

### Core idea
The paper documents **production lessons** from deploying large-scale CTR models, emphasizing feature engineering, calibration, and system tradeoffs over novel architectures.

### Architecture highlights
- **Logistic regression & early DNNs**: Simple models with heavy feature engineering.
- **Feature hashing**: Manage high-cardinality categorical features.
- **Calibration & monitoring**: Essential for business impact.

### Results
Demonstrated substantial CTR improvements through pragmatic choices rather than complex models, influencing Facebook’s ad stack for years.

### Strengths
- Honest production perspective
- Highlights non-obvious failure modes
- Historically influential

### Weaknesses / limitations
- Predates modern deep recsys architectures
- Accepts feature hashing collisions
- Limited discussion of long-term embedding lifecycle

### Relevance to recsys trends
This paper anchors Meta’s **pragmatic, iteration-driven culture**, contrasting with later Google emphasis on correctness (Monolith) and ByteDance focus on modeling user interests.

### Takeaways
Many modern debates (collisions, consistency, calibration) already existed implicitly; today’s systems formalize and scale these lessons.
