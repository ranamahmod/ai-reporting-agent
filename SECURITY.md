# Security Policy

## Supported Versions

| Version | Supported |
|---------|-----------|
| latest  | ✅        |

## Reporting a Vulnerability

If you discover a security vulnerability, please **do not** open a public issue.

Instead, report it privately:

1. Email: **security@thelabelaistudios.ph** (or open a private security advisory on GitHub)
2. Include:
   - Description of the vulnerability
   - Steps to reproduce
   - Potential impact
   - Suggested fix (if any)

We will respond within **72 hours** and aim to release a patch within **7 days** for critical issues.

## Security Best Practices for This Project

- Never commit API keys or credentials — use `.env` files and add them to `.gitignore`
- Rotate API keys regularly
- Use environment variables for all secrets
- Review dependencies for known vulnerabilities before deploying

## Scope

This policy covers the source code in this repository. Third-party integrations (GoHighLevel, Telegram, Notion, Slack, etc.) are governed by their own security policies.
