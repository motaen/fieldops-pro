# FieldOps Pro — Product and UX Specification

## Product ambition
Deliver a trusted operating layer for construction portfolios: field workflows, project controls, documents, decisions, and executive intelligence connected through auditable data.

The product should compete through workflow depth, source-grounded intelligence, speed of execution, implementation quality, and measurable business outcomes—not visual polish alone. Competitive superiority must be validated with customer pilots rather than assumed.

## Primary users and jobs to be done
- **Owner / executive:** understand portfolio health, financial exposure, decision bottlenecks, and actions required within minutes.
- **Project director:** identify critical-path threats, overdue decisions, change exposure, and accountability gaps.
- **Planner / project controls:** reconcile baseline vs actual, explain variance, and track forecast assumptions.
- **Commercial / cost:** connect changes, commitments, quantities, approvals, and evidence to cost impact.
- **Document controller:** find the current approved revision, detect superseded documents, and prove distribution.
- **HSE lead / site engineer:** capture observations quickly, assign corrective actions, and retain traceable evidence.
- **Contractor / consultant:** act on assigned work within project-scoped permissions.

## UX principles
1. Executive summary first; evidence and detail one click away.
2. Use progressive disclosure: concise signal, impact, evidence, owner, due date, next action.
3. Separate actual facts, computed values, forecasts, and AI recommendations visually.
4. Make every risk actionable: accountable owner, deadline, status, escalation path.
5. Minimize field input with templates, QR access, speech-to-text where appropriate, and safe offline drafts.
6. Arabic and English are first-class; test RTL/LTR, dates, numerals, PDFs, and mixed-language document names.
7. Accessible contrast, keyboard support, meaningful labels, and mobile targets.
8. No misleading green/red-only signals; pair color with text and iconography.

## Executive dashboard information architecture
- Portfolio overview: cost, schedule, safety, quality, decisions, documents, trends.
- Variance explanation: baseline, current forecast, variance, cause, evidence, confidence.
- Decisions needed: requested decision, due date, financial/schedule consequence, recommendation, accountable approver.
- Risk radar: probability, impact, proximity, trend, mitigations, owner.
- Document intelligence: critical documents, revisions, approval bottlenecks, extracted obligations.
- AI brief: executive narrative, key changes since last report, source citations, uncertainties, suggested questions.
- Drill-down: project → package → work area → workflow record → evidence.

## Core workflows
### Project and portfolio setup
Create a project, configure work packages, calendars, baseline, currencies, approval matrix, project roles, contractor organizations, and data retention requirements.

### Action and decision management
Create from meeting minutes, field observation, document review, or manual entry. Capture owner, due date, priority, dependencies, evidence, approval, and closure proof. Escalate overdue items according to project policy.

### Document control
Upload → malware scan → extract metadata/OCR → assign document number/revision/status → route for review → approve/reject with comments → distribute → mark prior revision superseded. Preserve immutable revision history and access logs.

### RFI
Draft → internal review → submit → assign responder → response and attachments → assess schedule/cost impact → approve/close. Track aging, response SLA, responsible party, and linked activities.

### Permit to work
Request → risk assessment → required controls and isolations → competent approvals → active permit → suspension/revalidation → close-out. High-risk actions require authorized human approval; AI may assist but cannot grant approval.

### HSE
Capture observation/inspection/near miss → classify → triage → assign corrective action → verify evidence → close. Maintain incident-specific access and auditable changes.

### Executive report
Choose project scope and period → retrieve authorized records and document versions → calculate deterministic metrics → generate cited narrative → flag missing/conflicting evidence → human review → export PDF/Excel → record report version and sources.

## AI capabilities: proposed, gated by evaluation
- Bilingual executive report summarization with page/section citations.
- Compare document revisions and explain material changes.
- Extract dates, obligations, responsible parties, amounts, and references into review queues.
- Detect potential duplicate RFIs, actions, observations, and documents.
- Identify schedule/cost/safety signals from structured records with explainable rules.
- Natural-language project Q&A, permission-aware and source-cited.
- Meeting-minutes to draft actions, with user confirmation before saving.
- Forecast scenarios with assumptions, ranges, and provenance; never present forecasts as facts.

## Product metrics
Measure against a pre-pilot baseline:
- Time to prepare weekly/monthly executive report.
- Median RFI response cycle and overdue RFI rate.
- Overdue action rate and median decision age.
- Superseded-document usage incidents.
- Rework events and verified cost associated with rework.
- Forecast error and time-to-detect schedule variance.
- HSE corrective-action closure time.
- AI citation coverage, extraction precision/recall, unsupported-claim rate, reviewer override rate.
- Active usage by role and time saved per workflow.

## Delivery gates
1. Prototype usability review with representative roles.
2. Data model and permission model reviewed before production data.
3. Threat model, privacy review, and secure architecture review.
4. Evaluation benchmark and quality thresholds for each AI workflow.
5. Pilot on redacted or explicitly approved data.
6. Independent security testing, restore drill, and performance testing.
7. Customer-verified outcome report before marketing quantified savings.

## Out of scope until explicitly approved
- Automatic contract interpretation as legal advice.
- Autonomous permit/HSE approval.
- Automatic financial commitments, payment approvals, or contractual notices.
- Unreviewed AI-generated changes to authoritative project records.
- Claims of guaranteed zero errors or guaranteed competitor superiority.
