# Wekan

[Wekan](https://wekan.github.io/) is an open-source kanban board — a self-hosted alternative to Trello.

## What Gets Deployed

- **Wekan** (latest) on port **8080**
- **MongoDB 8** database via Triton recipe container

## Required Secrets

No secrets required. MongoDB runs without authentication by default.

## Environment Variables

| Variable | Default | Description |
|----------|---------|-------------|
| `MONGO_URL` | `mongodb://mongo:27017/wekan` | MongoDB connection string |
| `ROOT_URL` | `http://localhost:8080` | Public URL for Wekan |

## Post-Deploy

1. Visit `http://<your-url>:8080/` to register your admin account
2. Create boards, lists, and cards
3. Invite team members and assign tasks
