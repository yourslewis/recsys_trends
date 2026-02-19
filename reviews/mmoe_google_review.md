# Multi-gate Mixture-of-Experts (MMoE) for Recommender Systems — Google

**Source**: Ma et al., Google, arXiv:1808.09574

## One-page evaluator review

### Problem
Large-scale recommender systems often need to optimize **multiple related objectives** (CTR, CVR, dwell time). Naively training separate models wastes data, while fully shared models suffer from negative transfer.

### Core idea
MMoE introduces a **multi-gate mixture-of-experts** architecture that allows tasks to share a pool of expert subnetworks, while learning task-specific gating functions to control which experts contribute to each task.

### Architecture highlights
- **Shared experts**: Multiple expert MLPs trained jointly.
- **Task-specific gates**: Soft gating networks select weighted combinations of experts per task.
- **Task towers**: Lightweight heads for each objective.

### Results
MMoE significantly outperforms both fully shared and task-specific baselines on multi-task learning benchmarks and production-scale datasets.

### Strengths
- Elegant solution to negative transfer
- Scales naturally to many tasks
- Widely adopted in industry multi-task recommenders

### Weaknesses / limitations
- Increases model complexity and tuning burden
- Does not address embedding storage or consistency
- Expert collapse can occur without care

### Relevance to recsys trends
MMoE extends the model-centric lineage (Wide & Deep → DLRM) into **multi-task optimization**, a requirement for mature recommender stacks. System-level concerns are still handled externally (e.g., Monolith).

### Takeaways
As objectives proliferate, architectural support for controlled sharing becomes essential—but infrastructure remains the dominant scaling bottleneck.
