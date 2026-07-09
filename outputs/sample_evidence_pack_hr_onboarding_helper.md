# Sample Evidence Pack - HR Onboarding Helper

## 1. Agent summary

Agent ID: AGT-HR-ONB-001  
Name: HR Onboarding Helper  
Version: 1.1  
Status: planned  
Environment: pre_production  
Owner department: Human Resources (DEP-HR)  
Business owner: HR Operations Manager  
Technical owner: Data & AI Lead  
Business unit: Kelvior Corporate (BU-COR)  
Business process: Hire-to-Retire (P02)  
Systems: Workday (SYS-HRMS-001), Microsoft 365 (SYS-M365-001), SharePoint HR Policy Library  
MCP connectors: MCP-HR (Kelvior HRMS Connector) – restricted_read, not approved for production  
Allowed actions: retrieval_response, recommendation (requires human approval), explanation, restricted_data_summary (requires human approval)  
Deployment scope: pre_production_validation, no production use, no direct employee-facing restricted HR data use, no autonomous HR decisions

## 2. Business context

The agent supports HR Operations in answering onboarding questions, suggesting training paths, and helping new employees understand onboarding tasks, policies, and required learning steps. It aligns with the Hire-to-Retire process. Deployment is limited to pre-production validation with no production approval. The agent may access restricted employee profile and confidential training status data. Human approval is mandatory before personalized HR guidance involving restricted data. Rollout limitations prohibit direct employee-facing restricted HR data responses or write actions.

## 3. Systems and MCP connectors

Primary systems:

- Workday (read-only) - system of record for employee, onboarding, and training status data
- Microsoft 365 and SharePoint HR Policy Library for policy and onboarding documents  
  MCP connector: MCP-HR
- Provides restricted read-only access to restricted HR context data only
- Production use and MCP-HR tools (EmployeeProfileLookup, TrainingStatusLookup) are not approved

## 4. Data classification

The agent processes restricted_employee_profile, confidential_onboarding, confidential_training_status data. It does not process financial or customer data but includes personal and restricted HR sensitive data. Prohibited data includes compensation, medical or absence records, disciplinary records, performance reviews, private HR case notes, immigration details, and legal investigations.

## 5. Audit domain scores

Inventory (15% weight): Complete identification, ownership, and scope with minor gaps (no data steward assigned). Score: 95  
Governance (25% weight): Ownership roles identified, human approval gate required and defined, escalation path defined, but missing production approval, missing data governance review, no data steward assigned, no audit logging accountability, no formal review cadence, no full exception handling, and no formal production approval. Score: 40  
Security (25% weight): Security review missing, audit logging planned but disabled, monitoring disabled, no incident response plan, role-based access control planned but not implemented, least privilege not evidenced, connector and tool approvals missing. Score: 30  
Policy (20% weight): Non-compliant with Kelvior AI, data governance and security policies due to missing data governance review, GDPR assessment, security review, human approval gate defined but formal approval missing, incomplete exception handling, no evidence retention policy. Score: 40  
Process (15% weight): Business process alignment is clear, human decision points and escalation path defined, but exception handling incomplete, SLA not defined, operational boundaries partially defined. Score: 65

## 6. Weighted readiness score

(Inventory 95 × 0.15) + (Governance 40 × 0.25) + (Security 30 × 0.25) + (Policy 40 × 0.20) + (Process 65 × 0.15)  
= 14.25 + 10 + 7.5 + 8 + 9.75 = 49.5 ≈ 50

Final score cap:

- Deployment scope is pre-production with no production approval; no final score cap required.

## 7. Mandatory blocking rule evaluation

No production approval completed for this agent which is planned and for pre-production scope only. This blocks production deployment readiness but not the current pre-production scope.

Data governance review missing → mandatory block for production deployment, but agent is pre-production, so not a blocking issue for current scope.

Security review missing for high-risk agent handling restricted HR data; production approval missing → mandatory block for production but pre-production status exempts current scope.

Audit logging disabled → mandatory block for production but not for pre-production.

Incident response plan missing → mandatory block for production but not for pre-production.

No data steward assigned — not a mandatory block but a governance finding.

MCP connector and tools not approved for production — not a mandatory block but a policy finding.

Agent has no write access or controlled actions (no autonomous HR decisions) — passes mandatory block criteria for access.

No mandatory block triggered for current pre-production validation scope.

## 8. Findings by domain

Inventory: Complete agent identity, ownership, systems, connectors, and deployment scope except missing data steward assignment.  
Governance: Missing production approval, data governance review, no audit logging accountability, no formal evidence retention policy, incomplete exception handling, no formal review cadence.  
Security: Security review missing, audit logging disabled, monitoring disabled, no incident response plan, least privilege not evidenced, no MCP connector or tool approvals.  
Policy: Data governance review and GDPR assessment missing, incomplete exception and retention policies, incomplete approval evidence for production.  
Process: Business process alignment is clear; human approval gates and escalation path set, but exception handling incomplete and SLA not defined.

## 9. Evidence references

Document ID: KEL-AGT-HRO-001  
Document title: HR Onboarding Helper Agent Evidence  
Evidence role: Agent-specific evidence for HR Onboarding Helper deployment readiness assessment  
Foundry IQ source document: 11_hr_onboarding_helper_evidence.md  
Citation or source reference: Detailed agent evidence covering identity, governance, security, data classification, systems, MCP connectors, deployment controls, human oversight, escalation, known gaps, required remediation, rollout limitations, and risk profile

