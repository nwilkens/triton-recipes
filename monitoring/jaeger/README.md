# Jaeger

[Jaeger](https://www.jaegertracing.io/) is an open-source distributed tracing platform for monitoring and troubleshooting microservices.

## What Gets Deployed

- **Jaeger All-in-One** (latest) on port **16686** (UI)
- No database required (uses in-memory storage by default)

## Required Secrets

No secrets required.

## Environment Variables

| Variable | Default | Description |
|----------|---------|-------------|
| `COLLECTOR_OTLP_ENABLED` | `true` | Enable OpenTelemetry collector |

## Post-Deploy

1. Visit `http://<your-url>:16686/` to access the Jaeger UI
2. Send traces via OpenTelemetry (port 4317/4318) or Jaeger protocol (port 14268)
3. Search and visualize distributed traces across your services
