---
document_id: KEL-AGT-SAL-001
title: Sales Proposal Agent Evidence
version: "1.1"
source: Kelvior Systems Agent Definition YAML
source_type: derived_agent_evidence
derived_from_yaml: true
foundry_iq_source_document: 10_sales_proposal_agent_evidence.md
agent_id: AGT-SAL-PRO-001
agent_name: Sales Proposal Agent
kb_id: KB-DAI
mvp_source_set: Kelvior Agent Decision Gate Foundry IQ Source Set
physical_upload_scope: single_foundry_iq_knowledge_base
logical_kb_role: Agent-specific evidence for Sales Proposal Agent deployment readiness assessment, grounded through KB-DAI with supporting commercial, product, legal and corporate policy context from KB-PROD and KB-CORP
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
business_unit: BU-OUT
department: DEP-SAL
process_id: P04
process_name: Order-to-Cash
data_classification: internal, confidential_commercial, customer_related
risk_level: medium
environment: limited_production
status: active
last_updated: 2026-06-12
---

Document ID: KEL-AGT-SAL-001

Document title: Sales Proposal Agent Evidence

Foundry IQ source document: 10_sales_proposal_agent_evidence.md

Evidence role: Agent-specific evidence for Sales Proposal Agent deployment readiness assessment.

---

# Sales Proposal Agent Deployment Readiness Evidence

## 1. Evidence purpose

This document provides retrieval-ready evidence for assessing the Sales Proposal Agent through Kelvior Agent Decision Gate.

This document is a derived evidence representation of the YAML source of truth. It is intended for Foundry IQ retrieval and enterprise deployment readiness assessment.

This document does not contain expected verdicts, test results, weighted scores or prior Foundry assessment outcomes.

## 2. Agent identity

| Field                    | Value                                                                                                                   |
| ------------------------ | ----------------------------------------------------------------------------------------------------------------------- |
| Agent ID                 | AGT-SAL-PRO-001                                                                                                         |
| Agent name               | Sales Proposal Agent                                                                                                    |
| Description              | Active AI agent that retrieves approved customer and product context and drafts sales proposal content for Sales teams. |
| Status                   | active                                                                                                                  |
| Environment              | limited_production                                                                                                     |
| Version                  | 1.1                                                                                                                     |
| Business unit ID         | BU-OUT                                                                                                                  |
| Business unit name       | Kelvior Outdoor                                                                                                         |
| Department ID            | DEP-SAL                                                                                                                 |
| Department name          | Sales                                                                                                                   |
| Process ID               | P04                                                                                                                     |
| Process name             | Order-to-Cash                                                                                                           |
| Process owner            | Sales and Finance                                                                                                       |
| Business capability      | Sales proposal preparation and customer opportunity support                                                             |
| Deployment scope         | sales_team_limited_production                                                                                           |
| Approval status          | limited_production_approved                                                                                             |
| Approval reference       | PROD-SAL-PRO-2026-03                                                                                                    |
| Change control reference | CHG-SAL-PRO-2026-05                                                                                                     |
| Last reviewed            | 2026-05-25                                                                                                              |
| Next review due          | 2026-07-25                                                                                                              |

## 3. Primary user groups

| User group                    |
| ----------------------------- |
| Sales representatives         |
| Account managers              |
| Sales operations coordinators |

## 4. Ownership and accountability

| Role                    | Owner                         |
| ----------------------- | ----------------------------- |
| Business owner          | Sales Director                |
| Technical owner         | Data & AI Lead                |
| Executive sponsor       | Commercial Director           |
| Security contact        | Security & Compliance Advisor |
| Data steward            | Sales Operations Data Steward |
| Deputy business owner   | Sales Operations Manager      |
| Escalation owner        | Sales Operations Manager      |
| Monitoring owner        | Data & AI Lead                |
| Incident response owner | Security & Compliance Advisor |
| Support owner           | Sales Operations              |

## 5. Systems and system of record

