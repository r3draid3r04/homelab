# VS Code Server

Web-based VS Code editor powered by code-server with Traefik integration.

## Services

| Service | Image |
|---------|-------|
| code-server | `linuxserver/code-server:latest` |

## Ports

| Host | Container | Description |
|------|-----------|-------------|
| 8443 | 8443 | Web UI |

## Volumes

| Host Path | Container Path | Description |
|-----------|---------------|-------------|
| `/home/kyle/appdata/vscode/config` | `/config` | VS Code configuration |
| `/home/kyle/appdata` | `/appdata` | Shared appdata access |

## Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `VSCODE_SUDO_PASSWORD` | Yes | Sudo password for the container |
| `HOSTNAME` | Yes | Traefik hostname |

## Networks

- `cn1` (external) - Shared Docker network for Traefik routing

## Links

- [code-server](https://github.com/coder/code-server)
- [Docker Image](https://docs.linuxserver.io/images/docker-code-server)
