# Hugo

[Hugo](https://gohugo.io/) is a fast static site generator written in Go, ideal for blogs, documentation, and landing pages.

## What Gets Deployed

- **Hugo** (extended Alpine image) on port **1313**
- No database required

## Required Secrets

No secrets required.

## Environment Variables

| Variable | Default | Description |
|----------|---------|-------------|
| `HUGO_ENV` | `production` | Hugo environment |

## Post-Deploy

1. Visit `http://<your-url>:1313/` to see your Hugo site
2. Add content by placing Markdown files in the `content/` directory
3. Choose a theme from [themes.gohugo.io](https://themes.gohugo.io/)
