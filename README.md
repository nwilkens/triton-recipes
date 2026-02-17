# Triton Recipes

Ready-to-deploy application recipes for [Triton Portal](https://github.com/nwilkens/triton-portal). Each recipe includes a `triton.toml` manifest, a `Dockerfile`, and any configuration needed to run on Triton DataCenter.

## Available Recipes

| Recipe | Description | Stack |
|--------|-------------|-------|
| [ghost](./ghost/) | Modern publishing platform | Node.js + MySQL |
| [gitea](./gitea/) | Self-hosted Git service | Go + PostgreSQL |
| [n8n](./n8n/) | Workflow automation tool | Node.js + PostgreSQL |

## Usage

### Deploy with AI Assistant

1. Fork or clone the recipe you want
2. In Triton Portal, go to **Deploy > Deploy with AI**
3. Select your forked repo — the AI reads `triton.toml` and handles the rest

### Deploy Manually

1. Fork or clone the recipe
2. In Triton Portal, go to **Deploy > From GitHub**
3. Select the repo and branch
4. The portal reads `triton.toml` for configuration

## Writing Your Own Recipe

Create a `triton.toml` in your repo root:

```toml
app = "my-app"

[build]
runtime = "nodejs"           # nodejs, python, rust, go, docker
build_command = "npm run build"

[deploy]
start_command = "npm start"

[http]
port = 3000
health_check_path = "/health"

[env]
NODE_ENV = "production"

[vm]
package = "g1.xsmall"
instances = 1
```

If your repo includes a `Dockerfile`, it will be used directly. Otherwise, Triton auto-generates one based on the detected runtime.

## License

MIT
