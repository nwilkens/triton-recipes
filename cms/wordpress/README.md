# WordPress

[WordPress](https://wordpress.org/) is the world's most popular open-source content management system, powering over 40% of the web.

## What Gets Deployed

- **WordPress 6** (PHP 8.3 image) on port **80**
- **MySQL 8** database via Triton recipe container

## Required Secrets

| Secret | Description |
|--------|-------------|
| `MYSQL_PASSWORD` | Password for the `wordpress` MySQL user |

## Environment Variables

| Variable | Default | Description |
|----------|---------|-------------|
| `WORDPRESS_DB_HOST` | `mysql` | MySQL hostname (Docker DNS) |
| `WORDPRESS_DB_USER` | `wordpress` | Database user |
| `WORDPRESS_DB_NAME` | `wordpress` | Database name |

## Post-Deploy

1. Visit `http://<your-url>/` to run the WordPress installation wizard
2. Choose your language, set site title, and create admin account
3. Install themes and plugins from the dashboard
