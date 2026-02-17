# Sentry

[Sentry](https://sentry.io/) is an application monitoring platform for error tracking, performance monitoring, and debugging in production.

## What Gets Deployed

- **Sentry** (latest) on port **9000**
- **PostgreSQL 17** database via Triton recipe container
- **Redis 7** cache via Triton recipe container

## Required Secrets

| Secret | Description |
|--------|-------------|
| `PGPASSWORD` | Password for the PostgreSQL `postgres` user |
| `SECRET_KEY` | Secret key for session signing and encryption |

## Environment Variables

| Variable | Default | Description |
|----------|---------|-------------|
| `SENTRY_POSTGRES_HOST` | `postgres` | PostgreSQL hostname (Docker DNS) |
| `SENTRY_REDIS_HOST` | `redis` | Redis hostname (Docker DNS) |

## Post-Deploy

1. Run database migrations: `sentry upgrade`
2. Create an admin user: `sentry createuser`
3. Visit `http://<your-url>:9000/` to configure your organization and projects
