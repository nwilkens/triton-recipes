# Ghost

[Ghost](https://ghost.org/) is an open-source publishing platform for blogs, newsletters, and membership sites.

## What Gets Deployed

- **Ghost 5** running on Node.js (Alpine-based image)
- **MySQL 8** database via Triton recipe container
- Exposed on port **2368**

## Configuration

The `triton.toml` manifest configures Ghost to connect to a MySQL container on the same Docker network. Ghost uses double-underscore (`__`) notation for nested config.

### Required Secrets

Set these in Triton Portal before deploying:

| Secret | Description |
|--------|-------------|
| `MYSQL_PASSWORD` | Password for the `ghost` MySQL user |

### Environment Variables

| Variable | Default | Description |
|----------|---------|-------------|
| `url` | Auto-detected | Public URL for your Ghost site |
| `database__client` | `mysql` | Database driver |
| `database__connection__host` | `mysql` | MySQL hostname (Docker DNS) |

## Post-Deploy

1. Visit `http://<your-url>:2368/ghost/` to set up your admin account
2. Configure your site title, admin email, and first post

## Customization

To add a custom theme, fork this repo and place your theme in a `content/themes/` directory, then update the Dockerfile:

```dockerfile
COPY content/themes/my-theme /var/lib/ghost/content/themes/my-theme
```
