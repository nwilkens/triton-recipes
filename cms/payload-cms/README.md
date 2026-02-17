# Payload CMS

[Payload](https://payloadcms.com/) is a headless CMS and application framework built with TypeScript, offering both REST and GraphQL APIs.

## What Gets Deployed

- **Payload CMS** on Node.js 22 (slim image) on port **3000**
- **MongoDB 8** database via Triton recipe container

## Required Secrets

| Secret | Description |
|--------|-------------|
| `PAYLOAD_SECRET` | Secret key used for encrypting data and signing tokens |

## Environment Variables

| Variable | Default | Description |
|----------|---------|-------------|
| `MONGODB_URI` | `mongodb://mongo:27017/payload` | MongoDB connection string |
| `NODE_ENV` | `production` | Node environment |

## Post-Deploy

1. Visit `http://<your-url>:3000/admin` to create your first admin account
2. Define collections in the Payload config
3. Access REST API at `/api/<collection>` or GraphQL at `/api/graphql`
