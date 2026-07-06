---
document_id: KEL-AGT-ITO-001
title: IT Ticket Triage Agent Evidence
version: "1.1"
source: Kelvior Systems Agent Definition YAML
source_file: agent_it_ticket_triage.yaml
source_type: derived_agent_evidence
derived_from_yaml: true
kb_id: KB-IT
mvp_source_set: Kelvior Agent Decision Gate Foundry IQ Source Set
physical_upload_scope: single_foundry_iq_knowledge_base
logical_kb_role: Agent-specific evidence for IT Ticket Triage deployment readiness assessment
primary_domains:
  - Inventory
  - Governance
  - Security
  - Process
secondary_domains:
  - Policy
evidence_type: agent_evidence
project: Kelvior Agent Decision Gate
intended_use: Foundry IQ grounding for AI-agent deployment readiness assessment
data_status: synthetic
confidentiality: public_demo_safe
---

# IT Ticket Triage Agent Evidence

Document ID: KEL-AGT-ITO-001  

Document title: IT Ticket Triage Agent Evidence  

Foundry IQ source document: 08_it_ticket_triage_evidence.md  

Evidence role: Agent-specific evidence for IT Ticket Triage deployment readiness assessment

## 1. Document Purpose

Evidence source: KEL-AGT-ITO-001 — 08_it_ticket_triage_evidence.md

This document provides retrieval-optimized evidence for assessing the IT Ticket Triage agent with Kelvior Agent Decision Gate.

This document is a retrieval-optimized Markdown representation derived from the source-controlled YAML agent definition. The YAML file is not uploaded to Foundry IQ as a knowledge source.

The YAML file remains the structured source-controlled agent definition. This Markdown document is the Foundry IQ retrieval representation used for evidence grounding.

This document does not include an expected verdict, test result, weighted readiness score, actual Foundry verdict or demo conclusion.

## 2. Agent Identity

| Field                 | Value            |
| --------------------- | ---------------- |
| Agent ID              | AGT-ITO-TKT-001  |
| Name                  | IT Ticket Triage |
| Version               | 1.1              |
| Status                | active           |
| Environment           | production       |
| Created date          | 2026-02-14       |
| Last reviewed         | 2026-05-28       |
| Next review due       | 2026-08-28       |
| Declared risk level   | medium           |
| Actual risk indicator | medium           |
| Business impact       | medium           |
| Operational impact    | medium           |

## 3. Agent Description

The IT Ticket Triage agent supports IT Operations by classifying incoming ServiceNow incidents, suggesting ticket priority, identifying likely assignment groups and recommending next handling steps.

The agent does not resolve tickets, close incidents, modify production systems or perform privileged actions.

The agent provides read-only incident context and recommendations. All ServiceNow record changes remain human-controlled.

## 4. Business Context

Evidence source: KEL-AGT-ITO-001 — 08_it_ticket_triage_evidence.md

| Field               | Value                                                                    |
| ------------------- | ------------------------------------------------------------------------ |
| Business unit ID    | BU-DIG                                                                   |
| Business unit name  | Kelvior Digital                                                          |
| Department ID       | DEP-ITO                                                                  |
| Department name     | IT Operations                                                            |
| Process ID          | P06                                                                      |
| Process name        | Incident-to-Recovery                                                     |
| Process owner       | IT Operations                                                            |
| Business capability | Incident triage, priority suggestion and assignment group recommendation |
| Primary user groups | Service Desk Analysts, Service Desk Lead, IT Operations team             |

The agent is active in production as an approved support agent for the Incident-to-Recovery process.

## 5. Systems and Connectors

Evidence source: KEL-AGT-ITO-001 — 08_it_ticket_triage_evidence.md

### Primary System

| System ID    | Name            | Purpose                                                        | Access Type |
| ------------ | --------------- | -------------------------------------------------------------- | ----------- |
| SYS-ITSM-001 | ServiceNow ITSM | IT service management system for incidents, changes and assets | read        |

### Supporting Systems

- ServiceNow Knowledge Base
- Microsoft 365
- SharePoint IT Operations Library

### System of Record

- ServiceNow ITSM

### MCP Connector

