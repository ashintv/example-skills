# PostgreSQL Production Verification Checklist

## Query & Plan Inspection
- [ ] Every slow query inspected with `EXPLAIN (ANALYZE, BUFFERS, TIMING)`.
- [ ] No sequential scans on tables exceeding 5,000 rows.
- [ ] No `SELECT *` across large text, bytea, or jsonb TOAST columns in high-throughput endpoints.
- [ ] Join columns and foreign keys have dedicated indexes.
- [ ] Composite indexes match query filtering order: equality columns first, followed by range/order columns.

## Migration & DDL Safety
- [ ] Indexes created using `CONCURRENTLY`.
- [ ] Migration lock timeouts set explicitly (`SET lock_timeout = '5s'`) to prevent transaction queues from starving traffic.
- [ ] Connection poolers (e.g. PgBouncer) configured with transaction-level pooling for high concurrency.
- [ ] Autovacuum parameters tuned for write-heavy update tables.
