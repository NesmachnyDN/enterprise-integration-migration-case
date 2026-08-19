# Lessons Learned

This case intentionally records generalized architectural conclusions rather than project-specific history.

## 1. Transition architecture is a real architecture state

In a large enterprise, migration may last long enough that coexistence becomes an operational state with its own availability, security, monitoring, ownership, and support requirements.

Treating it as an informal workaround hides risk. Modeling it explicitly makes the temporary state governable.

## 2. Start from deployed reality, not documentation alone

Legacy environments accumulate configuration drift, operational exceptions, and undocumented dependencies. Migration planning based only on documentation can underestimate blast radius.

A reliable migration process therefore begins with configuration verification and dependency discovery.

## 3. Do not copy legacy behavior automatically

A transparent replacement is useful only when it preserves a valid application contract. If the legacy transport contains application-specific processing, reproducing that behavior inside the new endpoint can transfer technical debt into the target architecture.

Separate those cases as application remediation.

## 4. Complexity and readiness solve different problems

Complexity estimates engineering effort and architectural difficulty. Readiness estimates whether a production migration can safely happen now.

Mixing them into one score produces poor prioritization.

## 5. Shared dependencies drive migration order

Migration waves are not simply sorted by technical difficulty. Shared endpoints, common transport components, application release calendars, and business criticality constrain sequencing.

The migration roadmap is therefore a dependency-aware planning artifact.

## 6. Rollback must be designed before cutover

A rollback plan written during an incident is not a rollback design.

The migration architecture must establish:

- rollback trigger conditions;
- the previous authoritative message path;
- restoration ownership;
- validation after restoration;
- the period during which rollback remains possible.

## 7. A pilot validates the process, not only the technology

The first migrations should test discovery quality, responsibilities, access provisioning, monitoring, runbooks, effort assumptions, and rollback mechanics.

A successful target-platform test does not prove that the migration factory is ready to scale.

## 8. Temporary compatibility needs an exit strategy

Bridges and coexistence mechanisms are useful for decoupling release schedules. They are dangerous when they acquire new consumers or lose a retirement owner.

Every temporary dependency should have an explicit exit condition and planned retirement wave.

## 9. Architecture leadership extends into delivery

Architecture decisions become real only through coordinated changes across platform engineering, operations, application teams, infrastructure, and security.

For large migration programs, the architect's role includes establishing the shared technical model, resolving cross-team dependencies, defining decision gates, and maintaining consistency between the migration plan and the target architecture.

## 10. Portfolio migration should become a learning system

Each migration produces evidence about actual complexity, hidden dependencies, effort, operational friction, and readiness criteria.

Feeding that evidence back into assessment rules makes later waves more predictable and reduces reliance on intuition.
