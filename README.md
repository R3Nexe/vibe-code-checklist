# Vibe-Code Hardening Skills

Agent skills designed to catch vulnerabilities, compliance gaps, performance bottlenecks, and architectural traps in vibe-coded applications before they ship.

AI code assistants optimize for functional code that runs on the happy path. They routinely skip input sanitization, access checks, session timeouts, consent records, and database indexing. These skills instruct the agent to apply production discipline proactively.

## Skills catalog

### Model-invoked

The agent reaches for these automatically when your prompt touches the matching surface. You can also invoke them directly.

- **[vibe-code-security](skills/security/vibe-code-security/SKILL.md)**: Hardens endpoints, queries, auth flows, file uploads, and forms against injection, XSS, CSRF, data leaks, and supply chain attacks.
- **[vibe-code-compliance](skills/compliance/vibe-code-compliance/SKILL.md)**: Enforces consent flows, checks legal page requirements, and audits UI code against WCAG 2.1 Level AA accessibility standards.
- **[vibe-code-perf](skills/performance/vibe-code-perf/SKILL.md)**: Detects N+1 queries, indexes database columns, splits heavy bundles, and checks production deployment configurations.

### User-invoked

Only reachable when you type the name manually. It carries `disable-model-invocation: true` to avoid consuming context window tokens during regular coding.

- **[vibe-code-principles](skills/architecture/vibe-code-principles/SKILL.md)**: Reference guide with 26 distributed system laws, scaling principles, and resilience patterns for architecture reviews.

## Repository layout

Every skill adheres to the two-tier structure: a minimal `SKILL.md` (under 30 lines) containing trigger conditions and steps, backed by external reference files reached via context pointers.

```
skills/
├── security/
│   └── vibe-code-security/
│       ├── SKILL.md
│       ├── auth.md
│       ├── input.md
│       ├── config.md
│       └── surface.md
├── compliance/
│   └── vibe-code-compliance/
│       ├── SKILL.md
│       ├── legal.md
│       └── accessibility.md
├── performance/
│   └── vibe-code-perf/
│       ├── SKILL.md
│       ├── database.md
│       └── frontend.md
└── architecture/
    └── vibe-code-principles/
        ├── SKILL.md
        └── reference.md
```

## Installation

### Copy into your agent directory

Copy the skills folder directly into your local agent skills path:

```bash
# For Amp / omp agents
cp -r skills/* ~/.omp/agent/managed-skills/

# For Claude Code or custom .agents repos
cp -r skills/* .agents/skills/
```

### Using skills CLI

```bash
npx skills add R3Nexe/vibe-code-checklist
```

## Contributing

To contribute a new check or rule:

1. Locate the matching domain under `skills/<category>/<skill-name>/`.
2. Add the check to the corresponding reference markdown file.
3. Keep checks concise and actionable, using positive instructions with leading verbs (harden, reject, scope, enforce, strip).
4. If the check derives from a security report or audit, append the source link.

## License

[MIT](LICENSE)
