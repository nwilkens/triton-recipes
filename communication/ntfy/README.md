# ntfy

[ntfy](https://ntfy.sh/) is a simple HTTP-based pub-sub notification service. Send push notifications to your phone or desktop via scripts.

## What Gets Deployed

- **ntfy** (latest) on port **80**
- No database required

## Required Secrets

No secrets required.

## Environment Variables

| Variable | Default | Description |
|----------|---------|-------------|
| `NTFY_BASE_URL` | `http://localhost` | Public URL for the ntfy server |
| `NTFY_UPSTREAM_BASE_URL` | `https://ntfy.sh` | Upstream ntfy server for push relay |

## Post-Deploy

1. Visit `http://<your-url>/` to access the ntfy web UI
2. Subscribe to a topic and send a test notification: `curl -d "Hello" http://<your-url>/test`
3. Install the ntfy app on your phone for mobile push notifications
