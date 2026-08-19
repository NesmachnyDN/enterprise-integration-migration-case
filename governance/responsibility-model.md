# Responsibility Model

## Purpose

This model defines the minimum technical roles needed to execute an integration migration without blurring accountability between architecture, engineering, operations, application ownership, infrastructure, and security.

## Roles

### Migration Architect / Technical Lead

Accountable for:

- migration architecture;
- classification rules;
- cross-system dependency resolution;
- transition-state design;
- architecture gates;
- consistency with the target architecture;
- escalation when assumptions are invalidated.

### Platform Team

Responsible for:

- target route and integration-platform configuration;
- compatibility bridge configuration where approved;
- technical diagnostics within the platform boundary;
- platform-side cutover actions.

### Operations

Responsible for:

- operational readiness;
- production execution support;
- monitoring during the change window;
- rollback execution within the operational boundary;
- post-cutover operational acceptance.

### Application Owner / Team

Accountable for:

- business ownership of the interaction;
- application-side prerequisites;
- representative test data;
- business validation;
- application remediation when M4 applies.

### Infrastructure

Responsible for:

- runtime capacity;
- connectivity prerequisites;
- host/platform availability;
- infrastructure-side change execution.

### Security

Accountable for:

- mandatory identity and access controls;
- certificates/key prerequisites where applicable;
- required security validation;
- security acceptance criteria.

## RACI

| Activity | Migration Architect | Platform Team | Operations | Application Owner | Infrastructure | Security |
|---|---|---|---|---|---|---|
| Define discovery model | A/R | C | C | C | C | C |
| Verify current state | A | C | R | R | C | C |
| Identify dependencies | A/R | R | C | R | C | C |
| Assign migration archetype | A/R | R | C | C | C | C |
| Design transition path | A/R | R | C | C | C | C |
| Prepare platform route | C | A/R | C | C | C | C |
| Prepare application | C | C | C | A/R | C | C |
| Prepare infrastructure | C | C | C | C | A/R | C |
| Prepare security controls | C | C | C | C | C | A/R |
| Approve production readiness | A | R | R | R | R | R |
| Execute cutover | A | R | R | R | C | C |
| Technical validation | A | R | R | C | C | C |
| Business validation | C | C | C | A/R | C | C |
| Execute rollback | A | R | R | R | C | C |
| Approve legacy retirement | A | R | R | C | C | C |

Legend: **R** — Responsible, **A** — Accountable, **C** — Consulted.

## Decision rights

### Go/no-go before cutover

No-go is mandatory when:

- a critical dependency is unknown;
- mandatory security prerequisites are incomplete;
- rollback is not feasible;
- actual configuration materially differs from the assessed state;
- required owners are unavailable;
- the change would violate a target-architecture invariant.

### Rollback decision

The Migration Architect coordinates the technical decision, but rollback actions remain owned by the teams responsible for their operational domains.

### Application remediation

The Migration Architect can classify an integration as M4, but application-change scope and acceptance remain owned by the Application Owner.

## Leadership principle

The migration lead is not a substitute for every specialist role. The value of architecture leadership is to establish a common technical model, make dependencies explicit, define decision boundaries, and ensure that independently managed teams can execute one coherent transformation plan.
