# Prometheus

[Prometheus](https://prometheus.io/) is an open-source systems monitoring and alerting toolkit, the standard for cloud-native metrics.

## What Gets Deployed

- **Prometheus** (latest) on port **9090**
- No database required (uses embedded TSDB)

## Required Secrets

No secrets required.

## Environment Variables

| Variable | Default | Description |
|----------|---------|-------------|
| `PROMETHEUS_RETENTION_TIME` | `15d` | Data retention period |

## Post-Deploy

1. Visit `http://<your-url>:9090/` to access the Prometheus web UI
2. Configure scrape targets in `prometheus.yml`
3. Create alerting rules and connect to Alertmanager
4. Pair with Grafana for visualization
