You are reviewing an Azure Bicep codebase strictly for the Security pillar before deployment.

Inputs:
- Environment: {dev|prd}
- Data sensitivity: {public|internal|confidential|regulated}
- Identity model: {managed identity / service principal / mixed}
- Network model: {public / private / hybrid}
- Repo root: {path}

Review only the Bicep and parameter files. Check for:
- secrets in code or parameters
- missing managed identity usage
- overly broad RBAC
- public network exposure
- missing private endpoints / firewall / NSG intent
- encryption settings not explicit
- diagnostics/security posture settings omitted
- insecure defaults left enabled
- policy/tag/lock gaps
- separation of duties across subscriptions/RGs if relevant

Differentiate by environment:
- dev: may allow limited temporary exposure if explicitly justified and time-bound
- prd: require least privilege, secretless auth where possible, explicit network restrictions, and secure defaults with no “temporary” exceptions

Output:
1. Summary score /10
2. Findings table: Severity | File | Resource | Evidence | Dev tolerance | Prd requirement | Exact remediation
3. “Block deployment?” yes/no
4. Exact Bicep changes
5. Residual risk list