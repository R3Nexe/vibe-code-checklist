---
name: vibe-code-perf
description: Optimize database queries, split bundles, enforce caching, verify production config. Use when writing schemas, handling images, configuring caching, or setting up deployment.
---

# Performance and infrastructure

Optimize queries, split bundles, enforce caching, verify production readiness. Vibe-coded apps work on localhost with 10 rows and one user. These checks prevent collapse at scale.

## Steps

1. Identify perf-relevant code: database queries, image handling, JS bundles, deployment config.
2. Read the matching checklist.
3. Apply optimizations inline during generation.
4. Flag scaling risks the user has not planned for.

## Checklists

| Surface | Read | When |
|---------|------|------|
| Indexes, N+1, pagination, backups, slow queries | [database.md](database.md) | Schema design, queries, migrations |
| Images, bundles, caching, code splitting, deployment | [frontend.md](frontend.md) | UI code, build config, deployment setup, error handling |
