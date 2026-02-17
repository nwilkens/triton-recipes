# Gitea

[Gitea](https://gitea.io/) is a lightweight, self-hosted Git service. Fork of Gogs, written in Go.

## What Gets Deployed

- **Gitea 1.22** (rootless image)
- **PostgreSQL 16** database via Triton recipe container
- Web UI on port **3000**, SSH on port **22**

## Configuration

The `triton.toml` manifest configures Gitea to use PostgreSQL via Docker DNS (`postgres:5432`). Gitea reads environment variables using double-underscore (`__`) section notation.

### Required Secrets

Set these in Triton Portal before deploying:

| Secret | Description |
|--------|-------------|
| `PGPASSWORD` | Password for the PostgreSQL `postgres` user |

### Environment Variables

| Variable | Default | Description |
|----------|---------|-------------|
| `GITEA__server__ROOT_URL` | `http://localhost:3000` | Public URL for your Gitea instance |
| `GITEA__server__SSH_DOMAIN` | `localhost` | Domain for SSH clone URLs |
| `GITEA__database__DB_TYPE` | `postgres` | Database driver |

## Post-Deploy

1. Visit `http://<your-url>:3000/` to run the initial setup wizard
2. Create your admin account
3. Configure SSH access if needed (port 22 is exposed)

## Customization

To add custom templates or themes, fork this repo and mount them into the container:

```dockerfile
COPY custom/ /var/lib/gitea/custom/
```