Document ID: KEL-SRC-MANIFEST-001  
Document title: Evidence Source Manifest  
Evidence role: Source manifest for all retrieved Foundry IQ evidence documents  
Foundry IQ source document: 00_evidence_source_manifest.md  
Citation or source reference: Source attribution and document ID mapping for evidence grounding

Document ID: KEL-DAI-AIPOL-001  
Document title: Kelvior AI Policy  
Evidence role: AI governance and approval requirements including human oversight and production approval mandates  
Foundry IQ source document: 02_kelvior_ai_policy.md  
Citation or source reference: Sections on production approval, human approval gates, and lifecycle controls relevant to HR agents accessing restricted data

Document ID: KEL-DAI-DGOV-001  
Document title: Kelvior Data Governance Policy  
Evidence role: Data governance controls required for restricted, confidential and HR data  
Foundry IQ source document: 03_kelvior_data_governance_policy.md  
Citation or source reference: Controls required for HR data access including GDPR assessment, data steward assignment, and security review

Document ID: KEL-SEC-SECPOL-001  
Document title: Kelvior Security Policy  
Evidence role: Security requirements including audit logging, monitoring, incident response, least privilege and connector approvals  
Foundry IQ source document: 04_kelvior_security_policy.md  
Citation or source reference: Security control requirements for HR agents handling sensitive data

Document ID: KEL-DAI-APPROC-001  
Document title: Kelvior Agent Approval Procedure  
Evidence role: Agent approval process including pilot, production approval, and requirements for governance and security controls  
Foundry IQ source document: 05_agent_approval_procedure.md  
Citation or source reference: Approval requirements and escalation path definition for HR Onboarding Helper agent

Document ID: KEL-RISK-EXC-001  
Document title: Kelvior Enterprise Risk Register Excerpt  
Evidence role: Risk register supporting identification of risks related to missing security review, data governance review, production approval, audit logging, and incident response  
Foundry IQ source document: 06_enterprise_risk_register_excerpt.md  
Citation or source reference: Risk IDs and descriptions triggered by missing foundational controls for HR agents processing restricted data

Document ID: KEL-ENT-CTX-001  
Document title: Kelvior Enterprise Context Excerpt  
Evidence role: Enterprise context for business units, processes, systems, MCP connectors, and domain mapping for readiness assessment  
Foundry IQ source document: 01_kelvior_enterprise_context_excerpt.md  
Citation or source reference: Business unit, process owner, systems and MCP connector context for HR Onboarding Helper agent

## 10. Risk assessment

Triggered risks:

- Missing data governance review for restricted HR data access.
- Missing GDPR assessment for processing restricted personal data.
- Missing security review for HRMS and Microsoft 365 connectors with restricted HR data.
- Missing audit logging implementation for restricted data access.
- Missing monitoring and monitoring ownership for security events.
- Missing incident response plan for high-risk HR data use.
- Missing production approval for pre-production planned agent with high risk.
- MCP-HR connector not approved for production use.

Mitigated or not-triggered risks:

- Human approval gates are defined and required, mitigating risk from autonomous decisions.
- The agent has no write access and no autonomous system control, mitigating controlled actions risk.
- Escalation path is defined to HR Operations Manager.

Not applicable risks:

- Financial data handling risks are not applicable since the agent does not process financial data.
- IT operations incident response risks are not applicable for this HR-specific agent.

## 11. Deployment verdict

REMEDIATE

The agent is in planned pre-production and lacks foundational controls critical for safe validation and production deployment. Missing controls include data governance review, GDPR assessment, security review, production approval, audit logging, monitoring, incident response, role-based access control implementation, MCP connector and tool approvals, and exception handling completeness. These gaps require remediation before expanding into production or broader employee-facing operational use.

## 12. Required remediation plan

- Complete GDPR and privacy assessment for restricted HR data use.
- Complete formal data governance review including data steward assignment.
- Complete formal security review for MCP-HR connector, Workday, and Microsoft 365 access.
- Obtain full production approval including business and technical owner sign-off.
- Approve MCP-HR connector production use and associated MCP tools.
- Implement audit logging for all restricted data access, including employee profile lookup and training status queries.
- Enable and assign monitoring ownership with alerting for security-relevant events.
- Define and document incident response plan with assigned owners and procedures.
- Implement and validate role-based access control and least privilege enforcement across connectors and tools.
- Fully define exception handling procedures for HR onboarding, policy interpretation, and employee-specific cases.
- Establish SLA and operational boundaries for HR support fallback and issue escalation.
- Document evidence retention and data audit requirements.
- Implement change control procedures and secure deployment documentation.

## 13. Human approval checklist

- Human approval gate is required and defined for all personalized onboarding guidance involving restricted employee data or training status.
- Personalized onboarding messages or training recommendations must not be sent without prior HR Operations Manager or delegated approval.
- All restricted data summaries require human review before release.
- Exception cases involving role, manager, or department-specific policy interpretation must be escalated for human decision.
- Ensure user guidance and training cover human approval process clearly to all operational users.

## 14. Re-audit recommendation

Re-audit is recommended after completion of all remediation items above, especially after GDPR, data governance, security reviews, and production approval are obtained. Validation of audit logging, monitoring activation, incident response readiness, and exception handling completeness must be included. A formal re-assessment will ensure readiness for broader production deployment and employee-facing restricted HR data use.
