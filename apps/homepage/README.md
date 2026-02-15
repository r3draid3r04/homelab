# Homepage

Modern application dashboard with service integrations and Docker support.

## Services

| Service | Image |
|---------|-------|
| homepage | `ghcr.io/gethomepage/homepage:latest` |

## Ports

Exposed via Traefik only (container port 3000).

## Volumes

| Host Path | Container Path | Description |
|-----------|---------------|-------------|
| `/home/kyle/appdata/homepage/config/` | `/app/config` | Configuration files |
| `/var/run/docker.sock` | `/var/run/docker.sock` | Docker socket (read-only) |

## Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `HOSTNAME` | Yes | Traefik hostname and allowed host |

## Networks

- `cn1` (external) - Shared Docker network for Traefik routing

## Links

- [Homepage](https://gethomepage.dev/)
- [GitHub](https://github.com/gethomepage/homepage)
