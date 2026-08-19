# Migration Risk Register

This register is synthetic and intended to demonstrate the risk model used by the case.

| ID | Risk | Category | Probability | Impact | Primary treatment | Owner role | Trigger / evidence |
|---|---|---|---|---|---|---|---|
| R-01 | Deployed configuration differs from documentation | Technical | Medium | High | Verify actual configuration before architecture assessment | Migration Architect | Mismatch found during discovery |
| R-02 | Shared legacy dependency is discovered late | Architecture | Medium | High | Dependency analysis; use M2 coexistence when needed | Migration Architect | Endpoint/route used by out-of-scope interaction |
| R-03 | Legacy transport contains hidden application-specific behavior | Architecture | Medium | High | Reclassify as M4 and create remediation scope | Application Owner | Target path cannot reproduce expected business behavior without custom logic |
| R-04 | Target infrastructure is unavailable in the change window | Infrastructure | Low/Medium | High | Treat infrastructure readiness as a wave-entry gate | Infrastructure Lead | Capacity/connectivity prerequisite incomplete |
| R-05 | Identity/certificate/access provisioning is incomplete | Security | Medium | High | Track security readiness separately and block cutover | Security Lead | Mandatory security prerequisite pending |
| R-06 | Application owner or operations team is unavailable | Organizational | Medium | Medium/High | Confirm accountable participants before wave commitment | Migration Lead | Ownership/change-window confirmation missing |
| R-07 | Migration effort is underestimated | Planning | High early in program | Medium | Pilot first; capture actual effort; recalibrate estimates | Migration Lead | Actual effort materially exceeds forecast |
| R-08 | Temporary bridge becomes permanent | Architecture Debt | Medium | High | Owner + exit criterion + retirement wave for every bridge dependency | Migration Architect | Bridge dependency ages beyond planned wave |
| R-09 | Duplicate delivery occurs during coexistence | Runtime | Low | High | Single authoritative path, controlled activation, duplicate checks | Platform Team | Same business message observed on both active paths |
| R-10 | Rollback path is no longer viable at cutover time | Recoverability | Low/Medium | Critical | Revalidate rollback prerequisites immediately before cutover | Operations Lead | Legacy state changed or restoration dependency missing |
| R-11 | Integration changes while migration analysis is in progress | Change | Medium | Medium/High | Configuration freeze around cutover; reverify before execution | Application Owner | New route/configuration version appears after assessment |
| R-12 | Test data does not represent production behavior | Validation | Medium | High | Require representative technical and business validation data | Application Owner | Production issue not reproduced by pre-cutover test set |

## Risk treatment principles

1. A risk is not closed because it has a mitigation description; evidence is required.
2. Risks that invalidate an architecture assumption trigger reassessment, not only operational escalation.
3. A production change does not start with unresolved critical rollback or security risks.
4. Temporary architecture debt is measured and retired deliberately.
5. Pilot findings update the risk model for subsequent waves.
