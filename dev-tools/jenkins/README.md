# Jenkins

[Jenkins](https://www.jenkins.io/) is the leading open-source automation server for CI/CD pipelines, builds, and deployments.

## What Gets Deployed

- **Jenkins LTS** (JDK 21) on port **8080**
- No database required (uses embedded file storage)

## Required Secrets

No secrets required for initial setup.

## Environment Variables

| Variable | Default | Description |
|----------|---------|-------------|
| `JAVA_OPTS` | (see triton.toml) | JVM options |

## Post-Deploy

1. Visit `http://<your-url>:8080/` to start the setup wizard
2. Retrieve the initial admin password from container logs
3. Install suggested plugins and create your admin user
4. Create your first pipeline job
