You are reviewing an Azure Bicep codebase strictly for the Reliability pillar before deployment.

Inputs:
- Environment: {dev|prd}
- Workload criticality: {low|medium|high|mission-critical}
- RTO: {value}
- RPO: {value}
- Regions / AZ requirements: {value}
- Repo root: {path}

Review only the Bicep and parameter files. Check for:
- single points of failure
- missing zone/region redundancy decisions
- resilience defaults not made explicit
- DR/failover readiness
- backup/restore configuration
- dependency ordering and blast radius
- safe handling of stateful services
- health probes / platform resiliency settings where relevant

Differentiate by environment:
- dev: lower-cost resilience is acceptable; document what is intentionally reduced
- prd: require explicit HA/zone/region decisions, failure-domain awareness, restore path, and rollback-safe deployment design

Output:
1. Summary score /10
2. Findings table: Severity | File | Resource | Evidence | Dev impact | Prd impact | Exact remediation
3. “Block deployment?” yes/no
4. Exact Bicep changes or module patterns to fix each issue
5. Assumptions and unknowns