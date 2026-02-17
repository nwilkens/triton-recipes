# Traggo

[Traggo](https://traggo.net/) is a tag-based time tracking tool with a clean UI and powerful reporting.

## What Gets Deployed

- **Traggo** (latest) on port **3030**
- No database required (uses embedded SQLite)

## Required Secrets

| Secret | Description |
|--------|-------------|
| `ADMIN_PASSWORD` | Password for the default `admin` user |

## Environment Variables

| Variable | Default | Description |
|----------|---------|-------------|
| `TRAGGO_DEFAULT_USER_NAME` | `admin` | Default admin username |
| `TRAGGO_DEFAULT_USER_PASS` | (secret) | Default admin password |

## Post-Deploy

1. Visit `http://<your-url>:3030/` and log in with admin credentials
2. Create tags and start tracking time
3. View reports and dashboards
