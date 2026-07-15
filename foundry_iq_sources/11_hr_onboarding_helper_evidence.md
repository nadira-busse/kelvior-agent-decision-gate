---
document_id: KEL-AGT-HRO-001
title: HR Onboarding Helper Agent Evidence
version: "1.1"
source: Kelvior Systems Agent Definition YAML
source_type: derived_agent_evidence
derived_from_yaml: true
foundry_iq_source_document: 11_hr_onboarding_helper_evidence.md
agent_id: AGT-HR-ONB-001
agent_name: HR Onboarding Helper
agent_definition_version: "1.1"
kb_id: KB-DAI
related_logical_kb: KB-HR
mvp_source_set: Kelvior Agent Decision Gate Foundry IQ Source Set
physical_upload_scope: single_foundry_iq_knowledge_base
logical_kb_role: Agent-specific evidence for HR Onboarding Helper deployment readiness assessment, grounded through KB-DAI with restricted HR policy context from KB-HR
primary_domains:
  - Inventory
  - Governance
  - Security
  - Policy
  - Process
secondary_domains:
  - Risk
evidence_type: agent_evidence
project: Kelvior Agent Decision Gate
intended_use: Foundry IQ grounding for AI-agent deployment readiness assessment
data_status: synthetic
confidentiality: public_demo_safe
risk_level: high
environment: pre_production
status: planned
last_updated: 2026-06-12
---

Document ID: KEL-AGT-HRO-001  
Document title: HR Onboarding Helper Agent Evidence  
Foundry IQ source document: 11_hr_onboarding_helper_evidence.md  
Evidence role: Agent-specific evidence for HR Onboarding Helper deployment readiness assessment, grounded through KB-DAI with restricted HR policy context from KB-HR  

---

# HR Onboarding Helper Agent Evidence

## Document Metadata

Evidence source: KEL-AGT-HRO-001 — 11_hr_onboarding_helper_evidence.md

| Field                      | Value                                                                            |
| -------------------------- | -------------------------------------------------------------------------------- |
| Document ID                | KEL-AGT-HRO-001                                                                  |
| Title                      | HR Onboarding Helper Agent Evidence                                              |
| Evidence role              | Agent-specific evidence for HR Onboarding Helper deployment readiness assessment |
| Foundry IQ source document | 11_hr_onboarding_helper_evidence.md                                              |
| Source set                 | Kelvior Agent Decision Gate Foundry IQ Source Set                                |
| Project                    | Kelvior Agent Decision Gate                                                      |
| Primary logical KB         | KB-DAI                                                                           |
| Related logical KB         | KB-HR                                                                            |
| Data status                | synthetic                                                                        |
| Confidentiality            | public_demo_safe                                                                 |

---

## 1. Evidence Purpose

This document provides retrieval-ready evidence for assessing the HR Onboarding Helper agent against the Kelvior Agent Decision Gate readiness domains:

- Inventory
- Governance
- Security
- Policy
- Process
- Risk

The evidence is derived from the HR Onboarding Helper structured YAML definition and is intended for Microsoft Foundry IQ grounding. It describes the agent's identity, scope, systems, data profile, controls, missing approvals, operational limitations and known gaps.

This document does not include an expected verdict, readiness score, test result, Foundry output or portfolio conclusion.

Evidence source: KEL-AGT-HRO-001 — 11_hr_onboarding_helper_evidence.md

---

## 2. Agent Identity

| Field                    | Value                |
| ------------------------ | -------------------- |
| Agent ID                 | AGT-HR-ONB-001       |
| Agent name               | HR Onboarding Helper |
| Agent definition version | 1.1                  |
| Status                   | planned              |
| Environment              | pre_production       |
| Created date             | 2026-04-08           |
| Last reviewed            | Not completed        |
| Next review due          | 2026-06-30           |

The HR Onboarding Helper supports HR Operations by answering onboarding questions, suggesting training paths and helping new employees understand onboarding tasks, policies and required learning steps.

The agent is planned for pre-production validation and is not approved for production use.

Evidence source: KEL-AGT-HRO-001 — 11_hr_onboarding_helper_evidence.md

---

## 3. Primary User Groups

The planned primary user groups are:

- HR Operations team
- HR Service Desk
- New employees
- Hiring managers

The agent may support employee onboarding interactions, but production employee-facing use is not approved when restricted HR data is involved.

Evidence source: KEL-AGT-HRO-001 — 11_hr_onboarding_helper_evidence.md

