# Migration Readiness Checklist

Use this checklist as the production wave-entry gate for each integration.

## Discovery and ownership

- [ ] Actual deployed configuration has been verified.
- [ ] Source and target application owners are confirmed.
- [ ] All known participants are identified.
- [ ] Shared legacy endpoints, routes, and infrastructure dependencies are identified.
- [ ] Current integration behavior is documented well enough to validate equivalence after migration.

## Architecture

- [ ] Migration archetype is assigned and reviewed.
- [ ] Target message path is documented.
- [ ] Any required transition/coexistence state is documented.
- [ ] Legacy-specific application behavior is either eliminated or tracked as M4 remediation.
- [ ] The target design does not introduce a new dependency on temporary compatibility mechanisms.

## Infrastructure and access

- [ ] Target endpoint runtime is available.
- [ ] Required network connectivity is approved and tested.
- [ ] Service identities are provisioned.
- [ ] Required access groups/roles are provisioned.
- [ ] Certificates or key material are available where required.
- [ ] Capacity prerequisites have been checked for non-standard volume profiles.

## Observability and support

- [ ] Target route and endpoint expose sufficient operational diagnostics.
- [ ] Operations team knows the expected normal message path.
- [ ] Alerting or monitoring required for the migration window is available.
- [ ] Support ownership during the change window is explicit.

## Validation

- [ ] Representative test data is available.
- [ ] Technical acceptance criteria are documented.
- [ ] Business acceptance criteria are documented.
- [ ] The source-side validation method is known.
- [ ] The target-side validation method is known.
- [ ] Duplicate-delivery checks are defined where coexistence is used.

## Rollback

- [ ] Rollback trigger conditions are agreed.
- [ ] Previous authoritative route can be restored.
- [ ] Rollback ownership is assigned.
- [ ] Restoration validation is defined.
- [ ] The rollback window is known.

## Change governance

- [ ] Change window is approved.
- [ ] Required participants are available during the window.
- [ ] Configuration freeze scope is agreed.
- [ ] Go/no-go authority is explicit.
- [ ] Post-cutover acceptance owner is explicit.

## Gate result

- **READY:** all mandatory items complete.
- **CONDITIONAL:** planning may continue, but unresolved items prevent production commitment.
- **BLOCKED:** material unknowns or missing dependencies prevent reliable migration planning.
