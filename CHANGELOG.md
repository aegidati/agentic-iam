# Changelog

All notable changes to AGENTIC-IAM should be documented in this file.

## 0.1.0 - 2026-03-17

Initial publishable release of AGENTIC-IAM as a documentation-first, architecture-agnostic Identity & Access foundation starter for the Agentic ecosystem.

### Added

- root repository positioning and publish-readiness guidance in README.md
- reusable Identity & Access domain template covering User, Tenant, TenantMembership, TenantRole, Permission, and AuditEvent
- reusable features catalog for IAM capability planning
- ADR seed set for unresolved identity, authorization, ownership, lifecycle, and audit decisions
- domain event sequences for membership, role, and ownership workflows
- tenant-scoped authorization principles and baseline Permission matrix
- starter scope, installation strategy, and consumption guidance for downstream projects
- audit placeholder and lightweight CI validation for documentation-first repository integrity
- repository guardrails for preserving architecture agnosticism and terminology consistency

### Publication Posture

- published as a manual-adoption foundation starter
- does not claim automated installation semantics
- does not ship runtime backend, frontend, or infrastructure code
- intended to be copied or vendored into downstream projects and translated into project-specific implementation work

### Notes For Consumers

- adopt the starter documentation before implementing runtime-specific IAM behavior
- preserve the canonical terminology unless a deliberate ADR records a change
- resolve project-specific decisions for tenant context, authentication approach, ownership transfer, and AuditEvent persistence before implementation
