# code-server

[code-server](https://coder.com/) runs VS Code in the browser, giving you a full development environment accessible from anywhere.

## What Gets Deployed

- **code-server** (latest) on port **8080**
- No database required

## Required Secrets

| Secret | Description |
|--------|-------------|
| `PASSWORD` | Password to access code-server |

## Environment Variables

| Variable | Default | Description |
|----------|---------|-------------|
| `PASSWORD` | (secret) | Login password |

## Post-Deploy

1. Visit `http://<your-url>:8080/` and enter your password
2. Install extensions from the marketplace
3. Open a terminal and start coding
