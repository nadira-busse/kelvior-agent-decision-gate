1. Agent summary  
Agent ID: AGT-SAL-PRO-001  
Name: Sales Proposal Agent  
Version: 1.0  
Status: Active  
Environment: Limited production  
Business Unit: Kelvior Outdoor (BU-OUT)  
Department: Sales (DEP-SAL)  
Business owner: Sales Operations Manager  
Technical owner: Data & AI Lead  
Primary Business Process: Order-to-Cash (P04)  
Primary Systems: Dynamics 365 Sales, Microsoft 365, SharePoint  
MCP Connectors: MCP-CRM (read-only, approved)  
Allowed Actions: retrieve_customer_context (read-only), draft_sales_proposal (requires human approval, does not write to system)  
Deployment Scope: Sales team limited production, no write or controlled actions performed by agent

2. Business context  
The Sales Proposal Agent supports drafting sales proposal content for Sales teams using approved customer, product, opportunity, and sales context from Dynamics 365 Sales. It operates in a limited production environment with read-only access to CRM data. The agent does not perform binding financial or legal actions, pricing changes, approvals, or external proposal sending without human review and approval. Human oversight is integral for all customer-facing proposals, pricing assumptions, discounts, delivery commitments, and non-standard terms.

3. Systems and MCP connectors  
Primary systems include Dynamics 365 Sales (system of record). The agent uses the MCP-CRM connector approved for read-only agent queries (no write or controlled actions). Connector approval is documented with reference MCP-CRM-APPROVAL-2026-01. Agent's connector and system access complies with least privilege and role-based access requirements.

4. Data classification  
Data classification includes internal, confidential commercial, and customer-related data. Contains personal data (customer-related) but no restricted data or HR confidential data. Financial data handling is limited and no payment or confidential contract negotiation data is accessed or processed. Prohibited data: payment details, private customer notes, unapproved discount logic, confidential contract negotiation notes, legal commitments, binding offer approval data.

5. Audit domain scores  

| Domain     | Score | Notes                                                                                                     |
|------------|--------|-----------------------------------------------------------------------------------------------------------|
| Inventory  | 100    | Complete agent identity, ownership, environment, process, systems, MCP connectors, and allowed actions.   |
| Governance | 80     | Clear ownership, human approval gates, escalation paths, production approval is conditional for limited production. Minor gaps in some operational governance controls.  |
| Security   | 90     | Security review completed; RBAC, least privilege, audit logging, monitoring, incident response assigned.   |
| Policy     | 85     | Data governance and GDPR assessment completed; compliance with AI, security and data governance policies; human oversight enforced. Minor gaps in prohibited-use guidance.      |
| Process    | 80     | Business process alignment to Order-to-Cash; exception handling and escalation defined. SLA partially defined and improvement needed in proposal quality review. |

6. Weighted readiness score  
Calculated weighted score = (100 × 0.15) + (80 × 0.25) + (90 × 0.25) + (85 × 0.20) + (80 × 0.15)  
= 15 + 20 + 22.5 + 17 + 12  
= 86.5 ≈ 87  

Domain caps:  
- Governance cap 84 available due to conditional production approval and some operational gaps. Actual Governance score 80 is below cap — no capping applied.  
- Policy cap 84 available for incomplete prohibited-use guidance; actual Policy score 85 exceeds cap, so capped to 84.  
- Process cap 84 available due to partially defined SLA; actual Process score 80 is below cap — no capping applied.

Recalculate weighted score with Policy cap:  
= 15 + 20 + 22.5 + (84 × 0.20) + 12  
= 15 + 20 + 22.5 + 16.8 + 12  
= 86.3 ≈ 86

Final weighted readiness score: 86

Final score cap:  
Limited production deployment scope and conditional production approval imply a final score cap of 84.  
Final weighted readiness score is 86 > 84, so capped to 84.

Final score cap applies: maximum 84 due to conditional production approval and limited production deployment scope.  
Calculated weighted readiness score before final cap: 86  
Final weighted readiness score after cap: 84

7. Mandatory blocking rule evaluation  
No mandatory blocking rules are triggered:  
- Data governance review, GDPR assessment, and security review are completed for the medium-risk agent with confidential commercial and customer data.  
- Audit logging, monitoring, incident response ownership, and escalation path exist.  
- Human approval gate is in place for financial and customer-facing decisions.  
- Agent has no write or controlled actions without human approval.  
- Production approval is conditional and scope is limited production, which is acceptable for current deployment.  

8. Findings by domain  

- Inventory: Complete and compliant.  
- Governance: Production approval is conditional; escalation path, human approval gates, accountable ownership are in place; minor operational governance controls need strengthening.  
- Security: Controls largely complete; security review done; least privilege, RBAC, logging, monitoring, incident response established.  
- Policy: Data governance and AI policy compliance evidenced; prohibited-use guidance for sales users requires clearer definition.  
- Process: Aligned to Order-to-Cash; proposal quality review SLA not formally defined; stronger sampling of AI-generated proposals recommended before broader rollout; exception handling and escalation defined but SLA partial.  

9. Evidence references  

Document ID: KEL-AGT-SAL-001  
Document title: Sales Proposal Agent Evidence  
Evidence role: Agent-specific evidence for Sales Proposal Agent deployment readiness assessment, with supporting product, legal, commercial and corporate policy context
Foundry IQ source document: 10_sales_proposal_agent_evidence.md  
Citation or source reference: Comprehensive agent metadata, control status, data classification, MCP connector evidence, human oversight, security controls, operational controls, gaps and next steps sections.

