# Strapi

[Strapi](https://strapi.io/) is the leading open-source headless CMS, fully customizable and developer-first.

## What Gets Deployed

- **Strapi** (latest) on port **1337**
- **PostgreSQL 17** database via Triton recipe container

## Required Secrets

| Secret | Description |
|--------|-------------|
| `PGPASSWORD` | Password for the PostgreSQL `postgres` user |

## Environment Variables

| Variable | Default | Description |
|----------|---------|-------------|
| `DATABASE_CLIENT` | `postgres` | Database driver |
| `DATABASE_HOST` | `postgres` | PostgreSQL hostname (Docker DNS) |
| `DATABASE_NAME` | `strapi` | Database name |
| `NODE_ENV` | `production` | Node environment |

## Post-Deploy

1. Visit `http://<your-url>:1337/admin` to create your first admin account
2. Define content types using the Content-Type Builder
3. Create API tokens for headless access
