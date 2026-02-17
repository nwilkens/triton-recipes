# Postal

[Postal](https://postal.atech.media/) is a complete open-source mail delivery platform for incoming and outgoing email.

## What Gets Deployed

- **Postal** (latest) on port **25** (SMTP)
- **MySQL 8** database via Triton recipe container

## Required Secrets

| Secret | Description |
|--------|-------------|
| `MYSQL_PASSWORD` | Password for the `postal` MySQL user |

## Environment Variables

| Variable | Default | Description |
|----------|---------|-------------|
| `MYSQL_HOST` | `mysql` | MySQL hostname (Docker DNS) |
| `MYSQL_DATABASE` | `postal` | Database name |
| `POSTAL_FNAME` | `Postal` | Display name |

## Post-Deploy

1. Run the initialization command to set up the database schema
2. Create an admin user via the CLI
3. Access the web UI to configure domains and routing rules
