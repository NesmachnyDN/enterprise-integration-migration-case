# ADR-002 — Temporary Hybrid Coexistence

- **Status:** Accepted
- **Decision type:** Transition architecture

## Context

Some integrations share legacy endpoint or routing components, while the participating applications cannot be migrated in the same maintenance window. A strict direct-cutover-only strategy would either block progress or force unrelated teams into synchronized releases.

## Decision

Allow a controlled compatibility bridge between the legacy messaging platform and the target enterprise integration platform for integrations that cannot migrate atomically.

The bridge is a transition mechanism, not a target capability.

## Consequences

### Positive

- decouples application migration schedules;
- allows incremental retirement of legacy participants;
- avoids unnecessary big-bang coordination;
- supports dependency-aware wave planning.

### Negative

- increases temporary architecture complexity;
- introduces additional monitoring and failure modes;
- creates a risk of duplicate or ambiguous message paths;
- can become permanent technical debt if not governed.

## Guardrails

- each bridged interaction has one authoritative active route;
- duplicate business delivery must be prevented;
- the bridge must preserve required transport semantics;
- no new integration may choose the bridge as its normal target design;
- every bridge dependency must have an owner, exit condition, and planned retirement wave;
- bridge usage is monitored as transition debt.
