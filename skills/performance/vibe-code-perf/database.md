# Database and data layer

## Schema and queries

- Add indexes on all columns used in WHERE, JOIN, and ORDER BY clauses.
- Use database migrations, never manual schema alterations.
- Paginate all list queries using LIMIT with OFFSET or cursor-based pagination.
- Use connection pooling, never open a separate database connection per request.
- Set up automated backups with verified restore procedures.
- Enable slow query logging during development and staging.

## Pitfalls in generated code

- Audit for N+1 queries. AI assistants often nest queries inside loops instead of joining or batching ([source](https://www.producthunt.com/p/vibecoding/what-broke-first-when-you-tried-to-scale-a-vibe-coded-project)).
- Audit for redundant tables. AI assistants tend to create new tables instead of normalizing relationships.
- Profile queries with realistic data volumes. Indexing strategies that succeed on 100 sample rows often fail on 100,000 rows ([source](https://seedium.io/blog/how-to-scale-your-vibe-coded-app/)).
