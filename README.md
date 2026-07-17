# Kelvior Agent Decision Gate

**A Microsoft Foundry reasoning-agent MVP that assesses whether an AI agent is ready for deployment.**

I built this for the Microsoft Agents League Hackathon 2026, Reasoning Agents track. I wanted to work through a question I think matters more than whether an agent can do the task:

> Should this agent be allowed to run in this process, with this data, under these controls?

I built a Microsoft Foundry reasoning agent to work through that question systematically, using synthetic Kelvior governance, security, policy, process and risk evidence instead of a general impression of whether an agent "looks okay."

The output is a structured **Agent Deployment Evidence Pack** that connects evidence, findings, risks, remediation actions and a deployment verdict.

Valid verdicts are:

- `GO`
- `CONDITIONAL GO`
- `REMEDIATE`
- `BLOCK`

---

## Project status

The hackathon phase is complete. I now maintain the project as a portfolio artifact that documents the Microsoft Foundry implementation, test cases, architecture and current MVP boundaries.

Kelvior Systems and all evidence used in the assessments are synthetic.

---

## The problem

AI agents can move faster than the controls around them.

An agent can look useful and still be unsafe or incomplete, because it has:

- unclear ownership
- missing approval status
- weak audit logging
- no human approval gate
- incomplete data governance review
- incomplete security review
- uncontrolled connector or MCP access
- no escalation path
- weak misuse prevention
- no evidence trail for deployment decisions

I built Kelvior Agent Decision Gate as a pre-deployment reasoning gate for that gap. It does not deploy agents automatically. It helps a human reviewer understand whether an AI agent is ready, conditionally acceptable, in need of remediation, or blocked from deployment.

---

## What the project does

The Decision Gate assesses an AI agent across five audit domains:

| Domain     | Weight | What it checks                                                                                                       |
| ---------- | -----: | ---------------------------------------------------------------------------------------------------------------------- |
| Inventory  |    15% | Whether the agent identity, owner, scope, systems, connectors, actions and deployment context are defined.           |
| Governance |    25% | Whether ownership, approval status, monitoring, audit logging, review cadence and human accountability are in place. |
| Security   |    25% | Whether access control, least privilege, logging, incident response and controlled actions are sufficiently covered. |
| Policy     |    20% | Whether the agent aligns with AI policy, data governance policy, security policy and approval procedure evidence.    |
| Process    |    15% | Whether operational boundaries, exception handling, escalation paths and human-in-the-loop controls are defined.     |

The agent then applies:

- mandatory blocking rules
- weighted readiness scoring
- score caps for conditional or limited deployments
- risk assessment
- source-grounded evidence references
- ethics and misuse-prevention checks
- human approval review logic

The decision chain:

```text
evidence → finding → risk → verdict → remediation plan → re-audit
```

Evidence supports a finding. The finding exposes a risk. The combined risks, blocking rules and readiness score determine the verdict. Where controls are missing, the Evidence Pack records the required remediation and the conditions for re-assessment.

A verdict should never stand on its own.

---

## Validated assessment results

The Decision Gate was tested against five synthetic Kelvior AI-agent scenarios.

| Agent                     | Verdict          | What the case shows                                                                                                                                                                                                                          | Sample output                                                        |
| ------------------------- | ---------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------- |
| Finance Invoice Assistant | `BLOCK`          | A finance automation agent should not go live when mandatory governance, security, data, approval or process controls are missing.                                                                                                           | [View output](outputs/sample_evidence_pack_finance.md)               |
| IT Ticket Triage          | `GO`             | A read-only, recommendation-only IT agent can pass when ownership, approval, logging, monitoring and human review are in place.                                                                                                              | [View output](outputs/sample_evidence_pack_it_ticket_triage.md)      |
| Learning Policy Coach     | `CONDITIONAL GO` | A controlled Academy pilot can be acceptable when foundational controls exist, but broader rollout still depends on clearer exception ownership, SLA definition and stricter HR knowledge-source retrieval filtering.                        | [View output](outputs/sample_evidence_pack_learning_policy_coach.md) |
| Sales Proposal Agent      | `CONDITIONAL GO` | A commercial drafting agent needs clear controls around discounts, binding offers, customer impact and human approval.                                                                                                                       | [View output](outputs/sample_evidence_pack_sales_proposal.md)        |
| HR Onboarding Helper      | `REMEDIATE`      | A planned pre-production HR agent can be assessed and remediated, but restricted HR data requires stronger privacy, governance, security, audit, monitoring and incident-response controls before production or broader employee-facing use. | [View output](outputs/sample_evidence_pack_hr_onboarding_helper.md)  |

