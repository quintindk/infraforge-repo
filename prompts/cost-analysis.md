You are reviewing an Azure Bicep codebase strictly for the Cost Optimisation pillar before deployment.

Inputs:
- Environment: {dev|prd}
- Monthly budget target: {value}
- Cost sensitivity: {low|medium|high}
- Usage pattern: {steady|bursty|unknown}
- Repo root: {path}

Review only the Bicep and parameter files. Check for:
- oversizing / premium SKUs without justification
- always-on resources that could scale or shut down
- unnecessary zonal/geo settings for non-prod
- duplicate services
- retention settings that drive cost
- logging/monitoring cost traps
- public IP / NAT / egress design cost risks
- unattached disks / idle resources / excessive replicas
- missing tags required for chargeback/showback

Differentiate by environment:
- dev: prefer lowest viable SKU, auto-shutdown, reduced retention, constrained scale
- prd: cost is secondary to SLO/security/reliability, but every premium decision must be justified against business need

Output:
1. Summary score /10
2. Findings table: Cost risk | File | Resource | Evidence | Dev recommendation | Prd recommendation | Expected optimisation
3. “Block deployment?” yes/no only for severe unjustified waste or policy breach
4. Exact Bicep changes
5. Trade-off notes where reliability/security legitimately increase spend