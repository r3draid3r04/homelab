# FreshRSS

Self-hosted RSS feed aggregator with a clean web interface.

## Services

| Service | Image |
|---------|-------|
| freshrss | `freshrss/freshrss:latest` |

## Ports

Exposed via Traefik only (container port 80).

## Volumes

| Host Path | Container Path | Description |
|-----------|---------------|-------------|
| `/home/kyle/appdata/freshrss/data` | `/var/www/FreshRSS/data` | Application data |
| `/home/kyle/appdata/extensions` | `/var/www/FreshRSS/extensions` | Extensions |

## Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `HOSTNAME` | Yes | Traefik hostname |

## Networks

- `cn1` (external) - Shared Docker network for Traefik routing

## Links

- [FreshRSS](https://freshrss.org/)
- [GitHub](https://github.com/FreshRSS/FreshRSS)
