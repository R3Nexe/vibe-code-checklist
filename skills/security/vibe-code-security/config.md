# Server config: secrets, headers, exposure

## Sensitive data exposure

- Isolate all secrets in environment variables, never in source code or client bundles.
- Scope database credentials to least privilege, never use the master or root key.
- Strip passwords, tokens, card numbers, and PII from logs.
- Add `.env` to `.gitignore`. Audit git history for previously leaked secrets.
- Strip sensitive fields from API responses (password hashes, internal IDs, debug info).
- Encrypt PII and payment data at rest.
- Use short-lived tokens with refresh rotation.

## Security misconfiguration

- Force HTTPS everywhere (HSTS header, redirect HTTP to HTTPS).
- Scope CORS to specific origins, never `Access-Control-Allow-Origin: *` in production.
- Disable debug mode, stack traces, and verbose errors in production.
- Strip default credentials, sample data, and test accounts before deploy.
- Set security headers: `X-Content-Type-Options: nosniff`, `Referrer-Policy`, `Permissions-Policy`.
- Strip server version headers (`X-Powered-By`, `Server`).
