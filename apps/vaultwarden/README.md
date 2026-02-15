# Vaultwarden

Lightweight Bitwarden-compatible password manager server.

## Services

| Service | Image |
|---------|-------|
| vaultwarden | `vaultwarden/server:latest` |

## Ports

Exposed via Traefik only (container port 80).

## Volumes

| Host Path | Container Path | Description |
|-----------|---------------|-------------|
| `/appdata/vaultwarden/data` | `/data` | Vault data |

## Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `HOSTNAME` | Yes | Traefik hostname |

## Networks

- `cn1` (external) - Shared Docker network for Traefik routing

## Links

- [Vaultwarden](https://github.com/dani-garcia/vaultwarden)
