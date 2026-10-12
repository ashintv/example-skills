# PostgreSQL Memory & Engine Tuning Reference

| Setting | Recommended Baseline | Purpose |
|---|---|---|
| `shared_buffers` | 25% of total server RAM | PostgreSQL internal page cache buffer |
| `effective_cache_size` | 50% to 75% of total server RAM | Planner assumption of OS filesystem cache |
| `work_mem` | 16MB to 64MB | Sort memory allocated per complex query operation |
| `maintenance_work_mem` | 512MB to 1GB | Memory allocated for VACUUM, CREATE INDEX, and ALTER TABLE |
| `wal_compression` | `on` | Reduces disk write amplification for write-heavy databases |
