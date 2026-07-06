# Sample Evidence Pack - IT Ticket Triage

## 1. Agent summary

| Field                 | Value            |
|-----------------------|------------------|
| Agent ID              | AGT-ITO-TKT-001  |
| Name                  | IT Ticket Triage |
| Version               | 1.1              |
| Status                | Active           |
| Environment           | Production       |
| Created date          | 2026-02-14       |
| Last reviewed         | 2026-05-28       |
| Next review due       | 2026-08-28       |
| Declared risk level   | Medium           |
| Actual risk indicator | Medium           |
| Business impact       | Medium           |
| Operational impact    | Medium           |

The IT Ticket Triage agent supports IT Operations by classifying incoming ServiceNow incidents, suggesting ticket priority, identifying likely assignment groups and recommending next handling steps. It is read-only and recommendation-only; it does not autonomously resolve tickets or modify production systems.

## 2. Business context

| Field               | Value                    |
|---------------------|--------------------------|
| Business unit ID    | BU-DIG                   |
| Business unit name  | Kelvior Digital          |
| Department ID       | DEP-ITO                  |
| Department name     | IT Operations            |
| Process ID          | P06                      |
| Process name        | Incident-to-Recovery     |
| Process owner       | IT Operations            |
| Business capability | Incident triage, priority suggestion, assignment group recommendation |
| Primary user groups | Service Desk Analysts, Service Desk Lead, IT Operations team |

Agent is aligned with IT Operations Incident-to-Recovery process providing classification and recommendation support.

## 3. Systems and MCP connectors

Primary system: ServiceNow ITSM (read-only access)  
Supporting systems: ServiceNow Knowledge Base, Microsoft 365, SharePoint IT Operations Library  
System of record: ServiceNow ITSM

MCP connector:

| Connector ID | Name                   | Target System   | Access Type              | Controlled Actions Enabled | Write Access Enabled | Production Use Approved |
|--------------|------------------------|-----------------|--------------------------|----------------------------|----------------------|-------------------------|
| MCP-ITSM     | Kelvior ITSM Connector | ServiceNow ITSM | read_recommendation_only | false                      | false                | true                    |

All MCP tools used are approved and limited to read or recommendation actions.

## 4. Data classification

| Data Type                  | Status |
|----------------------------|--------|
| Financial data             | False  |
| Personal data              | False  |
| Restricted data            | False  |
| HR sensitive data          | False  |
| Customer data              | False  |
| Sensitive operational data | True   |

Allowed data scope includes incident id, category, priority, short description, assignment group, status, impacted service, asset type.

Prohibited data scope includes privileged credentials, secrets, production system modification data, private employee HR data, customer confidential records, payment or financial records.

## 5. Audit domain scores

| Domain     | Score | Notes                                                                                     |
|------------|-------|-------------------------------------------------------------------------------------------|
| Inventory  | 100   | Complete agent identity, owners, business unit, department, process, systems, connectors |
| Governance | 95    | Business & technical owners defined, accountable, full production approval, human gate   |
| Security   | 95    | Security review completed, least privilege, RBAC, audit logging and monitoring active     |
| Policy     | 95    | Data governance review completed, complies with AI, data and security policy             |
| Process    | 95    | Clear process alignment, operational boundaries, exception handling, escalation defined  |

## 6. Weighted readiness score

Calculation:  
(Inventory 100 × 0.15) + (Governance 95 × 0.25) + (Security 95 × 0.25) + (Policy 95 × 0.20) + (Process 95 × 0.15) =  
15 + 23.75 + 23.75 + 19 + 14.25 = 95.75 ≈ 96

No domain caps apply as all controls are present with full production approval.

No final score cap applies since full production approval and no remediation is visible.

## 7. Mandatory blocking rule evaluation

No mandatory blocking conditions triggered:  
- Full production approval is evidenced.  
- Agent is read-only, recommendation-only with mandatory human approval gate.  
- Audit logging, monitoring, security review, incident response plan are complete and active.  
- No restricted confidential data processed.  
- Escalation path and exception handling are defined.  
- No write or controlled actions enabled without human approval.  

## 8. Findings by domain

Inventory: Complete agent identification and scope definition.

Governance: Strong ownership, accountability, production approval, review cadence and escalation.

Security: Complete controls including least privilege, RBAC, audit logging, monitoring, incident response assigned.

Policy: Compliant with data governance and AI policy. No policy exceptions.

Process: Fully aligned with Incident-to-Recovery process, human approval gates, exception handling, SLAs and fallback defined.

No known gaps or conditional approvals reported.

## 9. Evidence references

Document ID: KEL-AGT-ITO-001  
Document title: IT Ticket Triage Agent Evidence  
Evidence role: Agent-specific evidence for IT Ticket Triage deployment readiness assessment  
Foundry IQ source document: 08_it_ticket_triage_evidence.md  
Citation or source reference: Complete agent metadata, deployment, governance, security, policy, process and operational evidence sections.

Document ID: KEL-SRC-MANIFEST-001  
Document title: Kelvior Evidence Source Manifest  
Evidence role: Manifest listing all source documents used in assessment  
Foundry IQ source document: 00_evidence_source_manifest.md  
Citation or source reference: Document listing for evidence provenance.

Document ID: KEL-DAI-APPROC-001  
Document title: Kelvior Agent Approval Procedure  
Evidence role: Approval procedure standards for IT operations agents  
Foundry IQ source document: 05_agent_approval_procedure.md  
Citation or source reference: Passages covering IT operations agent approval and governance requirements.

Document ID: KEL-DAI-AIPOL-001  
Document title: Kelvior AI Policy  
Evidence role: Corporate AI governance and data governance policy document  
Foundry IQ source document: 02_kelvior_ai_policy.md  
Citation or source reference: Sections covering audit logging, monitoring, security, data governance and approval requirements.

Document ID: KEL-SEC-SECPOL-001  
Document title: Kelvior Security Policy  
Evidence role: Enterprise security requirements for AI agents  
Foundry IQ source document: 04_kelvior_security_policy.md  
Citation or source reference: Security requirements including least privilege, audit logging, incident response and monitoring.

Document ID: KEL-ENT-CTX-001  
Document title: Kelvior Enterprise Context Excerpt  
Evidence role: Enterprise business processes and systems landscape context  
Foundry IQ source document: 01_kelvior_enterprise_context_excerpt.md  
Citation or source reference: Business process P06 Incident-to-Recovery, IT Operations alignment, and system descriptions.

## 10. Risk assessment

Triggered risks:  
* None identified.

Mitigated or not-triggered risks:  
- Medium risk level aligned with agent data scope and use case.  
- Security review completed, audit logging and monitoring active mitigates operational risks.  
- Human approval gate prevents unauthorized write actions.  
- Data governance review completed mitigates data handling risks.

Not applicable risks:  
- Financial, HR confidential, customer personal data risks not applicable due to data scope.  
- Write-capable controlled actions risk not applicable due to read-only, recommendation-only design.

## 11. Deployment verdict

GO

## 12. Required remediation plan

No required remediation. Optional continuous improvement items only.

## 13. Human approval checklist

- Human approval gate is enabled and mandatory for all recommendations that affect ticket priority, assignment group, or incident status.  
- Approved user roles defined: Service Desk Analyst, Service Desk Lead.  
- Required human decision points confirmed and operational.  

## 14. Re-audit recommendation

Re-audit at next scheduled review interval (2026-08-28) or upon significant agent, system, or policy changes to validate continued compliance and operational effectiveness.
