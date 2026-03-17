# AGENTIC-IAM

AGENTIC-IAM is an optional Identity & Access foundation starter for the Agentic ecosystem. It standardizes domain language, invariants, feature seeds, ADR seeds, permission baselines, and starter-consumption guidance so downstream projects can begin from a shared IAM foundation without inheriting a fixed runtime stack.

This repository is intentionally architecture-agnostic. It does not ship backend services, frontend applications, API handlers, persistence models, authentication middleware, or enforcement code. Its purpose is to provide a reusable, documentation-first foundation that derived projects can adopt and then implement according to their own architecture and delivery constraints.

## Why This Starter Exists

Identity & Access concerns tend to drift when each project starts from scratch. AGENTIC-IAM provides a common baseline for:

- core Identity & Access terminology
- tenant-scoped authorization rules
- reusable feature framing for IAM capabilities
- ADR prompts for high-impact design choices
- starter-ready guidance for downstream adoption

Standardizing the domain first reduces ambiguity before runtime choices are made.

## What Is Included

- a reusable Identity & Access domain template centered on User, Tenant, and TenantMembership
- policy documents for tenant-scoped authorization and a baseline Permission matrix
- feature catalog seeds for common IAM capabilities
- ADR seeds for unresolved architectural and governance decisions
- descriptive starter metadata for review and publication alignment
- lightweight CI validation for repository hygiene
- an audit placeholder for pre-publish review

## What Is Intentionally Excluded

- backend or frontend runtime code
- API contracts or transport definitions
- persistence schemas or migrations
- authentication provider implementation
- stack-specific enforcement patterns
- infrastructure or deployment artifacts

AGENTIC-IAM is a domain/foundation starter, not a runtime stack starter.

## Repository Structure

```text
AGENTIC-IAM/
  app/
    README.md
  docs/
    domain-templates/
      IDENTITY-ACCESS/
        ADR-SEEDS.md
        DOMAIN-MODEL.md
        EVENTS.md
        FEATURES-CATALOG.md
    policies/
      AUTHORIZATION-PRINCIPLES.md
      PERMISSION-MATRIX.md
    starter/
      CONSUMPTION-GUIDE.md
      INSTALLATION-STRATEGY.md
      STARTER-SCOPE.md
  .github/
    workflows/
      ci.yml
    copilot-instructions.md
  AUDIT-REPORT.md
  README.md
  starter.json
  starter.manifest.yaml
```

## How To Consume It

Downstream projects should adopt this starter as a domain baseline through manual copy or subtree-style vendoring, then translate it into project-specific implementation work.

1. Copy or vendor the relevant starter files into the target repository using the guidance in [docs/starter/INSTALLATION-STRATEGY.md](docs/starter/INSTALLATION-STRATEGY.md).
2. Keep the domain language intact unless there is a deliberate, documented reason to change it.
3. Convert the feature catalog into project backlog items.
4. Promote the ADR seeds into project ADRs before implementing runtime behavior.
5. Map the baseline Permission matrix and authorization principles into the chosen enforcement model.

## Relationship To Agentic Starters And Feature Lifecycle

AGENTIC-IAM is designed to be optional. A downstream project may use it as:

- a documentation-only domain baseline
- a seed for a runtime-specific IAM starter
- a governance reference for multi-tenant authorization decisions

The feature catalog in this repository is deliberately starter-oriented. It describes reusable IAM capability seeds rather than claiming completed product features.

## Starter Metadata Notes

The starter manifest is descriptive metadata for a documentation-first foundation starter. It intentionally describes a manual-adoption model rather than implying automated installation support that is not documented by platform tooling.

## Publish Readiness Expectations

This repository is designed for official publication only under a manual-adoption model unless and until the current Agentic starter publishing process defines stronger schema-backed installation semantics for documentation-first foundation starters. The repository documentation, metadata, and CI are aligned to that narrower and defensible publication posture.