| System type       | System             |
| ----------------- | ------------------ |
| Primary system    | Dynamics 365 Sales |
| Primary system    | Microsoft 365      |
| Supporting system | SharePoint         |
| System of record  | Dynamics 365 Sales |

The Sales Proposal Agent retrieves approved customer, lead and opportunity context from Dynamics 365 Sales. The agent supports proposal drafting but does not update CRM records.

## 6. Knowledge sources

| Knowledge Base ID | Name                                    | Purpose                                          | Retrieval Mode     | Approved for Agent Use |
| ----------------- | --------------------------------------- | ------------------------------------------------ | ------------------ | ---------------------- |
| KB-CORP           | Kelvior Corporate Knowledge             | Corporate policies, strategy and governance      | SharePoint Indexed | true                   |
| KB-PROD           | Kelvior Product Academy Legal Knowledge | Product, academy, legal and compliance documents | SharePoint Indexed | true                   |
| KB-DAI            | Kelvior Data AI Knowledge               | AI, data governance and Foundry IQ guidance      | SharePoint Indexed | true                   |

The agent-specific evidence is grounded through KB-DAI. Product, legal, proposal and commercial references are supported through KB-PROD. Corporate governance and policy context is supported through KB-CORP.

## 7. MCP connector evidence

| Field                      | Value                           |
| -------------------------- | ------------------------------- |
| Connector ID               | MCP-CRM                         |
| Connector name             | Kelvior CRM Connector           |
| Target system              | Dynamics 365 Sales              |
| Objects                    | customers, leads, opportunities |
| Access policy              | read-only for agent queries     |
| Production use approved    | true                            |
| Approval reference         | MCP-CRM-APPROVAL-2026-01        |
| Access type                | read_only                       |
| Controlled actions enabled | false                           |
| Write access enabled       | false                           |

The MCP-CRM connector is approved for read-only agent queries. The connector does not enable write actions or controlled CRM updates for this agent.

## 8. Allowed actions

| Action ID                 | Description                                                                                  | Action type      | Requires human approval | Writes to system |
| ------------------------- | -------------------------------------------------------------------------------------------- | ---------------- | ----------------------- | ---------------- |
| retrieve_customer_context | Retrieve approved customer, lead and opportunity context from Dynamics 365 Sales.            | retrieval        | false                   | false            |
| draft_sales_proposal      | Draft proposal text using approved customer context, product information and sales guidance. | content_drafting | true                    | false            |

The Sales Proposal Agent may retrieve approved sales context and draft proposal content. Drafted proposal content requires human review before customer-facing use.

## 9. Restricted actions

| Restricted action         |
| ------------------------- |
| approve_discount          |
| change_pricing            |
| modify_opportunity_stage  |
| create_binding_offer      |
| send_proposal_to_customer |
| update_customer_record    |
| commit_delivery_timeline  |
| approve_contract_terms    |
| accept_customer_order     |

The Sales Proposal Agent must not approve discounts, change pricing, modify opportunity stages, create binding offers, send proposals to customers, update customer records, commit delivery timelines, approve contract terms or accept customer orders.

## 10. Data profile

| Field                      | Value                                               |
| -------------------------- | --------------------------------------------------- |
| Data classification        | internal, confidential_commercial, customer_related |
| Contains personal data     | true                                                |
| Contains restricted data   | false                                               |
| Contains financial data    | limited                                             |
| Contains HR sensitive data | false                                               |
| Contains customer data     | true                                                |
| Contains contractual data  | limited                                             |

## 11. Allowed data scope

| Allowed data                           |
| -------------------------------------- |
| customer account summary               |
| lead context                           |
| opportunity metadata                   |
| approved product descriptions          |
| approved proposal templates            |
| non-binding commercial recommendations |

## 12. Prohibited data scope

| Prohibited data                         |
| --------------------------------------- |
| payment details                         |
| private customer notes                  |
| unapproved discount logic               |
| confidential contract negotiation notes |
| legal commitments                       |
| binding offer approval                  |

