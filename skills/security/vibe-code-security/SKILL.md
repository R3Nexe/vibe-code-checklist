---
name: vibe-code-security
description: Harden web app code against auth bypass, injection, XSS, data leaks, and supply chain attacks. Use when writing endpoints, auth flows, queries, forms, uploads, or input handling.
---

# Security hardening

Harden every endpoint, form, and data path against vulnerabilities LLMs routinely ship.

## Steps

1. Identify which attack surfaces the current code touches.
2. Read the matching checklist for each surface.
3. Apply fixes inline during generation. Do not wait for the user to ask.
4. Flag unresolved gaps to the user with specific risk.

## Attack surfaces

Read only what the current task touches:

| Surface | Read | When |
|---------|------|------|
| Auth, sessions, passwords, access control | [auth.md](auth.md) | Login, signup, password reset, role checks, resource ownership |
| Injection, XSS, CSRF, deserialization, SSRF | [input.md](input.md) | Queries, form handlers, rendering user content, webhooks, cookies |
| Secrets, logging, headers, CORS, debug mode | [config.md](config.md) | API responses, env config, server setup, deployment, HTTPS |
| Rate limiting, uploads, dependencies | [surface.md](surface.md) | Public endpoints, file handling, package installation |
