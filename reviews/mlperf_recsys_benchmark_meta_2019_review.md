# MLPerf Recommendation Benchmark — Meta et al.

**Source**: Facebook (Meta) et al., arXiv:1911.09706

## One-page evaluator review

### Problem
Recommender systems lack standardized benchmarks that reflect real-world industrial workloads, making it difficult to compare hardware, systems, and training approaches fairly.

### Core idea
The MLPerf Recommendation benchmark introduces a **standardized, production-inspired workload** based on DLRM, capturing key characteristics of industrial recommenders: large embedding tables, mixed sparse/dense features, and stringent throughput requirements.

### Architecture highlights
- **DLRM-based model**: Represents a realistic recsys training workload.
- **Public dataset**: Based on Criteo-style ad data.
- **End-to-end metrics**: Measures training throughput and time-to-target quality.

### Results
MLPerf RecSys enables apples-to-apples comparison across hardware and system stacks, rapidly becoming the de facto standard for benchmarking recommender training.

### Strengths
- Strong industry backing
- Reflects real deployment constraints
- Drives system-level innovation

### Weaknesses / limitations
- Focused on training, not serving
- Single-model bias (DLRM-centric)

### Relevance to recsys trends
The benchmark crystallizes Meta’s view of recommenders as **system-scale workloads**, reinforcing the shift from pure modeling to infrastructure and efficiency competition.

### Takeaways
Standardized benchmarks accelerate progress by turning system design into a competitive, measurable discipline.
