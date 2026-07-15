---
document_id: KEL-AGT-ACD-001
title: Learning Policy Coach Agent Evidence
version: "1.1"
source: Kelvior Systems Agent Definition YAML
source_type: derived_agent_evidence
derived_from_yaml: true
foundry_iq_source_document: 09_learning_policy_coach_evidence.md
kb_id: KB-DAI
mvp_source_set: Kelvior Agent Decision Gate Foundry IQ Source Set
physical_upload_scope: single_foundry_iq_knowledge_base
logical_kb_role: Agent-specific evidence for Learning Policy Coach deployment readiness assessment, grounded through KB-DAI with conditional HR policy context from KB-HR
primary_domains:
  - Inventory
  - Governance
  - Policy
  - Process
secondary_domains:
  - Security
evidence_type: agent_evidence
project: Kelvior Agent Decision Gate
intended_use: Foundry IQ grounding for AI-agent deployment readiness assessment
data_status: synthetic
confidentiality: public_demo_safe
---

Document ID: KEL-AGT-ACD-001

Document title: Learning Policy Coach Agent Evidence

Foundry IQ source document: 09_learning_policy_coach_evidence.md

Evidence role: Agent-specific evidence for Learning Policy Coach deployment readiness assessment.

---

# Learning Policy Coach Agent Evidence

## 1. Document Purpose

This document provides retrieval-ready evidence for assessing the Learning Policy Coach agent with Kelvior Agent Decision Gate.

This document is a retrieval-ready Markdown representation derived from the source-controlled YAML agent definition. The YAML file is not uploaded to Foundry IQ as a knowledge source.

This document does not include an expected verdict, test result, weighted readiness score, actual Foundry verdict or demo conclusion.

## 2. Agent Identity

| Field                   | Value                 |
| ----------------------- | --------------------- |
| Agent ID                | AGT-ACD-LRN-001       |
| Name                    | Learning Policy Coach |
| Version                 | 1.1                   |
| Status                  | pilot                 |
| Environment             | controlled_pilot      |
| Declared risk level     | medium                |
| Actual risk indicator   | medium                |
| Business impact         | medium                |
| Learner decision impact  | advisory_only            |
| Deployment scope         | controlled_academy_pilot |
| Approval reference       | PILOT-ACD-LRN-2026-01    |
| Change control reference | CHG-ACD-LRN-2026-04      |
| Last reviewed            | 2026-05-20               |
| Next review due          | 2026-07-20               |

## 3. Agent Description

The Learning Policy Coach is a pilot AI agent that answers learning policy questions, explains course requirements and recommends learning paths for Kelvior Academy users.

The agent uses approved Academy, HR and Data & AI knowledge sources. It supports general learning, certification and policy guidance. It does not approve certification exceptions, modify training records, update employee learning status, enroll users in required training, override certification requirements or issue certificates.

## 4. Business Context

| Field               | Value                                                      |
| ------------------- | ---------------------------------------------------------- |
| Business unit ID    | BU-ACD                                                     |
| Business unit name  | Kelvior Academy                                            |
| Department ID       | DEP-ACD                                                    |
| Department name     | Academy                                                    |
| Process ID          | P08                                                        |
| Process name        | Learn-to-Certify                                           |
| Process owner       | Academy                                                    |
| Business capability | Training, certification and e-learning support             |
| Primary user groups | Kelvior employees, Academy learners, Training coordinators |

The agent operates in the Learn-to-Certify process and supports learners and training coordinators with advisory learning-path and policy guidance.

## 5. Ownership and Accountability

| Role                  | Owner                         |
| --------------------- | ----------------------------- |
| Business owner        | Academy Manager               |
| Technical owner       | Data & AI Lead                |
| Executive sponsor     | Head of Kelvior Academy       |
| Security contact      | Security & Compliance Advisor |
| Data steward          | Academy Knowledge Steward     |
| Deputy business owner | Senior Training Coordinator   |

Ownership is defined across business, technical, executive, security and data stewardship roles.

## 6. Systems and Connectors

### Primary Systems

- Moodle
- Microsoft 365

### Supporting Systems

- SharePoint

### System of Record

- Moodle

### MCP Connector