| Connector ID | Name                   | Target System   | Access Type              | Controlled Actions Enabled | Write Access Enabled | Production Use Approved |
| ------------ | ---------------------- | --------------- | ------------------------ | -------------------------- | -------------------- | ----------------------- |
| MCP-ITSM     | Kelvior ITSM Connector | ServiceNow ITSM | read_recommendation_only | false                      | false                | true                    |

Approval reference:

- MCP-APPROVAL-2026-ITSM-014

## 6. Knowledge Sources

| Knowledge Base ID | Name                            | Purpose                                            | Retrieval Mode     | Approved for Agent Use |
| ----------------- | ------------------------------- | -------------------------------------------------- | ------------------ | ---------------------- |
| KB-IT             | Kelvior IT Operations Knowledge | IT operations and security procedures              | SharePoint Indexed | true                   |
| KB-CORP           | Kelvior Corporate Knowledge     | Corporate governance and approval procedures       | SharePoint Indexed | true                   |
| KB-DAI            | Kelvior Data AI Knowledge       | AI governance and data governance policy retrieval | SharePoint Indexed | true                   |

## 7. Data Sources and Classification

Evidence source: KEL-AGT-ITO-001 — 08_it_ticket_triage_evidence.md

### ITSM Incident Records

| Field          | Value                                                                        |
| -------------- | ---------------------------------------------------------------------------- |
| System         | ServiceNow ITSM                                                              |
| Classification | internal                                                                     |
| Access type    | read                                                                         |
| Data entities  | incident_id, category, priority, short_description, assignment_group, status |

### IT Asset Context

| Field          | Value                                  |
| -------------- | -------------------------------------- |
| System         | ServiceNow ITSM                        |
| Classification | internal                               |
| Access type    | read                                   |
| Data entities  | asset_id, asset_type, impacted_service |

### Data Profile

| Data Type                  | Status |
| -------------------------- | ------ |
| Financial data             | false  |
| Personal data              | false  |
| Restricted data            | false  |
| HR sensitive data          | false  |
| Customer data              | false  |
| Sensitive operational data | true   |

Allowed data scope:

- incident id
- incident category
- priority
- short description
- assignment group
- incident status
- impacted service
- asset type

Prohibited data scope:

- privileged credentials
- secrets
- production system modification data
- private employee HR data
- customer confidential records
- payment or financial records

## 8. Allowed Actions

Evidence source: KEL-AGT-ITO-001 — 08_it_ticket_triage_evidence.md

| Action ID                  | Description                                                   | Action Type    | Requires Human Approval | Writes to System |
| -------------------------- | ------------------------------------------------------------- | -------------- | ----------------------- | ---------------- |
| classify_ticket            | Classify incoming incidents by category and likely routing    | recommendation | true                    | false            |
| suggest_priority           | Suggest incident priority based on available incident context | recommendation | true                    | false            |
| recommend_assignment_group | Recommend likely ServiceNow assignment group                  | recommendation | true                    | false            |
| summarize_incident_context | Summarize incident context for Service Desk review            | summary        | false                   | false            |

The agent is recommendation-only and does not write to ServiceNow.

## 9. Restricted Actions

Evidence source: KEL-AGT-ITO-001 — 08_it_ticket_triage_evidence.md

The following actions are prohibited for the IT Ticket Triage agent:

- close_ticket
- update_incident_status
- change_priority_without_review
- assign_ticket_without_review
- trigger_change_request
- access_privileged_credentials
- modify_production_system
- execute_remediation_action

These restrictions prevent autonomous incident resolution, production system modification and privileged action execution.

## 10. MCP Tools

Evidence source: KEL-AGT-ITO-001 — 08_it_ticket_triage_evidence.md

| Tool ID                       | Connector ID | Action Type    | Approved | Approval Date | Approver                   |
| ----------------------------- | ------------ | -------------- | -------- | ------------- | -------------------------- |
| ITSM.IncidentLookup           | MCP-ITSM     | read           | true     | 2026-04-12    | Security & Compliance Lead |
| ITSM.ClassificationSuggest    | MCP-ITSM     | recommendation | true     | 2026-04-12    | Security & Compliance Lead |
| ITSM.AssignmentGroupRecommend | MCP-ITSM     | recommendation | true     | 2026-04-12    | Security & Compliance Lead |

