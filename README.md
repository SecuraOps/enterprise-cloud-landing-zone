# enterprise-cloud-landing-zone

A landing zone is:
> “A secure, scalable, multi-account cloud foundation designed for enterprises and regulated environments.”

## Purpose
This repository provides a **reference Azure cloud landing zone** designed for
enterprises and regulated environments.

It focuses on **architecture, governance, security, and scalability**, not on
application workloads.

## Target Audience
- Enterprise architects
- Cloud & platform engineers
- Security and governance teams
- Consulting & advisory contexts

## Design Principles
- Security by default
- Least privilege
- Environment isolation
- Auditability
- Cost awareness

## Scope
Included:
- Management Group hierarchy
- Identity & access model
- Network topology (Hub & Spoke)
- Security baseline
- Centralized logging
- Terraform-based implementation examples

Excluded (by design):
- Application workloads
- CI/CD pipelines for applications
- Customer-specific configurations
- Full Microsoft CAF parity

## Disclaimer
This repository provides **reference architectures and example implementations**.
It is **not intended for direct production use without adaptation, review, and validation**.

## License
Apache License 2.0

