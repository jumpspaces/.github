# Security Policy

## Reporting a Vulnerability

At JUMP SPACES, we take security seriously. If you discover a security vulnerability in any of our repositories, **please do not open a public GitHub issue.**

Instead, report it privately through one of the following channels:

| Method | Contact |
|---|---|
| 📬 Email | security@jumpspaces.com |
| 🔒 GitHub Private Disclosure | Use the **Report a vulnerability** button on the Security tab of any repo |

We will acknowledge your report within **48 hours** and aim to provide a resolution timeline within **5 business days**.

---

## What to Include in Your Report

To help us triage quickly, please include:

- A description of the vulnerability and its potential impact
- The affected repository, file(s), and line numbers (if known)
- Step-by-step instructions to reproduce the issue
- Any proof-of-concept code or screenshots
- Your recommended fix (optional, but appreciated)

---

## Scope

The following are **in scope** for security reports:

- Authentication and authorization bypass
- Injection vulnerabilities (SQL, NoSQL, command, etc.)
- Cross-site scripting (XSS) and cross-site request forgery (CSRF)
- Sensitive data exposure (API keys, credentials, PII)
- Broken access control
- Security misconfigurations in deployed services
- Dependency vulnerabilities with confirmed exploitability

The following are **out of scope**:

- Vulnerabilities in third-party services we use but do not control
- Social engineering attacks targeting our team
- Physical security issues
- Denial of service (DoS) attacks
- Issues already known or reported

---

## Supported Versions

We actively maintain security patches for:

| Status | Support |
|---|---|
| ✅ Current release | Full security support |
| ⚠️ Previous release | Critical patches only |
| ❌ Older releases | No support — please upgrade |

---

## Responsible Disclosure

We kindly ask that you:

- Give us reasonable time to investigate and patch before public disclosure
- Avoid accessing, modifying, or deleting data that is not yours
- Not perform actions that could harm users, systems, or data availability

In return, JUMP SPACES commits to:

- Responding promptly and keeping you informed of progress
- Not pursue legal action against researchers acting in good faith
- Crediting you in our release notes (unless you prefer to remain anonymous)

---

## Internal Security Standards

All JUMP SPACES team members are expected to follow our internal security practices:

- Enable Two-Factor Authentication (2FA) on GitHub and all project tools
- Never commit secrets, credentials, or `.env` files to any repository
- Use GitHub Secrets for CI/CD credentials
- Rotate Personal Access Tokens every 6 months
- Report suspicious activity to security@jumpspaces.com immediately
