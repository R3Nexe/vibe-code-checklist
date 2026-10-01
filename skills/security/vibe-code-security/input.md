# Input handling: injection, XSS, CSRF

## Injection and input validation

- Use parameterized queries or prepared statements, never string concatenation.
- Validate all user input server-side for type, length, format, and range.
- Reject user input in `eval()`, `exec()`, `child_process`, `Function()`, and template engines.
- Use allowlists over denylists for input validation.
- Sanitize file names and paths to block directory traversal (`../`).
- Reject untrusted deserialization. Validate schemas before deserializing external data ([source](https://innowise.com/blog/vibe-coding-security/)).
- Audit webhook handlers and URL-fetching for SSRF. Allowlist target hosts, reject private IP ranges ([source](https://www.ox.security/blog/vibe-coding-security/)).

## Cross-site scripting (XSS)

- Reject `dangerouslySetInnerHTML` and `v-html` with user-supplied content.
- Sanitize rendered HTML with DOMPurify or an equivalent library.
- Set `Content-Security-Policy` headers to restrict script and style sources.
- Use `textContent` instead of `innerHTML` for plain text.
- Escape output by context: HTML, JavaScript, URL, and CSS contexts each need distinct encoding.

## CSRF and client-side security

- Enforce CSRF tokens on all state-changing requests.
- Set `SameSite=Strict` or `SameSite=Lax` on cookies.
- Reject tokens, secrets, or PII in localStorage and sessionStorage.
- Validate `Origin` and `Referer` headers on sensitive endpoints.
- Set `X-Frame-Options: DENY` or CSP `frame-ancestors 'none'` to block clickjacking.
