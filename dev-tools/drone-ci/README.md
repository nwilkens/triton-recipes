# Drone CI

[Drone](https://www.drone.io/) is a container-native continuous integration platform with pipeline-as-code configuration.

## What Gets Deployed

- **Drone 2** on port **80**
- **PostgreSQL 17** database via Triton recipe container

## Required Secrets

| Secret | Description |
|--------|-------------|
| `PGPASSWORD` | Password for the PostgreSQL `postgres` user |
| `DRONE_RPC_SECRET` | Shared secret for runner authentication |

## Environment Variables

| Variable | Default | Description |
|----------|---------|-------------|
| `DRONE_SERVER_HOST` | `localhost` | Public hostname |
| `DRONE_SERVER_PROTO` | `http` | Protocol (`http` or `https`) |
| `DRONE_DATABASE_DRIVER` | `postgres` | Database driver |

## Post-Deploy

1. Visit `http://<your-url>/` and authenticate via your Git provider
2. Activate repositories for CI builds
3. Add a `.drone.yml` pipeline to your repos
