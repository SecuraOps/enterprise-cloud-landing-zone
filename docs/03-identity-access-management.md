# Identity and Access Management

## Identity Provider
Azure Entra ID (Azure Active Directory) is the **central identity provider**
for all users, groups, and service principals.

## Core Principles

### 1. Least Privilege
Access is granted:
- Only when required
- At the lowest possible scope
- For the shortest possible duration

### 2. Role-Based Access Control (RBAC)
RBAC is used consistently across:
- Management Groups
- Subscriptions
- Resource Groups

Built-in roles are preferred over custom roles.

### 3. Separation of Duties
Key responsibilities are separated:
- Platform administration
- Security governance
- Application operations

## Access Model

### Human Access
- Group-based RBAC assignments
- No direct user-to-resource permissions
- Privileged roles assigned via **Privileged Identity Management (PIM)** (conceptual)

### Non-Human Access
- Service principals or managed identities
- Scoped to specific subscriptions or resources
- No tenant-wide permissions

## Scope Strategy

| Scope | Usage |
|------|------|
| Tenant | Identity configuration only |
| Management Group | Governance roles |
| Subscription | Operational roles |
| Resource Group | Application-specific roles |

## Security Considerations
- No long-lived credentials stored in code
- Access reviewed periodically
- Identity changes audited centrally

## Out of Scope
- Detailed PIM configuration
- Conditional Access policies
- Identity lifecycle automation

These are organization-specific by nature.
