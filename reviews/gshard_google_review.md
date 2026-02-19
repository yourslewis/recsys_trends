# GShard: Scaling Giant Models with Conditional Computation — Google

**Source**: Lepikhin et al., Google, arXiv:2006.16668

## One-page evaluator review

### Problem
As recommender and ranking models grow, dense parameterization leads to prohibitive compute and memory costs. Scaling embedding-heavy or interaction-rich models requires new approaches beyond straightforward data/model parallelism.

### Core idea
GShard introduces **Mixture-of-Experts (MoE) with conditional computation**, activating only a small subset of experts per example. This enables trillion-parameter models without linear increases in compute cost.

### Architecture highlights
- **Sparse MoE layers**: Many experts, few activated per token/example.
- **Learned gating**: Routes inputs to experts dynamically.
- **Shard-aware training**: Designed for large TPU pods.

### Results
GShard demonstrates dramatic scaling improvements on language and ranking-style workloads, showing that sparse activation can unlock previously infeasible model sizes.

### Strengths
- Breaks dense scaling limits
- Infrastructure-aware design
- Influences later MoE recommender architectures

### Weaknesses / limitations
- Significant system complexity
- Requires specialized hardware and networking
- Load balancing is non-trivial

### Relevance to recsys trends
GShard connects Google’s **model and system philosophies**: extreme-scale models demand tight co-design of architecture and infrastructure. It complements Monolith and ScaNN by enabling larger ranking and interaction models.

### Takeaways
Future recommender gains may come from *conditional computation* rather than uniformly larger dense models.
