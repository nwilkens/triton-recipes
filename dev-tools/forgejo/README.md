# Forgejo

[Forgejo](https://forgejo.org/) is a self-hosted Git forge — a community-driven fork of Gitea focused on sustainability and openness.

## What Gets Deployed

- **Forgejo 9** on port **3000**
- **PostgreSQL 17** database via Triton recipe container

## Required Secrets

| Secret | Description |
|--------|-------------|
| `PGPASSWORD` | Password for the PostgreSQL `postgres` user |

## Environment Variables

| Variable | Default | Description |
|----------|---------|-------------|
| `FORGEJO__database__DB_TYPE` | `postgres` | Database driver |
| `FORGEJO__database__HOST` | `postgres:5432` | PostgreSQL hostname (Docker DNS) |
| `FORGEJO__server__ROOT_URL` | `http://localhost:3000` | Public URL |

## Post-Deploy

1. Visit `http://<your-url>:3000/` to run the initial setup wizard
2. Create your admin account
3. Create repositories and invite collaborators
