# Triton Recipes

Ready-to-deploy application recipes for [Triton Portal](https://github.com/nwilkens/triton-portal). Each recipe is a `triton.toml` manifest that references a pre-built Docker image — no Dockerfile needed.

## How It Works

1. Browse recipes below or in the [catalog.toml](./catalog.toml)
2. In Triton Portal, go to **Deploy > From Recipe**
3. Select a recipe — the portal reads `triton.toml` and handles the rest
4. Provide any required secrets when prompted
5. Your app is deployed on Triton DataCenter

Each recipe uses pre-built Docker images. When deployed, the Triton Portal deploy engine creates an instance, pulls the image, starts any required database containers on a shared Docker network, and launches the app with the configured environment variables.

## Categories

| Category | Count | Description |
|----------|-------|-------------|
| [cms](./cms/) | 8 | Content Management Systems — Ghost, WordPress, Drupal, Strapi, Directus, KeystoneJS, Payload CMS, Hugo |
| [communication](./communication/) | 8 | Chat, messaging, email — Rocket.Chat, Mattermost, Matrix Synapse, Zulip, Listmonk, Postal, ntfy, Gotify |
| [project-management](./project-management/) | 8 | Project tracking, kanban, todos — Plane, Focalboard, Wekan, Vikunja, Taiga, Redmine, Leantime, Traggo |
| [dev-tools](./dev-tools/) | 10 | CI/CD, code hosting, registries — Gitea, Forgejo, Jenkins, Drone CI, Woodpecker CI, SonarQube, Sentry, Verdaccio, Harbor, code-server |
| [monitoring](./monitoring/) | 8 | Metrics, uptime, tracing — Grafana, Prometheus, Jaeger, Uptime Kuma, Cachet, Glances, Healthchecks, Changedetection |
| [analytics](./analytics/) | 5 | Web and product analytics — Plausible, Matomo, Umami, PostHog, Langfuse |
| [automation](./automation/) | 5 | Workflow and integration tools — n8n, Node-RED, Huginn, Activepieces, Windmill |
| [storage](./storage/) | 4 | File and object storage — Nextcloud, MinIO, FileBrowser, Paperless-ngx |
| [media](./media/) | 5 | Photos, video, music, books — Jellyfin, Immich, PhotoPrism, Navidrome, Audiobookshelf |
| [knowledge](./knowledge/) | 8 | Wikis, docs, notes — Wiki.js, BookStack, Outline, Docusaurus, MkDocs, Etherpad, HedgeDoc, Excalidraw |
| [ecommerce](./ecommerce/) | 3 | Online stores — Medusa, Saleor, PrestaShop |
| [security](./security/) | 6 | Auth, identity, passwords, VPN — Keycloak, Authentik, ZITADEL, Casdoor, Vaultwarden, WireGuard Easy |
| [ai](./ai/) | 12 | AI/ML tools — Ollama, Open WebUI, Label Studio, LocalAI, Flowise, Dify, LibreChat, AnythingLLM, Perplexica, Qdrant, ChromaDB, Whisper |
| [databases](./databases/) | 15 | Standalone databases — PostgreSQL, MySQL, MariaDB, MongoDB, Redis, ClickHouse, Cassandra, CockroachDB, TimescaleDB, Neo4j, SurrealDB, InfluxDB, PocketBase, Valkey, KeyDB |
| [networking](./networking/) | 5 | Proxies, DNS, ad blocking — Nginx Proxy Manager, Pi-hole, AdGuard Home, SearXNG, Portainer |
| [forms](./forms/) | 3 | Forms, surveys, chatbots — Typebot, HeyForm, LimeSurvey |
| [search](./search/) | 2 | Search engines — Meilisearch, Typesense |
| [nocode](./nocode/) | 4 | No-code / low-code platforms — NocoDB, Baserow, Hasura, Appwrite |
| [utilities](./utilities/) | 8 | Misc tools — Stirling PDF, IT Tools, Dashy, Homepage, Linkding, Wallabag, FreshRSS, draw.io |
| [scheduling](./scheduling/) | 1 | Booking and calendars — Cal.com |
| **Total** | **128** | |

## Recipe Format

Each recipe directory contains:

- **`triton.toml`** — Deployment manifest with image, port, environment variables, and VM size
- **`README.md`** — Description, secrets, env vars, and post-deploy instructions

Example `triton.toml`:

```toml
app = "ghost"

[build]
runtime = "docker"
image = "ghost:5-alpine"

[http]
port = 2368
health_check_path = "/ghost/api/admin/site/"

[env]
NODE_ENV = "production"
database__client = "mysql"
database__connection__host = "mysql"
database__connection__password = "${{secrets.MYSQL_PASSWORD}}"

[vm]
package = "g1.small"
instances = 1
```

### Key Conventions

- `[build].image` — Pre-built Docker image to pull. No Dockerfile needed.
- `[env]` — Environment variables passed to the container. Use `${{secrets.VAR}}` for sensitive values.
- Database hostnames use Docker container names: `postgres`, `mysql`, `redis`, `mongo`
- `[vm].package` — Triton package size: `g1.xsmall` (light), `g1.small` (medium), `g1.medium` (heavy)

## Contributing

1. Create a new directory under the appropriate category
2. Add `triton.toml` and `README.md` following the format above
3. Update `catalog.toml` with the new recipe entry
4. Submit a pull request

## License

MIT