All listed MCP tools are approved and limited to read or recommendation actions.

## 11. Ownership and Accountability

Evidence source: KEL-AGT-ITO-001 — 08_it_ticket_triage_evidence.md

| Role                  | Owner                      |
| --------------------- | -------------------------- |
| Business owner        | IT Operations Manager      |
| Technical owner       | ITSM Platform Owner        |
| Deputy business owner | Service Desk Lead          |
| Executive sponsor     | Chief Information Officer  |
| Support team          | IT Operations              |
| Security contact      | Security & Compliance Lead |
| Data steward          | ITSM Data Steward          |

Accountability is defined across business ownership, technical ownership, security contact, data stewardship and operational support.

## 12. Risk and Compliance Evidence

Evidence source: KEL-AGT-ITO-001 — 08_it_ticket_triage_evidence.md

| Control                          | Status       |
| -------------------------------- | ------------ |
| Declared risk level              | medium       |
| Actual risk indicator            | medium       |
| Business impact                  | medium       |
| Operational impact               | medium       |
| GDPR assessment completed        | true         |
| Data governance review completed | true         |
| Security review completed        | true         |
| Policy exception requested       | false        |
| EU AI Act risk indicator         | limited_risk |

The agent processes internal IT operations data and sensitive operational metadata. It does not process financial data, personal data, restricted data, HR sensitive data or customer data.

## 13. Human Oversight

Evidence source: KEL-AGT-ITO-001 — 08_it_ticket_triage_evidence.md

| Control                         | Status            |
| ------------------------------- | ----------------- |
| Human approval gate             | true              |
| Human approval required         | true              |
| Escalation path defined         | true              |
| Escalation owner                | Service Desk Lead |
| Exception handling defined      | true              |
| Segregation of duties validated | true              |

Human approval is required before ticket priority, assignment group or incident status is changed in ServiceNow.

The agent only recommends. A Service Desk Analyst or IT Operations user performs the actual update.

Required approval roles:

- Service Desk Analyst
- Service Desk Lead

Human decision points:

- ticket priority change
- assignment group change
- incident status update
- major incident escalation
- security incident escalation

## 14. Deployment Controls

Evidence source: KEL-AGT-ITO-001 — 08_it_ticket_triage_evidence.md

| Control                    | Status                        |
| -------------------------- | ----------------------------- |
| Environment                | production                    |
| Deployment stage           | active                        |
| Deployment date            | 2026-04-18                    |
| Deployed by                | IT Operations                 |
| Deployment scope           | approved_production_scope     |
| Operating model            | read_only_recommendation_only |
| Production approval        | true                          |
| Formal production approval | true                          |
| Approval status            | approved                      |
| Approval reference         | CHG-2026-0418-ITSM-AI-TRIAGE  |
| Change control reference   | CHG-2026-0418-ITSM-AI-TRIAGE  |
| Last reviewed              | 2026-05-28                    |
| Next review due            | 2026-08-28                    |

Approved production safety boundaries:

- recommendation-only
- read-only MCP access
- no autonomous ServiceNow updates
- no privileged system actions

### Approved Production Scope Clarification

Evidence source: KEL-AGT-ITO-001 — 08_it_ticket_triage_evidence.md

The IT Ticket Triage Agent has full production approval for its defined IT Operations recommendation-only scope.

The deployment scope is approved production.

The operating model is read-only and recommendation-only.

The agent is not in pilot, limited production, conditional production, controlled pilot or restricted rollout.

The approved production scope includes:

- read-only ServiceNow incident retrieval
- ticket classification recommendation
- priority recommendation
- assignment group recommendation
- human-reviewed IT triage support

The recommendation-only design and mandatory human approval gate are approved production safety controls, not unresolved deployment limitations.

The human approval gate is part of the validated production operating model and does not indicate conditional approval.

Formal production approval is completed for the defined read-only, recommendation-only IT Operations scope.

There are no unresolved mandatory remediation items for the approved production scope.

There are no rollout limitations within the approved production scope.

This evidence establishes that the agent has full production approval for the defined read-only, recommendation-only IT Operations scope.

