# Immich

Self-hosted photo and video management platform with machine learning features.

## Services

| Service | Image | Description |
|---------|-------|-------------|
| immich-server | `ghcr.io/immich-app/immich-server` | Main API and web server |
| immich-machine-learning | `ghcr.io/immich-app/immich-machine-learning` | ML model inference |
| redis | `redis:6.2-alpine` | Cache layer |
| database | `ghcr.io/immich-app/postgres` | PostgreSQL with vector extensions |
| power-tools | `ghcr.io/varun-raj/immich-power-tools` | Immich management tools |

## Ports

| Host | Container | Service | Description |
|------|-----------|---------|-------------|
| 2283 | 2283 | immich-server | Web UI and API |
| 5432 | 5432 | database | PostgreSQL |

## Volumes

| Host Path | Container Path | Description |
|-----------|---------------|-------------|
| `${UPLOAD_LOCATION}` | `/usr/src/app/upload` | Photo/video uploads |
| `/etc/localtime` | `/etc/localtime` | System time (read-only) |
| `synology-photos` (external) | `/usr/src/app/external/synology` | External Synology photos |
| `model-cache` | `/cache` | ML model cache |
| `${DB_DATA_LOCATION}` | `/var/lib/postgresql/data` | Database storage |

## Environment Variables

| Variable | Required | Default | Description |
|----------|----------|---------|-------------|
| `IMMICH_VERSION` | No | `release` | Immich Docker image tag |
| `UPLOAD_LOCATION` | Yes | - | Host path for photo uploads |
| `DB_PASSWORD` | Yes | - | PostgreSQL password |
| `DB_USERNAME` | Yes | - | PostgreSQL username |
| `DB_DATABASE_NAME` | Yes | - | PostgreSQL database name |
| `DB_DATA_LOCATION` | Yes | - | Host path for database storage |
| `HOSTNAME` | Yes | - | Traefik hostname for power-tools |

## Networks

- `cn1` (external) - Shared Docker network for Traefik routing

## Links

- [Immich](https://immich.app/)
- [GitHub](https://github.com/immich-app/immich)
- [Immich Power Tools](https://github.com/varun-raj/immich-power-tools)
