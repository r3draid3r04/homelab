# Huntarr

Automated missing media hunter for Sonarr and Radarr.

## Services

| Service | Image |
|---------|-------|
| huntarr | `ghcr.io/plexguide/huntarr:latest` |

## Ports

| Host | Container | Description |
|------|-----------|-------------|
| 9705 | 9705 | Web UI |

## Volumes

| Host Path | Container Path | Description |
|-----------|---------------|-------------|
| `/home/kyle/appdata/huntarr` | `/config` | Configuration files |

## Environment Variables

No configurable environment variables. TZ is hardcoded to `America/Chicago`.

## Networks

- `cn1` (external) - Shared Docker network for Traefik routing

## Links

- [GitHub](https://github.com/plexguide/huntarr)
