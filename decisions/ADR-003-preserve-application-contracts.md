# ADR-003 — Preserve Application Contracts Where Reasonable

- **Status:** Accepted
- **Decision type:** Application boundary

## Context

The legacy transport may expose file locations, message conventions, acknowledgements, packaging rules, and other behaviors that applications implicitly treat as part of their integration contract.

Changing every application during transport migration would dramatically enlarge scope. Conversely, blindly reproducing all legacy behavior inside the new endpoint would transfer technical debt into the target architecture.

## Decision

Preserve existing application-facing integration contracts when they represent valid transport concerns and can be supported without compromising target architecture principles.

When legacy behavior is application-specific, obsolete, or would make the new endpoint agent stateful and complex, classify the interaction as **M4 — Application Remediation** and change it explicitly.

## Consequences

### Positive

- keeps standard migrations bounded;
- reduces unnecessary application releases;
- protects the target endpoint from becoming a clone of the legacy platform;
- makes modernization debt explicit instead of hiding it.

### Negative

- some integrations require separate remediation projects or backlog items;
- migration sequencing becomes dependent on application changes for M4 cases;
- architecture assessment must distinguish true transport behavior from application behavior.

## Guardrails

The lightweight integration agent must not accumulate:

- business-specific transformation logic;
- application-specific orchestration;
- undocumented routing rules;
- long-lived business state;
- compatibility behavior that should belong to the application or integration platform.