---

## 4. Ownership and Accountability

| Role                  | Assigned owner                |
| --------------------- | ----------------------------- |
| Business owner        | HR Operations Manager         |
| Technical owner       | Data & AI Lead                |
| Deputy business owner | HR Service Lead               |
| Executive sponsor     | Chief Human Resources Officer |
| Support team          | HR Operations                 |
| Security contact      | Security & Compliance Lead    |
| Data steward          | Not assigned                  |

Ownership is partially defined. Business, technical, support and security ownership are identified, but no data steward is assigned for restricted HR data usage.

Evidence source: KEL-AGT-HRO-001 — 11_hr_onboarding_helper_evidence.md

---

## 5. Business Context and Process Alignment

| Field               | Value                                                      |
| ------------------- | ---------------------------------------------------------- |
| Business unit ID    | BU-COR                                                     |
| Business unit name  | Kelvior Corporate                                          |
| Department ID       | DEP-HR                                                     |
| Department name     | Human Resources                                            |
| Process ID          | P02                                                        |
| Process name        | Hire-to-Retire                                             |
| Process owner       | Human Resources                                            |
| Business capability | Employee onboarding support and required training guidance |

The agent supports the Hire-to-Retire process through onboarding support and required training guidance.

The operational context is pre-production validation only. The agent may retrieve restricted employee profile data and confidential training status data, so readiness depends on completed HR data governance, privacy, security, access and monitoring controls.

Evidence source: KEL-AGT-HRO-001 — 11_hr_onboarding_helper_evidence.md

---

## 6. Systems and System of Record

### Primary systems

| System ID    | System        | Purpose                                                           | Access type |
| ------------ | ------------- | ----------------------------------------------------------------- | ----------- |
| SYS-HRMS-001 | Workday       | HR system for employees, managers, onboarding and training status | read        |
| SYS-M365-001 | Microsoft 365 | HR policy retrieval and onboarding document access                | read        |

### Supporting systems

- Microsoft 365
- SharePoint HR Policy Library

### System of record

- Workday

Workday is the system of record for employee, manager, onboarding and training status data. Microsoft 365 and SharePoint HR Policy Library provide policy and onboarding document context.

Evidence source: KEL-AGT-HRO-001 — 11_hr_onboarding_helper_evidence.md

---

## 7. Knowledge Sources

| Knowledge base ID | Name                        | Purpose                                            | Retrieval mode     | Approved for agent use |
| ----------------- | --------------------------- | -------------------------------------------------- | ------------------ | ---------------------- |
| KB-HR             | Kelvior HR Knowledge        | Employee policies and HR procedures                | SharePoint Indexed | true                   |
| KB-CORP           | Kelvior Corporate Knowledge | Corporate governance and approval procedures       | SharePoint Indexed | true                   |
| KB-DAI            | Kelvior Data AI Knowledge   | AI governance and data governance policy retrieval | SharePoint Indexed | true                   |

The HR Onboarding Helper uses HR, Corporate and Data & AI knowledge sources. HR evidence is logically associated with KB-HR, while this Foundry IQ MVP source document is grounded through KB-DAI for readiness assessment consistency.

Evidence source: KEL-AGT-HRO-001 — 11_hr_onboarding_helper_evidence.md

---

## 8. MCP Connector Evidence

| Field                      | Value                  |
| -------------------------- | ---------------------- |
| Connector ID               | MCP-HR                 |
| Connector name             | Kelvior HRMS Connector |
| Target system              | Workday                |
| Connected system           | Workday                |
| Access policy              | restricted_hr_context  |
| Access type                | restricted_read        |
| Production use approved    | false                  |
| Approval reference         | Not available          |
| Controlled actions enabled | false                  |
| Write access enabled       | false                  |

### Connector objects

- employees
- managers
- onboarding_tasks
- training_status

The MCP-HR connector is restricted to HR context and is not approved for production use. It provides restricted read access only. No write access is enabled.

Evidence source: KEL-AGT-HRO-001 — 11_hr_onboarding_helper_evidence.md

---

## 9. MCP Tool Evidence

| Tool ID                  | Connector ID | Action type | Approved | Approval date | Approver      |
| ------------------------ | ------------ | ----------- | -------- | ------------- | ------------- |
| HR.EmployeeProfileLookup | MCP-HR       | read        | false    | Not available | Not available |
| HR.TrainingStatusLookup  | MCP-HR       | read        | false    | Not available | Not available |

