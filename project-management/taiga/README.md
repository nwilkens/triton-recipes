# Taiga

[Taiga](https://taiga.io/) is an open-source agile project management platform for scrum and kanban teams.

## What Gets Deployed

- **Taiga** (latest) on port **9000**
- **PostgreSQL 17** database via Triton recipe container
- **Redis 7** cache via Triton recipe container

## Required Secrets

| Secret | Description |
|--------|-------------|
| `PGPASSWORD` | Password for the PostgreSQL `postgres` user |
| `SECRET_KEY` | Django secret key for session signing |

## Environment Variables

| Variable | Default | Description |
|----------|---------|-------------|
| `POSTGRES_HOST` | `postgres` | PostgreSQL hostname (Docker DNS) |
| `POSTGRES_DB` | `taiga` | Database name |

## Post-Deploy

1. Visit `http://<your-url>:9000/` to access Taiga
2. Create a project using scrum or kanban templates
3. Set up sprints, user stories, and tasks