The Sales Proposal Agent is limited to approved sales, customer, opportunity and product context. The agent must not use payment details, private customer notes, unapproved discount logic, confidential contract negotiation notes, legal commitments or binding offer approval data.

## 13. Risk and compliance controls

| Field                            | Value               |
| -------------------------------- | ------------------- |
| Declared risk level              | medium              |
| Actual risk indicator            | medium              |
| Business impact                  | medium              |
| Customer impact                  | medium              |
| Financial control impact         | limited             |
| GDPR assessment completed        | true                |
| Data governance review completed | true                |
| Security review completed        | true                |
| EU AI Act category               | null                |
| EU AI Act risk indicator         | potential_high_risk |
| Policy exception required        | false               |
| Risk acceptance required         | false               |

The Sales Proposal Agent has completed GDPR assessment, data governance review and security review. The declared and actual risk indicators are medium. The agent handles customer-related and confidential commercial data, but restricted data is not included in the allowed data scope.

## 14. Human oversight

| Control                    | Value                    |
| -------------------------- | ------------------------ |
| Human approval gate        | true                     |
| Escalation path defined    | true                     |
| Escalation owner           | Sales Operations Manager |
| Exception handling defined | true                     |

## 15. Approval required for

| Approval area                  |
| ------------------------------ |
| external proposal sharing      |
| customer-facing final proposal |
| pricing assumptions            |
| discounts                      |
| delivery commitments           |
| non-standard terms             |

Human approval is required before proposal content is shared externally or used for customer-facing final proposals. Human review is also required for pricing assumptions, discounts, delivery commitments and non-standard terms.

## 16. Human decision points

| Human decision point                |
| ----------------------------------- |
| proposal quality review             |
| sales manager approval              |
| pricing review                      |
| legal review for non-standard terms |

The Sales Proposal Agent supports draft creation only. Final commercial decisions remain with Sales, Finance or Legal stakeholders.

## 17. Escalation and exception handling

| Field                      | Value                                                                                                                                                                                                |
| -------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Escalation path defined    | true                                                                                                                                                                                                 |
| Escalation owner           | Sales Operations Manager                                                                                                                                                                             |
| Exception handling defined | true                                                                                                                                                                                                 |
| Escalation gap             | Standard escalation exists for pricing and legal review, but the proposal quality review SLA is not yet formally defined for AI-assisted drafts.                                                     |
| Exception handling gap     | Exceptions for pricing, discounts and legal terms are routed to existing Sales, Finance and Legal processes, but quality review timing for generated proposal drafts requires formal SLA definition. |

The escalation path is defined for pricing and legal review. The remaining gap is that the proposal quality review SLA is not yet formally defined for AI-assisted drafts.

This gap is a conditional readiness item. It does not block the current limited production deployment, but it prevents full GO or broader production rollout until the proposal quality review SLA is formally defined. Escalation path, exception handling, human approval gate and human decision points are fully defined and active.

## 18. Deployment controls

| Control                  | Value                         |
| ------------------------ | ----------------------------- |
| Production approval      | conditional                   |
| Approval status          | limited_production_approved   |
| Approval reference       | PROD-SAL-PRO-2026-03          |
| Deployment scope         | sales_team_limited_production |
| Last reviewed            | 2026-05-25                    |
| Next review due          | 2026-07-25                    |
| Change control reference | CHG-SAL-PRO-2026-05           |

## 19. Rollout limitations

| Limitation                                 |
| ------------------------------------------ |
| Draft-only use                             |
| No CRM write actions                       |
| No external sending by the agent           |
| No pricing approval by the agent           |
| No contract or legal approval by the agent |

The deployment is limited to sales-team production use. The agent is not allowed to perform write actions, external sending, pricing approval, contract approval or legal approval.

## 20. Security controls

