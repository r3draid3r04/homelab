# Open WebUI

Web interface for interacting with Ollama and other LLM backends.

## Services

| Service | Image |
|---------|-------|
| webui | `ghcr.io/open-webui/open-webui:main` |

## Ports

| Host | Container | Description |
|------|-----------|-------------|
| 3080 | 8080 | Web UI |

## Volumes

| Host Path | Container Path | Description |
|-----------|---------------|-------------|
| `webui` (named volume) | `/app/data` | Application data |

## Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `OLLAMA_BASE_URL` | Yes | Ollama server URL |
| `HOSTNAME` | Yes | Traefik hostname |

## Networks

- `cn1` (external) - Shared Docker network for Traefik routing

## Links

- [Open WebUI](https://openwebui.com/)
- [GitHub](https://github.com/open-webui/open-webui)
