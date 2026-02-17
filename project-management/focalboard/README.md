# Focalboard

[Focalboard](https://www.focalboard.com/) is an open-source project management tool by Mattermost — a self-hosted alternative to Trello, Notion, and Asana.

## What Gets Deployed

- **Focalboard** (latest) on port **8000**
- **PostgreSQL 17** database via Triton recipe container

## Required Secrets

| Secret | Description |
|--------|-------------|
| `PGPASSWORD` | Password for the PostgreSQL `postgres` user |

## Environment Variables

| Variable | Default | Description |
|----------|---------|-------------|
| `FOCALBOARD_DB_TYPE` | `postgres` | Database driver |
| `FOCALBOARD_DB_CONFIG` | `postgres://...@postgres:5432/focalboard` | PostgreSQL connection string |

## Post-Deploy

1. Visit `http://<your-url>:8000/` to create your account
2. Create boards with kanban, table, gallery, or calendar views
3. Share boards with your team
