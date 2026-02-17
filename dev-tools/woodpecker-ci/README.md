# Woodpecker CI

[Woodpecker CI](https://woodpecker-ci.org/) is a community-driven fork of Drone CI — a simple, container-native CI/CD engine.

## What Gets Deployed

- **Woodpecker CI** (latest) on port **8000**
- **PostgreSQL 17** database via Triton recipe container

## Required Secrets

| Secret | Description |
|--------|-------------|
| `PGPASSWORD` | Password for the PostgreSQL `postgres` user |
| `AGENT_SECRET` | Shared secret for agent authentication |

## Environment Variables

| Variable | Default | Description |
|----------|---------|-------------|
| `WOODPECKER_HOST` | `http://localhost:8000` | Public URL |
| `WOODPECKER_DATABASE_DRIVER` | `postgres` | Database driver |

## Post-Deploy

1. Visit `http://<your-url>:8000/` and authenticate via your Git forge
2. Activate repositories for CI builds
3. Add a `.woodpecker.yml` pipeline to your repos
