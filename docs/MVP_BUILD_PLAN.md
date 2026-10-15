# MVP Build Plan — FieldOps Pro

This plan turns the concept into a staged, testable product. It is intentionally a plan, not a claim that these systems already exist.

## Milestone 1 — Product and engineering foundation
- [ ] Confirm pilot customer, project type, roles, data residency, retention, and hosting constraints.
- [ ] Choose a supported web framework and runtime; pin versions and add a lockfile.
- [ ] Define local development, staging, and production environments.
- [ ] Add formatting, linting, type checking, unit tests, and CI checks.
- [ ] Establish design tokens and shared components for Arabic RTL and English LTR.
- [ ] Add accessible loading, empty, error, and permission-denied states.
- [ ] Establish architecture decision records and threat model.

**Acceptance:** a clean checkout can install dependencies, run locally, and pass automated checks; no secrets are required in the repository.

## Milestone 2 — Identity, organizations, and projects
- [ ] Integrate a maintained identity provider; define MFA/SSO requirements with pilot customer.
- [ ] Implement organization, project, membership, and role models.
- [ ] Enforce authorization server-side on every read/write, export, and background task.
- [ ] Add audit events for sign-in, membership changes, permission changes, and record updates.
- [ ] Add negative authorization tests across organizations and projects.

**Acceptance:** unauthorized cross-project and cross-tenant access is denied even when identifiers are guessed or modified.

## Milestone 3 — Actions and decisions (first end-to-end workflow)
- [ ] Create, assign, prioritize, comment on, and close an action.
- [ ] Record owner, due date, origin, linked project, evidence, status, and closure proof.
- [ ] Add overdue views, filters, notification rules, and configurable escalation.
- [ ] Preserve a traceable history of status and ownership changes.
- [ ] Add mobile-friendly quick capture and safe draft handling.

**Acceptance:** a user can capture an issue, assign a responsible person, track it through closure, and audit every important change.

## Milestone 4 — Document register and source-grounded search
- [ ] Add secure upload, size/type validation, malware scanning, and quarantine.
- [ ] Model document number, revision, status, discipline, originator, dates, and permissions.
- [ ] Keep superseded revisions available for audit but clearly marked as superseded.
- [ ] Add background text extraction/OCR and processing status.
- [ ] Implement permission-aware search and source previews.

**Acceptance:** users can find the current approved revision; unauthorized users cannot discover file contents, snippets, citations, or metadata.

## Milestone 5 — AI executive brief (controlled release)
- [ ] Establish a representative, redacted evaluation corpus with reviewer-approved expected answers.
- [ ] Generate a draft summary from authorized records and documents only.
- [ ] Attach citations to each material claim, including document revision and page/section.
- [ ] Distinguish facts, calculations, assumptions, forecasts, and recommendations.
- [ ] Add abstention for missing, conflicting, stale, or low-confidence evidence.
- [ ] Require a human review step before sending or publishing the report.
- [ ] Measure extraction accuracy, citation coverage, unsupported-claim rate, latency, and cost.

**Acceptance:** release only after product owners approve quality thresholds; unsupported claims and uncited material claims are tracked and below the agreed limit.

## Milestone 6 — RFI, permits, HSE, and portfolio analytics
- [ ] Add configurable RFI states, response SLA, attachments, and impact assessment.
- [ ] Add permit-to-work workflow with authorized human approvals and audit history.
- [ ] Add HSE observations, inspections, corrective actions, and closure evidence.
- [ ] Define authoritative metric formulas for schedule, cost, quality, and safety.
- [ ] Show source freshness, calculation method, and missing data on dashboard indicators.
- [ ] Add CSV/PDF exports with permissions, version identifiers, and audit events.

**Acceptance:** every KPI is reproducible from source records, and workflows respect configured approval and escalation rules.

## Milestone 7 — Pilot readiness
- [ ] Complete Arabic/English and RTL/LTR QA on supported browsers and mobile devices.
- [ ] Run accessibility, performance, dependency, secret, and security scans.
- [ ] Test backup restoration, data export/deletion, account revocation, and incident response.
- [ ] Perform independent penetration testing and remediate release-blocking findings.
- [ ] Compare pilot metrics to a pre-agreed baseline and document limitations.
- [ ] Obtain customer sign-off before production data migration or broad rollout.

**Acceptance:** no unresolved critical/high security findings, tested recovery procedures, approved privacy/security review, and measured pilot outcomes.

## Priority recommendation
Build one complete vertical slice first: identity and project access → actions/decisions → evidence attachment → audit history → source-linked executive summary. Avoid implementing every module shallowly before one workflow is secure, reliable, and demonstrably useful.
