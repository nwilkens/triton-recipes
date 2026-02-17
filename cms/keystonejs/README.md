# KeystoneJS

[KeystoneJS](https://keystonejs.com/) is a powerful headless CMS and application framework built on Node.js with GraphQL.

## What Gets Deployed

- **KeystoneJS** on Node.js 22 (slim image) on port **3000**
- **PostgreSQL 17** database via Triton recipe container

## Required Secrets

| Secret | Description |
|--------|-------------|
| `PGPASSWORD` | Password for the PostgreSQL `postgres` user |

## Environment Variables

| Variable | Default | Description |
|----------|---------|-------------|
| `DATABASE_URL` | `postgres://postgres:...@postgres:5432/keystone` | PostgreSQL connection string |
| `NODE_ENV` | `production` | Node environment |

## Post-Deploy

1. Visit `http://<your-url>:3000/` to access the KeystoneJS admin UI
2. Create your initial admin user
3. Define your schema in the Keystone config and redeploy
