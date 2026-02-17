# Mattermost

[Mattermost](https://mattermost.com/) is an open-source, self-hosted messaging platform — a Slack alternative for teams.

## What Gets Deployed

- **Mattermost Team Edition** on port **8065**
- **PostgreSQL 17** database via Triton recipe container

## Required Secrets

| Secret | Description |
|--------|-------------|
| `PGPASSWORD` | Password for the PostgreSQL `postgres` user |

## Environment Variables

| Variable | Default | Description |
|----------|---------|-------------|
| `MM_SQLSETTINGS_DRIVERNAME` | `postgres` | Database driver |
| `MM_SERVICESETTINGS_SITEURL` | `http://localhost:8065` | Public URL for your instance |

## Post-Deploy

1. Visit `http://<your-url>:8065/` to create your admin account
2. Create a team and invite members
3. Configure integrations and plugins from System Console
