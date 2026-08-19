# ADR-004 — Pilot Before Migration at Scale

- **Status:** Accepted
- **Decision type:** Migration validation strategy

## Context

At the start of a large migration program, effort estimates and operational assumptions are often based on incomplete documentation and limited experience with the full production change sequence.

Scaling immediately would amplify errors in discovery, readiness criteria, runbooks, ownership, monitoring, and rollback procedures.

## Decision

Run a representative pilot before committing to large migration waves.

The pilot must validate the migration process as a whole, not only technical connectivity to the target platform.

## Pilot objectives

- verify discovery and configuration-analysis artifacts;
- validate responsibility boundaries and hand-offs;
- verify access and security provisioning lead times;
- validate monitoring and diagnostics;
- exercise the cutover runbook;
- validate rollback feasibility;
- measure actual engineering effort;
- recalibrate complexity assumptions and readiness criteria.

## Selection principles

Pilot integrations should be:

- representative enough to exercise the real process;
- well understood;
- operationally reversible;
- owned by teams able to participate actively;
- neither the simplest possible case nor a high-risk critical outlier.

## Consequences

### Positive

- early evidence replaces assumptions;
- later waves can be estimated more realistically;
- governance gaps are discovered with limited blast radius;
- reusable migration templates improve before scale-up.

### Negative

- the first wave starts later than a purely execution-driven approach;
- pilot scope must be protected from pressure to treat it as ordinary delivery;
- some pilot findings may require redesign of migration procedures.

## Exit criteria

The migration factory can scale after the pilot only when:

- the end-to-end runbook has been executed;
- readiness gates have been validated;
- operational owners accept the support model;
- rollback has been demonstrated or credibly validated;
- actual effort has been captured;
- identified process defects have owners and resolutions.