## 15. Security Controls

Evidence source: KEL-AGT-ITO-001 — 08_it_ticket_triage_evidence.md

| Control                     | Status                            |
| --------------------------- | --------------------------------- |
| Authentication required     | true                              |
| Role-based access control   | implemented                       |
| Least privilege evidenced   | true                              |
| Audit logging               | active                            |
| Audit logging enabled       | true                              |
| Audit logging status        | active                            |
| Audit logging scope         | all_recommendations_and_mcp_calls |
| Monitoring enabled          | true                              |
| Monitoring owner            | IT Operations                     |
| Incident response plan      | IRP-ITSM-AI-2026-004              |
| Incident response reference | IRP-ITSM-AI-2026-004              |
| Data retention defined      | true                              |
| Evidence retention policy   | ERPOL-ITSM-90D                    |

Logged events:

- incident_lookup
- classification_recommendation_generated
- priority_suggestion_generated
- assignment_group_recommendation_generated
- human_review_decision
- mcp_tool_execution
- retrieved_policy_sources

Missing expected events:

- none

## 16. Operational Controls

Evidence source: KEL-AGT-ITO-001 — 08_it_ticket_triage_evidence.md

| Control                            | Status            |
| ---------------------------------- | ----------------- |
| Support owner                      | IT Operations     |
| Fallback channel                   | Service Desk Lead |
| SLA defined                        | true              |
| SLA impact assessed                | true              |
| Rollback or stop procedure defined | true              |
| Workflow boundary defined          | true              |

Exception types defined:

- unclear_incident_category
- conflicting_priority_signal
- security_related_incident
- major_incident_candidate
- missing_asset_context

Escalation rules:

- security_related_incident escalates to Security Operations
- major_incident_candidate escalates to IT Operations Manager
- unclear_assignment escalates to Service Desk Lead

Known operational dependencies:

- ServiceNow incident data quality
- IT knowledge base freshness
- assignment group taxonomy accuracy
- Service Desk review capacity

## 17. Operational Notes

Evidence source: KEL-AGT-ITO-001 — 08_it_ticket_triage_evidence.md

The IT Ticket Triage agent is an active production support agent for IT Operations.

The agent is read-only and recommendation-only. These are approved production safety boundaries, not unresolved deployment limitations.

The agent does not update ServiceNow records directly and does not perform privileged, irreversible or production-changing actions.

Human review is required before any ticket priority, assignment group or status change is applied.

## 18. Known Gaps

Evidence source: KEL-AGT-ITO-001 — 08_it_ticket_triage_evidence.md

No known gaps are listed in the source YAML definition.

## 19. Readiness-Relevant Evidence Summary

Evidence source: KEL-AGT-ITO-001 — 08_it_ticket_triage_evidence.md

| Evidence Area   | Readiness Relevance                                                                                                                                 |
| --------------- | --------------------------------------------------------------------------------------------------------------------------------------------------- |
| Inventory       | Agent identity, owners, business unit, department, process, systems, MCP connector and deployment scope are defined                                 |
| Governance      | Business owner, technical owner, deputy owner, executive sponsor, approval status, production approval and review dates are defined                 |
| Security        | Security review completed, least privilege evidenced, RBAC implemented, monitoring enabled, audit logging active and incident response plan defined |
| Policy          | Data governance review completed, no policy exception requested and prohibited data scope excludes privileged, HR, customer and financial data      |
| Process         | Agent is aligned to Incident-to-Recovery, recommendation-only, human-controlled, exception handling defined and escalation path documented          |
| Deployment      | Full production approval, change control reference and approved production safety boundaries are documented                                         |
| Human oversight | Human approval gate, human decision points and segregation of duties are defined and validated                                                      |

## 20. Evidence Boundaries

Evidence source: KEL-AGT-ITO-001 — 08_it_ticket_triage_evidence.md

This document provides evidence only for IT Ticket Triage.

It does not define a final deployment verdict, weighted readiness score, test result or expected outcome.

The deployment readiness verdict must be generated by Kelvior Agent Decision Gate using this evidence together with relevant Kelvior governance, security, data, process and risk evidence.
