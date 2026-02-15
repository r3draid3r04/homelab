# MediaScan

Plex media library scanner and analyzer for tracking media health.

## Services

| Service | Image |
|---------|-------|
| mediascan | `registry.kylerockwell.dev/docker/mediascan:0.3.3` |

## Ports

| Host | Container | Description |
|------|-----------|-------------|
| 3092 | 80 | Web UI |

## Volumes

| Host Path | Container Path | Description |
|-----------|---------------|-------------|
| `unraid-plex-media` (external) | `/media/Plex` | Plex media library |
| `/home/kyle/appdata/mediascan/config` | `/app/config` | Configuration files |

## Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `PLEX_BASE_URL` | Yes | Plex server URL |
| `PLEX_TOKEN` | Yes | Plex authentication token |

## Networks

- `cn1` (external) - Shared Docker network for Traefik routing

## Health Check

Checks `http://localhost/api/` every 30 seconds.
