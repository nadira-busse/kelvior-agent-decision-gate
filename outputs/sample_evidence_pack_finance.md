# Sample Evidence Pack - Finance Invoice Assistant

## 1. Agent summary

Agent ID: AGT-FIN-INV-001  
Agent Name: Finance Invoice Assistant  
Version: 1.1  
Status: Active  
Environment: Not explicitly evidenced but in active use context  
Owner Department: DEP-FIN — Finance  
Business Owner: Finance Operations Manager  
Technical Owner: ERP Automation Lead  
Business Unit: BU-COR — Kelvior Corporate  
Business Process: P03 — Procure-to-Pay  
Systems: Dynamics 365 Business Central, MCP-ERP connector  
MCP Connectors: MCP-ERP  
Allowed Actions: Read invoice, validate invoice, create payment recommendation, update payment status (includes controlled or write-adjacent finance actions)  
Deployment Scope: Active finance workflow context; production readiness cannot be confirmed without documented production approval

## 2. Business context

The agent supports invoice-related work within Kelvior’s finance operations, specifically in the Procure-to-Pay process. It deals with purchase requests, vendor invoices, validation, payment recommendations, and vendor payment controls. Therefore, it is financially material, handling sensitive invoices, payment data, and financial workflows with potential direct payment impact.

## 3. Systems and MCP connectors

- Dynamics 365 Business Central: ERP system with financial, order, and invoice records
- MCP-ERP connector: provides system integration access to Business Central
- Microsoft Foundry and Foundry IQ platforms: are used for platform reasoning and policy knowledge grounding.

## 4. Data classification

| Data Category           | Classification            | Relevance                                                   |
| ----------------------- | ------------------------- | ----------------------------------------------------------- |
| Invoice data            | Confidential              | Contains vendor, invoice, payment info                      |
| Vendor data             | Confidential              | Supplier records, payment terms                             |
| Financial workflow data | Restricted / Confidential | Influences payments, finance operations, and audit controls |
| ERP system records      | Confidential              | Business Central contains finance and operational data      |

The agent accesses confidential and restricted financial data. A mandatory data governance review is required for production use.

## 5. Audit domain scores

Inventory (15% weight)

- All required inventory fields are present: agent ID, name, version, status, environment, owners, business unit, business process, systems, connectors, allowed actions, deployment scope.  
  Score: 100

Governance (25% weight)

- Missing or no evidence for production approval
- No evidenced human approval gate for payment-related actions
- Business owner and technical owner identified
- Accountability exists but lifecycle and escalation path controls are not fully evidenced  
  Score: 45 (reduced due to missing production approval and human approval gate for critical finance agent)

Security (25% weight)

- Security review missing or not evidenced
- Audit logging disabled or not evidenced enabled
- Monitoring disabled or not evidenced enabled
- Least privilege access not validated
- Incident response ownership missing
- Connector permission review missing  
  Score: 30 (significant gaps for critical and finance-sensitive agent)

Policy (20% weight)

- Data governance review missing for confidential and restricted data
- Missing security policy compliance evidence
- Approval procedure incomplete
- Auditability and retention policy missing or not evidenced  
  Score: 40 (missing required foundational policies for restricted/confidential finance data)

Process (15% weight)

- Process mapped to Procure-to-Pay process
- Human review points for payment actions required but not evidenced as implemented
- Exception handling not evidenced
- Re-audit required after remediation  
  Score: 50 (partial process evidence, missing exception handling and human approval enforcement)

## 6. Weighted readiness score

Raw weighted score = (100 _ 0.15) + (45 _ 0.25) + (30 _ 0.25) + (40 _ 0.20) + (50 \* 0.15)  
= 15 + 11.25 + 7.5 + 8 + 7.5  
= 49.25 ≈ 49

Final score cap implications:

- Missing production approval for active critical agent; mandatory block applies
- Missing human approval gate on finance payment actions; mandatory block applies
- Missing data governance review on restricted finance data; mandatory block applies
- Security review missing; mandatory block applies
- Audit logging missing; mandatory block applies

Therefore, score must remain low as blocking issues exist.

## 7. Mandatory blocking rule evaluation

Multiple mandatory blocking conditions triggered:

- Active production use without documented production approval
- Finance agent influencing payment workflows without human approval gate
- Confidential/restricted finance data processed without data governance review
- Security review missing for system-connected agent
- Audit logging disabled for production agent
- Incident response ownership missing for a critical finance agent

Mandatory block triggered; deployment readiness is BLOCK for production deployment.

## 8. Findings by domain

Inventory: Complete and sufficient.

Governance: Lacking production approval, no evidence of human approval gate, missing escalation and monitoring ownership.

Security: Security review missing; audit logging and monitoring disabled; no incident response owner; no least privilege validation.

Policy: Data governance review for confidential finance data missing; approval procedures incomplete; auditability controls missing.

Process: Partial evidence of process alignment; exception handling not evidenced; human review points required but not fully implemented.

## 9. Evidence references

Document ID: KEL-AGT-FIN-001  
Document title: Finance Invoice Assistant Agent Evidence  
Evidence role: Agent-specific evidence document showing agent metadata, business context, inventory, governance, security, policy, process and risk evidence for readiness assessment.  
Foundry IQ source document: 07_finance_invoice_assistant_evidence.md  
Citation or source reference: Derived evidence from YAML origin; detailed agent identity, process mapping, system and connector use, risk level, and evidence gaps.

