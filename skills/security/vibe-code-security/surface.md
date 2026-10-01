# External surface: rate limiting, uploads, dependencies

## Rate limiting and bot protection

- Rate limit all auth endpoints (login, register, password reset, OTP verification).
- Enforce CAPTCHA or bot protection on signups and public forms.
- Set billing alerts and spending caps on cloud services to prevent surprise bills from denial of service attacks.
- Rate limit API endpoints per-user and globally.
- Enforce request size limits and pagination on all list endpoints.
- Set timeout limits on long-running operations.

## File upload and storage

- Validate file type server-side by checking magic bytes, not just the file extension.
- Enforce file size limits.
- Generate random file names, never use user-provided names directly.
- Isolate uploads outside webroot or on a separate domain or object store.
- Set `Content-Disposition: attachment` on downloads to block browser execution.
- Scan uploads for malware when practical.

## Dependency and supply chain

- Pin dependency versions, never use `latest` or `*`.
- Commit lockfiles (`package-lock.json`, `yarn.lock`, `Pipfile.lock`).
- Run `npm audit` or `pip audit` regularly.
- Audit third-party SDKs for data collection and permission scope.
- Verify AI-suggested packages exist on the registry before installing.
- Prefer well-maintained packages with proven security records.
