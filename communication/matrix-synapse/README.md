# Matrix Synapse

[Synapse](https://matrix.org/) is the reference homeserver for the Matrix decentralized communication protocol, supporting chat, VoIP, and bridging to other platforms.

## What Gets Deployed

- **Synapse** (latest) on port **8008**
- **PostgreSQL 17** database via Triton recipe container

## Required Secrets

| Secret | Description |
|--------|-------------|
| `PGPASSWORD` | Password for the PostgreSQL `postgres` user |

## Environment Variables

| Variable | Default | Description |
|----------|---------|-------------|
| `SYNAPSE_SERVER_NAME` | `localhost` | Matrix server domain name |
| `SYNAPSE_REPORT_STATS` | `no` | Report anonymous usage stats |
| `POSTGRES_HOST` | `postgres` | PostgreSQL hostname (Docker DNS) |

## Post-Deploy

1. Register an admin user: `docker exec synapse register_new_matrix_user -c /data/homeserver.yaml`
2. Connect using Element or any Matrix client at `http://<your-url>:8008`
3. Configure federation by setting `SYNAPSE_SERVER_NAME` to your public domain
