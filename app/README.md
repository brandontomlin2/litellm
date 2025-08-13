LiteLLM App

This directory holds your organization-specific configuration and deployment for the LiteLLM Proxy.

Structure:
- config/: your proxy config files and any templates
- docker-compose.yml: local/dev compose that mounts your config
- .env.example: environment variables template for secrets and connection strings

Quickstart
1) Copy `.env.example` to `.env` and fill in keys
2) Put your model config in `config/proxy.config.yaml` (sample provided)
3) Start with Docker: `docker compose -f app/docker-compose.yml up --build`

Notes
- The compose uses the built image if available, otherwise builds from repo Dockerfile
- Mounts your config into the container at `/app/config.yaml` and passes `--config=/app/config.yaml`
- Postgres is included and data is persisted in a named volume
