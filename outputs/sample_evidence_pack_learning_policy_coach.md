1. Agent summary

The Learning Policy Coach (Agent ID AGT-ACD-LRN-001, version 1.0) is a medium-risk, pilot-status AI agent deployed in a controlled pilot environment within Kelvior Academy (BU-ACD). It is designed to answer learning policy questions, explain course requirements, and recommend learning paths for Academy users. The agent is advisory only, with no write capabilities or autonomous decision-making authority over certifications or employee learning records. The declared risk level and the actual risk indicator are both medium.

2. Business context

The agent operates under the Academy business unit and is associated with the Academy department (DEP-ACD). It supports the Learn-to-Certify business process, aiding users in understanding learning policies and available certification pathways. The pilot approval reference is PILOT-ACD-LRN-2026-01, and the agent is under change control CHG-ACD-LRN-2026-04. The agent is intended for controlled Academy pilot deployment, focusing on advisory interactions without formal certification exception handling or record updates.

3. Systems and MCP connectors

The agent accesses the Moodle LMS system through the MCP-LMS connector for course, enrollment, and certification data retrieval. It uses approved Academy, HR, and Data & AI knowledge sources grounded through respective logical knowledge bases. The agent does not perform writes or operate with elevated system privileges. There are clearly defined MCP connectors and no unauthorized access to HR or other restricted systems beyond advisory use.

4. Data classification

The agent processes data classified as restricted employee profile, confidential onboarding, and confidential training status data. It contains personal but not financial data. HR knowledge sources are conditionally approved with restrictions for full rollout, and strict retrieval filtering is necessary before expansion due to the sensitivity of employee-related data. Human approval gates are established for handling exceptions and HR-sensitive learning accommodations. The agent operates with GDPR compliance and completed data governance and security reviews.

5. Audit domain scores

| Domain       | Score | Rationale                                                                                         |
|--------------|-------|-------------------------------------------------------------------------------------------------|
| Inventory    | 95    | Complete agent identification, environment, ownership, MCP connectors, and deployment scope.  |
| Governance   | 82    | Ownership defined, pilot approval exists; certification exception ownership requires clarification.|
| Security    | 85    | Security review completed; RBAC, least privilege, audit logging, monitoring, and incident response are evidenced.|
| Policy      | 80    | Data governance and GDPR reviews done; HR knowledge source conditional approval limits full rollout.|
| Process     | 78    | Aligned with Learn-to-Certify process; escalation and exception handling exist but cross-department clarity and SLA need strengthening.|

6. Weighted readiness score

Calculated weighted score before final cap:

= (Inventory 95 × 0.15) + (Governance 82 × 0.25) + (Security 85 × 0.25) + (Policy 80 × 0.20) + (Process 78 × 0.15)

= 14.25 + 20.5 + 21.25 + 16 + 11.7

= 83.7 (rounded to 84)

Final score cap available: maximum 84 due to controlled pilot deployment scope. Actual final weighted readiness score remains 84 because the calculated score is already below the cap.

7. Mandatory blocking rule evaluation

No mandatory blocks are identified. The agent has completed essential foundational controls like data governance review, GDPR assessment, security review, audit logging, monitoring, incident response ownership, and production approval is replaced with documented pilot approval supporting controlled pilot scope. Human approval gates are in place for certification exceptions and HR-sensitive guidance. No missing audit logging or security review gaps affect production or pilot deployment at this stage.

8. Findings by domain

Inventory: Complete with no identified gaps.

Governance: Ownership roles defined with pilot approval; however, certification exception routing ownership across Academy, HR, and Legal departments requires clarification. Escalation ownership and SLA require further definition.

Security: All critical security controls are implemented, including RBAC, least privilege, audit logging, and incident response ownership. Monitoring is active.

Policy: Data governance and GDPR reviews are complete; however, HR knowledge source requires stricter retrieval filtering before full rollout. Deployment limited to advisory use with conditional restrictions on HR-sensitive data.

Process: Agent mapped to Learn-to-Certify process with human oversight and exception handling. SLA for learner support escalation is partially defined and should be clarified before broader rollout. Exception handling ownership across departments needs formalization.

9. Evidence references

Document ID: KEL-AGT-ACD-001  
Document title: Learning Policy Coach Agent Evidence  
Evidence role: Agent-specific evidence for Learning Policy Coach deployment readiness assessment  
Foundry IQ source document: 09_learning_policy_coach_evidence.md  
Citation or source reference: Detailed agent metadata, control evidence, status overview, domain readiness mapping, operational gaps and known remediation from the agent evidence document.

