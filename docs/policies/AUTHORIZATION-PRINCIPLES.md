# Authorization Principles

## Purpose

This policy establishes the baseline business principles for tenant-scoped authorization in AGENTIC-IAM derived projects.

## Tenant-Scoped Authorization

- Authorization is evaluated for a User within a specific Tenant.
- The relevant business relationship is TenantMembership.
- TenantRole and Permission evaluation must use the active User-Tenant pair.

## Platform-Scoped Authorization

- Platform-scoped operations are evaluated outside TenantMembership and TenantRole.
- Platform-scoped authorization requires explicit PlatformRole or an equally explicit project-defined rule.
- The baseline PlatformRole for this starter is Superadmin.
- A platform-scoped operation that targets a specific Tenant must still name that Tenant explicitly in the business flow.

## Deny-By-Default

- If Tenant context is missing, access must be denied by default.
- If TenantMembership is missing, access must be denied by default.
- If TenantMembership is invalid, access must be denied by default.
- If PlatformRole authorization is missing or invalid for a platform-scoped operation, access must be denied by default.
- If no explicit Permission baseline or project-specific rule grants an action, access must be denied by default.

## No Cross-Tenant Inheritance

- Rights granted in one Tenant do not imply rights in any other Tenant.
- TenantRole values are local to the Tenant in which they are assigned.
- Cross-tenant authorization inheritance is forbidden unless a future governance decision explicitly redefines the model.
- Superadmin does not implicitly become Owner, Admin, Member, or Viewer in any Tenant.

## Authentication And Authorization Are Separate Concerns

- Authentication establishes who the User is.
- Authorization determines what that User may do in a given Tenant.
- A successfully authenticated User is not implicitly authorized for any tenant-scoped action.
- A successfully authenticated User is not implicitly authorized for any platform-scoped action.

## Auditability Requirements

- Changes to TenantMembership should produce an AuditEvent.
- Changes to TenantRole should produce an AuditEvent.
- Ownership transfer should produce an AuditEvent.
- Assignment or revocation of Superadmin should produce an AuditEvent.
- Sensitive platform-scoped governance actions should produce an AuditEvent.
- Derived projects should define retention, access, and review expectations for AuditEvent records.

## Principle Of Least Privilege

- Users should receive only the minimum Permission set required for their role and context.
- Elevated actions should remain limited to roles that are explicitly allowed to perform them.
- Self-elevation to a higher TenantRole is forbidden.
- Platform-scoped elevation should remain limited to explicitly governed assignment flows.

## Enforcement Note

Concrete authorization enforcement mechanisms are project-specific. This repository defines the domain and policy baseline only. It does not prescribe middleware, policy engines, access-control libraries, storage models, or transport-level techniques.
