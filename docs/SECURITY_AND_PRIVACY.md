# Pet360 — Security and Privacy Notes

## Public repository safety

This repository intentionally excludes application source code. Before every public push, check that it does not contain:
- `.env` files or environment-specific configuration.
- API keys, Firebase service-account files, access tokens, or passwords.
- Database URLs or Redis credentials.
- Private model files, datasets, logs, or user exports.
- Screenshots containing real personal information.
- University or third-party material that the team is not permitted to publish.

## Application security checklist

- Enforce authentication and authorization on the server.
- Use least-privilege database users and Firebase rules.
- Store secrets in environment variables managed by the deployment platform.
- Validate and sanitize inputs.
- Use HTTPS for deployed traffic.
- Set request body and file upload size limits.
- Allow only required image formats and validate file content, not just filename.
- Add rate limiting for authentication and AI endpoints.
- Avoid logging tokens, passwords, raw private prompts, or uploaded images.
- Keep dependencies updated and review security advisories.
- Define backup, deletion, retention, and incident-response procedures.
- Use generic client-facing errors; keep diagnostic details in protected logs.

## AI and animal-health safety

- Label AI content as educational, not diagnostic.
- Do not claim the image model reliably detects or diagnoses disease without appropriate validation.
- Tell users to contact a veterinarian for concerning symptoms.
- Avoid treatment, medication, or dosage instructions from unvalidated outputs.
- Handle AI failures gracefully and do not fabricate a result when the service fails.
- Obtain appropriate consent before transmitting images or prompts to external providers.
- Define whether AI inputs are retained, who can access them, and when they are deleted.

## Privacy by design

Collect only necessary information, explain why it is needed, restrict access by role, and establish retention periods. Before real users are onboarded, review applicable university requirements and relevant privacy laws.
