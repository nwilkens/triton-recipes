# Leantime

[Leantime](https://leantime.io/) is an open-source project management system designed for non-project-managers, with kanban, timesheets, and strategy boards.

## What Gets Deployed

- **Leantime** (latest) on port **80**
- **MySQL 8** database via Triton recipe container

## Required Secrets

| Secret | Description |
|--------|-------------|
| `MYSQL_PASSWORD` | Password for the `leantime` MySQL user |

## Environment Variables

| Variable | Default | Description |
|----------|---------|-------------|
| `LEAN_DB_HOST` | `mysql` | MySQL hostname (Docker DNS) |
| `LEAN_DB_DATABASE` | `leantime` | Database name |

## Post-Deploy

1. Visit `http://<your-url>/` to run the installation wizard
2. Create your admin account and first project
3. Set up milestones, to-dos, and timesheets
