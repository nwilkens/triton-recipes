# SonarQube

[SonarQube](https://www.sonarsource.com/products/sonarqube/) is a platform for continuous code quality inspection with static analysis for 30+ languages.

## What Gets Deployed

- **SonarQube Community Edition** on port **9000**
- **PostgreSQL 17** database via Triton recipe container

## Required Secrets

| Secret | Description |
|--------|-------------|
| `PGPASSWORD` | Password for the PostgreSQL `postgres` user |

## Environment Variables

| Variable | Default | Description |
|----------|---------|-------------|
| `SONAR_JDBC_URL` | `jdbc:postgresql://postgres:5432/sonarqube` | JDBC connection string |
| `SONAR_JDBC_USERNAME` | `postgres` | Database user |

## Post-Deploy

1. Visit `http://<your-url>:9000/` and log in with `admin` / `admin`
2. Change the default password immediately
3. Create a project and generate an analysis token
4. Run `sonar-scanner` in your CI pipeline
