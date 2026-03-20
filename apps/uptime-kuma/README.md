# Uptime Kuma

Self-hosted uptime monitoring tool with notifications and status pages.

## Services

| Service | Image |
|---------|-------|
| uptime-kuma | `louislam/uptime-kuma:2` |

## Ports

| Host | Container | Description |
|------|-----------|-------------|
| 3021 | 3001 | Web UI |

## Volumes

| Host Path | Container Path | Description |
|-----------|---------------|-------------|
| `uptime-kuma-data` (named) | `/app/data` | Application data |

## Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `HOSTNAME` | Yes | Traefik hostname |

## Networks

- `cn1` (external) - Shared Docker network for Traefik routing

## Links

- [Uptime Kuma](https://uptime.kuma.pet/)
- [GitHub](https://github.com/louislam/uptime-kuma)