Document ID: KEL-SRC-MANIFEST-001  
Document title: Evidence Source Manifest  
Evidence role: Derived evidence representation of the source manifest for all retrieved Foundry IQ documents used in this assessment  
Foundry IQ source document: 00_evidence_source_manifest.md  
Citation or source reference: Source registry mapping and verification for agent, policy, governance, security and risk evidence documents.

Document ID: KEL-DAI-AIPOL-001  
Document title: Kelvior AI Policy  
Evidence role: AI governance policy evidence including human oversight, approval procedures, audit logging, and deployment readiness requirements  
Foundry IQ source document: 02_kelvior_ai_policy.md  
Citation or source reference: Sections on AI governance, human approval gates, audit logging, monitoring, incident response requirements.

Document ID: KEL-DAI-DGOV-001  
Document title: Kelvior Data Governance Policy  
Evidence role: Data governance controls for confidential and customer data, data owner accountability, privacy compliance and access scope management  
Foundry IQ source document: 03_kelvior_data_governance_policy.md  
Citation or source reference: Sections covering data classification, data governance review requirements, data owner roles, and privacy constraints.

Document ID: KEL-SEC-SECPOL-001  
Document title: Kelvior Security Policy  
Evidence role: Security controls for system access, least privilege, logging, monitoring and incident response for AI agents using system connectors  
Foundry IQ source document: 04_kelvior_security_policy.md  
Citation or source reference: Controls for access control, least privilege, audit logging, monitoring, incident response ownership and escalation.

Document ID: KEL-DAI-APPROC-001  
Document title: Kelvior Agent Approval Procedure  
Evidence role: Approval procedures including business review, data governance review, security review, human oversight determination, production approval and re-audit requirements  
Foundry IQ source document: 05_agent_approval_procedure.md  
Citation or source reference: Stages 1–7 covering inventory registration, business review, data governance review, security review, human oversight, production approval and re-audit.

Document ID: KEL-RISK-EXC-001  
Document title: Kelvior Enterprise Risk Register Excerpt  
Evidence role: Risk register entries for missing production approval, security review, audit logging, data governance, and human approval gates relevant to AI agent deployment  
Foundry IQ source document: 06_enterprise_risk_register_excerpt.md  
Citation or source reference: Risk conditions R-GOV-001, R-SEC-001, R-DATA-001, R-AUD-001, and R-FIN-001 relevant to finance and sales agents.

Document ID: KEL-ENT-CTX-001  
Document title: Kelvior Enterprise Context Excerpt  
Evidence role: Enterprise context on business units, departments, processes, systems, MCP connectors and readiness governance relevant to AI agents  
Foundry IQ source document: 01_kelvior_enterprise_context_excerpt.md  
Citation or source reference: Business unit BU-OUT (Kelvior Outdoor), department DEP-SAL (Sales), process P04 (Order-to-Cash), systems Dynamics 365 Sales, MCP-CRM connector details and governance roles.

10. Risk assessment  

Triggered risks:  
* None identified.

Mitigated or not-triggered risks:  
- R-GOV-001 Missing production approval for active AI agent – mitigated by conditional production approval and limited production scope.  
- R-SEC-001 Missing security review for system-connected AI agent – mitigated by completed security review.  
- R-DATA-001 Restricted or confidential data processed without data governance review – mitigated by completed data governance review.  
- R-AUD-001 Audit logging disabled for production AI agent – mitigated by enabled audit logging.  
- R-FIN-001 Finance automation without human approval gate – mitigated by human approval gate for proposal sharing, pricing assumptions and discounts.

Not applicable risks:  
- Risks related to write-capable or controlled actions are not applicable since the agent performs read-only, draft-only actions without write permissions.  
- HR and legal data risks are not applicable as the agent does not process HR or legal confidential data.  

11. Deployment verdict  
CONDITIONAL GO  

Rationale: The Sales Proposal Agent meets foundational controls including data governance review, GDPR compliance, security review, audit logging, monitoring, incident response, human approval gates, RBAC and least privilege. Deployment is limited to a sales-team scoped limited production environment with conditional production approval. Minor gaps remain in operational governance such as a formally defined proposal quality review SLA and stronger sampling review before broader rollout. Sales-user guidance on prohibited actions requires strengthening. These gaps require resolution before full production rollout but do not block current limited production use under defined operational conditions.

12. Required remediation plan  
- Define and document a formal proposal quality review SLA for AI-assisted drafts.  
- Strengthen sampling review procedures for AI-generated sales proposals before broader rollout.  
- Enhance sales-user guidance regarding prohibited actions and mandatory human review points.  
- Conduct a post-deployment review and validation before expanding beyond the current limited production scope.

13. Human approval checklist  
- Human approval gate for external proposal sharing and customer-facing final proposals is active.  
- Human review required for pricing assumptions, discounts, delivery commitments, and non-standard terms.  
- Sales manager approval, pricing review, and legal review for non-standard terms are established human decision points.  
- Escalation path and exception handling defined and assigned to Sales Operations Manager.

14. Re-audit recommendation  
Re-audit is recommended after completion of the required remediation plan, particularly after formalizing operational SLAs, strengthening sampling review, and expanding sales-user training. Routine re-audit should also be triggered by any material changes to agent capabilities, deployment scope, or data sources.