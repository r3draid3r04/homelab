# n8n

Workflow automation platform with a visual editor for connecting APIs and services.

## Services

| Service | Image |
|---------|-------|
| n8n | `docker.n8n.io/n8nio/n8n:latest` |

## Ports

| Host | Container | Description |
|------|-----------|-------------|
| 5678 | 5678 | Web UI |

## Volumes

| Host Path | Container Path | Description |
|-----------|---------------|-------------|
| `/home/kyle/appdata/n8n` | `/home/node/.n8n` | Application data |

## Environment Variables

| Variable | Required | Default | Description |
|----------|----------|---------|-------------|
| `N8N_BASIC_AUTH_USER` | No | `admin` | Basic auth username |
| `N8N_BASIC_AUTH_PASSWORD` | Yes | `securepassword` | Basic auth password |
| `HOSTNAME` | Yes | - | Traefik hostname |

## Networks

- `cn1` (external) - Shared Docker network for Traefik routing

## Links

- [n8n](https://n8n.io/)
- [Documentation](https://docs.n8n.io/)
