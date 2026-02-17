# Vikunja

[Vikunja](https://vikunja.io/) is an open-source to-do app with lists, kanban boards, gantt charts, and CalDAV support.

## What Gets Deployed

- **Vikunja** (latest) on port **3456**
- **PostgreSQL 17** database via Triton recipe container

## Required Secrets

| Secret | Description |
|--------|-------------|
| `PGPASSWORD` | Password for the PostgreSQL `postgres` user |

## Environment Variables

| Variable | Default | Description |
|----------|---------|-------------|
| `VIKUNJA_DATABASE_TYPE` | `postgres` | Database driver |
| `VIKUNJA_DATABASE_HOST` | `postgres` | PostgreSQL hostname (Docker DNS) |
| `VIKUNJA_SERVICE_FRONTENDURL` | `http://localhost:3456/` | Public URL |

## Post-Deploy

1. Visit `http://<your-url>:3456/` to create your account
2. Create projects, tasks, and assign labels
3. Use CalDAV sync with your calendar app