These examples are included to show that the gate does not simply block everything. It makes different decisions based on evidence, scope and risk.

### About the sample outputs

The files in `outputs/` are Evidence Packs generated during MVP testing.

They are assessment examples from a synthetic environment, not compliance certifications or production deployment approvals. In organizational use, the evidence sources, risk model, approval rules, evaluation process and access controls would need to be adapted to that organization.

---

## Architecture

The system is designed as a reasoning gate that bases its assessment on retrieved and traceable evidence.

```text
Agent evidence + Kelvior governance and risk requirements
→ Ingestion Security and Ethics Layer (concept)
→ Foundry IQ Knowledge Base
→ Evidence retrieval
→ Microsoft Foundry reasoning agent
→ Agent Deployment Evidence Pack
→ External human review and deployment decision
```

![Kelvior Agent Decision Gate architecture](docs/assets/kelvior_architecture.svg)

The source set combines two types of evidence: agent evidence describing the agent under assessment, and Kelvior governance, policy, security, process and risk evidence defining the requirements against which that agent is assessed. The Evidence Source Manifest provides canonical document identities for source traceability; it does not itself carry assessment content.

The Ingestion Security and Ethics Layer represents pre-retrieval validation responsibilities. In this MVP it is an architecture boundary, not an enforced control.

The reasoning agent produces a deployment-readiness verdict. The organizational deployment decision is made by a human reviewer, outside this system.