| Connector ID | Name                  | Target System | Access Type | Controlled Actions Enabled | Write Access Enabled | Production Use Approved |
| ------------ | --------------------- | ------------- | ----------- | -------------------------- | -------------------- | ----------------------- |
| MCP-LMS      | Kelvior LMS Connector | Moodle        | read_only   | false                      | false                | true                    |

Approval reference:

- MCP-LMS-APPROVAL-2026-02

The MCP-LMS connector is approved for read-only Academy agent use. Controlled actions and write access are disabled.

## 7. Knowledge Sources

| Knowledge Base ID | Name | Purpose | Retrieval Mode | Approved for Agent Use |
| --- | --- | --- | --- | --- |
| KB-PROD | Kelvior Product Academy Legal | Product, academy, legal and compliance references | SharePoint Indexed | true |
| KB-DAI | Kelvior Data AI Knowledge | AI, data governance and Foundry IQ guidance | SharePoint Indexed | true |
| KB-HR | Kelvior HR Knowledge | Employee learning policy and HR procedure references | SharePoint Indexed | conditional |

### HR Knowledge Source Conditions

KB-HR may be used only under these conditions:

- Use only for general employee learning policy questions.
- Do not expose restricted HR records or individual employee data.
- Redirect personal HR cases to Human Resources.

HR knowledge source usage requires stricter retrieval filtering before full rollout.

## 8. Data Profile and Classification

| Data Type                   | Status                |
| --------------------------- | --------------------- |
| Internal data               | true                  |
| Employee-related data       | true                  |
| Personal data               | true                  |
| Restricted data             | false                 |
| Financial data              | false                 |
| HR sensitive data           | limited               |
| Customer data               | false                 |
| Learner progress visibility | limited_metadata_only |

Allowed data scope:

- course catalogue
- certification requirements
- learning path metadata
- general enrollment status

Prohibited data scope:

- performance reviews
- medical data
- disciplinary records
- compensation data
- private HR case notes

The agent processes internal and employee-related learning metadata. Personal data is present, but restricted data is not present. HR-sensitive data is limited and must remain within approved boundaries.

## 9. Allowed Actions

| Action ID               | Description                                                                          | Action Type    | Requires Human Approval | Writes to System |
| ----------------------- | ------------------------------------------------------------------------------------ | -------------- | ----------------------- | ---------------- |
| answer_course_questions | Answer questions about course content, learning paths and certification requirements | recommendation | false                   | false            |
| recommend_learning_path | Recommend learning paths based on role, skill target and available Academy catalogue | recommendation | false                   | false            |

The agent is advisory and does not write to Moodle or employee records.

## 10. Restricted Actions

The following actions are prohibited for the Learning Policy Coach:

- approve_certification_exception
- modify_training_record
- update_employee_learning_status
- enroll_user_in_required_training
- override_certification_requirement
- issue_certificate

These restrictions prevent the agent from making formal learning, certification or employee-record decisions.

## 11. Risk and Compliance Evidence

| Control                          | Status              |
| -------------------------------- | ------------------- |
| Declared risk level              | medium              |
| Actual risk indicator            | medium              |
| Business impact                  | medium              |
| Learner decision impact          | advisory_only       |
| GDPR assessment completed        | true                |
| Data governance review completed | true                |
| Security review completed        | true                |
| EU AI Act risk indicator         | potential_high_risk |
| Policy exception required        | false               |
| Risk acceptance required         | false               |

The agent has completed GDPR, data governance and security reviews. The agent has a potential high-risk indicator under EU AI Act screening due to its employee-related learning context, but its decision impact is advisory only and it does not make formal certification or employment decisions.

## 12. Human Oversight

| Control                    | Status          |
| -------------------------- | --------------- |
| Human approval gate        | true            |
| Escalation path defined    | true            |
| Escalation owner           | Academy Manager |
| Exception handling defined | true            |

Human approval is required for:

- certification exceptions
- disputed eligibility
- mandatory training conflicts
- learner complaints
- policy interpretation conflicts

Human decision points:

- certification exception handling
- formal learner appeal
- HR-sensitive learning accommodation

### Escalation Gap

Escalation exists for standard Academy support, but certification exception routing between Academy, HR and Legal requires clearer ownership and response timing.

### Exception Handling Gap

Standard learner support exceptions are handled by Academy Operations, but certification exception ownership is not yet fully formalized across Academy, HR and Legal.

