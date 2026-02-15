# Trilium

Hierarchical note-taking application with rich text editing and scripting.

## Services

| Service | Image |
|---------|-------|
| trilium | `triliumnext/trilium:latest` |

## Ports

| Host | Container | Description |
|------|-----------|-------------|
| 8383 | 8080 | Web UI |

## Volumes

| Host Path | Container Path | Description |
|-----------|---------------|-------------|
| `/home/kyle/appdata/trilium` | `/home/node/trilium-data` | Application data |

## Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `HOSTNAME` | Yes | Traefik hostname |

## Networks

- `cn1` (external) - Shared Docker network for Traefik routing

## Links

- [TriliumNext](https://github.com/TriliumNext/Notes)
