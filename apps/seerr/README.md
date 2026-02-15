# Seerr

Media request management tool (Jellyseerr) for Plex, Sonarr, and Radarr.

## Services

| Service | Image |
|---------|-------|
| seerr | `fallenbagel/jellyseerr:latest` |

## Ports

| Host | Container | Description |
|------|-----------|-------------|
| 5055 | 5055 | Web UI |

## Volumes

| Host Path | Container Path | Description |
|-----------|---------------|-------------|
| `/home/kyle/appdata/seerr/config` | `/app/config` | Configuration files |

## Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `HOSTNAME` | Yes | Traefik hostname |

## Networks

- `cn1` (external) - Shared Docker network for Traefik routing

## Health Check

Checks `/api/v1/status` every 15 seconds.

## Links

- [Jellyseerr](https://github.com/Fallenbagel/jellyseerr)