| Security control            | Value                         |
| --------------------------- | ----------------------------- |
| Authentication required     | true                          |
| Role-based access control   | true                          |
| Least privilege evidenced   | true                          |
| Audit logging               | enabled                       |
| Monitoring enabled          | true                          |
| Monitoring owner            | Data & AI Lead                |
| Incident response plan      | defined                       |
| Incident response owner     | Security & Compliance Advisor |
| Incident response reference | IRP-DAI-AGENTS-2026           |
| Data retention defined      | true                          |
| Retention period days       | 180                           |

Incident response accountability is assigned to the Security & Compliance Advisor. AI monitoring ownership is assigned to the Data & AI Lead.

## 21. Logged events

| Logged event               |
| -------------------------- |
| user_query                 |
| customer_context_retrieved |
| retrieved_knowledge_source |
| proposal_draft_generated   |
| restricted_action_refusal  |
| human_review_required      |

Audit logging is enabled for user queries, customer context retrieval, retrieved knowledge sources, proposal draft generation, restricted action refusal and human review requirement events.

## 22. Operational controls

| Operational control                 | Value                    |
| ----------------------------------- | ------------------------ |
| Support owner                       | Sales Operations         |
| Fallback channel                    | Sales Operations Support |
| SLA defined                         | partially_defined        |
| Proposal quality review SLA defined | false                    |
| User feedback enabled               | true                     |
| Model output review frequency       | monthly                  |
| Knowledge review frequency          | quarterly                |

## 23. Operational dependencies

| Dependency                              |
| --------------------------------------- |
| Dynamics 365 Sales data quality         |
| Product knowledge freshness             |
| Approved proposal template availability |
| Sales manager review capacity           |

The Sales Proposal Agent depends on Dynamics 365 Sales data quality, fresh product knowledge, approved proposal templates and Sales manager review capacity.

## 24. Known gaps

| Gap                                                                                   |
| ------------------------------------------------------------------------------------- |
| Proposal quality review SLA is not formally defined.                                  |
| AI-generated proposal drafts require stronger sampling review before broader rollout. |
| Sales users need clearer guidance on prohibited use cases.                            |
| Customer-facing proposal approval remains manual and must be reinforced in training.  |

### Readiness interpretation guidance

The Sales Proposal Agent should be assessed as a limited-production sales-support agent with material rollout conditions.

Relevant evidence:

- Production approval is conditional.
- Deployment scope is limited to `sales_team_limited_production`.
- Proposal quality review SLA is not formally defined.
- Stronger sampling review is required before broader rollout.
- Sales-user guidance on prohibited use cases must be strengthened.
- Customer-facing proposal approval remains manual and must be reinforced in training.
- Core governance, security, data and human approval controls are present for the current limited scope.

These gaps are readiness conditions for broader rollout. The final deployment verdict must be generated by Kelvior Agent Decision Gate using the complete evidence set.

## 25. Recommended next steps

| Recommended next step                                                             |
| --------------------------------------------------------------------------------- |
| Define proposal quality review SLA for AI-assisted drafts.                        |
| Add sales-user guidance for prohibited actions and required human review.         |
| Add monthly sample review of generated proposals.                                 |
| Complete post-deployment review before expanding beyond limited production scope. |

## 26. Evidence interpretation guidance for assessment

The Sales Proposal Agent should be assessed as a limited-production, medium-risk sales-support agent.

The agent handles customer-related and confidential commercial data, but the evidence states that data governance review, GDPR assessment and security review are completed.

The agent has read-only MCP connector access and does not have CRM write access.

The agent may draft sales proposal content, but it must not approve discounts, change pricing, create binding offers, send proposals externally, update customer records, approve contract terms or accept customer orders.

Human approval is required for customer-facing proposal sharing, pricing assumptions, discounts, delivery commitments and non-standard terms.

The main unresolved controls are operational rather than mandatory blocking controls: proposal quality review SLA, stronger sampling review before broader rollout and clearer prohibited-use guidance for Sales users.

This document provides evidence for Inventory, Governance, Security, Policy and Process readiness assessment. It does not prescribe a deployment verdict.
