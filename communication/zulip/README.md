# Zulip

[Zulip](https://zulip.com/) is a powerful open-source group chat application with topic-based threading for organized conversations.

## What Gets Deployed

- **Zulip** (latest) on port **443**
- **PostgreSQL 17** database via Triton recipe container
- **Redis 7** cache via Triton recipe container

## Required Secrets

| Secret | Description |
|--------|-------------|
| `PGPASSWORD` | Password for the PostgreSQL `postgres` user |

## Environment Variables

| Variable | Default | Description |
|----------|---------|-------------|
| `SETTING_EXTERNAL_HOST` | `localhost` | Public hostname for Zulip |
| `SETTING_ZULIP_ADMINISTRATOR` | `admin@example.com` | Admin email address |
| `DB_HOST` | `postgres` | PostgreSQL hostname (Docker DNS) |
| `SETTING_REDIS_HOST` | `redis` | Redis hostname (Docker DNS) |

## Post-Deploy

1. Visit `http://<your-url>/` and log in with the admin email
2. Create your Zulip organization
3. Configure streams (channels) and invite team members