The full component flow, design choices and MVP boundaries are documented in [docs/architecture_overview.md](docs/architecture_overview.md#architecture-decisions).

---

## Evidence sources

The Foundry IQ source set can be found in `foundry_iq_sources/`. It contains synthetic Kelvior evidence: enterprise context, AI policy, data governance policy, security policy, agent approval procedure, an enterprise risk register excerpt, and agent-specific evidence documents for each assessed agent, plus the Evidence Source Manifest.

The YAML files in `agent_definitions/` are the source-controlled reference definitions for each agent. Foundry IQ does not retrieve from YAML directly; the Markdown files in `foundry_iq_sources/` are the retrieval-ready representation of that same agent evidence.

The Evidence Source Manifest maps source documents to canonical document IDs, titles and evidence roles. This reduces the risk of unclear source attribution or invented document references in the Evidence Pack.

The full traceability model is documented in [docs/architecture_overview.md](docs/architecture_overview.md#7-evidence-traceability) and [foundry_iq_sources/README.md](foundry_iq_sources/README.md#evidence-traceability).

---

## Ethics and misuse prevention

The Decision Gate checks whether an assessed agent stays within its declared purpose, business process, deployment scope, data scope, user groups, systems, MCP connectors and allowed actions.

This matters because many AI-agent risks do not come from the model alone. They come from using an agent outside the context it was approved for.

Examples of misuse that should be blocked or escalated:

- a finance agent initiating or approving a vendor payment without the required authorization;
- an HR agent ranking employees using sensitive or unapproved inferred characteristics;
- a sales agent committing Kelvior to pricing or contract terms without commercial or legal approval;
- an IT agent granting or expanding system access without an approved request and human authorization.

Ethics and misuse prevention are assessed through the Governance, Policy and Process domains. These checks are implemented in the agent instruction and assessment logic. They are not pre-ingestion enforcement controls.

---

## Guardrails

The assessment uses these guardrails:

| Guardrail                      | Purpose                                                                                                                                       |
| ------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------- |
| Foundry IQ grounding           | Retrieves relevant Kelvior source material for the assessment, so the agent can support findings with project-specific evidence instead of relying on general model knowledge. |
| Evidence Source Manifest       | Preserves canonical document identity and source traceability.                                                                                |
| Mandatory blocking rules       | Prevents `GO` or `CONDITIONAL GO` when critical controls are missing.                                                                         |
| Risk ID rules                  | Prevents invented risk IDs.                                                                                                                    |
| Section 9 evidence references  | Forces source-level evidence traceability.                                                                                                    |
| Section 10 risk classification | Separates triggered, mitigated and not-applicable risks.                                                                                       |
| Score caps                     | Prevents numeric overstatement for limited or conditional deployments.                                                                        |
| Human approval checks          | Keeps high-impact decisions under human review.                                                                                               |
| Ethics and misuse checks       | Detects use outside approved scope, process, data or action boundaries; implemented as agent-instruction logic, not ingestion-layer enforcement. |

---

## Evidence Pack output

Each full readiness assessment produces a 14-section **Agent Deployment Evidence Pack**:

1. Agent summary
2. Business context
3. Systems and MCP connectors
4. Data classification
5. Audit domain scores
6. Weighted readiness score
7. Mandatory blocking rule evaluation
8. Findings by domain
9. Evidence references
10. Risk assessment
11. Deployment verdict
12. Required remediation plan
13. Human approval checklist
14. Re-audit recommendation

The Evidence Pack is meant to be readable by governance, security, data, risk and business stakeholders.

Its purpose is to make the reasoning path reviewable.

---

## Repository structure

```text
agent_definitions/
  agent_finance_invoice.yaml
  agent_hr_onboarding.yaml
  agent_it_ticket_triage.yaml
  agent_learning_coach.yaml
  agent_sales_proposal.yaml

agent_instructions/
  kelvior_agent_decision_gate_instruction.md

foundry_iq_sources/
  00_evidence_source_manifest.md
  01_kelvior_enterprise_context_excerpt.md
  02_kelvior_ai_policy.md
  03_kelvior_data_governance_policy.md
  04_kelvior_security_policy.md
  05_agent_approval_procedure.md
  06_enterprise_risk_register_excerpt.md
  07_finance_invoice_assistant_evidence.md
  08_it_ticket_triage_evidence.md
  09_learning_policy_coach_evidence.md
  10_sales_proposal_agent_evidence.md
  11_hr_onboarding_helper_evidence.md
  README.md

outputs/
  sample_evidence_pack_finance.md
  sample_evidence_pack_it_ticket_triage.md
  sample_evidence_pack_learning_policy_coach.md
  sample_evidence_pack_sales_proposal.md
  sample_evidence_pack_hr_onboarding_helper.md

docs/
  architecture_overview.md
  assets/
    kelvior_architecture.svg

scripts/
  check_internal_links.py

.editorconfig
.gitattributes
.gitignore
README.md
LICENSE
```

---

## How to run the MVP

This project requires a configured Microsoft Foundry project with Foundry IQ connected.

1. Upload the source documents from `foundry_iq_sources/` to a Foundry IQ knowledge base.

2. Configure a Microsoft Foundry reasoning agent with the instruction in:

```text
   agent_instructions/kelvior_agent_decision_gate_instruction.md
```

3. Connect the Foundry IQ knowledge base to the reasoning agent.

4. Run an assessment prompt, for example:

```text
   Perform a full deployment readiness assessment for the Finance Invoice Assistant using the connected Kelvior Foundry IQ knowledge base.
```

5. For regression-style testing, use the stricter prompt below:

```text
   Perform a full deployment readiness assessment for the [AGENT NAME] using the connected Kelvior Foundry IQ knowledge base. Produce the full 14-section Agent Deployment Evidence Pack. Base the assessment only on retrieved Kelvior evidence. Do not use expected verdicts, sample outputs or prior test results.
```

Replace `[AGENT NAME]` with one of the assessed agents:

- `Finance Invoice Assistant`
- `IT Ticket Triage`
- `Learning Policy Coach`
- `Sales Proposal Agent`
- `HR Onboarding Helper`

6. Review the generated Agent Deployment Evidence Pack.

Sample outputs are available in `outputs/` if you want to inspect the expected assessment format without running the agent.

---

## Repository checks

This repository includes a small local validation script for internal Markdown links.

Windows:

```powershell
py scripts/check_internal_links.py
```

macOS or Linux:

```bash
python3 scripts/check_internal_links.py
```

Depending on the local Python installation, `python` may also be available.

The repository also includes `.editorconfig` and `.gitattributes` for basic editor consistency and line-ending normalization.

---

## Live environment status

I don't keep the original Microsoft Foundry / Foundry IQ environment running as a permanent public demo.

This started as a hackathon MVP, and I now maintain it as a portfolio artifact, not a hosted product. Some of the Azure resources supporting Foundry, Foundry IQ and retrieval can continue to incur charges while they remain provisioned, even when I am not actively running assessments.

To avoid paying for infrastructure I am not using, I delete the cloud resources after testing. The repository remains available as the source artifact. It contains the architecture, Foundry IQ source set, agent instruction and sample Evidence Packs, so the implementation can be understood and recreated without access to my original live environment.

The MVP can be recreated in another Microsoft Foundry environment. The evidence sources, approval rules, risk model, retrieval permissions and production controls would then need to be adapted to that organization's governance context.

---

## Platform and implementation

### Agent platform

- Microsoft Foundry Agent Service
- Foundry IQ
- Azure AI Search

### Repository formats and tooling

- YAML
- Markdown
- Mermaid
- Python
- Git and GitHub

The Foundry IQ knowledge base uses Azure AI Search for indexing and retrieval. Markdown is used for retrieval-ready evidence documents, YAML for source-controlled agent definitions, and Mermaid for the editable architecture diagram.

---

## Demo

[Demo video](https://youtu.be/gCxCNNIsIQ0)

I picked three cases for the demo that show different sides of the same system.

### Finance Invoice Assistant → BLOCK

This is the case I lead with, because it shows why a governance gate matters.

The Finance Invoice Assistant is blocked because financial automation requires strong controls around governance, approval, audit logging, data review, security review, segregation of duties and human approval.

### IT Ticket Triage → GO

I included this case to show that the Decision Gate doesn't block everything by default.

The IT Ticket Triage agent receives a `GO` verdict because it is read-only, recommendation-only, approved, logged, monitored and controlled through human review.

### Sales Proposal Agent → CONDITIONAL GO

This case shows the middle ground: limited use can be acceptable while broader rollout still needs work.

The Sales Proposal Agent receives a `CONDITIONAL GO` because key governance, security, data and human approval controls are present, but the deployment remains limited to a scoped sales-team rollout.

---

## MVP boundary and production requirements

This is a working Microsoft Foundry reasoning-agent MVP using synthetic enterprise evidence. It implements the retrieval-grounded assessment flow, verdict logic and Evidence Pack output.

It does not implement production identity controls, live policy enforcement, automated approval execution or a human-review workflow. I couldn't test any of that without a real organizational environment — real identities, and production access to policy, monitoring and security systems.

The reusable architecture pattern:

```text
curated evidence enters retrieval
→ the reasoning agent evaluates deployment readiness
→ the Evidence Pack exposes findings, risks and required actions
→ an authorized human reviewer makes the deployment decision
```

The full MVP boundary and production hardening path are documented in [docs/architecture_overview.md](docs/architecture_overview.md#mvp-boundary).

---

## License and disclaimer

This repository uses the MIT License.

Kelvior Systems is a fictional enterprise simulation environment created for educational, architectural and portfolio purposes. No real employee, customer, vendor or confidential business data is used.

Microsoft Foundry, Foundry IQ, Azure and related Microsoft product names are product names or trademarks of Microsoft.

This project is independent and is not affiliated with, endorsed by or certified by Microsoft.

---

## Author

**Nadira Büsse**

I build portfolio projects around AI systems, agent workflows, context infrastructure and responsible deployment decisions.

[LinkedIn](https://www.linkedin.com/in/nadirabusse)
