# Rocket.Chat

[Rocket.Chat](https://rocket.chat/) is an open-source team communication platform with channels, direct messages, video conferencing, and integrations.

## What Gets Deployed

- **Rocket.Chat 7** on port **3000**
- **MongoDB 8** database via Triton recipe container

## Required Secrets

No secrets required for basic setup. MongoDB runs without authentication by default.

## Environment Variables

| Variable | Default | Description |
|----------|---------|-------------|
| `MONGO_URL` | `mongodb://mongo:27017/rocketchat` | MongoDB connection string |
| `ROOT_URL` | `http://localhost:3000` | Public URL for Rocket.Chat |

## Post-Deploy

1. Visit `http://<your-url>:3000/` to run the setup wizard
2. Create your admin account and configure organization info
3. Invite team members and create channels
