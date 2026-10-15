# FieldOps Pro

**Construction operations intelligence — from field activity to executive decision.**

FieldOps Pro is being developed as an enterprise-oriented operations platform for complex construction portfolios. Its product goal is to help owners, developers, PMCs, contractors, and project leadership reduce avoidable delay, rework, document errors, and decision latency through connected workflows and evidence-grounded analytics.

> **Current status:** interactive front-end concept / pre-MVP. The current dashboard uses illustrative sample data. It is not connected to a database, identity provider, document store, live project controls, or an AI model. Do not use its displayed metrics for operational or financial decisions.

## Current prototype

The first concept iteration focuses on an Arabic-first, right-to-left executive dashboard with:
- Portfolio KPI cards and a progress-versus-baseline visualization.
- An executive-brief concept with proposed actions and explicit data caveats.
- Project list search and status filtering.
- Responsive desktop/mobile navigation.
- A downloadable, clearly labelled illustrative executive brief.
- Navigation concepts for projects, field operations, HSE, documents, actions, AI insights, and reporting.

Open `index.html` locally or serve it with any static web server. External Google Fonts are optional; system fallbacks are defined.

## Product principles

1. **Evidence before eloquence.** Every AI-generated claim should cite its source document or record, version, page/section, timestamp, and confidence. Unknowns must be stated as unknowns.
2. **Human approval for consequential actions.** AI may summarize, classify, compare, and recommend; it must not autonomously approve permits, alter safety status, issue contractual instructions, or commit financial changes.
3. **One auditable record.** Decisions, RFIs, permits, observations, documents, and actions need owners, due dates, statuses, version history, and an audit trail.
4. **Fast for field teams.** Mobile-first forms, QR/deep links, offline-tolerant drafts, minimal duplicate entry, and role-specific work queues.
5. **Portfolio clarity for executives.** Show what changed, why it matters, likely schedule/cost exposure, the next decision, and who owns it.
6. **Secure by default.** Least privilege, tenant/project isolation, encrypted transport and storage, managed secrets, audit logs, retention controls, and tested recovery.

## Suggested delivery roadmap

### Phase 0 — Product discovery and validation
- Confirm target buyer, initial project type, current tools, user roles, reporting obligations, and Saudi data/residency requirements.
- Interview project directors, PMCs, planning, commercial, document control, HSE, and site teams.
- Select measurable pilot outcomes: reporting preparation time, overdue-action rate, RFI cycle time, document revision errors, rework incidents, and forecast accuracy.

### Phase 1 — Secure MVP foundation
- Choose and document the application framework, API, relational database, object storage, deployment environment, and identity provider.
- Implement authentication, MFA/SSO options, role-based access control, project/tenant boundaries, audit events, backups, and migration strategy.
- Define core entities and APIs before expanding the prototype.

### Phase 2 — High-value operational workflows
- Projects, work packages, users, contractors, and responsibility matrix.
- Actions/decisions with ownership, deadlines, escalation, evidence, and immutable event history.
- Document register with revision, transmittal, review status, metadata, permissions, and superseded-version warnings.
- RFI and permit workflows with clear states, SLA timers, escalation, and approvals.
- HSE observations and inspections with controlled severity, corrective actions, and incident reporting.

### Phase 3 — Trusted document intelligence
- Secure upload and malware scanning; file-type validation and size limits.
- OCR and extraction for PDF, scanned pages, tables, spreadsheets, and supported office files.
- Retrieval augmented generation (RAG) scoped to the user's project and permissions.
- Source-linked summaries, bilingual executive briefs, obligation/date extraction, change comparison, duplicate detection, and discrepancy flags.
- Evaluation set with representative redacted project documents; measure extraction accuracy and unsupported-claim rate before release.

### Phase 4 — Forecasting and portfolio intelligence
- Schedule variance and critical-path signals, risk registers, change/variation exposure, commitments, and cost forecasts.
- Scenario analysis with explicit assumptions and sensitivity ranges.
- Explainable alerts, configurable thresholds, confidence labels, and human review.
- Integrations with approved project controls, document management, ERP, scheduling, and collaboration systems.

### Phase 5 — Enterprise readiness
- SSO/MFA, tenant isolation testing, permission-aware search, encryption/key management, backups and restore drills, monitoring, incident response, and penetration testing.
- Performance and accessibility testing, Arabic/English QA, mobile field trials, and disaster recovery.
- Pilot with a small number of real projects; publish validated outcomes before broad claims.

## AI reliability and document safety requirements

- Never invent project facts, amounts, contractual clauses, dates, or document references.
- Display a source for each material statement and let reviewers open the cited evidence.
- Distinguish extracted fact, calculation, inference, and recommendation.
- Use confidence thresholds and abstain or request review when evidence is incomplete or conflicting.
- Treat uploaded documents as untrusted data, not instructions. Defend against prompt injection and data exfiltration in document content.
- Enforce authorization before retrieval and again before displaying citations or generated output.
- Keep AI provider keys server-side in a managed secret store; never embed secrets in browser JavaScript or repository files.
- Log model/version, source IDs, reviewer decisions, and evaluation results without unnecessarily retaining sensitive document contents.

## Recommended initial architecture (to validate during discovery)

- **Web client:** accessible, responsive Arabic/English application with RTL/LTR support.
- **API:** authenticated service enforcing tenant, project, and record-level authorization.
- **Relational database:** canonical project/workflow state and audit records.
- **Object storage:** versioned source documents with encryption, malware scanning, and retention policies.
- **Background jobs:** OCR, document parsing, notifications, and report generation.
- **AI orchestration:** permission-aware retrieval, source citations, structured outputs, evaluation, and human review.
- **Observability:** metrics, traces, structured logs, alerts, and cost monitoring.

This is a target direction, not an implemented architecture.

## Definition of done for the first production pilot

- Users cannot access another tenant's or project's records by changing URLs, IDs, search terms, or document references.
- Every important AI statement is traceable to source evidence or clearly marked as a hypothesis.
- Document revisions and approvals are auditable.
- Core workflows are tested on mobile and desktop in Arabic and English.
- Backup restoration, access revocation, failure recovery, and incident procedures are tested.
- Pilot outcomes are measured against a documented baseline.

## Repository status

This repository currently contains a static HTML prototype. Production authentication, persistence, file processing, AI integration, external-system connectors, automated tests, and deployment pipelines remain future work.
