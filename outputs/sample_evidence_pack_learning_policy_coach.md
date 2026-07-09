# Sample Evidence Pack — Learning Policy Coach

## 1. Agent summary

| Field                    | Value                    |
| ------------------------ | ------------------------ |
| Agent ID                 | AGT-ACD-LRN-001          |
| Name                     | Learning Policy Coach    |
| Version                  | 1.0                      |
| Status                   | pilot                    |
| Environment              | controlled_pilot         |
| Declared Risk Level      | medium                   |
| Actual Risk Indicator    | medium                   |
| Business Impact          | medium                   |
| Learner Decision Impact  | advisory_only            |
| Deployment Scope         | controlled_academy_pilot |
| Approval Reference       | PILOT-ACD-LRN-2026-01    |
| Change Control Reference | CHG-ACD-LRN-2026-04      |
| Last Reviewed            | 2026-05-20               |
| Next Review Due          | 2026-07-20               |

The Learning Policy Coach answers learning policy questions, explains course requirements and recommends learning paths for Kelvior Academy users.

It uses approved Academy, HR and Data & AI knowledge sources. It does not make formal certification exceptions or modify records.

---

## 2. Business context

| Field            | Value                    |
| ---------------- | ------------------------ |
| Business unit    | BU-ACD — Kelvior Academy |
| Department       | DEP-ACD — Academy        |
| Business process | Learn-to-Certify         |
| Deployment model | Controlled Academy pilot |
| Decision impact  | Advisory only            |

The agent supports the Learn-to-Certify process within Kelvior Academy for training and certification workflows.

Its impact on learner decisions is advisory only. It does not make formal changes to employee records, certification status or learning records.

---

## 3. Systems and MCP connectors

The Learning Policy Coach uses Academy, HR and Data & AI knowledge sources approved for pilot use.

No system write actions are permitted.

The agent provides recommendations and explanations only. It cannot make system changes.

MCP connectors and system integrations are defined but controlled for advisory scope.

---

## 4. Data classification

| Data / control area                     | Status                 |
| --------------------------------------- | ---------------------- |
| Academy learning and certification data | In scope               |
| HR data                                 | Conditionally approved |
| GDPR assessment                         | Completed and positive |
| Data governance review                  | Completed              |
| Security review                         | Completed              |
| EU AI Act risk indicator                | potential_high_risk    |
| Learner decision impact                 | advisory_only          |

The HR knowledge source is conditionally approved and requires stricter retrieval filtering before full rollout.

The agent operates in an employee-related learning context. This creates sensitivity around HR-linked learning information, but the assessed decision impact remains advisory only.

---

## 5. Audit domain scores

| Domain     | Score | Notes                                                                                                                                                                       |
| ---------- | ----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Inventory  |   100 | Complete agent identity, ownership, environment, business unit, process and connector details.                                                                              |
| Governance |    80 | Pilot approval exists and ownership is defined. Some escalation and exception ownership gaps require clarification across Academy, HR and Legal.                            |
| Security   |    85 | Security review completed. RBAC, least privilege, audit logging, monitoring and incident response owner are assigned.                                                       |
| Policy     |    82 | AI, data governance and GDPR reviews are completed. HR knowledge source is conditionally approved and requires stronger retrieval controls before production expansion.     |
| Process    |    78 | Process alignment is clear with Learn-to-Certify. Advisory use is limited. Exception handling and escalation are defined, but cross-department SLA clarity is still needed. |

---

## 6. Weighted readiness score

| Domain     | Score | Weight | Weighted contribution |
| ---------- | ----: | -----: | --------------------: |
| Inventory  |   100 |    15% |                 15.00 |
| Governance |    80 |    25% |                 20.00 |
| Security   |    85 |    25% |                 21.25 |
| Policy     |    82 |    20% |                 16.40 |
| Process    |    78 |    15% |                 11.70 |

Calculated weighted readiness score:

```text
15 + 20 + 21.25 + 16.4 + 11.7 = 84.35 ≈ 84
```