Document ID: KEL-SRC-MANIFEST-001  
Document title: Evidence Source Manifest  
Evidence role: Source registry for all Foundry IQ evidence documents referenced in assessment  
Foundry IQ source document: 00_evidence_source_manifest.md  
Citation or source reference: List and identification of all source documents used in the readiness assessment.

Document ID: KEL-ENT-CTX-001  
Document title: Kelvior Enterprise Context Excerpt  
Evidence role: Enterprise business unit, departmental, process, systems and knowledge source context supporting the agent environment and deployment  
Foundry IQ source document: 01_kelvior_enterprise_context_excerpt.md  
Citation or source reference: Business context, MCP connectors, enterprise systems, knowledge bases, and process definitions relevant to agent environment.

Document ID: KEL-DAI-AIPOL-001  
Document title: Kelvior AI Policy  
Evidence role: AI governance and policy evidence for agent approval, data governance, security, monitoring, audit logging, and human oversight  
Foundry IQ source document: 02_kelvior_ai_policy.md  
Citation or source reference: Minimum AI governance controls, production approval, data governance review requirements, security needs, audit log mandates and risk acceptance criteria.

Document ID: KEL-DAI-DGOV-001  
Document title: Kelvior Data Governance Policy  
Evidence role: Data governance controls for classification, restricted data handling, human approval gates and traceability  
Foundry IQ source document: 03_kelvior_data_governance_policy.md  
Citation or source reference: Data classification controls, data owner accountability, access boundaries, human oversight for sensitive data and re-audit triggers.

Document ID: KEL-SEC-SECPOL-001  
Document title: Kelvior Security Policy  
Evidence role: Security controls covering access review, least privilege, audit logging, monitoring, incident response ownership and connector permissions  
Foundry IQ source document: 04_kelvior_security_policy.md  
Citation or source reference: Security readiness control minimums, audit logging requirements, monitoring expectations, incident response and escalation ownership.

10. Risk assessment

Triggered risks:

* None identified.

Mitigated or not-triggered risks:

* Data governance review missing — not triggered; review completed for this agent.  
* Audit logging missing — not triggered; audit logging enabled.  
* Security review missing — not triggered; security review completed.  
* Production approval missing — not triggered for pilot scope; pilot approval evidenced.  
* Incident response owner missing — not triggered; incident response ownership established.  
* Escalation path missing — not triggered; escalation paths exist but require clarification.  

Not applicable risks:

* Segregation of duties for financial workflow — Not applicable; agent does not perform financial operations.  
* Controlled write access without human approval — Not applicable; agent has no write or controlled actions.  

11. Deployment verdict

CONDITIONAL GO

The Learning Policy Coach is suitably controlled and approved for controlled pilot deployment within the Kelvior Academy. All foundational governance, security, data governance, audit logging, monitoring and human oversight controls are present and active for the pilot scope. Full production approval is not evidenced but is not required for controlled pilot status. Known operational and governance gaps remain in certification exception ownership clarity and escalation SLA definition, which should be resolved before broader rollout. HR knowledge source retrieval filtering requires strengthening prior to any full production expansion. Given these factors, the agent is ready to operate under controlled pilot conditions with conditions for broader deployment.

12. Required remediation plan

- Clarify cross-department ownership and escalation routing for certification exception handling involving Academy, HR, and Legal teams.  
- Define and formalize SLA for learner support escalation and certification exception response times.  
- Enhance HR knowledge source retrieval filters to ensure strict control of employee-sensitive data before full rollout.  
- Complete pilot review metrics and define human oversight cadence to validate agent performance and compliance.  
- Confirm all exception handling procedures across involved departments and document responsible owners.  

13. Human approval checklist

- Human approval gates exist for certification exceptions and HR-sensitive learning accommodations.  
- Human decision points are defined for certification exception handling, learner appeals, mandatory training conflicts and policy interpretation conflicts.  
- Escalation path is defined with an identified escalation owner (Academy Manager), pending ownership clarity for certification exceptions across departments.  
- Exception handling procedures are present but require completion and cross-department formalization before full rollout.  
- Human oversight roles and SLA are partially defined and require explicit documentation and enforcement.

14. Re-audit recommendation

Re-audit is recommended after completion of the pilot review, remediation of governance and process gaps including escalation ownership and SLA definition, and validation of enhanced HR knowledge source controls. A re-audit should also follow full production approval request to ensure all mandatory controls are validated for expanded deployment scope.