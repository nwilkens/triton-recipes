# Plane

[Plane](https://plane.so/) is an open-source project management tool — a self-hosted alternative to Jira and Linear.

## What Gets Deployed

- **Plane** (latest) on port **3000**
- **PostgreSQL 17** database via Triton recipe container
- **Redis 7** cache via Triton recipe container

## Required Secrets

| Secret | Description |
|--------|-------------|
| `PGPASSWORD` | Password for the PostgreSQL `postgres` user |
| `SECRET_KEY` | Secret key for session signing |

## Environment Variables

| Variable | Default | Description |
|----------|---------|-------------|
| `DATABASE_URL` | `postgres://...@postgres:5432/plane` | PostgreSQL connection string |
| `REDIS_URL` | `redis://redis:6379` | Redis connection string |

## Post-Deploy

1. Visit `http://<your-url>:3000/` to create your workspace
2. Set up your first project with issues and cycles
3. Invite team members and configure integrations
