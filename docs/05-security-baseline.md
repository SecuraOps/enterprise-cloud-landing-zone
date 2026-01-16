# Security Baseline

## Objective
Define a **minimum, enterprise-grade security baseline** that is applied
consistently across the Azure tenant to reduce risk and enforce good practices
by default.

This baseline focuses on **preventive and detective controls** at scale.

---

## Security Design Principles

### 1. Defense in Depth
Security controls are applied across multiple layers:
- Identity
- Network
- Platform
- Workloads

No single control is assumed to be sufficient.

### 2. Secure by Default
New subscriptions and resources:
- Inherit security controls automatically
- Are compliant unless explicitly exempted

### 3. Centralized Governance
Security policies and configurations are:
- Defined centrally
- Applied consistently
- Auditable

---

## Governance and Policy Enforcement

### Azure Policy
Azure Policy is used to enforce:
- Resource location restrictions
- Mandatory tagging
- Approved resource types
- Encryption at rest
- Secure configuration baselines

Policies are applied primarily at:
- Management Group level
- Subscription level (when required)

### Policy Strategy
- Prefer **Deny** or **DeployIfNotExists** effects
- Avoid overly restrictive policies in early phases
- Document all exemptions

---

## Identity Security

### Authentication
- Entra ID is the single identity provider
- MFA is required for privileged roles (conceptual)

### Authorization
- RBAC is used consistently
- No direct user assignments to resources
- Access granted via groups

### Privileged Access
- Privileged roles are eligible, not permanent
- Emergency access is documented and controlled

---

## Network Security

### Baseline Controls
- Network Security Groups (NSGs) applied to all subnets
- Default deny inbound traffic
- Explicitly allowed outbound traffic where required

### Traffic Inspection
- Centralized inspection in the hub network (conceptual)
- No direct internet exposure unless justified

---

## Resource Security

### Encryption
- Encryption at rest enabled by default
- Customer-managed keys (CMK) are optional and contextual

### Secrets Management
- Secrets stored in Azure Key Vault
- No secrets in code or configuration files

---

## Security Monitoring

### Defender for Cloud
Microsoft Defender for Cloud is used to:
- Identify misconfigurations
- Detect threats
- Provide security posture visibility

Baseline plans are enabled at the subscription level.

---

## Incident Response Readiness

- Centralized logging supports investigation
- Access and activity logs are retained
- Clear ownership for incident handling

---

## Out of Scope
This baseline does not include:
- Detailed SIEM/SOAR implementations
- Organization-specific compliance mappings
- Incident response playbooks

These are addressed per organization.
