# Security Baseline — FieldOps Pro

This document defines requirements for a future production implementation. The current repository is a static prototype and does not implement these controls.

## Identity and authorization
- Use a maintained identity provider; support MFA and enterprise SSO as required.
- Enforce server-side role- and attribute-based access checks on every API request.
- Scope records, files, search results, embeddings, citations, exports, and background jobs to tenant and project authorization.
- Deny by default. Do not rely on hidden UI controls for authorization.
- Test IDOR/BOLA risks by changing record IDs, file IDs, project IDs, filters, and citation URLs.
- Provide prompt access revocation and periodic role review.

## Data protection
- TLS in transit and encryption at rest with managed keys.
- Store secrets only in a managed secret store; never commit tokens, credentials, private keys, or provider API keys.
- Define classification, retention, deletion, legal hold, backup, and recovery policies.
- Minimize sensitive data in logs; redact tokens, personal information, and document contents where not needed.
- Validate file size, extension, MIME type, and file signatures; quarantine and scan uploads before processing.
- Keep customer documents private by default and do not use them for model training unless separately and explicitly agreed.

## AI and retrieval security
- Treat file content, OCR output, spreadsheets, comments, and retrieved text as untrusted data, never as executable instructions.
- Defend against indirect prompt injection, cross-project retrieval, data exfiltration, malicious links, and poisoned metadata.
- Authorize retrieval before generation and re-check permissions before returning each citation, snippet, and export.
- Use structured output schemas and server-side validation; do not let model output directly invoke privileged tools.
- Require explicit human confirmation for any write or consequential action.
- Keep citations with stable document/version identifiers and page or section references.
- Track model version, prompt/config version, retrieved source IDs, reviewer decisions, and evaluation results.
- Provide abstention when evidence is missing, stale, contradictory, or below quality threshold.
- Test hallucination, citation faithfulness, OCR errors, Arabic/English mixed text, tables, scanned PDFs, and adversarial documents.

## Application security
- Validate all inputs on the server; parameterize database queries.
- Use CSRF protection where cookie sessions apply, secure HttpOnly SameSite cookies, appropriate CORS, and content security policy.
- Rate-limit authentication, file processing, expensive AI calls, and exports.
- Protect against XSS, SSRF, SQL injection, insecure direct object references, path traversal, and unsafe deserialization.
- Separate development, test, staging, and production environments and credentials.
- Run dependency, secret, static-analysis, and container scans in CI.
- Protect default branch with reviews, required checks, and restricted write permissions.

## Audit and operations
- Append-only audit records for authentication, permission changes, record changes, approvals, exports, and AI-assisted decisions.
- Monitoring and alerts for suspicious access, unusual exports, authorization failures, and model/provider anomalies.
- Test backup restoration and incident-response procedures.
- Define service objectives, data-loss objectives, recovery-time objectives, and escalation ownership.
- Conduct privacy impact assessment, threat modeling, penetration testing, and customer security review before production.

## Release-blocking acceptance checks
- Cross-tenant and cross-project access tests pass.
- Unauthorized users cannot infer sensitive content from search counts, autocomplete, error messages, or AI citations.
- All privileged changes have an authenticated actor and audit event.
- Secrets scan and dependency/security checks pass.
- AI evaluation meets approved thresholds for factuality, source attribution, abstention, and language coverage.
- Restore drill succeeds and incident response contacts are current.