Final score cap: because the agent is in controlled pilot scope with conditional pilot approval, a final score cap of maximum 84 applies.

| Score stage                                          | Value |
| ---------------------------------------------------- | ----: |
| Calculated weighted readiness score before final cap |    84 |
| Final weighted readiness score after cap             |    84 |

---

## 7. Mandatory blocking rule evaluation

No mandatory blocking rule is triggered for the assessed pilot scope.

| Control                | Assessment                                                                                           |
| ---------------------- | ---------------------------------------------------------------------------------------------------- |
| Data governance review | Completed for the assessed pilot scope.                                                              |
| Security review        | Completed with audit logging and monitoring active.                                                  |
| Human approval gates   | Present for learning certification exception scenarios requiring human decision points.              |
| Production approval    | Pilot-level approval is in place and consistent with the controlled pilot environment.               |
| Escalation path        | Exists, but certification exception ownership across Academy, HR and Legal needs clearer definition. |

The escalation ownership gap is a governance finding. It does not trigger a mandatory block for the controlled pilot scope.

---

## 8. Findings by domain

### Inventory

Inventory is complete.

### Governance

Pilot approval is in place.

Certification exception ownership and escalation across Academy, HR and Legal require clarification.

Full production approval is not present, which is expected for the current pilot scope.

### Security

Controls are in place and consistent with the medium-risk pilot scope.

Audit logging, monitoring and security review are complete.

### Policy

HR knowledge source usage requires stronger retrieval filtering before full rollout.

This is acceptable for the monitored pilot scope but remains a condition before broader deployment.

### Process

Escalation and exception handling are defined.

Clearer SLA expectations and cross-department exception ownership are needed before production expansion.

---

## 9. Evidence references

### KEL-AGT-ACD-001

| Field                        | Value                                                                                                                                                                    |
| ---------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Document title               | Learning Policy Coach Agent Evidence                                                                                                                                     |
| Evidence role                | Derived evidence representation of the YAML source of truth.                                                                                                             |
| Foundry IQ source document   | 09_learning_policy_coach_evidence.md                                                                                                                                     |
| Citation or source reference | Agent identity, environment, risk level, business context, approval references, governance and policy controls, security and process controls for Learning Policy Coach. |

### KEL-ENT-CTX-001

| Field                        | Value                                                                                                                                |
| ---------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| Document title               | Kelvior Enterprise Context Excerpt                                                                                                   |
| Evidence role                | Enterprise context for business unit, department, process mapping, system and connector scopes.                                      |
| Foundry IQ source document   | 01_kelvior_enterprise_context_excerpt.md                                                                                             |
| Citation or source reference | Context of Kelvior Academy, Data & AI, Security & Compliance and IT Operations that support agent environment and process alignment. |

### KEL-DAI-AIPOL-001

| Field                        | Value                                                                                                    |
| ---------------------------- | -------------------------------------------------------------------------------------------------------- |
| Document title               | Kelvior AI Policy                                                                                        |
| Evidence role                | AI governance and policy baseline for inventory, governance, security, policy and process assessment.    |
| Foundry IQ source document   | 02_kelvior_ai_policy.md                                                                                  |
| Citation or source reference | Requirements for approval, ownership, production readiness, human approval gate and risk classification. |

### KEL-DAI-DGOV-001

| Field                        | Value                                                                                                 |
| ---------------------------- | ----------------------------------------------------------------------------------------------------- |
| Document title               | Kelvior Data Governance Policy                                                                        |
| Evidence role                | Data governance requirements and controls for agents handling confidential, restricted or HR data.    |
| Foundry IQ source document   | 03_kelvior_data_governance_policy.md                                                                  |
| Citation or source reference | Data governance review requirement for restricted data and HR data used by the Learning Policy Coach. |

### KEL-SEC-SECPOL-001

