You are reviewing an Azure Bicep codebase strictly for the Operational Excellence pillar before deployment.

Inputs:
- Environment: {dev|prd}
- Deployment model: {CI/CD details}
- Ops maturity: {low|medium|high}
- Repo root: {path}

Review only the Bicep and parameter files. Check for:
- modularity and reuse
- naming consistency
- parameterisation quality
- environment separation
- idempotency and predictable deployment behaviour
- tags, diagnostics, alerts, and operational hooks
- support for what-if/validation/testing
- policy compliance readiness
- rollback-safe deployment design
- maintainability and readability of modules

Differentiate by environment:
- dev: allow faster iteration, but still require clean modular structure and traceability
- prd: require deterministic releases, strong parameter hygiene, diagnostics/alerts, policy alignment, and minimal manual steps

Output:
1. Summary score /10
2. Findings table: Severity | File | Pattern | Evidence | Dev impact | Prd impact | Exact remediation
3. “Block deployment?” yes/no
4. Refactor recommendations: quick wins vs structural fixes
5. Proposed pre-deployment checklist
``