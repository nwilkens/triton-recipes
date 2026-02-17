# Listmonk

[Listmonk](https://listmonk.app/) is a self-hosted newsletter and mailing list manager with a modern dashboard.

## What Gets Deployed

- **Listmonk** (latest) on port **9000**
- **PostgreSQL 17** database via Triton recipe container

## Required Secrets

| Secret | Description |
|--------|-------------|
| `PGPASSWORD` | Password for the PostgreSQL `postgres` user |

## Environment Variables

| Variable | Default | Description |
|----------|---------|-------------|
| `LISTMONK_db__host` | `postgres` | PostgreSQL hostname (Docker DNS) |
| `LISTMONK_db__database` | `listmonk` | Database name |
| `LISTMONK_app__address` | `0.0.0.0:9000` | Listen address |

## Post-Deploy

1. Visit `http://<your-url>:9000/` to access the admin dashboard
2. Configure SMTP settings for sending emails
3. Create mailing lists and import subscribers
