# Tracearr

Activity tracker for *arr stack applications with built-in PostgreSQL and Redis.

## Services

| Service | Image |
|---------|-------|
| tracearr | `ghcr.io/connorgallopo/tracearr:supervised-next` |

## Ports

| Host | Container | Description |
|------|-----------|-------------|
| ${PORT:-3000} | 3000 | Web UI |

## Volumes

| Host Path | Container Path | Description |
|-----------|---------------|-------------|
| `tracearr_postgres` (named) | `/data/postgres` | PostgreSQL data |
| `tracearr_redis` (named) | `/data/redis` | Redis data |
| `tracearr_data` (named) | `/data/tracearr` | Application data |

## Environment Variables

| Variable | Required | Default | Description |
|----------|----------|---------|-------------|
| `PORT` | No | `3000` | Host port mapping |
| `TZ` | No | `UTC` | Timezone |
| `LOG_LEVEL` | No | `info` | Log verbosity |
| `HOSTNAME` | Yes | - | Traefik hostname |

## Networks

- `cn1` (external) - Shared Docker network for Traefik routing

## Health Check

Checks `/health` every 30 seconds.

## Links

- [GitHub](https://github.com/connorgallopo/tracearr)
