# Duties

System-wide segregation of duties policy and multi-agent supervisory boundaries for ICU Sepsis Early Warning Agent.

## Roles

| Role | Agent | Permissions | Description |
|------|-------|-------------|-------------|
| maker | vitals-trend-analyzer | create, submit | Formulates candidate analysis plans and executes initial problem decomposition |
| checker | sofa-score-auditor | review, approve, reject | Validates findings, audits invariant constraints, and authorizes final output |
| auditor | compliance-auditor | audit, report | Audits execution trace logs, verifies provenance, and monitors safety policies |
| executor | task-executor | execute | Executes verified remediation actions against external environments |

## Conflict Matrix

No single agent may hold conflicting roles in any execution lifecycle:

- An agent assigned the maker role cannot perform verification or auditing
- An agent assigned the checker role cannot perform plan generation or execution
- An agent assigned the executor role cannot perform compliance auditing
- An agent assigned the auditor role cannot perform action execution

## Handoff Workflows

1. The maker agent generates the initial diagnostic assessment and candidate remediation strategy.
2. The checker agent audits evidence quality, checks policy constraints, and validates invariants.
3. The auditor agent signs the cryptographic trace and verifies that no sensitive data is leaked.
4. The executor agent delivers the approved intervention to the target runtime environment.

## Isolation Policy

- **State isolation:** full
- **Credential segregation:** separate

## Enforcement

strict
