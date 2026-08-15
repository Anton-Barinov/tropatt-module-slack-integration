# Security Policy

## Reporting a vulnerability

Report security issues responsibly through the main project policy:

- [TropaTT SECURITY.md](https://github.com/Anton-Barinov/TropaTT/blob/main/SECURITY.md)
- or open a private security advisory in this repository.

Do not publish vulnerability details publicly before a fix is released.

## Security model

- API tokens and credentials are stored encrypted (AES-256-GCM, key derived per module from `APP_SECRET`).
- Secrets are never written to logs or returned by API responses.
- Outbound HTTP is validated against SSRF (DNS resolution, private-IP blocking), size and MIME checks.
- Webhook callbacks are signed and verified; callback URLs are derived from the installation, never hard-coded.
