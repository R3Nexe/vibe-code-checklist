# Frontend, bundles, and infrastructure

## Performance and bundles

- Compress and resize images. Serve modern formats such as WebP and AVIF, and provide `srcset` for responsive sizing.
- Never serve full-resolution original media assets to the client.
- Code-split routes and heavy dependencies through dynamic imports.
- Add explicit loading states and skeleton views for asynchronous data.
- Cache fetched responses using libraries such as SWR or TanStack Query, and configure HTTP cache headers.
- Never refetch entire datasets on every client navigation. Use targeted cache invalidation.
- Tree-shake unused code and audit bundle size during CI builds.
- Serve static assets through a content delivery network (CDN).

## Pitfalls in generated code

- Review loops and recursion for O(n^2) algorithms. LLMs often miss native language methods optimized in C or Rust ([source](https://sense.eng.uwaterloo.ca/pubs/EMSE_2026_SHUANG_LI.pdf)).
- Prune duplicated logic blocks. Code generators routinely duplicate logic instead of refactoring shared helpers ([source](https://www.infoworld.com/article/3844363/why-ai-generated-code-isnt-good-enough-and-how-it-will-get-better.html)).
- Verify UI success indicators match backend persistence. Generated handlers sometimes render success before writes succeed ([source](https://dev.to/ail_akram_dcc5063c428734b/why-vibe-coding-fails-and-how-to-fix-it-a-complete-guide-for-2026-3gj1)).

## Infrastructure and deployment

- Configure application error tracking with tools such as Sentry.
- Establish automated database backups with defined retention policies.
- Build a CI/CD pipeline running automated tests before deploying.
- Expose health check endpoints for uptime monitoring.
- Aggregate logs with automated alerts on error rate spikes.
- Strip dev-time permissive settings, including open database ports and debug credentials, before shipping to production ([source](https://platformengineering.org/events/vibe-coding-vs-reality-how-to-stay-in-flow-without-shipping-misconfigurations-2025-08-28)).
- Validate error handling along non-happy paths. Generated code often omits recovery logic for network and database timeouts ([source](https://dev.to/ail_akram_dcc5063c428734b/why-vibe-coding-fails-and-how-to-fix-it-a-complete-guide-for-2026-3gj1)).