Document ID: KEL-DAI-AIPOL-001  
Document title: Kelvior AI Policy  
Evidence role: AI governance and deployment approval policies; requirements for ownership, approval, human oversight, audit logging, monitoring, and production approval.  
Foundry IQ source document: 02_kelvior_ai_policy.md  
Citation or source reference: Policy requirements for production approval, data governance, human gates, audit logging, monitoring, and security reviews.

Document ID: KEL-DAI-DGOV-001  
Document title: Kelvior Data Governance Policy  
Evidence role: Data governance requirements for processing confidential and restricted data, approval gates, data owner assignment, review requirements.  
Foundry IQ source document: 03_kelvior_data_governance_policy.md  
Citation or source reference: Policies mandating data governance review for confidential finance data, access boundaries, auditability, retention, and re-audit triggers.

Document ID: KEL-SEC-SECPOL-001  
Document title: Kelvior Security Policy  
Evidence role: Security control requirements, including least privilege, connector permission, audit logging, monitoring, incident response, approval gates.  
Foundry IQ source document: 04_kelvior_security_policy.md  
Citation or source reference: Security requirements for system-connected finance agents; evidence on missing security review, audit logging, monitoring, and incident response ownership.

Document ID: KEL-DAI-APPROC-001  
Document title: Kelvior Agent Approval Procedure  
Evidence role: Agent approval stages, production approval evidence requirements including business and technical approval, data governance, security review, human oversight, audit logging, monitoring, incident response.  
Foundry IQ source document: 05_agent_approval_procedure.md  
Citation or source reference: Describes production approval requirements and mandatory controls for finance agents.

Document ID: KEL-RISK-EXC-001  
Document title: Kelvior Enterprise Risk Register Excerpt  
Evidence role: Risk conditions and mandatory control requirements relevant to finance agents handling confidential data.  
Foundry IQ source document: 06_enterprise_risk_register_excerpt.md  
Citation or source reference: Risks R-FIN-001, R-AUD-001, R-DATA-001, R-SEC-001, and R-GOV-001 related to missing human approval, audit logging, data governance, security review and lack of production approval.

Document ID: KEL-ENT-CTX-001  
Document title: Kelvior Enterprise Context Excerpt  
Evidence role: Business process mapping and systems landscape supporting the Procure-to-Pay context for Finance Invoice Assistant.  
Foundry IQ source document: 01_kelvior_enterprise_context_excerpt.md  
Citation or source reference: Relevant business unit, process, systems and MCP connectors context for financial workflows.

Document ID: KEL-SRC-MANIFEST-001  
Document title: Evidence Source Manifest  
Evidence role: Provides registry of evidence documents used for the audit.  
Foundry IQ source document: 00_evidence_source_manifest.md  
Citation or source reference: Index of evidence documents relevant to this assessment.

## 10. Risk assessment

Triggered risks:

- R-FIN-001: Finance automation without human approval gate (present — no human approval gate evidenced)
- R-AUD-001: Audit logging disabled for production AI agent (present — audit logging not evidenced)
- R-DATA-001: Restricted or confidential data processed without data governance review (present — data governance review missing)
- R-SEC-001: Missing security review for system-connected AI agent (present — security review missing)
- R-GOV-001: Missing production approval for active AI agent (present — production approval missing)

Mitigated or not-triggered risks:

- None (All key risks are triggered)

Not applicable risks:

- Risks related to HR data and other domains not relevant to the finance agent.

## 11. Deployment verdict

BLOCK

Rationale: Multiple mandatory blocking conditions exist for the Finance Invoice Assistant agent, including missing production approval, absent human approval gate for financially material actions, lack of data governance review for confidential financial data, missing security review, disabled audit logging, and no incident response ownership. These block production deployment readiness and require remediation before the agent can operate safely in production or production-like environments.

## 12. Required remediation plan

- Obtain full documented production approval including business, technical and data governance endorsements.
- Implement and evidence a human approval gate specifically for payment-related recommendations and status changes.
- Complete the required data governance review covering all confidential and restricted finance data sources and access boundaries.
- Conduct a comprehensive security review, including connector permission assessment, least-privilege validation, authentication and authorization model confirmation.
- Enable audit logging for all agent activities, capturing user requests, outputs, human approvals, system actions, timestamps, and responsible parties.
- Implement active monitoring of the agent for unexpected outputs, policy violations, unauthorized accesses, missing approvals, and operational exceptions.
- Assign and document a named incident response owner with an escalation path and response procedures for security or operational incidents.
- Define and document exception handling procedures and fallback mechanisms for payment process workflows.
- Schedule re-audit after remediation completion and any substantial agent changes.

## 13. Human approval checklist

- Is there a documented human approval gate for all payment-related recommendations and payment status updates? NO, remediation required.
- Are the roles, responsibilities, and approval recording mechanisms clearly defined? NO, absent in evidence.
- Is human approval enforced before the agent can perform controlled or write-capable finance actions? NO, missing.
- Is audit logging capturing human approval decisions? NO, audit logging not evidenced.
- Verification of restriction on automated payment execution without approval: NO, not evidenced.

## 14. Re-audit recommendation

A full re-audit is recommended after all required remediation actions are completed, including production approval, security review, data governance review, enabling audit logging and monitoring, and operationalizing the human approval gate for payment-related actions. This will verify that the Finance Invoice Assistant meets all Kelvior enterprise governance, security, policy, and process controls for safe production deployment.
