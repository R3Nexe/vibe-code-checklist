# Auth, sessions, and access control

## Authentication and sessions

- Hash passwords with bcrypt, scrypt, or argon2, never plain text.
- Store session tokens in `httpOnly`, `Secure`, `SameSite` cookies, never `localStorage`.
- Set session expiry, both idle timeout and absolute timeout.
- Rate limit `/login`, `/register`, and `/reset-password` (5 attempts per minute).
- Enforce 2FA or OTP for sensitive accounts.
- Check passwords against breach databases using the Have I Been Pwned API.
- Enforce password rules client-side and server-side (minimum length, complexity).
- Password reset links must be single-use, 15 minutes maximum lifetime.
- Invalidate all sessions on password change.
- Use constant-time comparison for tokens and passwords to prevent timing attacks.

## Authorization

- Enforce all authorization server-side, never trust client-side role checks.
- Verify resource ownership on every request (`WHERE user_id = ?`).
- Use UUIDs or opaque IDs, never sequential integers for sensitive resources.
- Centralize access control with RBAC or ABAC, do not scatter role checks across files.
- Deny by default: grant access explicitly, never deny explicitly.