## 13. Deployment Controls

| Control                  | Status                   |
| ------------------------ | ------------------------ |
| Production approval      | conditional              |
| Approval status          | pilot_approved           |
| Approval reference       | PILOT-ACD-LRN-2026-01    |
| Deployment scope         | controlled_academy_pilot |
| Last reviewed            | 2026-05-20               |
| Next review due          | 2026-07-20               |
| Change control reference | CHG-ACD-LRN-2026-04      |

Pilot user group:

- Academy staff
- selected internal learners

Rollout limitations:

- No automatic certification decisions.
- No LMS write actions.
- No employee record changes.
- No certification exception approvals.

The agent is approved for controlled Academy pilot use, not full enterprise production expansion.

## 14. Security Controls

| Control                     | Status              |
| --------------------------- | ------------------- |
| Authentication required     | true                |
| Role-based access control   | true                |
| Least privilege evidenced   | true                |
| Audit logging               | enabled             |
| Monitoring enabled          | true                |
| AI monitoring owner         | Data & AI Lead                |
| Incident response owner     | Security & Compliance Advisor |
| Incident response plan      | defined                       |
| Incident response reference | IRP-DAI-AGENTS-2026          |
| Data retention defined      | true                |
| Retention period            | 180 days            |

Logged events:

- user_query
- retrieved_knowledge_source
- recommendation_generated
- escalation_suggested
- restricted_action_refusal

Security controls are defined for pilot use. Audit logging and monitoring are enabled.

Incident response accountability is assigned to the Security & Compliance Advisor. AI monitoring ownership is assigned to the Data & AI Lead.

## 15. Operational Controls

| Control                       | Status               |
| ----------------------------- | -------------------- |
| Support owner                 | Academy Operations   |
| Fallback channel              | Academy Support Desk |
| SLA defined                   | partially_defined    |
| User feedback enabled         | true                 |
| Model output review frequency | monthly              |
| Knowledge review frequency    | quarterly            |

Known operational dependencies:

- Moodle course catalogue quality
- Academy policy versioning
- SharePoint knowledge source freshness

SLA for learner support escalation is partially defined and requires clarification before broader rollout.

## 16. Known Gaps

The following known gaps are present:

- Certification exception escalation path requires clearer cross-department ownership.
- SLA for learner support escalation is only partially defined.
- HR knowledge source usage requires stricter retrieval filtering before full rollout.
- Pilot metrics must be reviewed before production expansion.

These gaps do not indicate that the pilot must be blocked, but they are relevant to whether the agent is ready for broader production deployment.

## 17. Recommended Next Steps

Recommended next steps from the source evidence:

- Define final escalation path for certification exceptions across Academy, HR and Legal.
- Add explicit SLA for learner support and exception handling.
- Validate HR knowledge retrieval filters for employee-related policy questions.
- Complete pilot review before expanding beyond controlled Academy user group.

## 18. Readiness-Relevant Evidence Summary

| Evidence Area   | Readiness Relevance                                                                                                                                           |
| --------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Inventory       | Agent identity, status, environment, business unit, department, process, systems and MCP connector are defined                                                |
| Governance      | Ownership roles are defined and pilot approval exists, but certification exception ownership across Academy, HR and Legal requires clarification              |
| Security        | Security review completed, authentication required, RBAC enabled, least privilege evidenced, audit logging and monitoring enabled                             |
| Policy          | Data governance and GDPR reviews completed; HR knowledge source is conditionally approved and requires stricter retrieval filtering before full rollout       |
| Process         | Agent is aligned to Learn-to-Certify and limited to advisory use; escalation and exception handling exist but need clearer cross-department ownership and SLA |
| Deployment      | Agent is pilot-approved for controlled Academy use; full expansion depends on pilot review and remediation of known gaps                                      |
| Human oversight | Human approval gate and human decision points exist for certification exceptions and HR-sensitive learning accommodations                                     |

## 19. Evidence Boundaries

This document provides evidence only for Learning Policy Coach.

It does not define a final deployment verdict, weighted readiness score, test result or expected outcome.

The deployment readiness verdict must be generated by Kelvior Agent Decision Gate using this evidence together with relevant Kelvior governance, security, data, process and risk evidence.
