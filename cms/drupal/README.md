# Drupal

[Drupal](https://www.drupal.org/) is a flexible, open-source content management platform used by millions of websites worldwide.

## What Gets Deployed

- **Drupal 11** (PHP 8.3 image) on port **80**
- **MySQL 8** database via Triton recipe container

## Required Secrets

| Secret | Description |
|--------|-------------|
| `MYSQL_PASSWORD` | Password for the `drupal` MySQL user |

## Environment Variables

| Variable | Default | Description |
|----------|---------|-------------|
| `DRUPAL_DB_DRIVER` | `mysql` | Database driver |
| `DRUPAL_DB_HOST` | `mysql` | MySQL hostname (Docker DNS) |
| `DRUPAL_DB_NAME` | `drupal` | Database name |

## Post-Deploy

1. Visit `http://<your-url>/` to run the Drupal installation wizard
2. Choose Standard or Minimal install profile
3. Configure site name, admin account, and regional settings