The MCP tools for employee profile lookup and training status lookup are not approved.

Evidence source: KEL-AGT-HRO-001 — 11_hr_onboarding_helper_evidence.md

---

## 10. Allowed Actions

| Action ID                   | Description                                                           | Action type             | Requires human approval | Writes to system |
| --------------------------- | --------------------------------------------------------------------- | ----------------------- | ----------------------- | ---------------- |
| answer_onboarding_questions | Answer general onboarding questions using approved HR policy content. | retrieval_response      | false                   | false            |
| suggest_training_path       | Suggest required training path based on role and onboarding context.  | recommendation          | true                    | false            |
| explain_policy_steps        | Explain HR policy steps for onboarding and required learning.         | explanation             | false                   | false            |
| summarize_required_training | Summarize required training status for onboarding support.            | restricted_data_summary | true                    | false            |

The agent is limited to retrieval, explanation, recommendation and restricted data summarization. It does not write to Workday or other enterprise systems.

Human approval is required when recommendations or summaries use employee-specific restricted HR data or training status records.

Evidence source: KEL-AGT-HRO-001 — 11_hr_onboarding_helper_evidence.md

---

## 11. Restricted Actions

The following actions are explicitly prohibited:

- modify_employee_record
- approve_hiring_decision
- approve_employee_status_change
- change_training_completion_status
- access_compensation_data
- access_medical_or_absence_records
- provide_legal_or_disciplinary_advice
- send_personalized_hr_guidance_without_review

The agent must not make autonomous HR decisions, change HR records, access compensation data, access medical or absence records, access disciplinary records or send personalized HR guidance without human review.

Evidence source: KEL-AGT-HRO-001 — 11_hr_onboarding_helper_evidence.md

---

## 12. Data Profile

| Field                      | Value                                                                               |
| -------------------------- | ----------------------------------------------------------------------------------- |
| Data classification        | restricted_employee_profile; confidential_onboarding; confidential_training_status |
| Contains financial data    | false                                                                               |
| Contains personal data     | true                                                                                |
| Contains restricted data   | true                                                                                |
| Contains HR sensitive data | true                                                                                |
| Contains customer data     | false                                                                               |

The HR Onboarding Helper processes or retrieves personal data, restricted employee profile data, confidential onboarding data and confidential training status data.

This data profile requires strong access control, privacy assessment, data governance review, security review, audit logging, monitoring, incident response and human oversight before production deployment.

Evidence source: KEL-AGT-HRO-001 — 11_hr_onboarding_helper_evidence.md

---

## 13. Allowed Data Scope

The allowed data scope is limited to:

- employee role
- department
- manager relationship
- onboarding task status
- required training status
- approved HR policy content

The agent may only use the minimum HR data needed to answer onboarding questions, explain HR policy steps, suggest required training paths and summarize required onboarding-related training status.

Evidence source: KEL-AGT-HRO-001 — 11_hr_onboarding_helper_evidence.md

---

## 14. Prohibited Data Scope

The prohibited data scope includes:

- compensation data
- medical or absence records
- disciplinary records
- performance review notes
- private HR case notes
- immigration case details
- legal investigation records

The agent must not retrieve, summarize, infer from or provide guidance based on prohibited HR data categories.

Evidence source: KEL-AGT-HRO-001 — 11_hr_onboarding_helper_evidence.md

---

## 15. Risk and Compliance Controls

| Control or indicator             | Status              |
| -------------------------------- | ------------------- |
| Declared risk level              | high                |
| Actual risk indicator            | high                |
| Business impact                  | medium              |
| HR data impact                   | high                |
| Contains financial data          | false               |
| Contains personal data           | true                |
| Contains restricted data         | true                |
| GDPR assessment completed        | false               |
| Data governance review completed | false               |
| Security review completed        | false               |
| EU AI Act category               | Not assigned        |
| EU AI Act risk indicator         | potential_high_risk |
| Policy exception requested       | false               |
| Policy exception reference       | Not available       |

The agent has a high declared risk level because it may use restricted employee profile records, confidential onboarding records and confidential training status records.

The GDPR assessment is not completed. The data governance review is not completed. The security review is not completed. No EU AI Act category has been assigned, but the risk indicator is potential_high_risk.

Evidence source: KEL-AGT-HRO-001 — 11_hr_onboarding_helper_evidence.md

---

## 16. Human Oversight

