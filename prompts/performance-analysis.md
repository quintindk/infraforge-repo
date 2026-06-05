You are reviewing an Azure Bicep codebase strictly for the Performance Efficiency pillar before deployment.

Inputs:
- Environment: {dev|prd}
- Performance targets: {latency|throughput|concurrency}
- Scaling expectation: {low|medium|high|unknown}
- Repo root: {path}

Review only the Bicep and parameter files. Check for:
- SKU choices aligned to workload profile
- scaling configuration explicitness
- storage/account performance tiers
- network path bottlenecks
- region placement issues
- limits/quotas likely to be hit
- caching/messaging/data service sizing assumptions
- autoscale or elasticity gaps
- noisy-neighbour or single-instance risks

Differentiate by environment:
- dev: right-size for functional validation; avoid paying for peak capacity unless perf testing requires it
- prd: require explicit scaling strategy, quota awareness, and performance-sensitive SKU/region choices aligned to SLOs

Output:
1. Summary score /10
2. Findings table: Severity | File | Resource | Evidence | Dev recommendation | Prd requirement | Exact remediation
3. “Block deployment?” yes/no
4. Exact Bicep changes
5. Capacity and scale assumptions that must be validated before go-live