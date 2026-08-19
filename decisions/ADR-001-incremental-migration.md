# ADR-001 — Incremental Migration over Big-Bang Replacement

- **Status:** Accepted
- **Decision type:** Transformation strategy

## Context

The legacy integration landscape contains many business-critical interactions owned by different application teams. Participants have independent release calendars, some endpoint components are shared, and actual configuration can differ from documentation.

A single enterprise-wide cutover would create a large blast radius, require simultaneous readiness across unrelated teams, and make rollback operationally difficult.

## Decision

Migrate integrations incrementally in controlled waves rather than replacing the legacy platform in one big-bang event.

Each integration must pass through discovery, architecture assessment, readiness evaluation, cutover, validation, and acceptance before its legacy dependency can be retired.

## Consequences

### Positive

- smaller blast radius per change;
- feedback from early migrations improves later waves;
- independent application schedules can be accommodated;
- rollback remains bounded to a smaller scope;
- risk becomes visible at integration level.

### Negative

- legacy and target platforms coexist for a period;
- transition architecture must be operated and monitored;
- migration governance becomes more important;
- total calendar duration can be longer than a hypothetical coordinated cutover.

## Guardrails

- no new business integration may be implemented on the legacy platform;
- every migrated integration must have explicit acceptance criteria;
- temporary coexistence must have an exit plan;
- migration sequencing must be dependency-aware rather than first-come-first-served.