| Field                           | Value                                                                                                                        |
| ------------------------------- | ---------------------------------------------------------------------------------------------------------------------------- |
| Human approval gate             | true                                                                                                                         |
| Human approval required         | true                                                                                                                         |
| Human approval trigger          | Required before personalized HR guidance is sent to a new employee when restricted employee data or training status is used. |
| Escalation path defined         | true                                                                                                                         |
| Escalation path                 | HR Operations Manager                                                                                                        |
| Escalation owner                | HR Operations Manager                                                                                                        |
| Exception handling defined      | false                                                                                                                        |
| Segregation of duties validated | false                                                                                                                        |

### Required approval roles

- HR Operations Manager
- HR Service Lead

Human oversight is defined for personalized HR guidance and employee-specific training recommendations. However, exception handling is not fully defined and segregation of duties has not been validated.

Evidence source: KEL-AGT-HRO-001 — 11_hr_onboarding_helper_evidence.md

---

## 17. Approval Required For

Human approval is required before:

- personalized onboarding guidance is sent to a new employee when restricted HR data is used
- required training recommendations use employee-specific records
- restricted employee profile data is summarized
- confidential training status data is summarized
- role-specific, manager-specific or department-specific policy interpretation is provided
- exception cases affect employee onboarding obligations or required training guidance

Evidence source: KEL-AGT-HRO-001 — 11_hr_onboarding_helper_evidence.md

---

## 18. Human Decision Points

The human decision points are:

- personalized onboarding guidance based on restricted HR data
- required training recommendations using employee-specific records
- exception cases involving role, manager or department-specific policy interpretation

The agent may support decision preparation but must not replace HR Operations, HR Service Desk, HR Legal or management decision-making.

Evidence source: KEL-AGT-HRO-001 — 11_hr_onboarding_helper_evidence.md

---

## 19. Escalation and Exception Handling

| Field                      | Value                 |
| -------------------------- | --------------------- |
| Escalation path defined    | true                  |
| Escalation path            | HR Operations Manager |
| Escalation owner           | HR Operations Manager |
| Exception handling defined | false                 |

The escalation path is defined through the HR Operations Manager. Exception handling is not fully defined.

Exception handling must be clarified before production use, especially for onboarding cases involving restricted employee data, policy ambiguity, role-specific training interpretation, employee status issues or manager-specific onboarding requirements.

Evidence source: KEL-AGT-HRO-001 — 11_hr_onboarding_helper_evidence.md

---

## 20. Deployment Controls

| Field                      | Value                     |
| -------------------------- | ------------------------- |
| Environment                | pre_production            |
| Deployment stage           | planned                   |
| Deployment date            | Not assigned              |
| Deployed by                | Not assigned              |
| Deployment scope           | pre_production_validation |
| Production approval        | false                     |
| Formal production approval | false                     |
| Approval status            | not_approved              |
| Approval reference         | Not available             |
| Change control reference   | Not available             |
| Last reviewed              | Not completed             |
| Next review due            | 2026-06-30                |

The agent is planned for pre-production validation only. It has no production approval, no formal production approval, no approval reference and no change control reference.

Evidence source: KEL-AGT-HRO-001 — 11_hr_onboarding_helper_evidence.md

---

## 21. Rollout Limitations

The rollout limitations are:

- no production use
- no direct employee-facing responses using restricted HR data
- no write access to Workday
- no autonomous HR decision-making

The deployment scope is limited to pre-production validation. The agent must not operate in production or provide direct employee-facing restricted HR guidance until required reviews, approvals and controls are completed.

Evidence source: KEL-AGT-HRO-001 — 11_hr_onboarding_helper_evidence.md

---

## 22. Security Controls

| Security control            | Status        |
| --------------------------- | ------------- |
| Authentication required     | true          |
| Role-based access control   | planned       |
| Least privilege evidenced   | false         |
| Audit logging               | planned       |
| Audit logging enabled       | false         |
| Audit logging status        | planned       |
| Audit logging scope         | Not defined   |
| Monitoring enabled          | false         |
| Monitoring owner            | Not assigned  |
| Incident response plan      | Not available |
| Incident response reference | Not available |
| Data retention defined      | false         |
| Evidence retention policy   | Not available |

Authentication is required, but role-based access control is only planned. Least privilege is not evidenced. Audit logging is planned but not enabled. Monitoring is disabled. No monitoring owner is assigned. No incident response plan is available. Data retention and evidence retention are not defined.

