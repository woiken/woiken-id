# Keycloak Config

Custom Keycloak Docker image with the [woiken/keycloak-theme](https://github.com/woiken/keycloak-theme).

## Features

- Based on official `quay.io/keycloak/keycloak:latest`
- Includes custom theme for Keycloak 22-25
- Health and metrics endpoints enabled
- PostgreSQL database support

## Usage

### Pull from GitHub Container Registry

```bash
docker pull ghcr.io/woiken/keycloak-config:latest
```

### Run with Docker Compose

```bash
docker compose up -d
```

### Development

```bash
docker compose -f docker-compose-dev.yml up -d
```

## CI/CD

The GitHub Actions workflow automatically:

1. Downloads the latest theme JAR from [woiken/keycloak-theme](https://github.com/woiken/keycloak-theme/releases)
2. Builds the Docker image
3. Pushes to `ghcr.io` with tags:
   - `latest`
   - `YYYYMMDD`
   - `YYYY-MM-DD-HHmmss`
   - Git SHA

Triggered on push to `main`/`master` or manually via workflow dispatch.
