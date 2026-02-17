# n8n

[n8n](https://n8n.io/) is a workflow automation tool that connects apps and services. Self-hosted alternative to Zapier.

## What Gets Deployed

- **n8n** (latest) running on Node.js
- **PostgreSQL 16** database via Triton recipe container
- Web UI on port **5678**

## Configuration

The `triton.toml` manifest configures n8n to use PostgreSQL via Docker DNS (`postgres:5432`). Workflow data and credentials are persisted in the database.

### Required Secrets

Set these in Triton Portal before deploying:

| Secret | Description |
|--------|-------------|
| `PGPASSWORD` | Password for the PostgreSQL `postgres` user |

### Environment Variables

| Variable | Default | Description |
|----------|---------|-------------|
| `N8N_PORT` | `5678` | Port for the n8n web UI |
| `N8N_PROTOCOL` | `http` | Protocol (`http` or `https`) |
| `GENERIC_TIMEZONE` | `UTC` | Timezone for scheduled workflows |
| `N8N_ENCRYPTION_KEY` | Auto-generated | Key for encrypting stored credentials |
| `WEBHOOK_URL` | Auto-detected | Public URL for incoming webhooks |

## Post-Deploy

1. Visit `http://<your-url>:5678/` to create your admin account
2. Start building workflows — n8n includes 400+ integrations out of the box
3. For production use, set `N8N_ENCRYPTION_KEY` as a secret to persist credential encryption across restarts

## Customization

To add custom nodes, fork this repo and install them in the Dockerfile:

```dockerfile
RUN cd /usr/local/lib/node_modules/n8n && npm install n8n-nodes-my-custom-node
```