Evidence source: KEL-AGT-HRO-001 — 11_hr_onboarding_helper_evidence.md

---

## 23. Logged Events

No logged events are currently defined.

### Missing expected events

The following expected events are missing:

- employee_profile_lookup
- training_status_lookup
- onboarding_answer_generated
- human_review_decision
- restricted_data_access
- retrieved_policy_sources

The absence of logged events means restricted HR data access, employee-specific lookup activity, generated guidance, human review decisions and retrieved policy sources are not yet auditable.

Evidence source: KEL-AGT-HRO-001 — 11_hr_onboarding_helper_evidence.md

---

## 24. Operational Controls

| Operational control                | Status          |
| ---------------------------------- | --------------- |
| Support owner                      | HR Operations   |
| Fallback channel                   | HR Service Desk |
| SLA defined                        | false           |
| Rollback or stop procedure defined | true            |
| Workflow boundary defined          | partially       |

A support owner and fallback channel are defined. A rollback or stop procedure is defined. However, no SLA is defined and workflow boundaries are only partially defined.

Evidence source: KEL-AGT-HRO-001 — 11_hr_onboarding_helper_evidence.md

---

## 25. Operational Dependencies

Known operational dependencies are:

- Workday employee profile accuracy
- HR policy content quality
- training catalogue completeness
- HR Operations review capacity

The agent depends on accurate Workday employee data, complete training records, current HR policies and sufficient HR Operations review capacity.

Evidence source: KEL-AGT-HRO-001 — 11_hr_onboarding_helper_evidence.md

---

## 26. Known Gaps

The following known gaps are identified in the HR Onboarding Helper YAML definition:

- security review not completed
- data governance review not completed
- GDPR assessment not completed
- MCP-HR production use not approved
- MCP-HR tools not approved
- audit logging not implemented
- monitoring disabled
- incident response plan missing
- evidence retention policy missing
- segregation of duties not validated
- exception handling not fully defined
- no formal production approval
- no change control reference
- least privilege evidence missing
- data steward not assigned

These gaps are unresolved in the current pre-production evidence.

Evidence source: KEL-AGT-HRO-001 — 11_hr_onboarding_helper_evidence.md

---

## 27. Recommended Next Steps

Recommended readiness steps before production deployment:

- complete GDPR assessment for HR personal and restricted employee data
- complete data governance review for restricted HR data access
- complete security review for MCP-HR, Workday and Microsoft 365 access
- assign a data steward for HR data usage
- approve MCP-HR production use or keep connector disabled outside pre-production validation
- approve or reject HR.EmployeeProfileLookup and HR.TrainingStatusLookup tools
- implement and enable audit logging
- define audit logging scope for restricted HR data access and policy source retrieval
- enable monitoring and assign a monitoring owner
- define incident response plan and incident response reference
- define evidence retention policy
- validate least privilege access
- implement role-based access control
- validate segregation of duties
- define exception handling for HR policy, role-specific and employee-specific cases
- define SLA for HR support and fallback review
- define full workflow boundaries
- obtain formal production approval before any production or employee-facing restricted-data use
- create change control reference before deployment

Evidence source: KEL-AGT-HRO-001 — 11_hr_onboarding_helper_evidence.md

---

## 28. Evidence Interpretation Guidance for Assessment

For readiness assessment, interpret this document as follows:

- The agent is planned and pre-production only.
- The agent is not approved for production.
- The agent has high risk because it may use restricted employee profile data, confidential onboarding data and confidential training status data.
- Workday is the system of record for employee and onboarding data.
- MCP-HR provides restricted HR context but is not approved for production use.
- MCP-HR tools are not approved.
- The agent has no write access and must not perform autonomous HR decisions.
- Human approval is required for personalized HR guidance or employee-specific training recommendations.
- Direct employee-facing responses using restricted HR data are not allowed under current rollout limitations.
- Data governance review, GDPR assessment and security review are not completed.
- Audit logging is planned but not enabled.
- Monitoring is disabled.
- No incident response plan is available.
- No evidence retention policy is defined.
- Role-based access control is planned but not implemented.
- Least privilege is not evidenced.
- Segregation of duties is not validated.
- Exception handling is not fully defined.
- Formal production approval and change control reference are missing.

This evidence should be used to assess deployment readiness across governance, security, policy, process and risk domains without relying on expected verdicts, previous test results or score assumptions.

Evidence source: KEL-AGT-HRO-001 — 11_hr_onboarding_helper_evidence.md
