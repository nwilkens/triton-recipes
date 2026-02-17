# Directus

[Directus](https://directus.io/) is an instant REST and GraphQL API for any SQL database, with an intuitive no-code data studio.

## What Gets Deployed

- **Directus 11** on port **8055**
- **PostgreSQL 17** database via Triton recipe container

## Required Secrets

| Secret | Description |
|--------|-------------|
| `PGPASSWORD` | Password for the PostgreSQL `postgres` user |
| `ADMIN_PASSWORD` | Password for the initial admin account |
| `DIRECTUS_KEY` | Unique identifier for this project |
| `DIRECTUS_SECRET` | Secret used for signing tokens |

## Environment Variables

| Variable | Default | Description |
|----------|---------|-------------|
| `DB_CLIENT` | `pg` | Database driver |
| `DB_HOST` | `postgres` | PostgreSQL hostname (Docker DNS) |
| `ADMIN_EMAIL` | `admin@example.com` | Initial admin email |

## Post-Deploy

1. Visit `http://<your-url>:8055/` to log in with admin credentials
2. Create collections and configure fields in the Data Studio
3. Access REST API at `/items/<collection>` or GraphQL at `/graphql`
