# Harbor

[Harbor](https://goharbor.io/) is an open-source container image registry with security scanning, RBAC, and replication.

## What Gets Deployed

- **Harbor** (latest) on port **80**
- **PostgreSQL 17** database via Triton recipe container
- **Redis 7** cache via Triton recipe container

## Required Secrets

| Secret | Description |
|--------|-------------|
| `PGPASSWORD` | Password for the PostgreSQL `postgres` user |
| `ADMIN_PASSWORD` | Password for the Harbor `admin` user |

## Environment Variables

| Variable | Default | Description |
|----------|---------|-------------|
| `POSTGRESQL_HOST` | `postgres` | PostgreSQL hostname (Docker DNS) |
| `REDIS_URL` | `redis://redis:6379/0` | Redis connection string |

## Post-Deploy

1. Visit `http://<your-url>/` and log in with `admin` and your configured password
2. Create a project to store container images
3. Push images: `docker push <your-url>/project/image:tag`
