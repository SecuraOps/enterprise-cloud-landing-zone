# Logging and Monitoring

## Objective
Provide **centralized visibility** into platform and workload activity
to support:
- Operational monitoring
- Security investigations
- Compliance requirements

Logging and monitoring are foundational to platform reliability and security.

---

## Design Principles

### 1. Centralization
Logs and metrics are:
- Collected centrally
- Retained according to policy
- Accessible to authorized teams

### 2. Separation of Duties
- Platform teams manage logging infrastructure
- Workload teams consume logs and metrics
- Security teams access audit and security data

### 3. Cost Awareness
Logging is:
- Purpose-driven
- Retention-based
- Reviewed periodically to control cost

---

## Logging Architecture

### Log Analytics Workspaces
- Central Log Analytics workspace per region (recommended)
- Platform subscriptions host shared workspaces
- Workloads send logs to central destinations

### Log Sources
Collected logs include:
- Azure Activity Logs
- Resource diagnostic logs
- Platform service logs
- Security-related logs

---

## Metrics and Monitoring

### Azure Monitor
Azure Monitor is used for:
- Resource health
- Performance metrics
- Basic alerting

Standard alerts are defined for:
- Resource availability
- Platform-level failures
- Capacity thresholds (conceptual)

---

## Security Logging

### Audit and Activity Logs
- Tenant-level activity logs are retained
- Subscription activity is centralized
- Access and role changes are logged

### Integration Readiness
The architecture supports:
- SIEM integration (e.g., Microsoft Sentinel)
- External monitoring tools

---

## Retention Strategy

| Log Type | Retention |
|--------|-----------|
| Activity Logs | 90+ days |
| Platform Logs | Contextual |
| Security Logs | Extended (as required) |

Retention periods are defined based on:
- Regulatory needs
- Operational value
- Cost considerations

---

## Access Control

- Read-only access for most users
- Elevated access for security and platform teams
- All access is audited

---

## Operational Considerations

- Alerts are actionable, not noisy
- Dashboards focus on platform health
- Logging configurations are reviewed periodically

---

## Out of Scope
This document does not cover:
- Detailed alert definitions
- Custom dashboards
- SIEM/SOAR tuning

These are implemented based on organizational needs.
