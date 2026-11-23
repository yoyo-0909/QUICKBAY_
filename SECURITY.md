# Security Policy

## Project status

QuickBay is an early-stage test website. Do not use it to store real customer data or process real payments unless the relevant production safeguards have been reviewed and enabled.

## Reporting a vulnerability

Please do not publish credentials, personal data or exploitable details in a public issue. Contact the repository owner privately through GitHub's available private reporting/contact options and include:

- A short description and potential impact
- Steps to reproduce
- A proof of concept, if safe to provide
- Any suggested mitigation

## Credential handling

- Never commit Supabase service-role keys, OAuth client secrets, private API keys, access tokens or passwords.
- Browser code may contain only the intended Supabase project URL and publishable key.
- Configure Google OAuth secrets directly in the Supabase Dashboard.
- Rotate any credential that is accidentally exposed and remove it from active deployments.
- Keep Supabase Row Level Security enabled and review policies before using real customer data.

## Scope notes

Third-party map data and external links are outside this repository's control. Report issues in QuickBay's own code or configuration; report upstream issues to the relevant provider.
