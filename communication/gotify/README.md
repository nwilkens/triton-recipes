# Gotify

[Gotify](https://gotify.net/) is a simple self-hosted push notification server with a REST API and WebSocket support.

## What Gets Deployed

- **Gotify** (latest) on port **80**
- No database required (uses embedded SQLite)

## Required Secrets

| Secret | Description |
|--------|-------------|
| `ADMIN_PASSWORD` | Password for the default `admin` user |

## Environment Variables

| Variable | Default | Description |
|----------|---------|-------------|
| `GOTIFY_DEFAULTUSER_NAME` | `admin` | Default admin username |
| `GOTIFY_DEFAULTUSER_PASS` | (secret) | Default admin password |

## Post-Deploy

1. Visit `http://<your-url>/` and log in with admin credentials
2. Create an application to get an API token
3. Send notifications via REST API: `curl http://<your-url>/message?token=<token> -F "title=Hello" -F "message=World"`
