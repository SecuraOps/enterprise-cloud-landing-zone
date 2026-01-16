# Cost Governance

## Objective
Establish a **transparent, predictable, and controlled cost model**
that enables teams to use Azure efficiently while preventing
unexpected spend and budget overruns.

Cost governance is treated as a **shared responsibility** between
platform teams, finance, and workload owners.

---

## Cost Management Principles

### 1. Visibility First
Teams must be able to:
- Understand where costs originate
- Attribute costs to environments and workloads
- Detect abnormal spending early

No cost optimization is effective without visibility.

### 2. Accountability
Costs are:
- Assigned to clear owners
- Reviewed regularly
- Managed proactively

Every subscription and workload has a responsible owner.

### 3. Guardrails Over Policing
Cost governance focuses on:
- Preventing obvious waste
- Guiding good behavior
- Avoiding excessive restrictions

Teams retain flexibility within defined limits.

---

## Organizational Cost Model

### Subscription-Level Cost Boundaries
Each subscription represents a **natural cost boundary**:
- Separate budgets per subscription
- Clear ownership per environment or workload
- Simplified reporting and chargeback

### Environment Isolation
Common patterns:
- Production and non-production subscriptions
- Sandbox subscriptions with strict budgets
- Platform subscriptions managed centrally

---

## Tagging Strategy (Cost Attribution)

### Mandatory Cost Tags
The following tags are required on all resources:

| Tag Name | Purpose |
|--------|---------|
| `Environment` | Prod / NonProd / Sandbox |
| `Application` | Logical application name |
| `Owner` | Responsible team or individual |
| `CostCenter` | Financial reporting |

Tag enforcement is implemented via Azure Policy.

---

## Budgeting and Alerts

### Azure Budgets
Budgets are defined at:
- Subscription level
- Resource group level (when required)

Budgets include:
- Monthly thresholds
- Alert notifications
- Escalation paths

### Alert Strategy
- Early warning alerts (e.g., 50–70%)
- Actionable alerts before budget exhaustion
- Notifications sent to workload owners and platform teams

---

## Cost Controls and Guardrails

### Allowed Services
- Restrict high-cost services in non-production environments
- Limit region selection where appropriate

### Resource Sizing Guidance
- Encourage right-sized SKUs
- Avoid over-provisioned defaults
- Prefer consumption-based services when suitable

### Sandbox Controls
Sandbox subscriptions:
- Have strict budgets
- Limited service availability
- Automatic cleanup policies (conceptual)

---

## Cost Optimization Practices

### Review Cadence
- Monthly cost reviews with stakeholders
- Periodic optimization recommendations
- Continuous improvement mindset

### Optimization Levers
- Reserved instances / savings plans (when stable)
- Autoscaling
- Lifecycle policies for storage
- Decommissioning unused resources

---

## Reporting and Chargeback

### Cost Reporting
- Azure Cost Management reports used as baseline
- Dashboards shared with stakeholders

### Chargeback / Showback
The architecture supports:
- Showback for transparency
- Chargeback where organizationally appropriate

Implementation depends on financial maturity.

---

## Governance Integration

Cost governance integrates with:
- Azure Policy (tag enforcement, allowed SKUs)
- Management Group hierarchy
- Logging and monitoring systems

---

## Out of Scope
This document does not define:
- Organization-specific financial processes
- Detailed budget thresholds
- Automated cost remediation workflows

These are tailored per organization.
