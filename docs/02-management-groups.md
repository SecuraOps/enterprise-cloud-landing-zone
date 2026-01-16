# Management Group Design

## Purpose
Management Groups provide a **hierarchical governance model** that enables:
- Policy inheritance
- RBAC consistency
- Clear ownership boundaries

They form the backbone of enterprise-scale Azure governance.

## Management Group Hierarchy

```psql
Tenant Root Group
├── Platform
│ ├── Identity
│ ├── Connectivity
│ └── Management
├── LandingZones
│ ├── Corp
│ └── Online
└── Sandbox
```


## Description of Groups

### Platform
Contains subscriptions hosting shared services.

- **Identity**  
  Identity-related resources and services.

- **Connectivity**  
  Central networking (hub VNet, gateways, firewalls).

- **Management**  
  Monitoring, logging, automation, and security tooling.

### LandingZones
Subscriptions where application workloads are deployed.

- **Corp**  
  Internal, line-of-business, or regulated workloads.

- **Online**  
  Internet-facing or customer-facing workloads.

### Sandbox
Low-governance area for experimentation and learning.

- Reduced policies
- Strict cost controls
- No production workloads

## Governance Strategy

- Policies are applied at the **highest reasonable level**
- RBAC assignments follow management group boundaries
- Subscriptions inherit controls automatically

## Design Rationale
This structure balances:
- Centralized control
- Team autonomy
- Long-term scalability

It is intentionally simpler than full CAF implementations while
retaining enterprise-grade governance.
