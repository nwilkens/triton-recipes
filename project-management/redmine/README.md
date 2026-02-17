# Redmine

[Redmine](https://www.redmine.org/) is a flexible project management web application with issue tracking, wikis, and time tracking.

## What Gets Deployed

- **Redmine 5** on port **3000**
- **PostgreSQL 17** database via Triton recipe container

## Required Secrets

| Secret | Description |
|--------|-------------|
| `PGPASSWORD` | Password for the PostgreSQL `postgres` user |

## Environment Variables

| Variable | Default | Description |
|----------|---------|-------------|
| `REDMINE_DB_POSTGRES` | `postgres` | PostgreSQL hostname (Docker DNS) |
| `REDMINE_DB_DATABASE` | `redmine` | Database name |

## Post-Deploy

1. Visit `http://<your-url>:3000/` and log in with `admin` / `admin`
2. Change the default admin password immediately
3. Create projects, trackers, and custom fields
