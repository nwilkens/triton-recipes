# Grafana

[Grafana](https://grafana.com/) is the open-source platform for monitoring and observability with beautiful dashboards and alerting.

## What Gets Deployed

- **Grafana** (latest) on port **3000**
- **PostgreSQL 17** database via Triton recipe container

## Required Secrets

| Secret | Description |
|--------|-------------|
| `PGPASSWORD` | Password for the PostgreSQL `postgres` user |
| `ADMIN_PASSWORD` | Password for the Grafana `admin` user |

## Environment Variables

| Variable | Default | Description |
|----------|---------|-------------|
| `GF_DATABASE_TYPE` | `postgres` | Database driver |
| `GF_DATABASE_HOST` | `postgres:5432` | PostgreSQL hostname (Docker DNS) |

## Post-Deploy

1. Visit `http://<your-url>:3000/` and log in with `admin` and your configured password
2. Add data sources (Prometheus, InfluxDB, etc.)
3. Import or create dashboards
