# ImmichStats

Statistics dashboard for Immich photo library.

## Services

| Service | Image |
|---------|-------|
| immichstat | `registry.kylerockwell.dev/docker/immichstats:latest` |

## Ports

Exposed via Traefik only (container port 3000).

## Volumes

No volumes mounted.

## Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `IMMICH_URL` | Yes | Immich server URL |
| `IMMICH_API_KEY` | Yes | Immich API key |
| `DATABASE_URL` | Yes | Database connection string |
| `HOSTNAME` | Yes | Traefik hostname |

## Networks

- `cn1` (external) - Shared Docker network for Traefik routing