| Field                        | Value                                                                                                               |
| ---------------------------- | ------------------------------------------------------------------------------------------------------------------- |
| Document title               | Kelvior Security Policy                                                                                             |
| Evidence role                | Security controls including review, audit logging, monitoring and incident response.                                |
| Foundry IQ source document   | 04_kelvior_security_policy.md                                                                                       |
| Citation or source reference | Security requirements met for the Learning Policy Coach, including least privilege and incident response ownership. |

### KEL-DAI-APPROC-001

| Field                        | Value                                                                                                    |
| ---------------------------- | -------------------------------------------------------------------------------------------------------- |
| Document title               | Kelvior Agent Approval Procedure                                                                         |
| Evidence role                | Agent approval stages including pilot, conditional production and full production approval requirements. |
| Foundry IQ source document   | 05_agent_approval_procedure.md                                                                           |
| Citation or source reference | Pilot approval process evidenced for controlled Academy pilot deployment.                                |

### KEL-RISK-EXC-001

| Field                        | Value                                                                                                     |
| ---------------------------- | --------------------------------------------------------------------------------------------------------- |
| Document title               | Kelvior Enterprise Risk Register Excerpt                                                                  |
| Evidence role                | Risk conditions and controls relevant to governance, security, policy and process for AI agents.          |
| Foundry IQ source document   | 06_enterprise_risk_register_excerpt.md                                                                    |
| Citation or source reference | Risk IDs and conditions considered in readiness assessment, including no triggered mandatory block risks. |

---

## 10. Risk assessment

### Triggered risks

None identified.

### Mitigated or not-triggered risks

| Risk area                                                  | Assessment                                                                                         |
| ---------------------------------------------------------- | -------------------------------------------------------------------------------------------------- |
| Governance risks from missing production approval          | Mitigated by pilot approval status supporting the current controlled pilot scope.                  |
| Security risks related to access, logging and monitoring   | Mitigated by completed security reviews and controls.                                              |
| Policy risks related to HR data management                 | Mitigated by data governance review and GDPR assessment.                                           |
| Process risks related to escalation and exception handling | Mitigated by established processes, although some operational clarity is needed before production. |

### Not applicable risks

| Risk area                  | Assessment                                                                                |
| -------------------------- | ----------------------------------------------------------------------------------------- |
| Finance and payment risks  | Not applicable. The agent does not handle financial data or controlled payment workflows. |
| Write-capable action risks | Not applicable. The agent is advisory-only with no system write permissions.              |

---

## 11. Deployment verdict

```text
CONDITIONAL GO
```

The Learning Policy Coach is in pilot status with controlled pilot deployment scope.

Inventory, security and foundational policy controls are complete, including data governance and GDPR assessment.

Governance controls are adequate for pilot approval, although full production approval and clearer cross-department escalation and exception ownership are required for broader rollout.

Process controls are largely defined but require SLA and exception ownership clarifications.

No mandatory blocking controls are triggered for the assessed pilot scope.

The overall readiness score of 84 aligns with controlled pilot conditional approval.

---

## 12. Required remediation plan

- Clarify and formalize cross-department ownership and escalation responsibilities for certification exceptions involving Academy, HR and Legal.
- Implement stricter retrieval filtering for HR knowledge sources before full production rollout.
- Define and document clear Service Level Agreements for exception handling and escalation timing.
- Continue pilot monitoring, sampling review and operational readiness validation before expanding deployment beyond pilot scope.
- Prepare for full production approval by resolving operational control gaps and governance clarity.

---

## 13. Human approval checklist

- Human approval gate is implemented for certification exceptions, disputed eligibility, mandatory training conflicts, learner complaints and policy interpretation conflicts.
- Escalation path is defined with assigned escalation owner: Academy Manager.
- Cross-department escalation roles still require clarification.
- Exception handling procedures are in place for learner support scenarios.
- Certification exception operational ownership still needs formalization.

---

## 14. Re-audit recommendation

Re-audit is recommended before transition from controlled pilot to full production deployment.

The re-audit should verify remediation completion for:

- governance clarity;
- operational SLAs;
- HR knowledge-source controls;
- confirmed full production approval.

Continued monitoring and sampling review during pilot deployment are recommended to confirm control effectiveness.
