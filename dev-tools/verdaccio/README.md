# Verdaccio

[Verdaccio](https://verdaccio.org/) is a lightweight private npm registry and proxy cache for Node.js packages.

## What Gets Deployed

- **Verdaccio** (latest) on port **4873**
- No database required (uses embedded file storage)

## Required Secrets

No secrets required.

## Environment Variables

| Variable | Default | Description |
|----------|---------|-------------|
| `VERDACCIO_PORT` | `4873` | Port for the registry |

## Post-Deploy

1. Visit `http://<your-url>:4873/` to browse packages
2. Configure npm to use your registry: `npm set registry http://<your-url>:4873/`
3. Register a user: `npm adduser --registry http://<your-url>:4873/`
4. Publish packages: `npm publish --registry http://<your-url>:4873/`
