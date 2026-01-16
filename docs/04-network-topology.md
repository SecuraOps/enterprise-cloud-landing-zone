# Network Topology

## Objective
Provide a **secure, scalable, and inspectable network foundation**
for all Azure workloads.

## Topology Overview
The landing zone uses a **Hub-and-Spoke** network model.

```java
       On-Premises
            |
       VPN / ExpressRoute
            |
        Hub VNet
    (Shared Services)
      /            \
 Spoke VNet     Spoke VNet
 (Corp)         (Online)
```


## Hub Network
The hub contains shared connectivity components:
- VPN / ExpressRoute Gateway
- Azure Firewall or NVA (conceptual)
- DNS services
- Shared jump or management services

The hub is managed centrally by the platform team.

## Spoke Networks
Spokes host application workloads:
- Isolated per environment or workload
- No direct connectivity between spokes by default
- Connected to hub via VNet peering

## Traffic Flow Principles
- North–South traffic flows via the hub
- East–West traffic is restricted and controlled
- Internet egress is inspected centrally (conceptual)

## Addressing Strategy
- Non-overlapping CIDR ranges
- Planned for future expansion
- Aligned with on-premises addressing if applicable

## Security Controls
- Network Security Groups (NSGs)
- User Defined Routes (UDRs)
- Centralized inspection (when required)

## Design Rationale
The hub-and-spoke model:
- Scales well across teams and subscriptions
- Enables centralized security controls
- Supports hybrid connectivity

## Out of Scope
- Detailed firewall rule sets
- Application-level networking
- Service mesh implementations
