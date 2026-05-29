# Security Policy

## Supported Content

This repository contains documentation, AI assistant skill instructions, examples, and helper scripts. It does not provide a hosted service.

Security reports are relevant when they involve:

- Exposed credentials, tokens, tenant IDs, private project IDs, or customer data.
- Unsafe guidance that could leak Autodesk credentials or user data.
- Helper scripts that execute commands insecurely.
- Incorrect authentication, authorization, callback, or webhook guidance.

## Reporting A Vulnerability

Please do not open a public issue for sensitive reports. Use GitHub Security Advisories when available, or contact the repository owner privately.

Include:

- Affected file or skill.
- Clear steps to reproduce or verify the issue.
- Impact and suggested mitigation, if known.
- Whether any credential or private data is already exposed.

## Handling Secrets

Never commit:

- Autodesk Client IDs or Client Secrets.
- OAuth access tokens or refresh tokens.
- Signed URLs that grant access to private objects.
- ACC, BIM 360, or Autodesk Docs project identifiers from private projects.
- Customer models, logs, payloads, or screenshots that reveal private data.

Use placeholders such as `<AUTODESK_CLIENT_ID>`, `<AUTODESK_CLIENT_SECRET>`, `<ACCESS_TOKEN>`, `<PROJECT_ID>`, and `<BUCKET_KEY>`.
