# Posthog Reverse Proxy

Provides a Docker image for hosting a reverse proxy to Posthog based on Caddy (alpine).

Based on the following documentation: https://posthog.com/docs/integrate/proxy

## Getting it to run on Azure App Services

Note that this expects traffic from port `8080`. In order to get this to work on Azure App Services, make sure to create a corresponding environment variable / Application Setting:

Name: `WEBSITES_PORT`

Value: `8080`

## Proxying to Posthog US

Caddy is configured to point to `eu.posthog.com`. If you have Posthog Cloud hosted in US, make sure to change the corresponding line within `Caddyfile` to `app.posthog.com`.

## Usage

This will expose your container on `localhost:8080`

```powershell
docker build -t posthog-proxy . && docker run -p 8080:8080 posthog-proxy
```

## Pull directly from Docker Hub

For your convenience: https://hub.docker.com/r/schwindelig/posthog-docker-caddy-reverse-proxy

Note that this is for Posthog EU
